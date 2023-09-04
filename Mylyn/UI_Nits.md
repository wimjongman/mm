Use this document for UI items that are very minor or require discussion
before being resolved via [bug
reports](http://eclipse.org/mylar/bugs.php).

Bugs with a target milestone of an upcoming release should not be listed
on this page.

### EclipseCon 2008 BOF Feedback

**Task List**

  - tooltips should have same colour as standard platform tooltips
  - tooltips not dissapearing when scrolling
  - activate task icon has no feedback and therefor isn't easily
    discoverable
  - consder making the button/outline glow when mouse over like a
    regular toolbar button
  - consider presenting an informative tooltip about activation upon
    hover over button
  - Make use of PONT dialogs for things like failure to activate a task
    when working or when working on a task that isn't assigned to 'me'
  - find taking up unnecessary space
      - Custom draw on bottom
      - preference to hide it, but on by default

**Task Editor**

  - deactivation of the editor should should not result in closing of
    the task editor

**Package Explorer**

  - User should never see a blank view.
  - Package explorer needs some form of custom drawn indication within
    the view of what is happening and how to proceed.
  - automate alt-click to reveal
  - Filter methods and not classes in declaration filters

**Breakpoints**

  - remove when task deactivated
  - recreate on activation

**Working Sets**

  - don't expand all nodes in selection dialog
  - use tri-state check boxes
  - add filter text support
  - consider using the 2 pain UI

**Other**

  - Popup dialogs while offline are not acceptable
      - For notifications provide ability to silence all
  - Communication errors reported need to be more user friendly. Instead
    of reporting IO Exceptions or UnknownHostExceptions, simply post a
    communication problem. Consider hyperlinking the error message
    giving the user the option to explore the cause, displaying the gory
    details

### Naming to improve

  - Nesting of subtasks in Task List

### Visual design to improve

  - When a task is opened but user is offline, change the icon to show
    an "out of synch" or "disconneced" metaphor in the icon instead of
    the warning, since nothing is wrong.
  - Provide overlay differentiation between Bugzilla tasks of normal
    status and local tasks.
  - When the Task List category is drilled into via *Go Into*, display
    the name of the drilled into category somewhere

### Policies requiring refinement

  - Automatic addition of containers to task working sets
  - When to show keys/ids (currently shown in Task List, and in as few
    other places as possible)
  - When to show empty query nodes in the Task List (currently when
    there are no matches, to indicate that something could be wrong with
    the query, e.g. email changed)
  - Silent removal query hits without allowing user to review incoming
    change
      - *Mik says: Eugene, I think you added this one, could you
        elaborate?*
  - Folding policy of comments and sections in the task editor

### Search/Navigation

  - Mark Landmark/Less Interesting, consider removing from navigation
    menu
  - (Why is the menu entry Less Interesting rather than Remove From
    Focus as in the context menu?)
  - If single task id entered for repository open tasks directly rather
    than searching
  - Add to tasklist needs to be available in sesarch results view
    (consider removing open repository task from Navigate menu)

### Preference Pages

  - Local Task Repository needs preference page (via Task Repository
    Settings page)

  - Restoring defaults not restoring all settings

### Colors

  - Change task editor incoming/conflict highlight color to be more
    pronounced.

### Task List

  - Sorting set to Summary but tasklist sorted by priority upon startup
  - Sub tasks should no longer be filtered by default
  - Add 'Defer a week' option to Schedule for context menu option
  - Improve layout of Find and bread crumb bar
  - Add Alt+Click tip to Focus on Active Task button tooltip
  - Consider adding Navigate actions (e.g. Open Repository Task) to Task
    List view menu
  - Due dates not currently not settable from context menu in task list
  - Tooltip: Synched vs. completed is confusing
  - Selecting a task obscures its active/inactive indicator
  - When a category is selected, the selection color shows through 4
    pixels of the folder icon
  - Italicizing the active task to indicate synchronization shouldn't
    un-bold it
  - Active/inactive indicators overlap clipboards after Going Into a
    category
  - Attempting to rename query with right-click -\> Rename has no effect
  - Right-click -\> Copy Details on a local task copies "null: " prefix
  - Sort By and Task Presentation menus should have radio buttons, not
    checkboxes

<!-- end list -->

  - Focus On Workweek Filter
      - Archive category has incoming decoration even if all incomings
        are shown in the tasklist and therefore not displayed in the
        archive (might only be for new hits)
      - Archive category filter is not restored to not applied upon
        unfocusing (the check beside the filter isn't there, but the
        archive isn't shown either). You have to toggle the archive
        filter to show the archive cateogry again.

<!-- end list -->

  - Task search UI

<!-- end list -->

  - Unmatching tasks are dropped from task list queries upon
    synchronization. This cause loss of information that issue got out
    of scope (silently moved out into a pile of the archive category),
    which is critical for queries that are used for project monitoring
    and not for tasks assigned to the current user (things she is
    working on)

### Notifications

  - Don't show notification for new bug reports submitted by user
  - Don't show notificaiton for new incoming if synched from editor
  - Local task icon in popup should not be bug icon
  - Investigate performance issue since taskdata now loaded upon popup
    show

### Task Editor

  - <font color="red">Last or incoming comment does not have email
    address tooltip</font>
  - Reveal in tasklist missing from popup
  - Icon in tab of Local Task editor is repository task icon, should be
    local task icon
  - Assign to needs content assist in New Task Editor
  - Update Attributes option (button) should be available in Task Editor
    header
  - Render context attachments 'comments' in Bugzilla as links to
    activate context or thumbnails, not comments.
  - If the Description of a repository task is editable, no border is
    drawn to indicate this in the editor
  - The Summary text field of a repository task editor is always
    editable even if the repository task attribute is read only.
  - The summary field of the task editors does not have a label. This
    could have implications related to accessibility such as screen
    readers. We should consider adding the Summary: label or
    investigating other ways to make this field obvious.
  - <font color=green> "Add To Task List" only appears in the context
    menu on the editor of an opened repository task if you have a
    category in your tasklist (can't add to root)</font> Uncategorized
    is now always available.
  - Uncategorized folder in "Add To Task List" context menu not
    decorated with Jar icon
  - Ampersand in task name misinterpreted as mnemonic in large heading
  - New Task -\> Local Tasks -\> Finish -\> start typing the summary
    quickly; your typing is overwritten by "New Task"
  - If I close a new local task without saving, delete it.

#### Keybindings

|             |        |
| ----------- | ------ |
| Shift+Alt+S | submit |

### Planning Editor

  - Category selection should be available within Task Planning editor

### Bugzilla Connector

  - Search page too small with clean workspace settings?
  - Proxy settings section expanded when shouldn't be for new Task
    Repository?

### Hyperlinking

  - editor hyperlink parsing problems and suggestions
  - Depending on connector hyperlink detection is slightly different.
    Should unify so that same patters work among all connectors:
    bug\#123, task\#123, task 123, \#123
  - Hyperlinks opening synchronously
  - Additional patterns:
      - \#XXXX
      - attachment 12345
  - Comment linking
    [bug\#164221](https://bugs.eclipse.org/bugs/show_bug.cgi?id=164221)
  - bla blah
    JiraWebIssueService$2.execute(JiraWebIssueService.java:105): still
    linking preceeding text where only class:line in brackets should be
    linked
  - Hyperlinks should have the task's summary as the tooltip (Eclipse
    hyperlink limitation here?)
  - Premature hyperlink termination:
    <http://wiki.eclipse.org/index.php/FAQ_How_do_I_hook_my_editor_to_the_Back_and_Forward_buttons%3F>
  - Avoid spell checking hyperlinks

### Recommended Preferences

  - Automatically disable Platform URL hyperlink detector.
  - Remove default linking from prefs?

### Task Repositories View

  - (from bug\#124321) Add properties page to Local Tasks repository
    that explains that it is automatically created and point to the Task
    List preference page which points the user at the data directory.

### Synchronization

There should be no synchronous repository communication. Cases that
could still be left:

  - Contact attach/retrieve.
  - Download of repository configuration after new bug created with no
    previous query.

<!-- end list -->

  - Job name in Progress view is misspelled "Synchronizying queries"

[Category:Mylyn](Category:Mylyn "wikilink")