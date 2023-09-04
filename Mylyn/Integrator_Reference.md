Also see: [Mylyn Architecture](Mylyn_Architecture "wikilink"), [Mylyn
Contributor Reference](Mylyn_Contributor_Reference "wikilink")

We recommend that those interested in integrating Mylyn email
mylyn-dev@eclipse.org regarding for pointers to examples and guidance on
upcoming changes. We encourage integrators to take the "better to ask
for forgiveness than permission" approach to adding and updating wiki
documentation. Committers review all changes and will update them as
needed. Evolving the documentation with integrator contributions works
well because it ensures that the documentation takes the perspective of
newcomers. It also helps committers dedicate more time to responding to
requests for improving the corresponding APIs.

# Building on Mylyn

Also see: '''[Mylyn/Porting Guide](Mylyn/Porting_Guide "wikilink")

We recommend listing your Mylyn integration on the
**[Mylyn/Extensions](Mylyn/Extensions "wikilink")** wiki page and in the
**[Eclipse Marketplace](http://marketplace.eclipse.org/)**.

For support and questions specific to an integration either [use the
mylyn-integrators mailing
list](http://www.eclipse.org/mylyn/development/) or **[file a
bug](http://www.eclipse.org/mylyn/support/)** along the following lines:

  - *\[connector\] support Mylyn integration with MySuperTracker*

## Feature configuration

When integrating Mylyn with an existing tool, we recommend creating a
new feature that declares a dependency on both the corresponding Mylyn
feature and on the plug-ins and features of the tool. The new feature
can then be deployed on the integrators' update site, and the update
manager will require that the correct version of Mylyn is installed
before allowing the new feature. The Mylyn Subversive integration can be
used as an [example of
this](http://www.polarion.org/index.php?page=mylyn&project=subversive).

## Workspace setup

The recommended workspace setup for integrators is check out the
projects to be extended from CVS. Instructions and project sets are
available on in the [Workspace Setup
documentation](Mylyn_Contributor_Reference#Setup "wikilink"). If you
would like a downloadable distribution that is not available on the
[download page](http://www.eclipse.org/mylyn/downloads/) please [submit
a bug report](http://www.eclipse.org/mylyn/bugs/).

In order to detect and protect yourself from API misuse, we highly
recommend using the '''[Eclipse API
Tools](API_Tooling_User_Guide "wikilink").

## Deciding on a version

We suggest targeting the Mylyn 3.x stream. So check out the HEAD project
set. Note that if you build against the HEAD stream your plug-in will
most likely support the last two major releases of Eclipse and the most
recent development stream because our APIs generally insulate the
connector from the platform internals that we use. But you will want to
verify this yourself by building against the oldest supported Eclipse
version before you deploy.

The general policy for Mylyn is that the current 4.x major release, the
latest 3.x major release or milestone, and the latest 4.x milestone of
Eclipse are supported. For example, on the Eclipse 4.4M1 release date,
August 23, 2013, Mylyn will support Eclipse 4.4M1 (latest milestone),
4.3 (current 4.x release) and 3.8 (current 3.x release/milestone).

Support for older Eclipse versions has ended: .

### Release policy

