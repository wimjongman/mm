# Migrating from Mylar 1.0 to Mylyn 2.0

Follow these instructions to migrate from the Mylyn 1.0 to 2.0 APIs,
noting that the [project changed
names](http://www.eclipse.org/mylyn/rename.php) during this period.

## Bugzilla

  - Open each query that you have, select **Update Attributes** and
    change the product from *Mylar* to *Mylyn*.
  - Note that `mylar-inbox@eclipse.org` has been renamed to
    `mylyn-inbox@eclipse.org`.
  - After synchronizing you may see a large number of bugs with incoming
    changes. This is due to the product name having changed on those
    bugs. If you have too many incomings to read through, we recommend
    selecting resolved bugs and using **Mark**-\>**Read** via the
    context menu.

## General

  - **Mylar to Mylyn project name refactoring**
      - Use Search \> File Search, enter in "org.eclipse.mylar" as
        search string and enter file types "\*.java, \*.xml, \*.xsd,
        \*.properties, \*.mf" and click on Replace... at bottom of
        Search dialog. In resulting Replace dialog enter
        "org.eclipse.mylyn" as the replace text.
      - Select all projects and execute Source \> Organize Imports.
      - If you get compile errors after Organizing Imports related to
        HttpClient ensure that the apache commons HttpClient (contained
        in org.eclipse.mylyn.web.core package) has been imported NOT the
        jvm's version.

<!-- end list -->

  - Library dependencies have moved to `org.eclipse.mylar`

<!-- end list -->

  - `MylarStatusHandler` and `IStatusHandler`
      - moved from `org.eclipse.mylar.context.core` to
        `org.eclipse.mylar.core`

<!-- end list -->

  - `MylarStatus` (place holder, will improve as we solidify this)
      - `MylarStatusHandler.displayStatus(dialog title, IStatus status)`
        - call to display error and information dialogs
      - When returning `CoreException` pass in a `MylarStatus` with
        appropriate code (see `IMylarStatusConstants`).
      - If `IMylarStatusConstants.INTERNAL_ERROR` is sent to
        `MylarStatusHandler.displayStatus` an error dialog will appear
        and the error will be logged.
      - `IMylarStatusConstants.REPOSITORY_COLLISION` used for mid-air
        collision. Pass repository url and appropriate dialog will be
        displayed.

<!-- end list -->

  - `WebClientUtil`
      - moved from `..mylar.tasks.core` to `..mylar.core.net`

<!-- end list -->

  - Methods that do I/O operations now take an `IProgressMonitor`
    parameter
    ([\#143011](https://bugs.eclipse.org/bugs/show_bug.cgi?id=143011))

## Tasks API

Sorting is alphabetical.

  - `AbstractAttributeFactory`
      - `getIsReadOnly()` renamed to `isReadOnly`

<!-- end list -->

  - `AbstractNewRepositoryTaskEditor`
      - handleNewBugPost() renamed to updatedSubmittedTask()

<!-- end list -->

  - `AbstractQueryHit`
      - The notion of special hit objects (AbstractQueryHit) has been
        completely removed from the Mylyn code base. Where once you
        provided hit objects (i.e. to a ITaskCollector) you may now
        provide AbstractTask objects or in many cases raw
        RepositoryTaskData.

<!-- end list -->

  - `AbstractRepositoryConnector`
      - `getLastSyncTimestamp(TaskRepository repository,
        Set`<AbstractRepositoryTask>`  changedTasks) `: added (may
        change as part of
        [bug\#176934](https://bugs.eclipse.org/bugs/show_bug.cgi?id=176934))
      - `getSupportedVersions()` has been removed
        ([\#1768159](https://bugs.eclipse.org/bugs/show_bug.cgi?id=176815))
      - `createTaskFromExistingId()` is no longer abstract and takes
        care of task creation
      - `updateTaskFromTaskData(TaskRepository, AbstractRepositoryTask,
        RepositoryTaskData)` added. Must be implemented to handle
        updating information on the `AbstractRepositoryTask` with data
        from the `RepositoryTaskData`
      - renamed `updateTask` to `updateTaskFromRepository`
      - `createTaskFromExistingKey()` renamed to
        createTaskFromExistingId() and is final
      - `makeTask()` added. Connector specific repository task
        construction
      - `setTaskDataManager()` added. Manager set upon connector
        construction in TasksUiPlugin. If being used headless, will need
        to manually set for offline support.
      - `retrieveContext()` moved to `AbstractAttachmentHandler`
      - `getContextAttachments()` moved to `AbstractAttachmentHandler`
      - `hasRepositoryContext()` moved to `AbstractAttachmentHandler`
      - `setTaskDataManagern()` moved to `AbstractAttachmentHandler`
      - `downloadContext()` moved to `AbstractAttachmentHandler`
      - `attachContext()` moved to `AbstractAttachmentHandler`
      - `getTaskWebUrl()` renamed to `getTaskUrl()`
      - `repositoryPropertyNames()` renamed to
        getRepositoryPropertyNames()</code>
      - `getRepositoryType()` renamed to `getConnectorKind()`

<!-- end list -->

  - `AbstractRepositoryConnectorUi`
      - `openRemoteTask(String repositoryUrl, String id)`: removed, this
        method no longer needs to be implemented by the connector.
        Instead classes can rely on the new `openRepositoryTask(..)`
        method, and override it if necessary.
      - getRepositoryUrl and all ID/URL methods: now final, change via
        setters
      - \+ findHyperlinks(...) override to detect hyperlinks in editors
      - handlesDueDates() added. Override and return true if connector
        capable of handling due dates.
      - getTaskKindLabel(RepositoryTaskData) returns suitable label for
        task kind (default is 'Task') override to suit
      - getRepositoryType renamed to getConnectorKind()
      - handlesDueDates() renamed to supportsDueDates();
      - handlesCustomNotificationHandling() renamed to
        isCustomNatificationHandling()
      - hasRichEditor() removed

<!-- end list -->

  - `AbstractRepositoryQuery`
      - `setMaxHits()` removed and constrctor no longer takes number of
        hits. Connectors can use QueryHitCollector.MAX_HITS (currently
        5000) when setting max number of hits to return.
      - `updateHits` removed (hits/tasks added by sync job via
        TaskList.addTask(...)
      - `addHit` removed
      - `removeHit` removed (use methods from parent class
        AbstractTaskContainer)
      - `findQueryHit` removed
      - `getHits()` removde (is a AbstractTaskContainer so can call
        getChildren() )
      - `setCurrentlySynchronizing()` rename to `setSyncrhonizing()`
      - `setLastRefreshTimestamp()` rename
        `setLastSynchronizedTimeStamp()`
      - `getLastRefreshTimeStamp()` rename to
        `getLastSynchronizedTimeStamp()`
      - `setStatus()` renamed `setSynchronizationStatus()`
      - `getStatus()` renamed `getSynchronizationStatus()`

<!-- end list -->

  - <codde>AbstractRepositoryQueryPage</code>
      - saveWidgetValues() renamed to saveState()

<!-- end list -->

  - `AbstractRepositorySettingsPage` validation changes.
      - `setNeedsValidation(boolean needsValidation)` if true validate
        button will be visible
      - `getValidator(TaskRepository repository)` return an instance of
        `Validator`.

<!-- end list -->

  - `AbstractRepositoryTask`
      - `Task`: constructor no longer takes newTask bookean, use
        setCreationDate(new Date()) for creating a new task instead
      - constructor now requires taskId (now immutable)
      - getIdentifyingLabel() -\> getTaskKey()
      - getLastRefreshTimeInMinutes(Date) removed
      - no more static methods (use RepositoryTaskHandleUtil)
      - Replace this idiom:

`   String handleIdentifier = AbstractRepositoryTask.getHandle(repository.getUrl(), taskId);`
`   ITask task = TasksUiPlugin.getTaskListManager().getTaskList().getTask(handle);`

  -   - with:

`   ITask task = TasksUiPlugin.getTaskListManager().getTaskList().getTask(repository.getUrl(), taskId);`

  -   - isDirty() and setDirty() removed
      - isDownloaded() removed
      - getTaskData(), setTaskData() removed
      - isSubmitting(), setSubmitting() added

<!-- end list -->

  - `AbstractRepositoryTaskEditor`
      - `attachContext()` Added `IProgressMonitor` parameter
        ([\#143011](https://bugs.eclipse.org/bugs/show_bug.cgi?id=143011))
      - `attributeChanged()` Anything that needs to be saved must be in
        attribute form and passed to this method. Most if this is all
        done for you but if you override
        AbstractRepositoryTaskEditor.createCustomAttributeLayout() then
        you will want to ensure that attributeChanged is called upon
        editing. Utility method createTextField() handles this call.
      - `createLabel()` Utility method added. It will put an '\*' at the
        front of the label if the attribute has been modified.
        Eventually this will be applied upon editing but currently only
        happens after re-freshing or re-opening the editor.
      - `createTaskFromExistingId()` Added `IProgressMonitor` parameter
        ([\#143011](https://bugs.eclipse.org/bugs/show_bug.cgi?id=143011))
      - `handleNewBugPost()` Added `IProgressMonitor` parameter
        ([\#143011](https://bugs.eclipse.org/bugs/show_bug.cgi?id=143011))
      - `SECTION_NAME` is an enum that holds default titles for the
        default sections. To override these default titles, set the
        appropriate (SECTION_NAME, new name) in
        `alternateSectionLabels` on `AbstractRepositoryTaskEditor`.
      - `updateEditor()` refreshes editor with new input in-place.
      - `uploadTaskFromRepository()` Added `IProgressMonitor` parameter
        ([\#143011](https://bugs.eclipse.org/bugs/show_bug.cgi?id=143011))
      - ComboSelectionListener removed (see createAttributeLayout for
        exmaple of attribute update lister)
      - comboListenerMap, removed
      - changedAttributes now private
      - setAttachContext() removed
      - attachContext renamed attachContextEnabled and private (use
        setAttachContextEnabled())
      - showAttachments now private, use setShowAttachments()
      - backgroundIncoming private, use getColorIncoming()
      - connector private, use getConnector()
      - HEADER_DATE_FORMAT private, use getCommonDateFormat()
      - isDisposed() removed, use
        getManagedForm().getForm().isDisposed()
      - updateTask() removed, implimentation moved to saveTaskOffline()
      - select(...) private
      - checkText() removed
      - toolkit private, use getManagedForm.getToolkit()
      - SummaryListener removed
      - display, VALUE, HEADER, PROPERTY, HYPERLINK_TYPE_TASK,
        HYPERLINK_TYPE_JAVA, HORZ_INDENT - removed
      - alternateSectionLabels, removed - overload getSectionLabel() if
        necessary
      - currentSelectedText removed
      - cutAction, pastAction removed
      - scrollIncrement, scrollVertPageIncrement,
        scrollHorzPageIncrement were protected now private
      - commetStyleText, textsindex, removed
      - createReportHeaderLayout() renamed to createSummaryLayout()

<!-- end list -->

  - `AbstractRepositoryTaskEditorInput`
      - constructor takes TaskRepository and task id

<!-- end list -->

  - `AbstractTaskDecorator` removed

<!-- end list -->

  - `AbstractTaskEditorInput` renamed to
    AbstractRepositoryTaskEditorInput

<!-- end list -->

  - `AttributeContainer`
      - `getAttributeFactory()` new method

<!-- end list -->

  - `AbstractTaskContainer`
      - constructor no longer takes a TaskList
      - getChildern() requires taskList parameter
      - setDescription() renamed to setSummary()
      - setSummary() removed, use setHandleIdentifier()

<!-- end list -->

  - `DateRangeContainer`
      - getChildren() now returns set of underlying task objects (not
        DateRangeActivityDelegates which will be deprecated)
      - getDateRangeDelegates() returns the delegate formerly returned
        by getChildren()

<!-- end list -->

  - `DelegatingTaskExternalizer` now extend AbstractTaskListFactory to
    externalize connector specific task
      - `readTaskInfo(..)` and `readQueryHitInfo(..)` are now called
        automatically and are private. Use your `createTask(..)` or
        `createQueryHit(..)` methods to customize reading additional
        attributes.
      - init() removed
      - readTaskData() removed

<!-- end list -->

  - `IAttachmentHandler` removed, all methods moved to
    AbstractAttachmentHandler
      - `downloadAttachment()` Added `IProgressMonitor` parameter
        ([\#143011](https://bugs.eclipse.org/bugs/show_bug.cgi?id=143011)).
        The data is now written to an `OutputStream` instead of a `File`
        ([\#](https://bugs.eclipse.org/bugs/show_bug.cgi?id=186070)186070).
        A default implementation for this method which uses
        `getAttachmentAsStream()` for retrieving the attachment is
        provided in `AbstractAttachmentHandler`.
      - `getAttachmentData()` has been replaced by
        `getAttachmentAsStream()` which now returns an InputStream for
        reading the attachment data
        ([\#](https://bugs.eclipse.org/bugs/show_bug.cgi?id=186070)186070).
      - `uploadAttachment()` Added `IProgressMonitor` parameter
        ([\#143011](https://bugs.eclipse.org/bugs/show_bug.cgi?id=143011)).
        Attachment properties are now passed as an object of type
        `ITaskAttachment`. This interface provides a
        `createInputStream()` method to create a stream for reading the
        data source
        ([\#](https://bugs.eclipse.org/bugs/show_bug.cgi?id=186070)186070).

<!-- end list -->

  - ITask
      - ITask and ITaskListElement have merged to form a single abstract
        class `AbstractClass`. This class extends
        `AbstractTaskContainer` which provides identity and containment
        facility.
      - `setDescription(...)` renamed to `setSummary`
      - `addSubTask()` removed
      - `removeSubTask()` removed

<!-- end list -->

  - `ITaskDataHandler`
      - made abstract and renamed to <code>AstractTaskDataHandler<code>
      - `getChangedSinceLastSync()` method moved to
        `AbstractRepositoryConnector`
      - New comment now held in an attribute:
        `RepositoryTaskAttribute.COMMENT_NEW` will need to update
        handler and factory to produce connector specific attribute
      - `getTaskData()` Added `IProgressMonitor` parameter
        ([\#143011](https://bugs.eclipse.org/bugs/show_bug.cgi?id=143011))
      - `initializeTaskData(TaskRepository repository,
        RepositoryTaskData data, IProgressMonitor monitor)` called by
        NewTaskWizard to initialize new taskData objects (currently only
        in use by Trac but will adopt).
      - `getAttributeFactory(String repositoryUrl, String
        repositoryKind, String taskKind)` signature changed
      - `getDateForAttributeType(...)` moved to
        `AbstractAttributeFactory`
      - `postTaskData()` Added `IProgressMonitor` parameter
        ([\#143011](https://bugs.eclipse.org/bugs/show_bug.cgi?id=143011))

<!-- end list -->

  - `ITaskCollector`
      - getTaskHits renamed getTasks()

<!-- end list -->

  - `ITaskEditorFactory` renamed to AbstractTaskEditorFactory
      - getPriority() renamed to getTabOrderPriority()

<!-- end list -->

  - `ITaskListElement`: now extends `java.lang.Comparable`, so
    Collections support of sorting can be used, since task list elements
    have a natural ordering. Default implementations are provided for
    tasks and containers.
    ([bug 171590](https://bugs.eclipse.org/bugs/show_bug.cgi?id=171590))

<!-- end list -->

  - `ITaskListExternalizer`
      - `readTask(..)` renamed to `createTask(..)`, no longer needs to
        set taskId, label, or repositoryUrl
      - `createQueryElement(...)` requires additional TaskList parameter
      - `getQueryHitTagName()` removed
      - <code>createQueryHitElement()<code> removed (hit read/write now
        handled by framework)
      - `canReadQueryHit()` removed
      - `createQueryHit()` removed

<!-- end list -->

  - `MylarStatusHandler` renamed to `StatusHandler`

<!-- end list -->

  - `MylarStatus` merged with `IMylarStatusConstants` renamed to
    `RepositoryStatus`

<!-- end list -->

  - `NewTaskEditorInput`
      - Constructor takes (TaskRepository repository, RepositoryTaskData
        taskData)

<!-- end list -->

  - `QueryHitCollector`
      - MAX_HITS constant can be used as standard default number of
        hits handled per query. User notified when \>= hits returned.

<!-- end list -->

  - `RepositoryTaskEditorInput`
      - constructor takes (TaskRepository repository, String taskId,
        String taskUrl)

<!-- end list -->

  - `RepositorySynchronizationManager`
      - `updateOfflineState` is now `saveIncoming` and `saveOutgoing`.
      - `discardOutgoing` discards any pending outgoing changes

<!-- end list -->

  - `RepositoryTaskAttribute`
      - getID() -\> getId()
      - COMMENT_AUTHOR property now used to set/get TaskComment author
        (was using USER_OWNER)

<!-- end list -->

  - `RepositoryTaskData`
      - constructor now requires a task kind (string) (i.e.
        `Task.DEFAULT_TASK_KIND`)
      - `getTaskKind` return the task kind
      - `setNew(boolean)` signifies that this is unsubmitted task data.
        Used by editor factory to determine if existing or new editor to
        be opened.
      - getCC renamed to getCc

<!-- end list -->

  - `SynchronizeQueryJob`
      - renamed setSynchTasks() to setSynchChangedTasks()

<!-- end list -->

  - `Task` renamed to AbstractTask
      - constructor no longer takes newTask boolean, use
        setCreationDate(new Date()) for creating a new task instead
      - `dropSubTasks`: added, removes all subtasks
      - `getTooltipText()`: deleted, not used
      - Due dates are now supported `getDueDate(), setDueDate()`
      - handleIdentifier: now private
      - get/setUrl are now get/setTaskUrl (to disambiguate with
        get/setRepositoryUrl())
      - `getElapsedTime()`: removed, not used previously, use
        `TaskListManager.getElapsedTime(ITask)` instead (note this
        method might move)
      - `setElapsedTime()`: removed, not used
      - `getParent()` removed
      - `setParent()` removed (tasks can have multiple parent tasks)
      - `isCategory()` removed
      - `setIsCategory()` removed
      - `addSubTask(), removeSubTask(), dropSubTasks()` removed Task
        extends AbstractTaskContainer so task containment semantics
        handled by parent. *To ADD subtasks use TaskList.addTask(child,
        parent) getting and dropping of subtasks can be performed via
        methods on the Task (inherited from
        AbstrTactTaskContainer)remove(), clear()*
  - `getRepositoryTaskSyncState` renamed to `getSynchronizationState()`
      - getRepositoryKind() renamed to getConnectorKind()
      - setLastSyncDateStamp() renamed to setLastReadTimeStamp()
      - getLastSyncDateStamp() renamed to getLastReadTimeStamp()
      - setKind() renamed to setTaskKind()
      - setStatus() renamed to setShcyronizationStatus()
      - getState() renamed to getSynchronizationState()
      - setCurrentlySynchronizting() renamed to setSynchronizing()
      - hasBeenReminded() renamed to isReminded()
      - removed getTaskUrl() use getUrl from parent
        AbstractTaskContainer

<!-- end list -->

  - `TaskContainer` and all others extending `AbstractTaskContainer`
      - constructor no longer takes tasklist parameter

<!-- end list -->

  - `TaskEditor`
      - `protected void pageChange(intNewPageIndex)` method removed
        (only called super)

<!-- end list -->

  - `TaskList`
      - `getChangeListeners()`: returns a `Set` instead of `List`
      - `getRootCategory` renamed to `getUncategorizedCategory`
      - `movedToRoot` use `moveToContainer()`
      - `removeFromRoot` removed
      - `getRootTasks()` removed, use default category

<!-- end list -->

  - `TaskListImages`
      - renamed to `TasksUiImages` (still an internal class, should move
        to API)

<!-- end list -->

  - `TaskListManager`
      - `setDueDate()` used to set due date on a task and cause
        notification of local info changed.
      - `isDue(ITask)` true if task's due date isn't null and date has
        past

<!-- end list -->

  - `TaskListWriter`
      - `setTaskDataManager()` removed

<!-- end list -->

  - `TaskRepository`
      - TaskRepository.isAnonymous()
      - TaskRepository.setAnonymous(boolean)
      - (-) TaskRepository.getDefaultProxy() (Renamed and moved to
        WebClientUtil.getPlatformProxy())
      - getSyncTyimeStamp() renamed getSynchronizationTimeStamp()
      - setSynchTimeStamp() renamed setSynchronizationTimeStamp()
      - userDefaultProxy() renamed isDefaultProxyEnabled()
      - getKind() renamed to getConnnectorKind()

<!-- end list -->

  - `TaskRepositoryManager`
      - SetSyncTime() renamed to setSynchronizationTime()

<!-- end list -->

  - `TasksUiPlugin`
      - getRepositoryUi renamed to getConnectorUi
      - isEclipseVersion_3_3 removed
      - isMultipleActiveTasksMode() removed
      - isShellActive() removed

<!-- end list -->

  - `TasksUiUtil`
      - `openUrl(String url)`: moved to `openUrl(String url, boolean
        useRichEditor)`
      - `getImageDescriptorForPriority(..)` moved to TasksUiImages
      - `getImageForPriority(..)`moved to TasksUiImages

\---

  - *Moved to appropriate internal package:*
      - `AttachmentTableLabelProvider`
      - `EditorBusyIndicator`
      - `IBusyEditor`
      - `RepositoryTaskEditorDropListener`
      - `RepositoryTaskOutlineNode`
      - `RepositoryTaskSelection`
      - `RepositoryTextViewer`
      - `TaskFormPage`
      - `TaskHyperlinkDetector`
      - `TaskUrlHyperlinkDetector`
      - `TaskUrlHyperlink`
      - `SearchScoreComputerAdapterFactory`
      - `RepositorySynchronizationManager`
      - `SynchronizeTaskJob`
      - `SynchronizeQueryJob`
      - `ProjectPreferenceLinkProvider`
      - `OpenRepositoryTaskJob`
      - `IRepositoryConstants`
      - `ContextUiUtil`
      - `MylarMessages` (moved to Bugzilla internal)
      - `UnrecognizedResponseException` (moved to Bugzilla internal)
      - `TaskRepositoryFilter`
      - `TaskCategory`

## Context API

  - <code>AbstractContextUiBridge<code>
      - removed: `restoreEditor(IMylarElement)` use
        `open(IMylarElement)` instead
  - `AbstractContextStore`
      - `notifyContextStoreMoved()`: change to `contextStoreMoved()`
  - `AbstractContextStructureBridge`
      - `getDegreesOfSeparation()`: moved to `AbstractRelationProvider`
      - `getRelationshipProviders()`: moved to extensions point, e.g.:

` `<extension point="org.eclipse.mylar.context.core.bridges">
`    `<relationProvider
           class="org.eclipse.mylar.internal.java.search.JavaImplementorsProvider"
           contentType="java"/>
` `</extension>

  - `IMylarContextListener`: renamed to `IInteractionContextListener`
      - `contextCleared(..)`: added
      - `presentationSettingsChanging(..)`: removed, not used
      - `presentationSettingsChanged(..)`: removed, not used
      - `UpdateKind`: removed, not used

<!-- end list -->

  - `IMylarContext`: renamed to `IInteranctionContext`
      - `getHandleIdentifier()`: added to facilitate mapping

<!-- end list -->

  - `IMylarElement`: renamed to `IInteractionElement`
  - `IMylarObject`: renamed to `IInteractionObject`
  - `IMylarRelation`: renamed to `IInteractionRelation`
  - `IContextWriter`: renamed to `IInteractionContextWriter`
  - `IContextReader`: renamed to `IInteractionContextReader`
  - `IMylarContextListener`: renamed to `IInteractionContextListener`
  - `MylarContextManager`: renamed to `InteractionContextManager`

## Monitor API

  - `MylarMonitorUiPlugin`: renamed to `MonitorUiPlugin`
      - (-) setInactivityTimeout(...)

<!-- end list -->

  - `MylarUsageMonitorPlugin`: renamed to `UiUsageMonitorPlugin`

<!-- end list -->

  - `org.eclipse.mylar.monitor`: split into `monitor.core` and
    `monitor.ui`, organize imports and update extension point IDs
  - `HandleObfuscator`
      - moved to `InteractionEventObfuscator`

<!-- end list -->

  - `org.eclipse.mylar.monitor.usage.core` and
    `org.eclipse.mylar.monitor.usage.ui`
      - moved to `..mylar.monitor.core`, `..mylar.monitor.usage` and
        `..mylar.monitor.usage.internal`

## Headless API

  - TaskRepository defautls to use platform proxy. To avoid dependance
    on a running platform you must manually set property
    TaskRepository.PROXY_USEDEFAULT to false

[Category:Mylyn](Category:Mylyn "wikilink")