This document contains the manual testing check-list. Use
<font color='firebrick'>red to indicate failures</font>.

## General

  - Ensure launch works with JRockit
  - Ensure clean start/restart has no messages in log
  - Verify documentation is available under Help \> Help Contents \>
    Tasks User Guide
  - Verify that all features and plug-ins are signed
  - Verify that no undesired update sites are added
  - Verify EPP perspective contributions

## Task Management

  - Test offline mode
  - Lazy loading
      - Startup without task list visible -\> Automatic synchronization
        is not triggered
      - Startup with task list in fast view mode with a task active -\>
        no errors in log
      - Startup with task editor visible -\> no errors in log
  - Test clean install with task list only installed then with only one
    connector installed. Ensure adding task repository doesn't cause
    errors.

### Task Repositories

  - Check if Local Task and Eclipse.org repository exists

### Task List

  - Ensure tasklist colors and decoration are correct for due dates
    (past due, due today, due this week)
  - Test data directory move
  - Ensure creating a new query either via task list popup or File \>
    New doesn't result in exception when there are no remote
    repositories set up
  - Ensure that when an unread task with a context is activated, the
    prompt to retrieve the context appears
  - Test proxy support using platform proxy settings
  - Make repository task in query active and delete query -\> Task moves
    to Unmatched and is active
  - Delete category that contains a repository task scheduled for today
    -\> Task moves to Unmachted
  - Open UI legend from view menu
  - Drag and Drop
      - From category to category -\> task is moved
      - From query to category -\> task is copied
      - To category -\> task is copied
      - To Uncategorized -\> nothing happens
      - To Unmatched -\> nothing happens
      - To Unsubmitted -\> nothing happens
      - To query -\> nothing happens
      - Task to external text -\> <font color='firebrick'>copies
        details</font>
      - Task to external explorer -\> exports task

#### Scheduled Presentation

  - Scheduled presentation showing empty days in focus mode
  - Create a local task "a" with subtask "b". Schedule a subtask for
    next week.
      - \-\> <font color='firebrick'>should make subtask and parent
        disappear</font>

#### Other

  - Change URL of Eclipse.org repository
  - File \> Export \> Tasks \> Task Data and Contexts
      - Test importing with task in active state
  - Change data directory in Preferences \> Tasks \> Advanced
      - Ensure all data is migrated including context and backup folders
        and contained data
      - Ensure that if 'load' is selected that the target folder is
        loaded and not overwritten
  - File \> Import \> Tasks \> Task Data and Contexts

### Task Editor

  - Clicking on a comment sets the editor selection to ITaskSelection
    resulting in a different popup menu
  - Attach context checkbox should not be on the editor when there is no
    context
  - New Task Editor shows Add to Category and Scheduled Date

### SDK Integration

  - Ensure integrated bug reporting works
  - Create Task Working Set. Add query. Open Project Explorer. Make
    Working Sets Top Level elements -\> Queries are not displayed
  - Perspective settings and new shortcuts for all SDK perspectives
  - Ensure change set refresh works due to change on
  - Context import and export

## Task-Focused Interface

  - Interest manipulation shortcuts in various perspectives
  - Verify that bridges are loaded lazily

### Java

  - Ensure that content assist has no duplicates with fresh workspace,
    and has focused entries on first task activation
      - Check for duplicate content assist on empty workspace
  - Ensure context tests can be created and work
      - Run JUnit context test without interesting tests: should get
        message
      - Run JUnit contexts test with interesting tests, should run
      - Do above for PDE JUnit tests
  - Ensure code folding works properly

### Team

  - Open Corresponding Task Action
      - Incoming change set classic mode
      - Incoming change set models mode
      - Outgoing change set classic mode
      - Outgoing change set models mode
      - History view element with old format (e.g. TasksUiPlugin comment
        before 2006-08)
      - History view element with new format (e.g. TasksUiPlugin comment
        after 2006-11)
  - Check non-models change sets mode
  - Context change sets don't have labels
  - Change sets don't always have a commit action
  - Activate local task and commit Mylyn changes -\> A warning message
    is displayed that the repository does not match

### SDK Integration

  - Filtering
      - Markers view
      - Problems view
      - Debug view
      - Eclipse native tasks view

