The Generic Web Repository Connector of [Mylyn](Mylyn "wikilink") can be
used to integrate [Sourceforge](http://sourceforge.net) trackers as task
repositories inside Eclipse. This page describes the necessary
configuration to be able to connect to multiple Sourceforge projects and
to browse all their tracker items (including project member only
trackers). Required settings are also available from the pre-packaged
templates that can be selected in the web connector repository
configuration.

## Preconditions

You need:

  - Eclipse 3.3 [Europa](Europa "wikilink") (choose one of the downloads
    from the main page),
  - Latest [Mylyn](Mylyn "wikilink") version. See [project download
    page](http://www.eclipse.org/mylyn/downloads/)
  - The [Generic Web Templates
    Connector](Mylyn_User_Guide#Generic_Web_Templates_Connector "wikilink")
    from the "extras" update site. This was formerly known as the
    Generic Web Repository Connector.
  - with Eclipse 3.4 or newer you need to add this
    [updatesite](http://download.eclipse.org/tools/mylyn/update/incubator/)
    to eclipse, to get the connector.
  - The latest version of mylyn. Older versions are not guaranteed to
    work with the latest Generic Web Templates Connector.

## Repository

Create a new task repository (inside the view "task repositories"),
choose "Generic web-based access" and use these configuration items:

  - Server: http://sourceforge.net/
  - Label: Sourceforge
  - Anonymous Access: (off)
  - User ID: *your Sourceforge username*
  - Password: *your Sourceforge password*
  - serverUrl: *<https://sourceforge.net>*

Open Additional Settings and then Advanced Configuration sections:

  - Login Request URL:
    ${serverUrl}/account/login.php?form_loginname=${userId}\&form_pw=${password}\&login=Login
  - Button after "Login Request URL": switch to "POST"

Note: If you want to integrate Mylyn with multiple Sourceforge projects,
you do **not** need multiple repositories. Instead you can create
multiple queries in the task list with corresponding configuration
parameters.

## Queries

Now that the repository is known in Mylyn you can create queries to show
bugs, feature requests and other tracker items inside Eclipse.

Follow the instructions at
<http://officefloor.wordpress.com/2012/12/10/allura-sourceforge-mylyn-connector/>
to set up the Web Template Connector.

[Category:Mylyn](Category:Mylyn "wikilink")