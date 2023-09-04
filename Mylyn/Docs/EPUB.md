The [EPUB](http://en.wikipedia.org/wiki/EPUB) framework in Mylyn Docs
offers API to create, manipulate, read and write EPUB formatted files.
There is also an UI operation for building publications from markup.
[WikiText](Mylyn/WikiText "wikilink") markup in all supported formats
(Textile, MediaWiki, Creole, Confluence etc.) can be converted to XHTML
and packaged as EPUB using a one step wizard found in the file popup
menu. If more control and flexibility is required when assembling EPUBs,
there is in addition an Ant task that may be used to this end. A
[talk](http://www.slideshare.net/torkildr/eclipsecon-europe-2011-build-your-epubs-with-eclipse)
was given at EclipseCon Europe 2011 introducing this tooling. There is a
YouTube [video
demonstrating](http://www.youtube.com/watch?v=kdcDMmx2ohY&feature=channel&list=UL)
the UI wizard.

The source code is in the Mylyn Docs Git repository at
<http://git.eclipse.org/c/mylyn/org.eclipse.mylyn.docs.git/>. Bugs
belonging to this component are handled using the
[EPUB](https://bugs.eclipse.org/bugs/buglist.cgi?classification=Mylyn;emailtype1=exact;query_format=advanced;email1=torkildr%40gmail.com;component=EPUB;product=Mylyn%20Docs;list_id=1575205)
component in the Eclipse Bugzilla.

## Features

  - Support for the [EPUB 2.0.1
    specification](http://idpf.org/epub/201).
  - Wizard for converting a single markup file to an EPUB.
  - Ant task for assembling an EPUB.
  - API for creating, reading, writing and manipulating an EPUB.
  - Content validation.

### Unsupported EPUB features

  - Digital Rights Management (DRM). Including signing, encryption and
    font obfuscation.
  - *Tours* element in the OPF. Was deprecated in version 2.0.1 and
    removed in version 3.0 of the EPUB specification.
  - *Out-of-line XML islands* in the OPF. Was removed in version 3.0 of
    the specification.

## Planned features

  - [EPUB editor](Mylyn/Docs/EPUB/Editor "wikilink") with support for
    handling multiple files. This should be used instead of the wizard
    when more control is required.
      - Store EPUB specification between sessions.
      - Generate Ant task.
      - Convert wiki markup automatically.
      - Link to content editors.
  - ~~[Improved wizard](Mylyn/Docs/EPUB/Improved_wizard_plan "wikilink")
    for converting markup to EPUB.~~
      - ~~Add more than one file to the EPUB.~~
      - ~~Store settings when done and repopulate fields when starting
        the wizard again ().~~
      - ~~Generate Ant task from wizard.~~
  - Support for the [EPUB 3.0 specification](http://idpf.org/epub/30)
    ().

[Category:Mylyn](Category:Mylyn "wikilink")