### CDT

  - Ensure that content assist has no duplicates with fresh workspace,
    and has focused entries on first task activation
  - Ensure code folding works properly
  - Ensure that with CDT and Java installed, there aren't 2 focus
    buttons
  - Ensure C/C++ Projects view can be focused

## Discovery

  - Verify that all connectors are installable
  - Verify that install buttons are not visible on 3.4

## Bugzilla

  - Adding new component, then refreshing attributes fails to make that
    component show, reopening editor fixes it
  - <font color=red>Ensure new milestones show up after attribute
    added</font>
  - <font color=red>Ensure duplicate actions do not show up</font>

<!-- end list -->

  - Offline Reports
      - Ensure that when a bug report is opened **offline** that has no
        offline data the editor banner has a hyperlinked warning
        indicating that the data is not available.
      - In the case of migration ensure that offline reports still open
        correctly (if not lost completely).
  - Seach \> Task Search \> Open Repository Task... , enter bad ID,
    Should result in invalid id error dialog
  - Repository Search (Search \> Search... \> Repository Search tab)
      - Repository search page
          - Ensure warning if no repository exists.
          - Cycle through available repository search pages ensuring
            that they populate with the last search performed on the
            respective repository
          - Ensure other repository types search pages appear when
            selected
      - Repository Search Results View
          - Test opening bug not in task list, editor should open with
            "Not in Task List" hyperlink that adds the bug to the task
            list.
          - Test opening report with local data. Bug should open in
            bugzilla editor

