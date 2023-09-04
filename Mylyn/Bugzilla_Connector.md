### Bugzilla Server Optimization

  - [Tips for server
    administrators](http://wiki.eclipse.org/index.php/Mylyn_FAQ#Tips_for_server_administrators)
    describes a solution taken by Eclipse.org webmasters to reduce the
    bandwidth requirements due to Mylyn clients updating their
    repository configuration.

### GZIP encoding and content negotiation

The Mylyn Bugzilla Connector has been modified to accept gzip encoding
on all requests, and will do content negotiation. See
[bug 205708](https://bugs.eclipse.org/bugs/show_bug.cgi?id=205708).

### Preventing excessive logfile fill up

  - When running /bugzilla/ locally, one can prevent Mylyn filling up
    the log files by adding this to httpd.conf:

<DirectoryMatch /bugzilla/ >
`    BrowserMatchNoCase mylyn mylyn=1`
</DirectoryMatch>
`CustomLog "/private/var/log/httpd/access_log" combined env=!mylyn`

### Users

  - [Mylyn User Guide](Mylyn_User_Guide "wikilink"), [Bugzilla Section
    of User Guide](Mylyn_User_Guide#Bugzilla_Connector "wikilink")
  - [Bugzilla FAQ](Mylyn_FAQ#Bugzilla_Connector "wikilink")

### Langugage Configurations

Since Version 2.2 of Mylyn you can now add support for alternate
languages via extension point:

`org.eclipse.mylyn.bugzilla.core.languages`

Here is an example definition for the English language (en (default)).

<extension
         point="org.eclipse.mylyn.bugzilla.core.languages">` `
` `<language name="en">` `
`           `<languageAttribute command="error_login"        response="Login"/>` `
`           `<languageAttribute command="error_login"        response="log in"/>` `
`           `<languageAttribute command="error_login"        response="check e-mail"/>` `
`           `<languageAttribute command="error_login"        response="Invalid Username Or Password"/>` `
`           `<languageAttribute command="error_collision"    response="Mid-air collision!"/>` `
`           `<languageAttribute command="error_comment_required"     response="Comment Required"/>` `
`           `<languageAttribute command="error_logged_out"   response="logged out"/>` `
`           `<languageAttribute command="bad_login"      response="Login"/>` `
`           `<languageAttribute command="bad_login"      response="log in"/>` `
`           `<languageAttribute command="bad_login"      response="check e-mail"/>` `
`           `<languageAttribute command="bad_login"      response="Invalid Username Or Password"/>` `
`           `<languageAttribute command="bad_login"      response="error"/>` `
`           `<languageAttribute command="processed"      response="processed"/>` `
`           `<languageAttribute command="changes_submitted"  response="Changes submitted"/>
`           `<languageAttribute command="error_confirm_match"    response="confirm match"/>
`  `</language>
</extension>

Here is the detail description.

We have the following seven Commands defined in Mylyn:

| Command                  | Class & Method                            | usage                                 |
| ------------------------ | ----------------------------------------- | ------------------------------------- |
| error_login             | BugzillaClient.parseHtmlError             | detect login errrors                  |
| error_collision         | BugzillaClient.parseHtmlError             | detect a midair collision             |
| error_comment_required | BugzillaClient.parseHtmlError             | detect if a comment is required       |
| error_logged_out       | BugzillaClient.parseHtmlError             | detect if the user is logged out      |
| changes_submitted       | BugzillaClient.parseHtmlError             | changes are submitted (no real error) |
| processed                | BugzillaClient.postTaskData               | process was successful                |
| bad_login               | BugzillaTaskHistoryParser.retrieveHistory | detect bad login                      |
| error_confirm_match    | BugzillaClient.parseHtmlError             | responce if usermatchmode is enabled  |

For every Action there must be one or more responses.

Here is and example where the English responses for bugzilla-3.0.1 were
found.
{| \! Text || File ||Line |- | processed
||template/en/default/bug/process/header.html.tmpl ||37 |- | "Mid-air
collision\!" || template/en/default/bug/process/header.html.tmpl ||40 |-
| "Comment Required" ||
template/en/default/global/user-error.html.tmpl||241 |- | "Invalid
Username Or Password" ||
template/en/default/global/user-error.html.tmpl||822 |- | 'bug' =\>
"Changes submitted for $link"
||template/en/default/bug/process/results.html.tmpl||45 |- | Login ||
currently not known || |- |log in || currently not known || |- | check
e-mail|| currently not known || |- | logged out|| currently not known ||
|- | "confirm match" ||
template/en/default/global/confirm-user-match.html.tmpl||43 |}

You must look for the tranlated responses in templates of the other
language.

## Custom Transitions

Custom Workflows have been enabled in Bugzilla since Bugzilla 3.2. As
the first stage of efforts to make Mylyn detect these workflows, Mylyn
has been given the ability to parse a workflow description file to pick
up custom transitions and custom statuses. For example, if you are using
Mylyn to connect to a Bugzilla instance which uses customized bug
statuses, you will find it useful to craft an appropriate workflow
description file. Once you've created the file, specify it in task
repository properties:

![Image:MylynWorkflowDescriptionFileOption.jpg](MylynWorkflowDescriptionFileOption.jpg
"Image:MylynWorkflowDescriptionFileOption.jpg")

Here is a simplified example of a workflow description file:

` CustomStatusNames=true`
` DuplicateStatus=CLOSED`
` StartStatus=UNCONFIRMED`
` ClosedCustomStatus=RESOLVED`
` ClosedCustomStatus=VERIFIED`
` ClosedCustomStatus=POST`
` `<transitions>
` name :UNCONFIRMED:, can_change_to :NEW,POST,CLOSED:`
` name :NEW:, can_change_to :POST,CLOSED:`

The first part of the file details some configuration details

1.  CustomStatusNames indicates whether custom statuses are used.
    Defaults to false if unspecified.
2.  DuplicateStatus is the value of duplicate_or_move_bug_status in
    the Bugzilla Bug Change Policies. Defaults to RESOLVED if
    unspecified.
3.  StartStatus is the status to use for newly submitted bugs. Defaults
    to NEW if unspecified.
4.  ClosedCustomStatus is a list of custom statuses which leave the bug
    in a closed state. Defaults to an empty list if unspecified.
    The default status RESOLVED and VERIFIED need to be in the list of
    ClosedCustomStatus when you not change there values and add an new
    close status.

The <transitions> marker is used to indicate the beginning of the
transitions list.

Transitions should follow the format:

` name :CURRENT_STATUS:, can_change_to :NEXT_STATUS1,NEXT_STATUS2,NEXT_STATUS3:`

Note that `name` and `can_change_to` are keywords and must not be
changed. Status names, as specified after `name` need to correspond to
status names available for the Bugzilla instance in question. Usually,
you'd want to create one line per custom status of your Bugzilla
instance. Say your custom statuses are UNCONFIRMED, ON_QA, MODIFIED and
CLOSED. In order to be able to change to any one of those statuses (i.e.
see UI for those statuses), you'd need something like the following in
your workflow description file:

` name :ON_QA:, can_change_to :CLOSED:`
` name :UNCONFIRMED:, can_change_to :MODIFIED:`
` name :CLOSED:, can_change_to :MODIFIED:`
` name :MODIFIED:, can_change_to :ON_QA:`

An example of a complete workflow description file for Red Hat's
Bugzilla can be found
[here](Media:RHBugzillaWorkflowDescriptionFile.zip "wikilink") (note
that one must use it unzipped).

Installations of Bugzilla 3.6 or higher that do not need a custom start
status or duplicate status can use the "Autodetect workflow" (XMLRPC)
option to detect workflow customizations.

**Development Plans**

Additional tags will be added as needed to accurately describe a
Bugzilla installation.

## Developer Resources

[Mylyn Offline Refactoring](Mylyn_Offline_Refactoring "wikilink")

[Category:Mylyn](Category:Mylyn "wikilink")