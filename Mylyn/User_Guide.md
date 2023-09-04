# Task List

Use the Task List to view and manage your tasks. If the task list view
is not visible, you can open it by navigating to Window -\> Show View
-\> Other... -\> Mylyn -\> Task List. The Task List contains both "Local
Tasks" and shared repository tasks that are stored in a task repository
such as Bugzilla or Trac. Local tasks are typically contained in
categories, which you can create by right-clicking on the task list and
selecting New -\> Category. Repository tasks are contained in special
categories that represent queries.

![Image:Feature-Reference-3.0-Task-List-Categorized1.png](Feature-Reference-3.0-Task-List-Categorized1.png
"Image:Feature-Reference-3.0-Task-List-Categorized1.png")

At the top of the Task List, you will find the following buttons and
features:

  - **New Task** - Create a new local or repository task.
  - **Synchronize** - Update repository tasks with changes from the
    server.
  - **Task Presentation** - Toggle between Scheduled and Categorized
    presentations.
  - **Focus on Workweek** - See only tasks scheduled for this week.
  - **Find** - search for a task by typing in words from the task
    summary, or specify specific fields to query. See [Finding
    Tasks](#Finding_Tasks "wikilink") for details.
  - **Working set indicator** - Indicates the currently active working
    set. Use the black arrow on the left to change the working set.
  - **Current task indicator** - Indicates the currently active task.
    Use the black arrow on the left to re-activate a recently active
    task.

## Finding Tasks

The task list can be filtered by providing a phrase to match against the
task summary. The phrase must appear in the summary of a task for the
task to be visible when a filter is applied. The task list filter
operates by searching on a locally-maintained index of the tasks in your
task list. (In rare cases, it may be necessary to manually refresh the
search index by selecting "Refresh Search Index" from the task list
menu.)

  - Search for task summary or task id by entering the value. For
    example, `NullPointerException` or `12345`.
  - Search for other task fields such as description or assignee by
    prefixing them with the field name. For example
    `description:NullPointerException` will search in the task
    description rather than the summary. Content assist can be used to
    provide a list of common field names, and will provide a list of
    known user names when searching on user fields.

![Image:Task-list-index-reporter.png](Task-list-index-reporter.png
"Image:Task-list-index-reporter.png")

  - Search for date ranges by qualifying the range. For example, show
    tasks that were created in the `(past week)`.

![Image:Task-list-index-content-assist.png](Task-list-index-content-assist.png
"Image:Task-list-index-content-assist.png")

  - Search for an exact phrase by enclosing it in double-quotes. For
    example, `description:"user experience"`.
  - Search for partial words by using the "\*" wildcard. For example,
    `exc*tion` matches both "exclamation" and "exception".

### Available Fields

Available fields can be found by using content assist in the search
field. The following fields are available for search with most
repositories:

  - content
    match against any of summary, description, comments and other long
    text fields
  - summary
    the task summary
  - description
    match against the task description
  - person
    match against any person field, such as reporter, assignee, watcher,
    etc.
  - task_key
    match against the task or bug id
  - attachment
    match against attachment names
  - assignee
    match against the assignee of the task
  - reporter
    match against the reporter of the task
  - product
    match against the product of the task
  - component
    match against the component of the task
  - creation_date
    match against the date when the task was created
  - completion_date
    match against the date when the task was completed
  - due_date
    match against the date when the task is due
  - modification_date
    match against the date when the task was last modified
  - status
    match against the status
  - resolution
    match against the resolution
  - severity
    match against the severity

Some fields listed above may not be available depending on the
repository and connector.

### Search Operators

The Task List provides logical operators. For example, `NPE AND
Display`. Note that unlike other search phrases, **search operators are
case-sensitive**; otherwise, the words are treated as part of the search
phrase.

  - AND
    Searches for tasks that contain both words.
  - OR
    Searches for tasks that contain at least one word.

## Task List Presentation

The task list supports several ways to present tasks. You can toggle
between the following modes by using the "Task Presentation" button in
the toolbar.

  - **Categorized** - View tasks grouped by their category

![Image:Feature-Reference-3.0-Task-List-Presentation-Select-Categorized.png](Feature-Reference-3.0-Task-List-Presentation-Select-Categorized.png
"Image:Feature-Reference-3.0-Task-List-Presentation-Select-Categorized.png")

  - **Scheduled** - View tasks grouped by the "*scheduled* date"

![Image:Feature-Reference-3.0-Task-List-Presentation-Select-Scheduled.png](Feature-Reference-3.0-Task-List-Presentation-Select-Scheduled.png
"Image:Feature-Reference-3.0-Task-List-Presentation-Select-Scheduled.png")

In either presentation, you can toggle the "Focus on Workweek" button.
In this mode, only the following tasks will be visible:

  - Tasks scheduled for this week.
  - Overdue tasks.
  - Tasks with unread changes from your task repository.

## Icon Legend and Color Coding

See the legend below to interpret the icons and color coding in the task
list. You can view this legend by selecting "Show UI Legend" from the
menu that appears when you click the white down arrow next to the
minimize button in the top right corner of the Task List view.

![Image:Feature-Reference-3.0-UI-Legend.png](Feature-Reference-3.0-UI-Legend.png
"Image:Feature-Reference-3.0-UI-Legend.png")

## Creating New Tasks

![Image:Feature-Reference-3.0-New-Task1.png](Feature-Reference-3.0-New-Task1.png
"Image:Feature-Reference-3.0-New-Task1.png")

You can create new tasks by clicking on the "New Task" button in the
Task List's toolbar. This will open the "New Task" dialog and prompt you
to select a repository. There are two main types of tasks, local tasks
and repository tasks.

### Local Tasks

Use local tasks if you do not have a shared task repository or if you
would like to create a private, personal task that is local to your
workspace. To create a local task, select **Local Task** and "Finish"
from the New Task dialog.

![Image:Feature-Guide-3.0-Local-Task1.png](Feature-Guide-3.0-Local-Task1.png
"Image:Feature-Guide-3.0-Local-Task1.png")

You can then provide the following details about the task.

  - '''Task Description - Your task is called "New Task" by default.
    Replace this with a brief task description.
  - **Priority** - Set the priority of your task. This will affect the
    task's icon and order in the task list.
  - **Status** - Set your task to "complete" or "incomplete". In your
    task list, completed tasks have a strikethrough font and will appear
    lower in the list.
  - **URL** - You can associate a URL with this task.
      - "Retrieve Task Description from URL" button - Set the task
        description to the title of the associated URL (page)
      - "Open with Web Browser" button - Open the URL in the integrated
        web browser
  - **Scheduled For** - Set the date when you will work on this task.
    Tasks scheduled for today or a date in the past will appear in blue
    in your task list. Tasks scheduled for future days will appear in
    black. If your task list is in focused mode, only tasks for the
    current week will be visible (unless they have unread changes).
  - **Due** - Set the date when your task must be completed. Overdue
    tasks and tasks due today will appear in red in your task list.
  - **Estimated Hours** - Estimate the number of hours it will take to
    complete this task.
  - **Active** - Displays the total time that you have worked on this
    task. Time is only recorded when this task is active and you are
    actively interacting with the system.
  - **Notes** - Record your personal notes about this task.

### Repository Tasks

Create a new repository task when you would like to share information
about the task with your team using a task repository such as Bugzilla
or Trac. To create a new repository task, click on the "New Task" button
in the Task List's toolbar. You can then select the repository where you
would like to create a task. If you don't see your team's task
repository, you will need to configure it in the task repositories view.
Once you have selected a repository, click "Next". If you are connecting
to a Bugzilla repository, select a "Product" as a top-level category for
your task and click "Finish".

![Image:Feature-Guide-3.0-Repository-Task1.png](Feature-Guide-3.0-Repository-Task1.png
"Image:Feature-Guide-3.0-Repository-Task1.png")

A new task editor will appear. If you are using Bugzilla, you can enter
the following information:

Required

  - **Description** - Enter a brief task description in the text box at
    the top (this box does not have a label).
  - **Component** - Specify a "Component" to further categorize this
    task within the previously selected "Product".
  - **Description** - Describe the task in detail.

Optional

  - You can specify additional information about your tasks in the
    "Attributes" section.
  - **Personal Planning** - You can enter information in this section
    that will be local to your workspace and **not** available on your
    team's task repository. See "Local Tasks" for more information about
    the personal planning fields.
  - **Assigned to** - Specify who should work on the task. Type the
    first several characters of the person's email address, and then
    press ctrl+space to select the address from a list. A task can be
    assigned to only one person at a time.
  - **Add CC** - Add the addresses of people who should be notified of
    changes to this task. You can add multiple addresses, separated by a
    comma, e.g. (mik.kersten@tasktop.com, steffen.pingel@tasktop.com).

When finished, click "Submit" to add your new task to your team's shared
task repository.

## Creating new Queries

![Image:Feature-Reference-3.0-New-Query-Combined.png](Feature-Reference-3.0-New-Query-Combined.png
"Image:Feature-Reference-3.0-New-Query-Combined.png")

Once you have configured your team's task repository, you can use
Queries to add tasks to your task list.

  - If the Task List is not visible, navigate to *Window -\> Show View
    -\> Other -\> Mylyn -\> Task List*
  - Right-click on the Task List and select "New -\> Query..."
  - Select the repository whose tasks you would like to download and
    click "Next".
  - If you are prompted to select a query type, select "Create query
    using form" and click "Next".
  - Complete the form to define which tasks will be downloaded as part
    of this query, and then click "Finish". You can provide values for
    only as many parameters as necessary to filter the query results.

If you are using the Bugzilla connector, you can specify the following
parameters by default. The parameters for most other connectors will be
similar.

  - **Query Title** - Label that appears in your task list.
  - **Summary** - Specify words that must appear in the summary of tasks
    matched by this query.
  - **Comment** - Words that must appear in the comments of matching
    tasks.
  - **Email** - Specify all or part of an email address. This address is
    used together with the following options:
      - **Owner** - The specified email must match the person who the
        task is assigned to
      - **Reporter** - The specified email must match the person who
        created the task
      - **CC** - The person with the specified email address must be
        CC'd on the task
      - **Commenter** - The person with the specified email address must
        have commented on the task
      - You can choose from the following options to specify how the
        email address will be matched:
          - **substring** - Only a part of the specified address must
            match
          - **exact** - The specified email address must match exactly
          - **regexp** - The email address must match the specified
            regular expression
          - **notregexp** - The email address must NOT match the
            specified regular expression
  - **Email 2** - You can use this parameter to specify another email
    address to further restrict the results
  - **Keywords** - Click the "Select..." button to specify a keyword
    that must be associated with matching tasks
  - **Product, Component, Version, ...** - Optionally select parameters
    to restrict the results to a particular product, version, etc.
  - **Update Attributes from Repository** - Click this to refresh the
    available parameters if the project structure on the task
    respository has changed recently.
  - **Changed in:** - Only tasks modified within the specified number of
    days will appear in the query results

## Scheduling

Two kinds of dates for scheduling are provided.

**Scheduled Date**

  - A soft date used for personal scheduling that can be easily deferred
    as priorities change. The scheduled date is the date you plan to
    start working on the task.
  - When a task reaches its scheduled date it will turn blue, indicating
    that the task should be activated and worked on today.
  - Scheduled dates are private to your local workspace

**Due Date**

  - A hard date when the task must be completed. This is often related
    to external constraints such as deadlines.
  - If you are using a shared task repository, due dates become an
    attribute of the shared task and will be visible to other team
    members.
  - A task with a due date has a small clock overlay that is blue before
    the due date and red after.

## Synchronization

Repository tasks and queries are synchronized to reflect the latest
changes on the server. Tasks are synchronized the following ways:

  - **Automatic Synchronization.** By default, tasks will be
    synchronized with the repository every 20 minutes. Automatic
    synchronization can be disabled via the *Synchronize Automatically*
    option in the view menu (e.g. when working with intermittently
    available connectivity). The synchronization interval can be changed
    via *Preferences -\> Mylyn -\> Task List*.

<!-- end list -->

  - **On Task Open.** Tasks are synchronized automatically in the
    background when a task editor is opened.

<!-- end list -->

  - **Manually.** Individual tasks and queries can be synchronized
    manually by right-clicking on them in the Task List and selecting
    "Synchronize", or via the toolbar button. Clicking the toolbar
    button will synchronize all queries in your task list.


**Disconnected Mode**
A task repository can be put into Disconnected mode via the right-click
menu in the *Task Repositories* view. This can be useful if the task
repository is not currently in use (e.g. you are no longer engaged with
the project, or the repository is no longer available). The offline
support will ensure that you can still access tasks that you have worked
with via their offline copies, and the Disconnected mode will ensure
that synchronization warnings do not appear. Note that it is not
necessary to turn off synchronization or work in Disconnected Mode when
working offline.

## Incoming Changes

A blue arrow to the left of a task indicates that the task has changed
in the shared repository. Double-click the task to view it in the task
editor. Changes to the task will be highlighted in blue.

To quickly review the differences since the task was last read, hover
over the task in the Task List to view a summary in a tooltip. You can
also press F4 to display a tooltip. You may also wish to view the task
list in "Focus on Workweek" mode, which will filter out tasks without
incoming changes that are not scheduled or due this week. You can toggle
"Focus on Workweek" using a button in the Task List's toolbar.

## Reviewing Tasks

The task list has been carefully designed to support quickly reviewing
tasks. Task reviewing is best done by configuring a query to show the
tasks that you want to review. Once the tasks are displayed in the Task
List they can be reviewed one at a time by scrolling through them using
the keyboard up/down arrows. The task tooltip should provide enough
detail to do a review and will display information relevant to the
currently selected task.

To edit the selected task press the enter key, use Ctrl+Enter to open
the task in the background. To quickly jump to the next unread task hold
down the Alt-key when pressing up or down. To mark a task as read while
navigating use Alt+shift+up/down. When reviewing tasks in this way, it
is best to avoid mouse-based and gesture-based scrolling.

![Image:Feature-Reference-3.0-Task-List-Tooltip.png](Feature-Reference-3.0-Task-List-Tooltip.png
"Image:Feature-Reference-3.0-Task-List-Tooltip.png")

## Task Progress Indicators

**Weekly progress**
When in *Focus on Workweek* mode (right-most toolbar button), the Task
List will show a progress bar that indicates progress on the tasks
scheduled for the current week. Each task that is scheduled for the week
but not yet completed adds to the bar. A task completed by you adds to
the green progress in the bar. Deferring a task to a future week will
also add to the apparent progress because it will remove the task from
the current week. Mousing over the bar will indicate details about your
progress, such as the number of tasks and hours completed. To avoid the
need for manual estimation by default every task is estimated for 1
hour, but if you have longer or shorter running tasks that week you can
adjust the estimate in the task editor's *Planning* page to ensure that
the progress bar is accurate.

Note that when in *Focus on Workweek* mode the *Task List* will show
each of the tasks scheduled for this week. However, overdue tasks and
those with incoming changes will also show, making the number of tasks
visible not be a reliable indicator of progress on the tasks planned for
the week.

![Image:Feature-Reference-3.0-Weekly-Progress.png](Feature-Reference-3.0-Weekly-Progress.png
"Image:Feature-Reference-3.0-Weekly-Progress.png")


**Category Progress**
You can hover over categories in the task list to display a tooltip that
displays a summary of complete and incomplete tasks.

![Image:Feature-Reference-3.0-Category-Progress.png](Feature-Reference-3.0-Category-Progress.png
"Image:Feature-Reference-3.0-Category-Progress.png")

## Task List Settings and Operations

Click the small white arrow in the top right of the Task List view to
access the following settings:

  - **Go Up to Root** - Return to the normal presentation after
    previously selecting "Go Into" to see only the tasks in a particular
    category.
  - **Sort** - Open a dialog to set the sort order for the task list.
    This option is only available when the task list is not in "Focus on
    Workweek" mode.
  - **Filter priority lower than** - Hide tasks with a priority less
    than the priority you select. This option is only availabe when the
    task list is not in "Focus on Workweek" mode.
  - **Filter completed tasks** - Hide local and repository tasks that
    are in a completed state.
  - **Search Repository** - Opens a dialog to search for repository
    tasks. Search results will appear in a separate search results view.
  - **Restore Tasks from History** - Opens a dialog for restoring lost
    tasks.
  - **Synchronize Changed** - Updates the task list with any changes on
    the task repository.
  - **Synchronize Automatically** - When checked, the task list will
    update from the task repository on an interval specified in Window
    -\> Preferences -\> Mylyn -\> Tasks
  - **Show UI Legend** - Displays a legend explaining icons and
    color-coding.
  - **Focus on Workweek** - Displays only tasks that are scheduled for
    this week, overdue, or have unread changes.
  - **Link with Editor** - Automatically selects the task corresponding
    to the active task editor.
  - **Preferences** - Access additional Task List preferences.


Right-clicking in the task list provides access to the following
operations

  - **New...** - Create new categories, queries, and tasks.
  - **Open with Browser** - Open the task in a web browser tab rather
    than the rich editor.
  - **Schedule for** - Set the soft date when you intend to work on the
    task.
  - **Mark as** - Mark a task as read or unread as you would an email
    message.
  - **Copy Details** - Places the task summary and html link in the
    clipboard so you can paste it into an email, document, etc.
  - **Delete** - Deletes local tasks. For repository tasks, the all
    downloaded data and local task information will be cleared but the
    task will re-appear if it still matches a query.
  - **Rename** - Rename a task.
  - **Go into** (queries only) - Show only the tasks in the selected
    category.
  - **Import and Export** - Access functionality for importing and
    exporting task data.
  - **Repository** (queries only) - Update repository settings
  - **Synchronize** - Update the selected tasks or queries from the
    shared task repository
  - **Properties** - Edit the settings for a repository query

# Task Repositories

![Image:Feature-Reference-3.0-Add-Task-Repository.png](Feature-Reference-3.0-Add-Task-Repository.png
"Image:Feature-Reference-3.0-Add-Task-Repository.png")

Use the Task Repositories view to configure Mylyn to connect to your
team's shared task repository (bug or issue tracker):

  - Open the task repositories view by navigating to *Window -\> Show
    View -\> Other -\> Mylyn -\> Task Repositories*
  - Click the "Add Task Repository" button located in the view's
    toolbar.
  - Select the type of repository you wish to connect to and click
    "Next". If you don't see your repository type, you will need to
    install the appropriate connector.
  - Enter the repository's address and your login credentials. After
    filling in these details, press the *Validate* button to ensure the
    repository exists and your login credentials are valid. Once the
    settings validate, Click Finish. Note that the settings will vary
    somewhat depending on the type of repository that you are connecting
    to. The screenshot shows the settings fore connecting to a Bugzilla
    repository.
  - You should now see the new repository in the *Task Repositories*
    view.
  - Now that you have created a repository, you may add queries to the
    Task List.

# Task Editor

The task editor allows you to view and edit the tasks in your task list.
Double-click on a task in your task list to open the editor. The
features of the task editor will vary depending on whether it is a local
task or a shared repository task. For shared repository tasks, there are
some differences depending on the type of repository (and corresponding
connector) that you are using (link: connectors).

## Repository Task Details

In this section, we describe the task editor for shared bugs in a
Bugzilla repository. Task editors for other repository types such as
Trac offer similar functionality.

![Image:Feature-Reference-3.0-Task-Editor-Top.png](Feature-Reference-3.0-Task-Editor-Top.png
"Image:Feature-Reference-3.0-Task-Editor-Top.png")

**Editor toolbar buttons**

  - **Synchronize Incoming Changes** - Updates the local copy of the
    task to reflect any changes on the server.
  - **Create a new subtask** - Creates a new task that will be
    considered a prerequisite to completing the current task. Subtasks
    appear nested under their parent task in the task list. In Bugzilla
    terminology, the subtask "Blocks" the parent task and the subtask's
    ID will appear in the "Blocks:" field of the parent task.
  - **History** - Displays the task's change history in an internal
    browser using the web interface.
  - **Open with Web Browser** - Displays the web interface for the task
    in an internal web browser.
  - **Find** - Find text in comments, description, summary and private
    notes.
  - **Activate** - Toggles the activation and deactivation of the task.

**Attributes** Use the Attributes section to add or update structured
information about the task.

**Team Planning** The Team Planning section contains time-related
information about the task that will be shared with your team. You can
use the **Due** field to set a due date for your task. On the due date,
the task will appear in red in your task list.

**Attachments** You can attach a file to this task so that a copy will
be uploaded to your task repository and become available to anyone who
can access the task.

To attach a file

  - click the "Attach..." button, which will open a wizard.
  - Select from one of the following:
      - **File** - Uploads a file from your system. Click "Browse" on
        the right to select the file.
      - **Clipboard** -
      - **Workspace** - Uploads a file from your workspace. Select the
        file from the box below.
  - Click next to enter attachment details:
      - **Description** - Provide a brief description of the file. This
        description will appear in the attachment list in the task
        editor.
      - **Comment** - Provide a comment about the file. This comment
        will appear in the comments section of the task editor.
      - **Content Type** - Optionally specify a content type for the
        file
      - **Patch** - Check this if the attachment is a source code patch
        file
      - **Attach Context** - Check this if you would also like to attach
        the context of your task. This context describes the resources
        that are most relevant to the task. If you attach a context,
        others can download it and focus the UI on the same resources
        that are relevant to you.
      - Click "Next" to preview your file. If your file is an image, a
        preview of the file will appear.
      - Click "Finish" to upload the file to the task repository. Files
        are uploaded without the need to click "submit" at the bottom of
        the task editor.

**Duplicate Detection** When submitting bug reports, you can avoid
duplicates by clicking the "Search" button. This will search the
repository for a stack trace that matches a stack trace in the task's
Description field. The results of the duplicate detection show up in the
Search view. If a match is found, you can open it and comment instead of
creating a new bug report.

**Comments** Use this section to add new comments about the task and
view all previous comments. Comments you have read previously are
folded. You can expand and re-read individual comments or click the "+"
at the top right to expand all comments.

![Image:Feature-Reference-3.0-Task-Editor-Bottom.png](Feature-Reference-3.0-Task-Editor-Bottom.png
"Image:Feature-Reference-3.0-Task-Editor-Bottom.png")

**Actions** Use this section to change the task's status or reassign the
task to another person.

  - **Attach Context** - Uploads information about the resources that
    you have interacted with to the server. The context will appear in
    the attachments list so that others can download it and focus their
    UI on the resources that you found relevant for this task.
  - **Submit** - Submits all local changes to the task to your team's
    shared task repository.

**People** This section shows the people who are collaborating on the
task.

  - **Assigned to** - This is the person who is responsible for
    completing the task
  - **Reporter** - This person created the task
  - **QA Contact** -
  - **Add CC** - Use this box to add new people to the "CC" list. People
    on the "CC" list will be notified of any changes to this task. To
    add a new person, type the start of their email address and then
    press ctrl+space to complete the address using content assist. You
    can add several addresses, separated with a comma.
  - **CC** - This box shows the people who are currently on the "CC"
    list. To remove a person, simply select their email address so that
    it is highlighted and click "Submit". You can hold down ctrl to
    select multiple people.

## Context

The context tab allows you to manage the context of resources associated
with the task. You can view the context tab by selecting it in the lower
left of the editor window.

**Elements**
This section lists the resources that are part of the task's context.
Because the number of elements may be large, you can adjust the level of
detail using the slider at the top of the *Actions* section. Sliding the
control all the way to the left will show you all elements in your task
context. As you slide to the right, only the elements with a high level
of interest will be displayed. You can manually remove elements from
your task context by right-clicking and selecting "Remove From Context".
You may choose to view all elements and prune irrelevant items in this
way before attaching the context to the task so that others can download
it.

**Actions**
\* **Element Detail Slider** - Adjusts the minimum level of interest
required for an element to be displayed in the *Elements* section.

  - **Attach Context** - Attaches the context to the task so that it is
    available for download from the shared task repository. The context
    consists of the elements shown on the right.
  - **Retrieve Context** - Replaces the current task context with one
    that is attached to the task in the shared task repository.
  - **Copy Context to...** - Copy the task context to another task. That
    task will then have the same context as the current task.
  - **Clear Context.** - Removes all context information from the task.

![Image:Feature-Reference-3.0-Context-Tab.png](Feature-Reference-3.0-Context-Tab.png
"Image:Feature-Reference-3.0-Context-Tab.png")

## Planning

Use the planning tab to access local information about the task that is
private to your workspace. You can view the planning tab by selecting it
in the lower left of the editor window. This tab contains a large area
where you can enter personal notes about the task. See the local task
section for more information about fields in the Personal Planning
section.

![Image:Feature-Reference-3.0-Planning-Tab.png](Feature-Reference-3.0-Planning-Tab.png
"Image:Feature-Reference-3.0-Planning-Tab.png")

# Task-Focused Interface

The task-focused interface is oriented around tasks and offers several
ways to focus the interface on only what is relevant for the currently
active task.

## Focusing Navigator Views

You can focus navigator views (e.g. Package Explorer, Project Explorer,
Navigator) by toggling the "Focus on Active Task" button in the toolbar.
When focused, the view will show only the resources that are
"interesting" for the currently active task.

![Image:Feature-Guide-3.0-Package-Explorer-Focused.png](Feature-Guide-3.0-Package-Explorer-Focused.png
"Image:Feature-Guide-3.0-Package-Explorer-Focused.png")

## Alt+Click Navigation / Show Filtered Children

To navigate to a new resource that is not a part of the active task's
context, you can toggle "Focus on Active Task" off, browse to the
resource, and then click "Focus on Active Task" again to see only
relevant resources. A more efficient way to add new resources is to use
Alt+Click navigation (clicking the mouse while holding the Alt key) or
click the \[+\] icon that appears to the right of a tree node when the
mouse hovers over it.

When a view is in Focused mode, you can click the \[+\] icon to the
right of a node, or Alt+Click the node, to temporarily show all of its
children.

  - Once an element that was previously not interesting is selected with
    the mouse, it becomes interesting and the other child elements will
    disappear. The clicked element is now a part of the task's context.
  - You can drill down multiple levels of filtered nodes by clicking the
    \[+\] icon to the right of each node you want to unfilter. Note that
    trying to expand the node in other ways (e.g. clicking the triangle
    to the left of the node) will not show its filtered children -
    clicking anywhere in the view (other than a \[+\] icon) will hide
    all filtered children again.
  - Alt can be held down while clicking to drill down from a top-level
    element to a deeply nested element that is to be added to the task
    context.
  - Multiple Alt+Clicks are supported so that you can add several
    elements to the task context. As soon as a normal click is made,
    uninteresting elements will disappear.
  - Ctrl+Clicks (i.e. disjoint selections, use Command key on Mac) are
    also supported and will cause each element clicked to become
    interesting. The first normal click will cause uninteresting
    elements to disappear. Note that Ctrl+clicked elements will become
    interesting (turn from gray to black) but only the most
    recently-clicked one will be selected while Alt is held down.

![Image:Show_filtered_children.png](Show_filtered_children.png
"Image:Show_filtered_children.png")

## Focusing Editors

Some editors such as the Java editor support focusing. Clicking the
Focus button in the toolbar will fold all declarations that are not part
of the active task context.

![Image:Feature-Guide-3.0-Focused-Editor.png](Feature-Guide-3.0-Focused-Editor.png
"Image:Feature-Guide-3.0-Focused-Editor.png")

## Task-focused Ordering

When a task is active, elements that are interesting are displayed more
prominently. For example, when you open the Java Open Type dialog
(Ctrl+Shift+T), types that are interesting for the active task are shown
first. Similarly, when you use ctrl+space to autocomplete a method name
in a Java source file, methods that are in the task context are
displayed at the top.

## Working Set Integration

When Focus is applied to a navigator view, the working sets filter for
that navigator view will be disabled. This ensures that you see all
interesting elements when working on a task that spans working sets. To
enforce visibility of only elements within one working set, do the
following:

  - Set the view to show working sets as top-level elements.
  - Use the *Go Into* action on the popup menu of the working set node
    in the view to scope the view down to just the working set.

## Open Task dialog

An *Open Type* style dialog is available for opening tasks (`Ctrl+F12`)
and for activating tasks (`Ctrl+F9`). The list is initially populated by
recently active tasks. The active task can also be deactivated via
`Ctrl+Shift+F9`. This can be used as a keyboard-only alternative for
multi-tasking without the *Task List* view visible. These actions appear
in the *Navigate* menu.

![Image:Feature-Reference-3.0-Open-Task.png](Feature-Reference-3.0-Open-Task.png
"Image:Feature-Reference-3.0-Open-Task.png")

## Task Hyperlinking

In the task editor, comments that include text of the form bug\#123 or
task\#123 or bug 123 will be hyperlinked. Ctrl+clicking on this text
will open the task or bug in the rich task editor.

To support hyperlinks within other text editors such as code or .txt
files, the project that contains the file must be associated with a
particular task repository. This is configured by right-clicking on the
project and navigating to "Properties" \> "Task Repository" and
selecting the task repository used when working with this project.

## Reporting Bugs from the Error Log

Bugs can created directly from events in the *Error Log* view. This will
create a new repository task editor with the summary and description
populated with the error event's details. If the Connector you are using
does not have a rich editor, the event details will be placed into the
clipboard so that you can paste them into the web-based editor that will
be opened automatically.

![Image:Feature-Reference-3.0-Error-Log.png](Feature-Reference-3.0-Error-Log.png
"Image:Feature-Reference-3.0-Error-Log.png")

# Team Support

The task-focused interface provides several ways to improve your work
flow when working with a source code repository such as CVS or
Subversion. CVS support is available out-of-the-box and task-focused
interface integration for Subversion is available via the Subclipse or
Subversive plugins.

## Task-focused Change Sets

When working with a source code repository, you can commit or update
only the resources that are in the context of a particular task. This
helps you work on several tasks concurrently and avoid polluting your
workspace with changes that are not relevant to the current task.

To enable this functionality, locate the "Synchronize" view. If the view
is not visible, you can open it by navigating to Window -\> Show View
-\> Other... -\> Team -\> Synchronize. Next, click the small black arrow
next to "Show File System Resources" in the Synchronize view toolbar and
select "Change Sets". Note that change sets are not currently supported
in the EGit connector.

You can now synchronize resources in your workspace as usual (e.g. by
right-clicking on a resource in the navigator and selecting "Team" -\>
"Synchronize with Repository". Your resources will now be grouped by
change sets corresponding to tasks. Expanding the task shows individual
resources. Changed resources that are not a part of any task context
will appear under the root of the Synchronize view. If needed missing
resources can be added to the task context Change Set via the
Synchronize View by right+clicking the resource and selecting "Add to"
and then selecting the corresponding task. Select "no set" to remove a
resource from a change set.

![Image:Feature-Reference-3.0-Change-Sets.png](Feature-Reference-3.0-Change-Sets.png
"Image:Feature-Reference-3.0-Change-Sets.png")

You can use buttons in the toolbar of the Synchronize view to change
modes as follows:

  - **Incoming Mode** - See only updates to be retrieved from the server
  - **Outgoing Mode** - See only your local changes to be committed to
    the server
  - **Incoming/Outgoing Mode** - See both incoming and outgoing changes

Right-clicking a Change Set provides access to the following operations:

  - **Add to Task Context** - Adds all changed files to the active task
    context, see [\#Working with
    Patches](#Working_with_Patches "wikilink") for more information
  - **Open Corresponding Task** - Opens the task associated with the
    Change Set in the Task Editor

## Automatic Commit Messages

When using task-focused change sets as described above, commit messages
are automatically be generated based on the task whose resources are
being commited. By default, the commit message includes information such
as the task ID, description, and URL. To change the template for these
commit messages, navigate to Window -\> Preferences -\> Mylyn -\> Team.

Note that for EGit, Task-focused Change Sets are not supported, however
the commit message will be populated based on your currently active
task.

## Working with Patches

When applying patches, the preferred scenario is to have a task context
attached to the task along with the patch. Since this is not always
feasible, Mylyn provides an action in the popup menu of the
*Synchronize* view that supports adding changed elements to the task
context.

1.  Activate the task containing the patch.
2.  Apply the patch. If you are using automatic change sets, this will
    cause the change set created by Mylyn to contain the outoing
    changes. If it doesn't you can use the *Add to* action on the popup
    menu to add the elements to the corresponding change set.
3.  Invoke the *Add to Task Context* action on the change set node,
    causing all of the changed files to be added to the task context.
    You can also invoke this action on a selection one or more elements
    (e.g. files) in the view.

![Image:Feature-Reference-3.0-Add-To-Context.png](Feature-Reference-3.0-Add-To-Context.png
"Image:Feature-Reference-3.0-Add-To-Context.png")

# Shortcuts

<b> Task List view</b>

  - F2: rename
  - F4: show tooltip
  - F5: synchronize selected
  - Alt + Down: go to next unread
  - Alt + Up: go to previous unread
  - Alt + Shift + C: mark complete (local tasks only)
  - Alt + Shift + I: mark incomplete (local tasks only)
  - Alt + Shift + R: mark as read
  - Alt + Shift + U: mark as unread
  - Esc: hide tooltip
  - Enter: open task
  - Insert: new local task
  - Shift + Insert: new sub task
  - Alt + N (Mac only): new local task
  - Alt + Shift + N (Mac only): new sub task
  - Ctrl+C: Copy details
  - Ctrl+F: Find
  - When dragging URLs to the Task List: in Mozilla/Firefox just drag,
    in Internet Explorer `Ctrl+drag`

<b> Task Editor</b>

  - Ctrl+F: Find text in comments, description, summary and private
    notes
  - Alt + Shift + C: mark complete (local tasks only)
  - Alt + Shift + I: mark incomplete (local tasks only)
  - Alt + Shift + R: mark as read
  - Alt + Shift + U: mark as unread

<b> General</b>

  - `Alt+click` or `Alt+RightArrow`: show all children of an element in
    a focused view, then click to select. Hold down alt to keep drilling
    in, click on whitespace in view to show all root elements.
  - `Ctrl+Shift+Alt+RightArrow` Quick Context View
  - `Ctrl+F9`: activate task dialog
  - `Ctrl+Shift+F9`: deactivate task
  - `Ctrl+F12`: open task dialog
  - `Ctrl+Shift+F12`: open repository task dialog

<b> Interest manipulation</b>

  - `Ctrl+Shift+Alt+Up`: mark as landmark
  - `Ctrl+Shift+Alt+Down`: mark less interesting

<b> Useful Eclipse shortcuts</b>

  - `Alt+Shift+Q, K`: show *Task List* view
  - `Ctrl+F10`: invoke view menu or ruler menu in editor

# Preferences

You can access the following Mylyn preference pages by navigating to
Window -\> Preferences -\> Tasks.

## Tasks

  - **Synchronization** - Set how often queries in your task list should
    update from your task repository. The default is 20 minutes.
  - **Scheduling** - Set the day when your week begins. This is used to
    determine whether tasks should appear as scheduled for this week.
  - **Task Editing** - Select whether tasks should be opened in the rich
    editor or an integrated browser window displaying the web interface
    for the task.


Click "Advanced" to reveal the following additional settings.

  - **Task Timing** - When a task is active, the time spent working on
    the task is recorded. If you check "Enable inactivity timeouts",
    time will not be accumulated while you are not actively working. You
    can set the number of minutes after which time will stop being
    accumulated toward the active task.
  - **Task Data** - Specify the location where your task list and task
    context data is stored.

## Context

Use the following checkboxes to set your preferences for the
task-focused interface.

  - **Auto focus navigator view on task activation** - Automatically
    toggle "Focus on Active Task" on when activating a task in
    navigation views such as the Package Explorer.
  - **Auto expand tree views when focused** - When toggling "Focus on
    Active Task", automatically expand trees so that all interesting
    elements are visible.
  - **Manage open editors to match task context** - When checked,
    activating a task will automatically open editors corresponding to
    the most interesting files in the task context. When deactivating a
    task, all editors will automatically close. While a task is active,
    files that become less interesting will automatically close as you
    work.
  - **Remove file from context when editor is closed** - When this
    option is checked, closing an editor will be considered an
    indication that you not interested in the corresponding file.
    Therefore, files you close will be removed from the task context. If
    you tend to close editors for files that you may want to return to,
    try unchecking this setting.
  - **Open last used perspective on task activation** - When this option
    is checked, activating a task will automatically switch to the
    perspective that was in use when the task was last active.

## Resources

Use this preference page to add or remove resources that should not be
included in the context of a task. Typically, excluded files are hidden
backup or lock files that are not intented to be opened directly by the
user of an application.

## Breakpoints

Use this preference page to enable breakpoints in context.

  - **Include breakpoints in task context (Experimental)** - When this
    option is checked, each task will have its own set of breakpoints
    which will be shared when you attach context to the task.
    Breakpoints created while a task is active will be removed from the
    workspace on task deactivation and restored the next time the task
    is activated. This feature has the following limitations (tracked on
    [bug 428378](https://bugs.eclipse.org/bugs/show_bug.cgi?id=428378)):
      - Breakpoints in closed projects are deleted from the context on
        task activation and cannot be recovered.
      - Breakpoints stored in context will not have their locations
        updated as the code changes, so they may be restored at the
        wrong location.

## Team

  - **Automatically create and manage with task context** - Enables
    automatic change set management. Change sets will be created
    automatically so that you can commit or update only resources that
    are in a task's context.
  - **Commit Message Template** - Set the values that will appear in
    commit messages that are automatically generated when committing
    resources associated with a task. Pressing Ctrl+Space activates
    content assist which displays a list of the variables. Clicking once
    on a variable shows a description of that variable. For example, the
    variable ${task.id} provides the ID of the task associated with the
    commit.

# Task Repository Connectors

Mylyn allows you to collaborate on tasks via a shared task repository,
also known as bug tracking systems. In order to collaborate, you need to
have a **Connector** to your particular repository.

See [Mylyn Extensions](Mylyn/Extensions "wikilink") for a list of
available connectors.

## Bugzilla Connector

  - See the [Bugzilla Connector](Mylyn/Bugzilla_Connector "wikilink")
    wiki page.
  - See [Bugzilla Connector
    Troubleshooting](Mylyn/FAQ#Bugzilla_Connector "wikilink").

## Trac Connector

See [Trac Connector
Troubleshooting](Mylyn/FAQ#Trac_Connector "wikilink").

## Generic Web Templates Connector

The generic web repository connector is NOT part of the default Mylyn
install. You can install it from the incubator update site. See the
[Mylyn download page](http://www.eclipse.org/mylyn/downloads/) for more
details.

The web connector allow to retrieve tasks from repositories that don't
have rich connectors, but can show list of tasks on the web UI. Out of
the box connector provides configuration templates for the following
issue tracking systems:

  - Google Code Hosting (`code.google.com`)
  - IssueZilla (`java.net, dev2dev, tigris.org`)
  - GForge (`objectweb.org`)
  - SourceForge (`sf.net`), see [Using Sourceforge with
    Mylyn](Using_Sourceforge_with_Mylyn "wikilink")
  - Mantis (`www.futureware.biz/mantis`)
  - ChangeLogic (`changelogic.araneaframework.org`)
  - OTRS (`otrs.org`)
  - phpBB
  - vBulletin

Lists of issues can be extracted from existing web pages using simple
parsing configuration. Configuration can be also parametrized to make it
easier to customize it for a specific project.

The parameters used for configuring project properties are typically
substituted into the URLs used to access the repository. Substitution
and matching rules can be edited under the *Advanced Configuration*
section on both the *Repository Settings* page and the *Edit Query*
page.

See [FAQ](Mylyn/FAQ#Web_Templates_Connector "wikilink") for the
troubleshooting tips.

**For example**, consider the configuration steps for GlassFish project
at `java.net`:

**1.** Create new Generic web-based repository (in the Task Repository
view). GlassFish is using IssueZilla and has a preconfigured template
that can be selected by server url
*<https://glassfish.dev.java.net/issues>*. You can also specify all
fields manually in the *Advanced Configuration* section. For GlassFish
the following settings are required:

  - Task URL: `${serverUrl}/show_bug.cgi?id=`
  - New Task URL: `${serverUrl}/enter_bug.cgi?issue_type=DEFECT`
  - Query URL:
    `${serverUrl}/buglist.cgi?component=glassfish&issue_status=NEW&issue_status=STARTED&issue_status=REOPENED&order=Issue+Number`
  - Query Pattern: `<a href="show_bug.cgi\?id\=(.+?)">.+?<span
    class="summary">(.+?)</span>`

<!-- end list -->

  -
    **Note:** *Query Pattern* field should be a `regexp` with 1st
    matching group on *Issue ID* and 2nd on *Issue Description*.
    Alternatively, you could use named matching groups: ({Id}.+?),
    ({Description}.+?), ({Status}.+?), ({Owner}.+?) and ({Type}.+?),
    then they can appear in query `regexp` in an arbitrary order. The
    second option requires build 2.0.0v20070717 or later.

<!-- end list -->

  -
    **Note:** the above fields are using parameter substitution `${..}`.
    Variables `serverUrl, userId` and `password` are substituted from
    the values of corresponding fields of the repository preference
    page. In addition you can specify any arbitrary parameters and their
    values that will be also substituted into the template fields.

<!-- end list -->

  -
    **Note:** the SourceForge template included with connector assume
    that *single repository is used for all projects*. User should
    create multiple queries, and set project parameters at the query
    level. Because web connector don't support actions like "open
    repository task" there is really no need to create separate
    repositories per project and if you think about it that is how it
    work for connectors for Bugzilla and Trac. However, it is still
    possible to setup separate repository per project using repository
    url like http://sourceforge.net/tracker/?group_id=172199 and
    accordingly updating derived urls is the advanced repository
    settings.

**For the web repository that require user to login, use advanced
configuration in following way.** <i>This configuration is for GForge,
you might need to change it for other repositories</i>:

  - Login Request URL - an address that form is using to submit login
    request:
    ` ${serverUrl}/account/login.php?return_to=&form_loginname=${userId}&form_pw=${password}&login=Login
     `**`(POST)`**
  - Login Form URL - an address where login form is located *(only
    needed if server need a login token in the parameters of the Login
    Request URL)*: `${serverUrl}/account/login.php`
  - Login Token Pattern - pattern to extract value of the `loginToken`
    parameter from the form page *(only needed if server need a login
    token in the parameters of the Login Request URL and Login Form URL
    is specified)*: `session_ser=(.+?)`

**2.** Create a new query for the GlassFish task repository created
above (either from popup context menu in the Task List view or using a
"New..." wizard from File -\> New... -\> Other... menu).

  - *Query URL* and *Query Pattern* in the *Repository Preferences* are
    used as default query parameters and can be overwritten in *Advanced
    Configuration* section in *Query Preferences*. Custom parameter
    values can also be overridden here as well as new parameters for
    substitution into the specific query.

<!-- end list -->

  - In the *Advanced Configuration* section of the "New Query" dialog,
    there is a "Preview" button. You can use it to test your query
    pattern.

![Image:Generic-web-repository-settings.gif](Generic-web-repository-settings.gif
"Image:Generic-web-repository-settings.gif")

[Category:Draft Documentation](Category:Draft_Documentation "wikilink")
[Category:Mylyn](Category:Mylyn "wikilink")