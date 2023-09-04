### Links

  - [Mylyn/FAQ\#WikiText](Mylyn/FAQ#WikiText "wikilink") Mylyn FAQ,
    WikiText

  - : \[wikitext\] Mylyn should support lightweight markup (eg: Textile)
    in its task editor

  - : A Wiki Integrated Task Editor

  - : Release review (see also
    [Mylyn/Incubator/WikiText/ReleaseReview](Mylyn/Incubator/WikiText/ReleaseReview "wikilink"))

## WikiText Project Charter

Lightweight markup languages (such as Textile), hereafter referred to as
LWM, are commonly used in issue tracking systems. Information displayed
by Mylyn is commonly authored in such formats and is displayed to the
user as raw markup.

The WikiText project will provide components for use in dislpaying and
authoring LWM. With these components, the user will have access to a
LWM-aware authoring environment and will be presented with formatted
content wherever LWM is authored or displayed.

### Requirements

The following are requirements that pertain to the WikiText project:

1.  The project shall provide a common framework for implementing
    parsers of LWM
    1.  The project shall provide a single reference implementation of
        such a parser, implementing the Textile markup language
    2.  Other markup language parsers may be provided by the project,
        focusing on markup languages supported by repositories for which
        there is a Mylyn connector (eg: TracWiki, Confluence markup and
        MediaWiki)
    3.  The project shall provide a means of extending the framework to
        support other markup languages, using standard Eclipse
        facilities such as extension points such that the framework may
        be extended outside of the project.
    4.  Where feasible the LWM parser framework and LWM parser
        implementations provided by the framework shall be usable
        outside of an Eclipse environment (stand-alone) without
        reference to Eclipse or OSGI APIs. The intention is to foster
        maximum community adoption of the parser components of the
        project in order to maximize community contributions back to the
        project in improving LWM parser components.
        1.  The project shall provide Ant tasks for converting files
            containing LWM to HTML, to Eclipse Help format, and where
            feasible to DocBook
2.  The project shall provide a means of displaying LWM content as it is
    intended to be viewed in its formatted form in an SWT UI
    1.  A 'lite' version of a viewer will be provided that makes a best
        attempt at displaying markup without use of a Browser component
    2.  The project shall also facilitate use of a Browser to display
        content
3.  The project shall provide an editor that is markup-aware, capable of
    authoring markup for any LWM supported by a parser component
4.  The project shall provide a set of patches to the Mylyn project
    which may be adopted by Mylyn in order to use components of WikiText
    in the Mylyn UI
    1.  The patches shall not reference APIs of the WikiText project,
        rather the reverse is true; the WikiText project may reference
        APIs of Mylyn

#### Non-Requirements

The following are non-requirements of the WikiText project, and as such
the listed features are explicitly identified as objectives and features
that are out of scope of the project.

1.  a WYSIWYG markup editor
2.  integration with wiki APIs for retrieving, submitting, managing or
    editing wiki content
3.  LWM parser implementations for arbitrary specific markup languages
    (only those listed above need be implemented by the project)

### Direction

The project shall consist initially of a contribution from the
open-source [Textile-J](https://textile-j.dev.java.net/) project, which
satisfies many of the project objectives and requirements.

### Stakeholders

  - Mylyn and Mylyn committers
  - Tasktop
  - Mylyn users and contributors
  - David Green and Textile-J
  - Jingwen 'Owen' Ou

#### Mentors and Committers

this project is sponsored and mentored by the following Mylyn
committers:

  - Steffen Pingal
  - Mik Kersten

## Plan

An initial draft of tasks and issues to be addressed by the project:

1.  Project Charter
    1.  Requirements
    2.  Roles/Responsibilities
2.  Textile-J Contribution
    1.  IP Process
    2.  Code Reorganization
        1.  Project Setup
        2.  Package/Class Naming
3.  Bugzilla Component WikiText under Mylyn
4.  CVS or SVN setup
5.  Build Process
    1.  Build Scripts
    2.  Continuous Integration
    3.  Test Reports, Code Coverage
    4.  Downloads/Update Site
    5.  Source Plug-Ins
6.  Development Tasks
    1.  Documentation for Developers/Contributors
        1.  How-To on adding a markup language
    2.  User Guide (adapted from Textile-J)
    3.  Mylyn Contributions
        1.  Extension Points
        2.  Task Editor Extensibility
        3.  Repository Configuration settings for editor
    4.  WikiText Features
        1.  Viewer to handle more HTML syntax
        2.  ITaskEditorExtension implementation
        3.  Preference pages
            1.  Browser/Viewer for viewing markup
            2.  page UI placement
        4.  Actions -\> Commands for commands outside of editor
        5.  MarkupToHtml/DocBook/EclipseHelp commands
        6.  Ant task tests
        7.  I18N

### Meeting Notes

**Notes from 2008-06-17 Meeting:**

  - no patches to be applied to head until after 3.0 release
  - 3.1 is target release for including WikiText contribution
      - maintenance branch to be created for 3.0 release
      - extension point to be moved into tasks.ui plugin after 3.0
        release
  - outstanding issues include
      - UI needed for per-repository configuration
      - 'preview' tab in editor area takes up too much space. either we
        get rid of the preview or move the preview function to a button
        in the header

**Notes from 2008-05-28 Meeting:**

  - Extension point to override default viewer and editor: needs to
    declare what editor it's using, need to declare language being used
  - If multiple viewer extensions present, our editor creates tabs
      - for example, if a viewer and editor are available, the edit area
        creates an 'Edit' tab and a 'Preview' tab for editable areas
  - E.g.: ITaskEditorExtension
      - createViewer()
      - createEditor()
      - createConfiguration()
      - getEditorContextId()
  - Activate a new context when the New Comment viewer is active, can
    extend default task editor context

[Category:Mylyn](Category:Mylyn "wikilink") [Category:Tools
Project](Category:Tools_Project "wikilink")