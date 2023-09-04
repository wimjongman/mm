This page is used to collect materials related to the design of the
Focused UI, Task List and Task Editor.

# Snapshots

  - [Mylar 0.4 overview flash
    video](http://eclipse.org/mylyn/doc/demo/mylar-demo-04.html) (3.5
    min, 8.7 MB)
  - [Mylar 0.4 Bugzilla integration flash
    video](http://eclipse.org/mylyn/doc/demo/mylar-demo-04-reports.html)
    (v0.4, 3.5 min, 6 MB)
  - [Mylar 0.3 Active views
    video](http://eclipse.org/mylyn/doc/demo/mylar-demo-03-search.html)
    (v0.3, 2 min, 3 MB)

# Idioms

## Avoid Hierarchies

While we are always tempted to add hierarchies to the *Task List* and
there is never a lack of requests to do so, this is something that we
have to proceed with very carefully because hiearchies are much
dramatically more difficult to interact with and use than monocline
lists. In general the Mylyn UI design attempts to follow the simpler
[monocline
grouping](http://platypuswiki.sourceforge.net/whatis/inspirational/cooper.html)
metaphor over the hierarchical metaphor.

## Avoid Preferences

While there is never a shortage of demand for additional preferences,
especially from advanced users, each preference that gets added has a
significant cost in terms of UI complexity. Preferences also mask ways
in which the tool should change by providing work arounds particular to
very specific use cases. We should strive to evolve the UI in a way that
meets the use cases proposed by requested preferences in a way that does
not overly clutter or add modalities to the UI. Oftentimes this can mean
improving on or changing existing functionality instead of adding a
preference to accommodate a specific use case. Since figuring out how to
do that can require implementation, preferences can be added more
liberally to the Sandbox component for the purpose of experimentation.

''' Task Repositories '''

  - For the common case the user should only need to enter the
    repository URL and their credentials. Additional settings are hidden
    out of the way (in a foldbale section) and should only be needed by
    expert users.

See "The Question of Preferences" in the following entry for a good
discussion: <http://ometer.com/free-software-ui.html>

# References

Using links vs. buttons in UI:

  - <http://wiki.eclipse.org/index.php/Links_and_Buttons>
  - <http://msdn2.microsoft.com/en-us/library/aa511456.aspx>
  - <http://www.useit.com/alertbox/command-links.html>

# Information Design

## Guaranteed Visibility

(in progress)

Tasks (when Task List is in focused mode)

  - Tasks that are overdue or "over scheduled" will always appear
      - Overdue tasks turn red by default
      - Over scheduled tasks turn blue and accumulate in Today's bin.
      - Tasks previously scheduled for "This Week" float accumulate in
        "This Week"
  - Tasks due this week will always be visible
  - Tasks scheduled for a specific day or "This Week" will always be
    visible
  - Tasks with incoming
  - Tasks with outgoing (edits or new unsubmitted tasks)

Query and category visibility

  - Empty queries and categories always show when not in Focused mode.

Working sets

  - No container has visibility when not a part of the working set
    (TODO: change for Archive?)

<font color="red"> Subtasks

  - A completed parent task is visible when a subtask has an incoming
    change or any subtask is still open
  - Incomings of subtasks are propagated to the parent task

</font>

## Synchronization States

  - The Task List shows only the current difference between what the
    user has read and what's accurate on the server. This means that a
    query will show all new hits that have not been read, but that hits
    that have disappeared from the query will not show (e.g., these
    could be show with a *Synchronize* view style minus). This ensures
    that queries only show matching elements, and not transitional
    states.

# Interaction Desgin

## Task Editor Lifecycle

Editors in Eclipse tend to follow the open-save-close lifecycle model
([UI Guideline 6.2](http://wiki.eclipse.org/User_Interface_Guidelines)).
Mylyn's *Task Editor* differs from editors of workspace resources,
because it typically shows content that is stored on a server, and not
as a resource in the workspace. In order to support a separation between
local save and server submission, the *Task Editor* follws an
open-save-submit-close model:

  - **open**: The offline copy is opened synchronously. If no offline
    copy exists the task contents are retrieved from the server.
  - **save**: If the user has made changes, the changes can be saved and
    the editor put into an outgoing state.
  - **submit**: Once changes are ready to be shared with others, the
    outgoing changes can be submitted to the server. The editor then
    refresh itself with the latest contents from the serrver. This
    action cannot be undone.
  - **close**: The editor can be closed with outgoing changes and
    reopened. Changes can be discarded. If outgoing changes exist
    locally and on the server the conflict state arises and the user is
    given options for merging changes.

## Task Scheduling

To come, discussion currently on

## Time Tracking

Mylyn automatically tracks the time spent working on each task in order
to assist with planning activities and to provide input to planning
tools. The following time tracking mechanism is provided with Mylyn:

  - Time spent actively interacting with the workbench via mouse and
    cursor events.

The following time tracking mechanisms are outside of the scope of
Mylyn, but can be provided by extensions:

  - Time spent actively interacting with the operating system, out of
    scope due to OS-specific implementatnoi requirements.
  - Total elapsed time spent on a task independent of activity
    monitoring, out of scope due to UI overhead imposed by the need to
    support periods of inactivity logged as activity.

## Task Drag & Drop

Mylyn supports drag & drop of tasks between the Task List, Task Editor
and other applications.

### Drag Sources

The following elements of Mylyn's UI can be dragged:

**Task List**

Task, Query, Category

  - `File` Export the dragged items to a zip file
  - `Text` Drags the URL of the items and the description, *(Link) Drags
    references to the dragged tasks, e.g. bug 12345 or KEY-12345*
  - `URL` *The URLs of the dragged items*

'''Task Editor '''

*Header section*

  - *(see Task List)*

*Attachment Table*

  - `File` *The dragged attachments*
  - `URL` *The URLs of the dragged attachments*

### Drop Targets

The following elements of Mylyn's UI allow dropping:

**Task List**

  - `File` Imports tasks from dropped file
  - `URL` Imports tasks if URL points to a task list archive
  - `Text` Creates a task if the dropped text is a task URL of a known
    repository, otherwise creates a local task that links to the URL

Category

  - `Task` Move task to category

Task

  - `File` Replaces the context of the target task with the dropped file
    if the file is a valid context

**Task Editor**

  - `File` Opens the attach file wizard

*Depends On, Blocks Field, New Comment, Description*

  - `Task` Insert ids of dropped tasks''

## Startup and Lazy Loading

Context activation is a blocking and synchronous operation because it
does a major reset of the UI. During this reset the user should not be
interacting with views or editors. During startup, context activation
causes models to get loaded (e.g. the Java model) if the corresponding
content is present in the task context. Even though this makes the
workbench appear to start more slowly, it means that the workbench is
ready for the user to work on the task once it has started. If the user
wants full lazy loading to happen, he or she has the option of
deactivating the task before the workbench is shutdown. Recently there
have been some experience around Windows Vista that indicate the
tradeoffs of lazy loading (the UI appears ready, but disk and CPU
activity are blocking the user from interacting during the lazy loads).
The current tradeoff taken by Mylyn appears to work well in practice,
but if more lazy loading were desired we could consider providing an
option to automatically deactivate the task on shutdown.

## Links

  - Discussion on non-modal dialogs in Eclipse:
    <https://bugs.eclipse.org/bugs/show_bug.cgi?id=229937#c4>

# Visual Design

## Incoming Indication

  - When Focused mode is enabled, incomings do not need to show on their
    parent containers because the elements with incomings will show due
    to the Guaranteed Visibility rules. Showing the indicator on both
    the container and the item results in visual noise. Since Guaranteed
    Visibility is not supported when Focused mode is off, the typical
    Eclipse rule of propagating the decorator to the parent needs to
    apply.

<!-- end list -->

  - Make it easy to scan vertically for incomings by aligning incoming
    indicators along the side of the view.

<!-- end list -->

  - Arrows direction is conceptual (e.g. incoming points at the item,
    outgoing way from the item).

## Colors

  - From 2007 UI Best Practices Working Group Review: Green is a better
    color than black for the outgoing arrows because it bares less
    similarity to the *Synchronize* view overlays, connotes action
    (there is something outgoing), is positive (you just did some work
    on this thing) and is consistent with the other places green is used
    for outgoing (WTP?).

## Task Context

  - Project open/closed state should not be included as part of the task
    context .

## Focused Views

  - **Filters**: when focus is applied to a view, all of the other
    filters for that view should be removed. Filters that correspond to
    elements that should not participate in selection (e.g. Java import
    declarations) can be preserved. To make this explicit, the manual
    filtering facilities should be disabled when focus is enabled.

<!-- end list -->

  - **Linking**: if the editor selection always causes an element to
    become interesting, the *Link with Editor* property should be
    automatically enabled when a view is focused. Turning off linking is
    intended to prevent a large scrolling tree from jumping around.
    However, when a view is focused the amount of content should be
    sufficiently small to ensure visual stability of the view without
    the need to suppress linking.

# Open Questions

**Task List**

  - Can we improve on the icon rendering strategy? Currently we custom
    draw the incoming and activation icon, overlay priority and create
    composite descriptors for the repository-specific kind. This still
    leaves problems of excessive indentation on Windows and custom-draw
    related limitations on Linux.
  - Should there be more consistency between our incoming/outgoing
    overlays and those of Platform/Team?
  - If we move the active task and working set switcher out, what do we
    do with the space to the right of *Find*?
  - What's the best mechanism for providing discoverability of Ctrl+H
    when using *Find*?
  - Is the disparity between Platfrom's use of bold and Mylyn's use of
    bold a problem? Mylyn uses bold to indicate the most relevant
    information in a view (e.g. active task, landmark element). The
    Platform uses bold for showing which editors are not visible in
    tabs.
  - Is the enforcement of a common task icon background a good idea? We
    currently encourage but to dont enforce.
  - Can our custom drawing of container separators be improved?
  - Should *Presentations* become a toolbar radio group? If so what's
    the maximum we should allow? Frequently switching presentations is
    cumbersome now, but we need to keep extensibility in mind.
  - Which *New* actions belong on the view toolbar?

**Task Repositories**

  - How do we support branding without making the UI overly noisy?
    Current approach is to not allow more than 7x8 overlays for
    branding. But we might want to include repository favicons.

**Working Sets**

  - Should Mylyn's aggregate working sets be supported at the Platform
    UI level? Single-command selection of working sets is valuable when
    the are frequently switched.
  - How do we improve aggregate working set switching and awareness of
    contents? It's not uncommon to switch working sets a dozen times a
    day, which can makes this action more frequent than perspective
    switching. The current drop-down selector has friction and cannot be
    used to show status of what's in another working set.

**Views**

  - What is the policy for when views should be cloned? One use has
    expressed interest in *Task List* cloning.
  - Which view state is considered transient and not worth restoring
    when switching tasks? Currently *Go Into* is in this category.
  - Is removing all viewer filters and forcing linking the right
    approach for Focused mode? Currently we do this for all but
    bridge-specific filters specified via extension point, e.g. the
    *Package Declarations* filter.
  - Is there a more obvious icon/metaphor for the *Focus* action?

**Editors**

  - Should split editor state be restored? The workbench does not
    restore it on startup.
  - Should we allow a scrollable box within a scrollable pane? This
    complicates interaction but can increase information density, e.g.
    for the Bugzilla *Description* section which can blow up the editor.
  - How should we support expansions of an editable area? Can be manual
    or dynamic.

**Content providers and filtering**

  - The Task List currently has a content provider that supports
    guaranteed visibility (e.g. the query containing an overdue task
    will always show). The task contenxt model captures guaranteed
    visibilty for landmarks by maintaining a map. Platform's
    FilteredTree has a different, and somewhat expensive, mechanism of
    computing guaranteed visibility for matches and the viewer/filter
    level. Can we improve on this disparity?

**Search**

  - If a search result has only one match should it open in an editor
    instead of showing and focusing the Search view? This is the current
    beahvior for entering a task key/id on the Task Search page.

**Forms**

  - What's the best mechanism for showing progress in a form-based
    editor? Mylyn current uses the editor tab's icon and does not use
    the standard for progress indicator.
  - Should all non-content actions on form editors be in the header? If
    not, should content vs. workflow/lifecycle buttons be
    differentiated?

**Documentation**

  - Is the UI Legend a good idea? Should it be view specific or more
    generic?
  - What's the best approach for documenting complex steps in a dialog?
    (i.e. the Task Repository Properties dialog)

**Minor**

  - Should we include FilteredTree filtering in the Search view? Should
    Platform include it for all searches?
    [bug 200411](https://bugs.eclipse.org/bugs/show_bug.cgi?id=200411)

[Category:Mylyn](Category:Mylyn "wikilink")