The Mylyn release policy follows the [Eclipse Development
Process](http://www.eclipse.org/projects/dev_process/development_process.php#4_2_Code_and_Releases).

**Major Releases**

  - Usually released every 6 month.
  - The minor qualifier of the version is incremented and the service
    qualifier is reset, e.g. 3.3.2 -\> 3.4.0.
  - Compatibility with previous releases is [documented in the
    plan](http://www.eclipse.org/projects/project-plan.php?projectid=tools.mylyn#compatibility).
    Generally, binary backwards compatibility of API is maintained with
    preceding major release, additional API is added and internals may
    change.
  - Major releases require a plan, release review and New & Noteworthy.
  - Compatible versions of connectors listed in the discovery portal
    need to be available on the release date.

**Service Releases**

  - Usually released every 3 - 6 weeks.
  - Only the service qualifier of the version is incremented, e.g. 3.4.0
    -\> 3.4.1.
  - Changes are never destabilizing and **UI backwards compatibility is
    maintained with preceding major release**.
  - Binary backwards compatibility of API and internals is maintained
    with preceding major release.

### Retention policy for builds

Integration builds against HEAD are provided on a weekly basis and
available from download.eclipse.org. Integration builds are deleted once
a release versions of the corresponding stream becomes available.
Release versions are listed on the [download
page](http://www.eclipse.org/mylyn/builds/). Versions older than one
year are archived on a regular basis and download URLs may change from
download.eclipse.org to archive.eclipse.org.

## Watching API changes

You can watch for API changes by creating a query for all Mylyn bugs
tagged `[api]`. Major API changes will be announced on the mylyn-dev
mailing list.

Also see: [Mylyn Porting Guide](Mylyn_Porting_Guide "wikilink")

## Using Internals

Following the lead of the Eclipse Platform, Mylyn makes a very clear
distinction between API and internals, placing the latter in packages in
the `org.eclipse.mylyn.internal` namespace. In order to support
experimentation, all internal packages are exported. However, they are
marked `x-internal:=true`, which means that the Eclispe will inform you
with warnings when you are using internals.

If you are using internals in your integration, the burden of
maintenance is placed entirely on your integration, since the project
only guarantees no breakage of internal classes between minor releases,
and these are likely to change in future major releases. Some tips for
using internals:

  - Check if there is API that you could use to achieve the same thing.
  - File a bug report stating that you would like the internals to
    become API.
  - Create a test case that exercises the API and/or internals that you
    use. This is the only way of ensuring that the behavior you are
    relying on won't change down the road.

## Innovating and Experimenting

One of the key challenges with building innovative or experimental tools
and solutions is to get the UI friction low enough to get enough people
to try it, without investing a lot of of time into the UI work since
that can take time away from the core work and evaluation. Some tips:

  - Decide and communicate whether you want the plug-in to be something
    that people experiment with, or something that they use for their
    daily development.

<!-- end list -->

  - If the plug-in is to be used for daily development, it should have a
    very low performance footprint. What's most important is that it
    does not slow down the user's Eclipse when it is not being used,
    otherwise many users will quickly disable it.

<!-- end list -->

  - When your plug-in is doing any background work, make sure to have
    that indicated in the Progress view (via the Jobs API). This will
    help people trust the tool, since their Eclipse could be getting
    slowed down by something else.

<!-- end list -->

  - Decide carefully on the UI that's needed to enable early adopters to
    make use of your tool. Eclipse users tend to have a very high
    expectation of UI polish, and UI work can dominate implementation
    time. Try to reuse existing UIs as much as possible. When adding new
    UI, it can help to follow the Eclipse UI guidelines (either the
    document or by example) since this will make it easier for people to
    use your tool without needing to read documentation.

<!-- end list -->

  - Eat your own dogfood as much as possible. If you expect others to be
    able to use the tool you should be able to use it yourself (as long
    as you are representative of the target audience). One of the key
    benefits of consuming what you produce is that it will help you
    prioritize both the performance and the UI work.

<!-- end list -->

  - Provide people with a public forum for feedback, since open
    discussion is important to many of the open source contributors who
    may try it. If you do not have a forum available you can start a
    discussion thread on the Mylyn newsgroup.

<!-- end list -->

  - Provide a short page describing how to use your plug-in (e.g.
    <http://www.cs.ubc.ca/labs/spl/projects/fishtail/>)

<!-- end list -->

  - In order to get support specific to your tool from the Mylyn
    committers create a Mylyn bug called "support integration with
    MyCoolTool".

## Capabilities

Mylyn provides the org.eclipse.mylyn.ide.capabilities plug-in that has
sample extensions for the org.eclipse.ui.activities extension point.

  - [1](http://dev.eclipse.org/viewcvs/viewvc.cgi/org.eclipse.mylyn.incubator/org.eclipse.mylyn.ide.capabilities/plugin.xml?root=Mylyn_Project&view=markup)

The plug-in is not distributed. Integrators are encouraged to ship their
own capability definitions based on the example extensions linked above
(see ).

# Commons API

*Since Mylyn 3.0*

The Mylyn Commons API provides common facilities that are used by the
other Mylyn components. The Commons facilities can be reused without
bringing in any other Mylyn dependencies and have very limited set of
Eclipse Platform dependencies. Note that some of the Commons components
provide tentative API that is identified with a `provisional` segment in
the package name. While the corresponding classes are being used by
Mylyn components, we are still seeking integrator input on them and as
such they are subject to change, and will move out of the `provisional`
package once their API has been hardened.

## Consuming commons plug-ins

The Mylyn update site provides an uncategorized feature that provides
all commons plug-ins. This feature is provided for backwards
compatibility with the old update manager (see ). Integrators are
encouraged to specify dependencies on a plug-in level in feature.xml
files, e.g.:

`<feature...`

` `<requires>
`   `<import plugin="org.eclipse.mylyn.commons.soap" version="3.4.0" match="equivalent"/>
` `</requires>

</feature>

## Commons Core

The `org.eclipse.mylyn.commons.core` plug-in provides the
`StatusHandler` API for handling errors, as well as additional utility
classes.

## Commons Net

The `org.eclipse.mylyn.commons.net` plug-in provides an API for the
Apache HttpClient connections that Mylyn Tasks API Connectors use for
web service connectivity. Some of the API features provided are:

  - Proxy configuraiotn
  - User agent setting, e.g., `Mylyn/2.3.0 Eclipse/3.3.1 (null)
    HttpClient/3.1 Java/1.5.0_13 (Apple) Mac OS X/10.5.1 (i386; en_US)`
  - Connection monitoring and cancellation support

## Commons SOAP

The `org.eclipse.mylyn.commons.soap` plug-in provides an API for SOAP
connections based on Apache Axis.

## Commons UI

The `org.eclipse.mylyn.commons.ui` plug-in provides common widgets and
workbench extensions used by other Mylyn components. Entry points
include:

  - **AbstractFilteredTree**: a filtered tree that provides an adaptive
    refresh policy, useful for tress with thousands of nodes or more.
  - **AbstractNotification**: desktop notification popups used by the
    Tasks view. A sample extension is in
    `org.eclipse.mylyn.commons.tests.manual.NoticicationPopupMain`. See
  - **CommonColors**: color constants used through the Mylyn UI.
  - **CommonFonts**: fonts used by Mylyn.
  - **CommonThemes**: theme extensions used by Mylyn.
  - **DatePicker**: date selection widget, a dialog class is also
    available
  - **ScreenshotCreationPage**: a wizard page that lows the user to
    capture the desktop and premits markup of screenshots. See

## Commons XML-RPC

The `org.eclipse.mylyn.commons.xmlrpc` plug-in provides an API for
XML-RPC connections based on the Apache XML-RPC library.

### Documentation

  - [Article on reusing the notification
    framework](http://stacktrace.be/blog/2009/11/09/eclipse-plugin-development-show-custom-mylyn-notification-dialog/)

# Discovery API

For discussion and requests please use

At a high level Mylyn uses the concept of a directory and connector
descriptors. The directory is a declarative (XML) resource that exists
at a well-known URL, and points to connector descriptors. Connector
descriptors describe an installable component, and include branding,
description, images, etc. So Connector Discovery first accesses the
directory to discover where the connector descriptors can be found, then
downloads the descriptors to discover what the installable units are.
This design provides a central point of control for updating what is
discoverable, and avoids the need to install any plug-ins to have
contributions to the discovery UI. It also gives vendors the freedom to
update their contributions without involving changes or involvement by
committers, providing that their contribution is already listed in the
directory. Contributions may also be provided by installed plug-ins if
desired.

The discovery listings are stored in file hosted on eclipse.org that has
entries of the following form:

<directory ns="http://www.eclipse.org/mylyn/discovery/directory/">
` `<entry url="http://www.eclipse.org/downloads/download.php?file=/tools/mylyn/discovery/org.eclipse.mylyn.discovery.jar&r=1" permitCategories="true" />
`.`
`.`
`.`
</directory>

Note that those entries do not store metadata. The metadata is stored in
the plug-in that the “file=” points to, and uses standard Eclipse
extension points. For example:

`     `<connectorDescriptor
            categoryId="org.eclipse.mylyn.discovery.directory.categories.TaskManagement"
            description="%connectorDescriptor.description.mantis"
            id="com.itsolut.mantis_feature"
            kind="task"
            license="%connectorDescriptor.license.mantis"
            name="%connectorDescriptor.name.mantis"
            provider="%connectorDescriptor.provider.mantis"
            siteUrl="http://mylyn-mantis.sourceforge.net/eclipse/update/">
`        `<icon
               image32="images/mantis-32.png"></icon>
`        `<overview
               screenshot="images/mantis-screenshot-320x240.png"
               summary="%connectorDescriptor.overview.summary.mantis"
               url="http://mylyn-mantis.wiki.sourceforge.net/">
`        `</overview>
`     `</connectorDescriptor>

Discovery API plug-ins:

  - `org.eclipse.mylyn.discovery.core`
  - `org.eclipse.mylyn.discovery.ui`
  - `org.eclipse.mylyn.discovery.tests`

Clients and extensions:

  - `org.eclipse.mylyn.discovery-directory`: discovery listing for
    Eclipse.org
  - `org.eclipse.mylyn.tasks.ui`: Mylyn Connector specific entry points

# Tasks API

A tutorial with screenshots is available here:
<http://jvliet.blogspot.com/2007/02/creating-mylar-connector-plugin-for.html>.

## Use Cases

See
<https://web.archive.org/web/20110718233712/http://www.ibm.com/developerworks/java/library/j-mylyn1/>

## Task repository requirements

Mylyn can be extended to any task/bug/issue/story repository or tracker
by creating a repository Connector that links Mylyn's task management
facilities with the repository. Connection to the task repository is
handled by the Connector (e.g. via HTTP/REST for the Bugzilla Connector,
via SOAP for the JIRA Connector). The following are required to support
task list integration:

  - Identifying tasks: must be uniquely identifiable by a per-repository
    integer or string handle (e.g. repository: bugs.eclipse.org/bugs, id
    138144). ID must be robust to task renames, moves within components
    and categories, etc.
  - Retrieving tasks: mechanism for retrieving the attributes for a task
    given an ID. Attributes can typically include the description,
    priority, assignee and comment thread. For example, REST is the
    mechanism used by the Bugzilla Connector (POST request asks for bug
    ID, and XML as the return format,
    [example](https://bugs.eclipse.org/bugs/show_bug.cgi?id=106990&ctype=xml)),
    and SOAP is the mechanism used by the JIRA Connector.
  - Performing queries: mechanism for executing a string-based query and
    returning all of the matching task IDs. Preferrably encoded as a URL
    to allow interoperability with the web UI. For example, the Bugzilla
    Connector issues a POST request with the query URL, and specifies
    that the return format should be RDF,
    [example](https://bugs.eclipse.org/bugs/buglist.cgi?query_format=advanced&short_desc_type=allwordssubstr&short_desc=&product=Mylyn&component=Bugzilla&long_desc_type=allwordssubstr&long_desc=&bug_file_loc_type=allwordssubstr&bug_file_loc=&status_whiteboard_type=allwordssubstr&status_whiteboard=&keywords_type=allwords&keywords=&bug_status=RESOLVED&emailtype1=substring&email1=&emailtype2=substring&email2=&bugidtype=include&bug_id=&votes=&chfieldfrom=&chfieldto=Now&chfieldvalue=&cmdtype=doit&order=Reuse+same+sort+as+last+time&field0-0-0=noop&type0-0-0=noop&value0-0-0=&ctype=rdf).

The following additional mechanisms enable rich editing:

  - Retrieving all of the operations possible on a task given login
    credentials (e.g. ability to reassign, change priority)
  - Accessing all of the repository attributes (e.g. lists of products,
    components, versions),
    [example](https://bugs.eclipse.org/bugs/config.cgi?ctype=rdf)
  - Setting any of the task's attributes (e.g. changing components,
    reassigning)
  - Adding and retrieving attachments (e.g. posting patches,
    screenshots)

The following are optional:

  - Notification of changes (e.g. RSS-based notification of an update
    made via that web UI)
  - Retrieving a user's saved queries (e.g. searches or filters saved
    via the web UI)

Dynamic repositories with user configurable attributes per task:

The case may be that most of the attributes for your particular
repository are highly customizable and user defined. A connector can be
written for this scenario but will require a bit more plumbing. At the
very least, you will need to map the id and summary of your repository
artifacts to Mylyn task data attributes. These fields are the minimal
requirements to give your 'task' representation in the task list.
Depending on when you retrieve the set of possible attributes and
values, you will likely either store it in your connector specific
repository configuration or on a per ticket basis. The latter is
supported by Mylyn's generic attribute facility which enables offline
support and rich editing for common attribute types. In addition the
editor is customizable to handle repository specific types or layouts.

## Integrating with Mylyn's Task List vs. using a custom view

The Mylyn Task List has a considerable amount of functionality that is
related to working with queries and to rich editing. For example, it
shows notifications of incoming changes, and indicates when a query
synchronization failed. It is also the anchor for managing the offline
support, since only the tasks that the user has read are stored offline,
only changed tasks are synchronized, and all of this state is maintained
in the Task List. Our architecture does provide a loosely-coupled
architecture so you can use the TaskList (in ..mylyn.tasks.core) without
using any of its UI or having your users install the corresponding view.
But for most cases we believe that the better approach is to integrate
with Mylyn's Task List rather than providing an separate view. Most
developers work with three kinds of tasks:

  - The issues and tasks that make up their project (i.e. in MKS
    integrity).
  - Bug reports and enhancement requests that they watch and create for
    the other frameworks that they use (e.g. bugs against Eclipse, JEE,
    Spring).
  - Personal tasks and todos they need to make for themselves (via
    Mylyn's Task List).

For this reason a fundamental part of our approach is to give developers
a single view for managing all of their tasks, and to make it easy for
vendors to customize the content of the Task List and rich editors to
meet their needs (e.g. as JIRA does with custom task icon type
overlays). There are substantial benefits to providing developers with a
single unified task management view, similar to those benefits of
providing them with a unified resource management view (i.e., Eclipse's
*Project Explorer*). Rather than bloating the user experience by
involving one or more disparate bug/task/issue/ticket management views,
developers can provide a single Task List that is seamlessly integrated
with Eclipse. For an overview of the benefits refer to the following
article:
<https://web.archive.org/web/20110718233712/http://www.ibm.com/developerworks/java/library/j-mylyn1/>

The other thing to consider is integration with Mylyn's automatic
context management facilities. Again, this is possible to integrate with
a custom view, but the Task List has been streamlined around the
interaction needed to make task activation easy. For an overview of task
context management refer to this article:
<https://web.archive.org/web/20110820221743/http://www.ibm.com/developerworks/java/library/j-mylyn2/>

## Creating connector projects

The Trac connector is a good example, because it is a nearly-full
featured implementation, but does not contain as much customization as
Bugzilla. Start by creating two plug-in projects using the following
suggested naming convention:

  - `com.mycompany.mytracker.core`: Java API for connecting to the task
    repository. This project should not make contributions to the
    Eclipse UI and hence does not need a plugin.xml file.
  - `com.mycompany.mytracker.ui`: Eclipse and Mylyn UI for the connector
    which does make contributions to the UI, so this will need a
    plugin.xml (created by PDE wizard).
  - `com.mycompany.mytracker.tests`: unit tests for both core and UI
    parts, should have JUnit on its classpath.

## Implementing core extension points

Your connector should extend AbstractRepositoryConnector
(org.eclipse.mylyn.provisional.tasklist). For basic operation you should
first implement importing existing tasks from the repository. Therefore
you need to implement the methods getConnectorKind,
canCreateTaskFromKey, and getTaskData. Use the Trac connector as an
example. If your first basic plugin works, you should handle
synchronization by implementing performQuery().

Here are some classes you should create for your connector:

  - MytrackerCorePlugin extends Plugin
  - MytrackerRepositoryConnector extends AbstractRepositoryConnector

Tips on adding external library JARs:

  - The [Eclipse Orbit project](http://eclipse.org/orbit) provides
    bundles for common Java libraries such as Apache HttpClient that you
    can use a dependencies in your plug-in.

## Implementing UI extension points

You have to create following list of Extensions from Plug-in Manifest
Editor tab. Create extension `org.eclipse.mylyn.tasks.ui.repositories`
and add:

  - MytrackerRepositoryConnector
  - MytrackerConnectorUi

Create extension org.eclipse.mylyn.task.core.templates and add:

  - Your connector template(s)

Create extension org.eclipse.mylyn.task.ui.editors and add:

  - MyTrackerTaskEditorPageFactory

Adding repositories:

  - Note, that each repository must have a unique url
  - Create UI to editor settings for your repository in
    MyTrackerRepositorySettingPage:
      - Implement createAdditionalControls
      - Override applyTo to store the data in TaskRepository properties
        so they can be retrieved and used later. Note, that you must
        call super.applyTo() when overridding this method.

## Query support

To create new queries, you have to implement the
`AbstractRepositoryConnector.performQuery()` method.

  - MytrackerConnectorUi.getQueryWizard() must return a Wizard instance
    (or `null` if queries are not supported)
      - Return an instance of RepositoryQueryWizard that and a page that
        extends AbstractRepositoryQueryPage
  - `AbstractRepositoryQueryPage`
      - Override createControl to create your widgets
  - In applyTo store connector query properties using
    `IRepositoryQuery.setAttribute()`

When the wizard is completed MyTrackerConnector.performQuery in your
connector will be triggered. Fetch all matching tasks and call
`resultCollector.accept(taskData)` for each. Implement
MyTrackerConnector.hasTaskChaned and
MyTrackerConnector.updateTaskFromTaskData to update tasks in the task
list from the received query results.

## Task editor

**What is required to add an editor for my connector?**

Each connector must supply an editor for their task type unless they are
displaying their task via a web page. A simple yet full featured editor
can be made easily:

1\) Create a MyTaskEditor class that extends AbstractTaskEditorPage. For
an example of how simple the editor code can be see the
[TracTaskEditorPage](http://dev.eclipse.org/viewcvs/index.cgi/org.eclipse.mylyn/org.eclipse.mylyn.trac.ui/src/org/eclipse/mylyn/internal/trac/ui/editor/TracTaskEditorPage.java?root=Tools_Project&view=markup).

2\) Create a page factory specific to your task type which extends
AbstractTaskEditorPageFactory To continue with the Trac connector as an
example see the
[TracTaskEditorPageFactory](http://dev.eclipse.org/viewcvs/index.cgi/org.eclipse.mylyn/org.eclipse.mylyn.trac.ui/src/org/eclipse/mylyn/internal/trac/ui/editor/TracTaskEditorPageFactory.java?root=Tools_Project&view=markup)

The factory you are building will be used by TaskEditor, a multi page
editor), to load your particular editor and display it along with the
other pages such as the context page. The TracTaskEditorPageFactory also
shows how to return a web page as an editor in order to display the task
as a web resource using a BrowserFormPage.

3\) Declare your page factory in your plugin.xml using the
*org.eclipse.mylyn.tasks.ui.editors* extension point. Here is the
corresponding definition for TracTaskEditorPageFactory which is found in
the trac.ui plugin.xml:

``` xml
   <extension
         point="org.eclipse.mylyn.tasks.ui.editors">
      <pageFactory
            class="org.eclipse.mylyn.internal.trac.ui.editor.TracTaskEditorPageFactory"
            id="org.eclipse.mylyn.trac.ui.pageFactory">
      </pageFactory>
   </extension>
```

**Customizing existing connector editors**

It is possible to contribute additional pages to existing editors using
the extension point described above.

In addition, existing editors is via a contribution to the popup menu
and sections can be contributed through this extension point:

``` xml
 <extension
       point="org.eclipse.mylyn.tasks.ui.taskEditorPageContribution">
    <repositoryPart
          class="org.eclipse.mylyn.tasks.ui.MyTaskEditorPart"
          id="org.eclipse.mylyn.tasks.ui.repositoryPart"
          path="additions">
    </repositoryPart>
 </extension>
```

**Showing custom attributes via TaskEditorAttributePart**

Task editor based on AbstractTaskEditorPage class consists of parts
(displayed as sections of editor in the UI). Mylyn comes with several
existing parts (subclasses of AbstractTaskEditorPart):
TaskEditorAttributePart, TaskEditorCommentPart, ... Each part is
responsible for showing and editing of subset of task.

TaskEditorAttributePart will display all "visible" task attributes it
finds. If attribute is read-only, it is displayed in non-editable
widget. Here is sample code which creates attribute be used by
TaskEditorAttributePart:

``` java
TaskAttribute createAttribute(TaskData data, String keyID, String attrType, boolean isVisible, String label, boolean readOnly) {
       TaskAttribute attr = data.getRoot().createAttribute(keyID);

       TaskAttributeMetaData metaData = attr.getMetaData();
       metaData.setType(attrType);
       metaData.setKind(isVisible ? TaskAttribute.KIND_DEFAULT : null);
       metaData.setLabel(label);
       metaData.setReadOnly(readOnly);

       return attr;
}
```

where

  - **keyID** is any unique ID string.
  - **attrType** can be one of TaskAttribute.TYPE_\* constants, or your
    custom constant. Type determines widget (subclasses of
    AbstractAttributeEditor) to be created. You can have custom editors
    too (in this case you'll need to use custom AttributeEditorFactory,
    and return it from your AbstractTaskEditorPage subclass).
  - **isVisible** determines whether TaskEditorAttributePart should
    display this attribute or not. Invisible attributes are useful for
    storing data in a task which you don't want to present to user, or
    which you want to present in some other way (or in other part)
  - **readOnly** -- determines if user can edit this attribute via UI.

''' Displaying comments with TaskEditorCommentPart '''

The task editor part created by TaskEditorCommentPart can be used to
display a list comments associated with a task. This part is included by
default in your task editor page by the behavior defined in
AbstractTaskEditorPage. Upon initialization, it selects a subset of the
current task's attributes for display as comments based on its own
criteria.

The easiest way to create attributes that it will select is to use the
TaskCommentMapper class. Here is an example of how you might add comment
attributes to a TaskData object. These attributes will automatically be
displayed by the task comment editor part.

``` java

public void updateTaskDataWithComments(
    TaskRepository taskRepository,
    TaskData taskData,
    YourNativeTask nativeTask   // a representation of a task in the database you're connecting to
{
    // Initialize a counter, since you want to number each task, since the editor part likes to display
    // them with numbers.
    int count = 0;

    // Loop through the comments in your native database.
    for (YourNativeComment nativeComment : nativeTask.getComments()) {
        TaskCommentMapper mapper = new TaskCommentMapper();  // Create a new one each time, to be safe.
        // Set properties and text associated with this comment.
        mapper.setAuthor(taskRepository.createPerson(nativeComment.getTaskCreator().getName()));
        mapper.setCreationDate(nativeComment.getCreationDate());
        mapper.setText(nativeComment.getBodyText());
    mapper.setNumber(count);

        // Create, in the task data object, a new attribute that will hold this comment.
    TaskAttribute attribute = taskData.getRoot().createAttribute(TaskAttribute.PREFIX_COMMENT + count);

        // Ask the mapper to copy the properties and text into the new attribute.
    mapper.applyTo(attribute);

    count++;
    }
}
```

## Offline data handling

Mylyn's offline data handling supports a number of features including:
incoming/outgoing notification, rich offline editing, instant open of
issues. All of these capabilities can be extended to your connector
through implementation of a few interfaces. In general, the bulk of the
information related to a task (i.e. long description, comments, and
various attributes) are held in another class, `TaskData`. The framework
manages the `TaskData` on behalf of the connectors. For offline support
to work, each connector is responsible for retrieving and sending task
data to and from the remote repository. Lightweight `ITask` objects
which are updated from `TaskData` hold the information necessary for
display in Mylyn's task list but little more.

To add offline support for your connector:

  - Extend `AbstractTaskDataHandler` (i.e. MyConnectorTaskDataHandler) -
    the interface through which `TaskData` is sent to (and received
    from) your repository. Behind this interface you will do the
    marshaling necessary to present your native repository data in
    `RepositoryTaskData` form.
      - At minimum you'll probably want to override these methods:
          - initializeTaskData(TaskRepository, TaskData, ITaskMapping,
            IProgressMonitor): create the attributes you want editable
            from the Task Editor.
          - postTaskData(TaskRepository, TaskData, Set<TaskAttribute>,
            IProgressMonitor): callback from
            [SubmitTaskJob](http://grepcode.com/file/repository.grepcode.com/java/eclipse.org/3.6.1/org.eclipse.mylyn.tasks/core/3.4.1/org/eclipse/mylyn/internal/tasks/core/sync/SubmitTaskJob.java#SubmitTaskJob).
            You can save your edited task back to the repository here.
  - Return your connector's data handler in
    `MyRepositoryConnector.getTaskDataHandler()` method.
  - Implement `MyRepositoryConnector.updateTaskFromTaskData()` - this is
    where you populate `ITask` object with information from the
    `TaskData`
  - Optionally extend `TaskAttributeFactory` (i.e.
    MyConnectorAttributeFactory) - this class does the work of mapping
    your repository's native attribute ids to ids understood by Mylyn
    (along with a few other utility functions) (see
    BugzillaAttributeFactory as an example)

Related classes:

  - TaskCommentMapper for managing comments on TaskData
  - TaskAttachmentMapper for managing attachments on TaskData
  - TaskOperation for creating actions that operate on TaskData

## Accessing the Task List *(Mylyn 2.x)*

Get the Task List:

` TaskList taskList = TasksUiPlugin.getTaskListManager().getTaskList();`

Retrieve all categories:

` Set`<AbstractTaskCategory>` categories = taskList.getCategories();`

Retrieve all queries:

` Set`<AbstractRepositoryQuery>` queries = taskList.getQueries();`

Call getChildren() on these returned types to get all `AbstractTask`
objects contained within.

## Deployment tips *(Eclipse 3.3 and earlier)*

  - Use Plug-in Editor to open META-INF/MANIFEST.MF
  - From Overview page click on Export Wizard and generate .jar for both
    core and ui plugin.
  - You have to generate the plugin jars with appropriate Eclipse
    version, for example check out your connector plugins for Eclipse
    3.2.1 and generate 3.2 version of connector plugins, then checkout
    your connector plugins for Eclipse 3.3 and generate 3.3 version of
    connector plugins.
  - Exit Eclipse copy the jars into eclipse/plugins directory and start
    eclipse with -clean option the first time
  - Open Task Repositories view and try to add new repository with your
    connector
  - If you do not see your connector, check Error Logs view for any
    errors

Note, that generating valid version of the plugins can be frustrating
experience. Be patient and explore Error Logs view if your connector
does not appear in the Task Repositories view Add Task Repository
dialog.

Here are few things to check if your connector fails to appear in the
Add Task Repository dialog (usually the error is ClassNotFound
exception):

  - Make sure you have . (dot) in the bin.includes, source.includes of
    your build.properties file of both connector plugins
  - Make sure you have . (dot) in the Bundle-ClassPath property of the
    META-INF/MANIFEST.MF file of both connector plugins
  - Check the generated .jar files with unzip tool (7-Zip and others) to
    make sure that your libraries and classes are present in the jar
  - Do not rely on Eclipse Plugin Manifest Editor, check the both
    build.properties and META-INF/MANIFEST.MF in Text Editor
  - Start Eclipse with -clean option the first time after you deploy
    your connector.

## Duplicate Detectors

Mylyn provides an extension point that allows contributors to create
duplicate detectors. Each duplicate detector can use its own algorithm
to determine if any similar bugs exist in the bug repository. Duplicate
detection can happen in one of two ways:

1.  Client-side: detectors that can rely entirely on the task
    repository's search facilities to issue a query that returns a set
    of potentially relevant tasks, then do client-side analysis of the
    contents of the results. For example, a Java stack trace detector
    can search for all tasks that refer to a type name, and then use
    heuristics to identify and rank the most relevant ones (e.g. based
    on where it appears in the stack trace).
2.  Server-side: some detectors require access to the all of the task
    data in the repository and are best implemented server-side. For
    example, a natural language matcher that checks every comment would
    be too cumbersome and could require too much network traffic to
    implement client-side. Such detectors can be integrated with Mylyn
    via a web service API.

Refer to
`org.eclipse.mylyn.internal.tasks.ui.search.StackTraceDuplicateDetector`
can be used as a reference implementation.

When you create a duplicate detector, you need to specify the extension
in the plugin.xml file. Below is the entry from the
org.eclipse.mylyn.tasks.ui plugin.xml file, as an example:

``` xml
     <extension
          point="org.eclipse.mylyn.tasks.ui.duplicateDetectors">
       <detector
             class="org.eclipse.mylyn.internal.tasks.ui.search.StackTraceDuplicateDetector"
             name="Stack Trace">
       </detector>
    </extension>
```

The class attribute of the detector extension is required and must be a
subclass of org.eclipse.mylyn.tasks.core.AbstractDuplicateDetector. The
name is also required and must be a string. The name attribute will be
displayed on the New Repository Task editor, so make sure it is short
but descriptive. There is also an optional kind attribute - this
attribute allows you to specify what kind of repository your duplicate
detector works with. If you leave the kind attribute blank, your
duplicate detector may be displayed in the duplicate detector list for
every repository (i.e., users could choose to use your detector
regardless of the type of repository that they are using)

The default behaviour is for every task editor page that uses
TaskEditorDescriptionPart to display all of the duplicate detectors that
are available.

To create a duplicate detector you should:

  - Create your duplicate detector class that subclasses
    org.eclipse.mylyn.tasks.ui.AbstractDuplicateDetector
  - Within your duplicate detector class, implement getDuplicatesQuery
  - Specify the extension (as shown above) in the plugin.xml file in the
    same plugin as your duplicate detector class and your subclass of
    SearchHitCollector.

## Adding presentations to the Task List view

Mylyn provides an extension point to contribute custom presentations for
the Task List view. Contributed presentations will appear in the drop
down list on the Task List toolbar. Each presentation must specify a
means of creating a content provider for a particular instance of the
`TaskListView`, as specified by the `AbstractTaskListPresentation`, a
subtype of which must be provided.

`     `<presentation
            class="org.eclipse.mylyn.internal.tasks.ui.CategorizedPresentation"
            icon="icons/etool16/category.gif"
            id="org.eclipse.mylyn.tasks.ui.categorized"
            name="Categorized"/>

Content provider implementation should be a subclass of the
`AbstractTaskListContentProvider` or one of its subclasses.

# Context API

Mylyn provides a task-focused interface for Eclipse, which affects the
way that view filtering, expansion and decoration work. This boils down
to viewers and editors showing only the structural information relevant
to a task (e.g. Bugzilla report) instead of all of the underlying
information available in the corresponding content provider(s).

The following resources provide an overview of the facilities and their
impact on viewers and a summary is provided below.

  - A user-centric overview of the UI is in the tutorial article:
    <https://web.archive.org/web/20110820221743/http://www.ibm.com/developerworks/java/library/j-mylyn2/>
  - Detailed description of the facilities is in the PhD theis:
    <http://kerstens.org/mik/publications/2007-01-mik-thesis.pdf> (pages
    39-40)

The following task-focused interface mechanisms affect views and
viewers:

  - **Filtering**: uninteresting elements are filtered from the view by
    an `InterestFilter` which is applied when the view is focused.
    Applying the interest filter causes all other viewer filters to be
    removed, since the `InterestFilter` hides all elements by default.
    Filtering requires the view to be lazily refreshed based on task
    context model changes in addition to content changes.
  - **Expansion and linking**: focused viewers always have their nodes
    expanded by default and are always linked to the editor, since they
    are much less likely to show a scrollbar.
  - **Decoration**: all focused viewers use a lightweight platform
    decorator to indicate interest level (e.g. gray is uninteresting and
    bold font is a very interesting element).
  - **Ranking**: sort order can be changed to bring the most interesting
    elements to the top (e.g. in a table viewer or a content assist
    list)

The following task-focused mechanisms work on editors:

  - **Folding**: uninteresting elements are automatically folded away in
    textual editors.
  - **Filtering**: uninteresting elements are automatically filtered
    from graphical editors.

The following task-focused interface mechanisms affect the workbench:

  - **View management**: views are automatically focused (i.e.
    facilities listed above are applied) when a task is activated.
  - **Editor management**: open editors are automatically matched to the
    task context (e.g. all closed when a task is deactivated, all
    restored when reactivated, if an element decays in interest the
    editor auto closes).
  - **Perspective management**: perspectives are automatically
    associated with tasks and activated when tasks are switched.

## Bridges

Mylyn relies on [Bridges](Mylyn_Architecture "wikilink") to integrate
the context model with the structure and UI features of domain-specific
tools. There are two kinds of bridges:

  - Structure Bridge: maps domain-specific elements and relationships to
    the generic *handleIdentifier*s understood by the structure model.
      - Extension point is: `org.eclipse.mylyn.context.core.bridges:
        structureBridge`
  - UI Bridges: integrate Mylyn facilities, such as the *Focus on Active
    Task* button, with editors and views.
      - Extension point is: `"org.eclipse.mylyn.context.ui.bridges:
        uiBridge`

The core set of Bridges supports the Eclipse SDK:

  - Resources (i.e. files and folders)
  - Java and JUnit
  - PDE and Ant XML editing

**How it works:** Generic workbench UI monitoring facilities
(org.eclipse.mylyn.monitor), translate interaction with domain-specific
elements (e.g. Java methods) into an interaction history. The context
manager (org.eclipse.mylyn.context.core) relies on a structure bridge to
create a context model from these elements and from the relations
between the elements. The structure bridge is also used by the Focused
UI facilities to map elements that show in views and editors to the
context model, in order to determine their interest rank. This ranking
is then used for filtering and folding elements.

## Resource Bridge

The generic `ResourceStructureBridge` provides a basic level of
interoperability with other tools that use files (e.g. .php, .cpp), and
enables Mylyn filtering to work for generic views that shows those files
(i.e. the *Project Explorer*, *Navigator*) and any corresponding markers
(i.e. the *Problems* and *Tasks* views). This is only the most basic
context model integration, and does not offer the benefits of a
specialized structure bridge, such as making declarations part of the
context and providing Active Search facilities. Without a bridge Mylyn
also can not be applied to tool-specific views.

To extend Mylyn to other kinds of structure and tools create a new
structure bridge and model it on the one in `org.eclipse.mylyn.java`.

## Excluding Elements

If an element should not participate in the task context, but can be
interacted with by the user, the
`AbstractContextStructureBridge.getHandleIdentifier(Object)` method
should return null for the element. For example, in the case of Java
null could be returned for implicitly uninteresting elements such as
import statements.

## Excluding Resources

Resource patterns can be excluded manually by the user via the *Mylyn
-\> Resources* preference page. To add defaults to this page use the
following extension point:

`   `<extension
         point="org.eclipse.mylyn.resources.ui.changeMonitoring">
`               `<exclude
                pattern=".*"/>
`   `</extension>

Note that file URIs are supported (e.g. <file:/foo/bar>). Resource
patterns can be programatically added via:

` ResourcesUiPreferenceInitializeraddForcedExclusionPattern(..)`

## Task-Focused UI

**Editor Management**

To exclude an editor from being automatically closed when a task is
deactivated have the editor extend the `IContextAwareEditor` class,
e.g.:

` public class MyEditor extends FormEditor implements IContextAwareEditor {`
`    public boolean canClose() {`
`        retrun false;`
`    }`
`    ...`
` }`

**Viewer Management**

When existing viewers are focused, the Context UI does not affect their
contents in any way, but instead affects the visibility of elements and
the refresh and expansion policy:

  - Adds a ViewerFilter (class is
    org.eclipse.mylyn.context.ui.InterestFilter) that determines
    visibility of elements based on whether or not they are in the task
    context.
  - Manages the refresh of viewers and refresh+expansion of tree viewers
    to ensure that when the context model changes the viewer is
    refreshed.

**Contributing Focus Actions**

<code>

<extension point="org.eclipse.ui.viewActions">` `
`  `<viewContribution id="org.eclipse.mylyn.ui.projectexplorer.filter" targetID="org.eclipse.ui.navigator.ProjectExplorer">
`    `<action
           class="org.eclipse.mylyn.internal.ide.ui.actions.FocusProjectExplorerAction"
           disabledIcon="icons/elcl16/focus-disabled.gif"
           enablesFor="*"
           icon="icons/elcl16/focus.gif"
           id="org.eclipse.mylyn.ide.ui.actions.focus.projectExplorer"
           label="Focus on Active Task"
           menubarPath="mylyn"
           style="toggle"
           toolbarPath="mylyn"
           tooltip="Focus on Active Task (Alt+click to reveal filtered elements)">
`       `<enablement>
`          `<systemProperty
                 name="org.eclipse.mylyn.context.core.context.active"
                 value="true">
`          `</systemProperty>
`       `</enablement>` `
`    `</action>` `
`  `</viewContribution>` `
</extension>

</code>

If the contributing bundle is not guaranteed to be activated on task
activation it may also be necessary to implement a context startup
extension to ensure correct enablement of the focus action.

## Processing interaction

The context model is a transformation of an interaction history. The
only way to change or affect the model is to issue `InteractionEvent`s.
For an example of how to translate interaction with UI facilities such
as views and editors, see:

  - `AbstractUserInterctionMonitor`
  - `JavaEditingMonitor`

*' Direct manipulation*'

The model can be mainpulated directly by issuing special kinds of
`InteractionEvent`s. For an example see:

  - `AbstractInterestManipulationAction` and subclasses.

# Team API

Mylyn provides several key features that facilitate working with version
control systems.

## Change set management

Automatic change set management (see [Mylyn User Guide\#Team
Support](Mylyn_User_Guide#Team_Support "wikilink")) creates change sets
for tasks on the user's behalf, and enables automatic commit messages.
There are two ways to implement this support.

**Relying on the Platform/Team ActiveChangeSetManager**

This is the way that the current CVS and SVN providers do it, and
involves providing the following extension point as shown with this
example of how it works for CVS:

` `<extension point="org.eclipse.mylyn.team.changeSets">
`   `<activeChangeSetProvider
       class="org.eclipse.mylyn.internal.team.ccvs.CvsActiveChangeSetProvider"/>
` `</extension>

Where the `CvsActiveChangeSetProvider` is a subclass of
`AbstractActiveChangeSetProvider`.

This will result in Mylyn's
`org.eclipse.mylyn.internal.team.ContextActiveChangeSetManager` bridging
between the Platform/Team change sets and the task context model.

> *Note that the change set manager must be a subtype of
> `org.eclipse.team.internal.core.subscribers.ActiveChangeSetManager`.
> 'This means relying on an internal class, and as such is **not
> guaranteed to be backwards compatible**. Consider voting to make this
> class API for Eclipse 3.3
> ([bug 116084](https://bugs.eclipse.org/bugs/show_bug.cgi?id=116084)).*

**Re-implementing change set management**

It is possible to provide an alternate change set bridge in order to
avoid extending the internal class as above, or if a different change
set management mechanism is used. Do this via the
`contextChangeSetManager` extension point, and as an example
implementation you can use `ContextActiveChangeSetManager` which
provides the bridging for the Platform/Team change sets described above.

` `<extension point="org.eclipse.mylyn.team.changeSets">
`   `<contextChangeSetManager
       class="com.example.team.ui.ActiveChangeSetManager"/>
` `</extension>

## Mapping from comments to tasks

The *Open Corresponding Task* action allows the user to navigate from
change sets in "Synchronize" view or from *History* view to the task
(e.g. bug report).

To support for *Open Corresponding Task* action in "Synchronize" and
"History" views, the team provider should register `IAdapterFactory`
that should adapt to `ILinkedTaskInfo`. This way, proprietary artifacts
shown in these views won't have hard dependency on Mylyn's classes. If
hard dependency on Mylyn classes is acceptable, you can also make your
artifacts implement `IAdaptable` interface and directly adapt to
`ILinkedTaskInfo`.

> ''This factory should return adapter as quick as possible to not slow
> down the UI because adapter will be queried and created for nearly
> every popup menu.

## Mapping from projects to Task Repositories

Mylyn allows contribution of a project link provider which maps from
workspace projects to task repositories.
`ProjectPreferencesLinkProvider` is contributed by the
`org.eclipse.mylyn.tasks.ui` plugin and stores the required information
in the project settings. Custom link providers can use metadata from
other sources, such as version control system (i.e. Subversion
properties) or Maven POM. Use
`org.eclipse.mylyn.tasks.ui.projectLinkProviders` extension point to
register link provider. For example:

` `<extension
        point="org.eclipse.mylyn.tasks.ui.projectLinkProviders">
`    `<linkProvider
           class="org.tigris.subversion.subclipse.mylyn.SubclipseTaskRepositoryLinkProvider"
           id="org.tigris.subversion.subclipse.mylyn.taskRepositoryLinkProvider"
           name="Subclipse Link Provider"
           order="100">
`    `</linkProvider>
` `</extension>

Important attribute is *order*. Recommended values are:

  - 1000 for generic or custom metadata
  - 100 for metadata from the version control systems
  - 10 for metadata from the project or build management systems

Implementation class should extend
`org.eclipse.mylyn.tasks.ui.AbstractTaskRepositoryLinkProvider` and
provide at least `getTaskRepository()` method.

## Distributing your extension

We recommend using one of the following options:

  - Have a separate plug-in for the Mylyn integration and create an
    optional feature with dependencies on Mylyn's features
  - Make Mylyn an optional dependency of your plug-in. This can be done
    via

`Require-Bundle: org.eclipse.mylyn.team;resolution:=optional`

If you would like your update site linked from the Mylyn update site
please send an email to the mylyn-dev mailing list.

# Monitor API

## Resources

  - The [Using task context to improve programmer
    productivity](http://www.eclipse.org/mylyn/publications/2006-11-mylar-fse.pdf)
    paper discusses interaction monitoring and interaction events.
  - The [How are Java software developers using the Eclipse
    IDE?](http://kerstens.org/mik/publications/mylar-ieee2006.pdf)
    article describes a user study done with the monitor.

## Examples

The *UI Usage Report* wizard can be used as an example of how to report
on usage activity. The main class for this is currently
`UsageSummaryReportEditorPart` and the project of interest is
`org.eclipse.mylyn.monitor.usage`

For a user study example
[checkout](Mylyn_Contributor_Reference#Checkout "wikilink"):
`sandbox/org.eclipse.mylyn.examples.monitor.study`

Note that this project relies on upload scripts that are currently
disabled. Send questions about reusing it to mylyn-dev.

## Overview

The Mylyn Monitor is a separately installable component that collects
information about a user’s activity in Eclipse. Clients of the monitor
include the Context UI, which transforms interaction into a
degree-of-interest model, and user study plug-ins, which can report on
Eclipse usage trends. The `org.eclipse.mylyn.monitor` plug-in is
structured to accept listeners to different Eclipse events, currently
including preference changes, perspective changes, window events,
selections, commands invoked through menus or key bindings and URLs
viewed through the embedded Eclipse browser. The `InteractionEvent`
class used by the monitor encapsulates a user or tool interaction.

The `org.eclipse.mylyn.monitor.usage` plug-in supports the transparent
capture of these events into a local file and the upload of these events
to an http server. The uploading mechanism includes functionality to
track anonymous IDs for users, to obfuscate the handles of targets of
selections and other such user data that may be collected, and to prompt
the user to view and send the log to an http server. The Monitor also
detects and reports in the trace when there has been a period of
inactivity with Eclipse. Extension points in
`org.eclipse.mylyn.monitor.usage` allow user study plug-ins to use the
monitoring facilities. The Usage Monitor manages the size of traces
produced by the Mylyn Monitor through compression, using a zipped format
that significantly reduces the size of the files. The repetitiveness of
user activity typically yields compression ratios over 95%, with a month
of typical full-time programming activity resulting in an approximately
1MB zip.

To help with the analysis of traces collected with the Mylyn Monitor,
the `org.eclipse.mylyn.monitor.reports` plug-in provides infrastructure
for collecting and summarizing data across one or more traces. This
reporting package provides an API to process records for a user across
one or more trace files in a chronological order.

## Interaction events

### Streams

Mylyn currently has two consumers of the user's interaction event
streams issued by the monitor:

  - Task Context model: all events that contribute to the
    degree-of-interest of elements are consumed, and externalized to
    zipped XML files in the `.metadata/.mylyn/contexts` directory.
    Currently the interaction event kinds included are *selection*,
    *edit*, *propagation*, *prediction*.
  - Interaction event logger: the logger in `..mylyn.monitor.usage`
    consumes all events and appends them to
    `.metadata/.mylyn/monitor-history.xml` if logging is enabled in the
    *Monitor* preference page. This stream includes additional events
    that are monitored, such as preference changes.

### Attributes

Note that if events are collapsed (i.e. multiple events are combined
into a single one) the *EndDate* and *Interest* fields capture the
aggregate information. These fields should not be used otherwise, since
interaction events should be considered immutable and should not
directly represent interest.

  - *Kind*: determines the type of interaction that took place (see
    listing below)
  - *OriginId*: the UI affordance that the event was issued from
  - *StructureKind*: the content type of the elementbeing interacted
    with
  - *StructureHandle*: a unique identifier for the element being
    interacted with
  - *Navigation*: an identifier for the kind of relation that corrsponds
    to the navigation to this element
  - *StartDate*: time stamp for the occurence of the event
  - *EndDate*: if an aggregate event, time stamp of the last occurrence
  - *Delta*: additional information relevant to interaction monitoring
  - *Interest*: if an aggregate event, amount of interest of all
    contained events (note: may be removed since interest should not be
    stored on events)

### Event Kinds

Depending on which stream you are using, the interaction events may
contain non user-initiated interactions such as interest propagations.
In general, *selection*, *edit* and *command* events are the ones that
initiate from the user, while *propagation* and *prediction* events
originate from a tool.

''NOTE: refer to the `InteractionEvent` Javadoc for the most up-to-date
documentation of kinds.

  - *Selection*: user selection of elements, issued by the Eclipse
    post-selection mechanism
  - *Edit*: edit events that are created by text selections in the
    editor
  - *Command*: commands and actions invoked via buttons, menus, and
    keyboard shortcuts
  - *Preference*: workbench preference changes
  - *Prediction*: elements determined relevant by Active Search
  - *Propagation*: elements determined to be structurally related, such
    as the parent chain in a containment hierarchy
  - *Manipulation*: direct manipulation of interest via "Mark as
    Landmark" and "Mark Less Interesting"
  - *Attention*: interaction with a task, used for the meta-context

### Extensibility

Interested developers can provide notification of other events by
generating their own `InteractionEvents`, and injected using
`MonitorUiPlugin.getDefault().notifyInteractionObserved(InteractionEvent)`.
`InteractionEvent`s are assumed to be <em>immutable</em> and thus their
fields are defined as string instances. The "delta" field can be used
for adding additional information to an event. As loggers of
`InteractionEvent`s are to be content-agnostic and transparently encode
and decode these fields, more complicated information may be provided as
an XML-encoded string in the delta field. The Apache Ant project's
`org.apache.tools.ant.filters.StringInputStream` class may be helpful
for processing such fields afterwards.

## Activity Meta-Context

Overview of meta context events.

<table border="1" width="100%">

<tr align=center>

<td>

`       Description`

</td>

<td>

Kind

</td>

<td>

OriginId

</td>

<td>

StructureKind

</td>

<td>

StructureHandle

</td>

<td>

Delta

</td>

</tr>

<tr>

<td>

Task activation

</td>

<td>

COMMAND

</td>

<td>

org.eclipse.ui.workbench

</td>

<td>

activation

</td>

<td>

<task handle>


(e.g. <https://bugs.eclipse.or/bugs-89806>)

</td>

<td>

activated
deactivated

</td>

</tr>

<tr>

<td>

Task activity timing

</td>

<td>

ATTENTION

</td>

<td>

org.eclipse.ui.workbench
os
user (for manipulations)

</td>

<td>

timing

</td>

<td>

<active task handle> (null if no active task)
(e.g. <https://bugs.eclipse.or/bugs-89806>)

</td>

<td>

added

</td>

</tr>

<tr>

<td>

Workbench lifecycle events

</td>

<td>

ATTENTION

</td>

<td>

org.eclipse.ui.workbench
os
user (for manipulations)

</td>

<td>

lifecycle

</td>

<td>

<product id>

</td>

<td>

started
stopped

</td>

</tr>

</table>

## Uploading interaction histories

The current code relies on CGI scripts that are not CVS, but that are
deprecated and will be replaced by Servlets. If you would like a copy of
the CGI scripts please email mylyn-dev.

# Headless and standalone use

The tasks core API in org.eclipse.mylyn.tasks.core allows generic access
to supported bug/task/ticket/issue trackers. In order to connect to a
specific repository a connector implementation that supports the tasks
core API is required.

## Bugzilla API

The Bugzilla connector core implementation is available in
org.eclipse.mylyn.bugzilla.core. The provisional Bugzilla API can be
used independently of the Eclipse Workbench and Mylyn UI facilities as a
Java API to Bugzilla. Also see the [Mylyn
Architecture](Mylyn_Architecture "wikilink") document.

A good way to get started is to run the test case as a JUnit test and
work from
`org.eclipse.mylyn.bugzilla.tests/src/org.eclipse.mylyn.bugzilla.tests.headless`.

  - Mylyn dependencies
      - org.eclipse.mylyn.bugzilla.core
      - org.eclipse.mylyn.commons.core
      - org.eclipse.mylyn.commons.net
      - org.eclipse.mylyn.tasks.core

<!-- end list -->

  - Eclipse dependencies (need to be on classpath but the platform does
    not need to be running)
      - org.eclipse.core.runtime
      - org.eclipse.core.net
      - org.eclipse.equinox.common
      - org.eclipse.osgi
      - org.eclipse.equinox.security
      - org.eclipse.update.core
      - org.eclipse.core.jobs
      - ...

<!-- end list -->

  - Library dependencies
      - org.apache.commons.codec
      - org.apache.commons.httpclient
      - org.apache.commons.lang
      - org.apache.commons.logging
      - org.apache.xmlrpc

### Quick Example

This project demonstrates how to connect to a Bugzilla repository:

[Bugzilla Standalone
Example](http://dev.eclipse.org/viewcvs/index.cgi/org.eclipse.mylyn.incubator/org.eclipse.mylyn.examples.bugzilla/src/org/eclipse/mylyn/internal/examples/bugzilla/Main.java?root=Mylyn_Project&view=markup)

Creating a standalone distribution:

  - Save the [team project
    set](http://www.eclipse.org/mylyn/doc/dev/mylyn-standalone.psf), and
    then use *File \> Import \> Team Project Set* in Eclipse to import
    the source code. Use username "anonymous" and an empty password.
  - Use *File \> Export \> Runnable JAR file* to create a jar file.
    Select *Bugzilla Example* as the launch configuration and enter a
    filename for the export destination. The export wizard will
    automatically package all required dependencies based on a Run
    configuration into a single JAR file that can be run without
    Eclipse.

The wizard may display an error *JAR creation failed. See details for
additional information.* and lists compile warnings and duplicate
entries in the details section. These warnings can be ignored and will
not affect running the JAR file as a standalone application.

You can invoke the standalone example by running `java -jar
example.jar`.

## Context API (org.eclipse.mylyn.context.core)

When Mylyn is running within the full eclipse platform, the
org.eclipse.mylyn.tasks.ui plugin specifies where the contexts should be
stored. When running without the org.eclipse.mylyn.tasks.ui plugin, you
must specify this location yourself.

In plugin.xml for your plugin:

`   `<extension point="org.eclipse.mylyn.context.core.bridges">
`       `<contextStore class="com.example.HardCodedContextStore"/>
`   `</extension>

com.example.HardCodedContextStore must extend
org.eclipse.mylyn.context.core.AbstractContextStore and implement
getRootDirectory().

[Category:Mylyn](Category:Mylyn "wikilink")