<!-- end list -->

  - Bugzilla Task Editor (Rich editor)
      - When opening remote tasks (ie. from search results view) ensure
        that posting authenticates properly
      - Editor Hyperlinking - URL Hyperlinks, Bug hyperlinks (bug\# 123,
        bug 12312, task\# 1, task 12, duplicate bug links), stack trace
        links
      - Editor menu/commands - Cut/Copy/Paste/Select-all from menu and
        using shortcut keys <font color='firebrick'>(March 30, 2007) Cut
        & Copy from menu broken in Linux due to loss of focus on
        text</font>

<!-- end list -->

  - Bugzilla Query Wizard (Tasklist)
      - Create new query
      - Open query to see that parameters are still there

<!-- end list -->

  - Update of Repository Configuration
      - Test from TaskRepositoriesView context menu
      - A dialog should be produced in either case when an io or login
        exceptions occur.

<!-- end list -->

  - New Bug submission (invalid credentials)
      - Remove username and password from a repository configuration in
        the Task Repositories view
      - Initiate new repository task action
      - Select repository with missing credentials
      - Upon submitting new bug editor user is presented with
        credentials dialog

<!-- end list -->

  - Submission of changes to a Bugzilla report should result in all
    parent queries being re-synchronized as well as the task itself
    being synchronized
  - Ensure submission of comment doesn't remove any depends on / blocks
    bugs
  - Submission of changes to existing bug with invalid repository
    credentials
      - Repository Settings page presented

<!-- end list -->

  - Synchronize from context menu (invalid userid and password)
      - Report Download Failed Dialog: Ensure proper repository
        configuration in Task Repositories view.

<!-- end list -->

  - Synchronizing while disconnected should not put errors in the
    eclipse log
  - Task Synchronization State
      - Open, modify, save, should have outgoing decorator
          - Case clear outgoing: confirmation dialog should pop up
              - Case confirm: outgoing decorator should go away
              - Case deny: outgoing decorator should remain
          - Case open: should retain outgoing overlay
          - Case edit and save again: outgoing overlay remains (should
            not receive conflict warning)
          - Case submit: outgoing overlay should disappear (should be no
            incoming upon synchronize)

<!-- end list -->

  -   - Task in CONFLICT state
          - Case open: changed to outgoing (incomings highlighted in
            editor)
          - Case synchronize: conflict remains
      - Open report in external editor and add a comment.
          - Case synchronize: incoming decoration should appear on task
              - Case open: task opens with new content highlighted
              - Case open (bug editor already open): Banner gets
                hyperlink indicating new changes available
              - Case Background Synchronization incoming state remains
          - Case open: task opens with offline content, user asked if
            they want to refresh with incoming content.
      - Open, modify, save, should have outgoing decorator, open report
        in external browser, add comment
          - Case open: Outgoing decorator remains
          - Case Submit: Mid air collision...synchronize task
              - Case Synchronize from editor: New incoming is updated,
                outgoing changes tagged with \*
      - Copy report to a local category, repeat above tests ensuring
        decoration always matches
      - Copy report to root category, repeat tests ensuring decoration
        always matches

<!-- end list -->

  - Check that auto background synchronize works
  - Ensure that new hits (i.e. reports created using web ui) appear in
    query after auto sync
  - Ensure that incoming on existing tasks appears after auto
    synchronization
  - Check that if changes are made to the notes field of the Planning
    section that save still works (editor doesn't remain dirty).
  - Ensure that when offline reports file is deleted, tasks don't
    suddenly all have incoming status upon synchronizing
  - Reports \> Outline View
      - Clicking on comments in outline view should cause editor to
        scroll to respective comment in the editor page.

<!-- end list -->

  - DnD Attachments: Ensure all of the following launch the new
    attachment wizard with the appropriate file specified.
      - Drag a file from the workspace to the attachments section or new
        comment box.
      - Drag a file from a different application (or desktop) onto the
        attachments section or new comment box.
      - Drag a region of text from any application (eg. a web browser)
        onto the attachments section or new comment box.

<!-- end list -->

  - Opening a repository task that has no repository should display
    warning indicating that the repository must be created.

## JIRA

  - Parent attribute is displayed for new tasks
  - The task editor does not select a default resolution

## Trac

  - Create Repositories:
      - <http://trac.edgewall.org/trac> (Trac 0.9 and higher)
          - Validate settings
          - \-\> Message: Repository is valid
      - <http://mylyn.eclipse.org/tractest>
          - Username: tests@mylyn.eclipse.org
          - Password: <password>
          - Repository is valid
          - \-\> Message: Authentication credentials are valid.
          - \-\> XML-RPC is selected

<!-- end list -->

  - Query (Trac 0.9)
      - Add query for <http://trac.edgewall.org>
      - \-\> Repository attributes are displayed in query dialog
      - Select "0.10" for version
      - Finish
      - \-\> Tickets are marked as incoming
      - \-\> Notifications popup
      - Open ticket
      - \-\> Ticket is opened in browser pane
      - \-\> Ticket is marked as synchronized

<!-- end list -->

  - Search
      - Open search
      - Select <http://mylyn.eclipse.org/tractest>
      - \-\> progress bar is shown while attributes are updated
      - \-\> attributes are displayed
      - Select <http://trac.edgewall.org>
      - Search for "ticket" in summary on edgewall.org
      - Double click search result
      - \-\> Browser is opened
      - Open another search result through context menu
      - \-\> Browser is opened

<!-- end list -->

  - Query and offline handler (XML-RPC)
      - Add query for all tickets in "component1" for
        <http://mylyn.eclipse.org/tractest>
      - \-\> All tickets are marked as incoming
      - Edit ticket summary of any ticket in **web browser** and submit
      - Synchronize query
      - \-\> Only edited ticket is synchronized and marked as incoming
      - Reopen query
      - \-\> "component1" is selected

<!-- end list -->

  - Create Ticket in Rich Editor (XML-RPC)
      - Select New \> Repository Task for
        <http://mylyn.eclipse.org/tractest>
      - Enter summary and description
      - Select Add to Task Category: root
      - Press Create New
      - \-\> New Ticket is added to task list
      - Open ticket
      - \-\> summary and description are correct

<!-- end list -->

  - Edit Ticket with Rich Editor (XML-RPC)
      - Open any ticket from query
      - Edit summary and save
      - \-\> Ticket is marked as outgoing
      - Edit ticket summary in **web browser** and submit
      - Synchronize ticket in task list
      - \-\> Task is marked as conflicting

<!-- end list -->

  - Context attachments (XML-RPC)
      - Activate ticket
      - Create new Java project
      - Open Java file
      - Attach context on active task
      - Retrieve context
      - \-\> Context is displayed in wizard
      - \-\> Context is loaded

[Category:Mylyn](Category:Mylyn "wikilink")