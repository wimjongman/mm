[Mylyn/User Guide](Mylyn/User_Guide "wikilink"), [Mylyn
Home](http://eclipse.org/mylyn), [Log in to
edit](http://wiki.eclipse.org/index.php?title=Special:Userlogin&returnto=Special:Userlogout)

For instructions on using Mylyn, see the [Mylyn/User
Guide](Mylyn/User_Guide "wikilink"). For instructions on developing and
contributing to Mylyn, see the [Mylyn/Contributor
Reference](Mylyn/Contributor_Reference "wikilink").

# What is Mylyn?

For **tutorials and articles on using Mylyn** refer to the **[Get
Started](http://www.eclipse.org/mylyn/start/)** page.

Mylyn is a task-focused interface for Eclipse that makes working with
very large workspaces as easy as working with small ones. Mylyn extends
Eclipse with mechanisms for keeping track of the tasks that you work on.
A task is defined as any unit of work that you want to recall or share
with others, such as a bug reported by a user or a note to yourself
about improving a feature. You can store tasks locally in your
workspace, or they can come from one or more task repositories. To
connect to a task repository, you must have a connector that supports
that repository. (A task repository is a bug/ticket/issue tracker such
as Bugzilla, Trac, JIRA, and
[others](http://wiki.eclipse.org/index.php/Mylyn/Extensions)).

Once your tasks are integrated, Mylyn monitors your work activity on
those tasks to identify information relevant to the task-at-hand. Mylyn
monitors Eclipse and captures your interaction in a task context. System
artifacts such as files, types, methods, and fields get assigned a
degree-of-interest based on how recently and frequently you interact
with them. This results in uninteresting elements being filtered from
view within Eclipse, allowing you to focus in on what is important. From
this, Mylyn creates a task context, which is the set of all artifacts
related to your task. These can include methods you have edited, APIs
you have referred to, and documents you have browsed. Mylyn uses this
task context to focus the Eclipse UI on interesting information, hide
what's uninteresting, and automatically find what's related. Having the
information you need to get your work done at your fingertips improves
your productivity by reducing the time you spend searching, scrolling,
and navigating. By making task context explicit, Mylyn also facilitates
multitasking, planning, reusing past efforts, and sharing expertise.

# Installation

  - [Mylyn download page](http://eclipse.org/mylyn/dl.php)

As of writing, Mylyn comes bundled with the main EPP distributions
([jee, java, cpp](http://www.eclipse.org/downloads/)). If you wish to
manually install Mylyn there are two methods depending on the version of
Eclipse. Method 1 outlines how to install using the Eclipse 3.4 update
manager. Method 2 below describes how to install Mylyn into Eclipse 3.3
and below using the Update Manager.

### Install - Eclipse 3.4 and later

1.  Select ''Help \> Software Updates...
2.  Select *Available Software* tab
3.  Press the *Add Site...* button
4.  Enter the Mylyn update site url:
    1.  <http://download.eclipse.org/mylyn/releases/latest>
    2.  Additional extension update sites are from [the download
        page](http://www.eclipse.org/mylyn/downloads/)
5.  After pressing *OK* the update site will be available in the sites
    list
6.  Expand the Mylyn update site node and select all components desired
7.  Press the *Install...* button to install Mylyn

## What is the release schedule?

  - Weekly builds: available every Wednesday and on-demand (should be
    used by all Mylyn contributors not self-hosting from CVS [straight
    from
    CVS](http://wiki.eclipse.org/index.php/Mylyn_Contributor_Reference#Self-hosting))
  - Release builds: see the [project
    plan](http://www.eclipse.org/projects/project-plan.php?projectid=tools.mylyn)

## Which sub-projects are included in Mylyn releases?

See the [New & Noteworthy](http://eclipse.org/mylyn/new/).

List of major and release train versions:

<table cellpadding="10">

<th>

Mylyn Version

</th>

<th colspan="7">

Sub-projects

</th>

<tr>

<td>

</td>

<td>

Mylyn Builds

</td>

<td>

Mylyn Commons

</td>

<td>

Mylyn Context

</td>

<td>

Mylyn Docs

</td>

<td>

Mylyn Reviews

</td>

<td>

Mylyn Tasks

</td>

<td>

Mylyn Versions

</td>

</tr>

<tr>

<td>

[3.8](http://www.eclipse.org/projects/project-plan.php?projectid=mylyn)
(Juno)

</td>

<td>

1.0

</td>

<td>

3.8

</td>

<td>

3.8

</td>

<td>

1.7

</td>

<td>

1.0

</td>

<td>

3.8

</td>

<td>

1.0

</td>

</tr>

<tr>

<td>

[3.7](http://eclipse.org/mylyn/doc/plan-3.6.html)

</td>

<td>

0.9

</td>

<td>

3.7

</td>

<td>

3.7

</td>

<td>

1.6

</td>

<td>

0.9

</td>

<td>

3.7

</td>

<td>

0.9

</td>

</tr>

<tr>

<td>

3.6.5 (Indigo SR2)

</td>

<td>

0.8.5

</td>

<td>

3.6.5

</td>

<td>

3.6.5

</td>

<td>

1.5.5

</td>

<td>

</td>

<td>

3.6.5

</td>

<td>

</td>

</tr>

<tr>

<td>

3.6.2 (Indigo SR1)

</td>

<td>

0.8.2

</td>

<td>

3.6.2

</td>

<td>

3.6.2

</td>

<td>

1.5.2

</td>

<td>

</td>

<td>

3.6.2

</td>

<td>

</td>

</tr>

<tr>

<td>

[3.6](http://eclipse.org/mylyn/doc/plan-3.6.html) (Indigo)

</td>

<td>

0.8

</td>

<td>

3.6

</td>

<td>

3.6

</td>

<td>

1.5

</td>

<td>

</td>

<td>

3.6

</td>

<td>

0.8

</td>

</tr>

<tr>

<td>

[3.5](http://eclipse.org/mylyn/doc/plan-3.5.html)

</td>

<td>

0.7

</td>

<td>

3.5

</td>

<td>

3.5

</td>

<td>

1.4

</td>

<td>

</td>

<td>

3.5

</td>

<td>

0.7

</td>

</tr>

<tr>

<td>

3.4.3 (Helios SR2)

</td>

<td>

</td>

<td>

3.4.3

</td>

<td>

3.4.3

</td>

<td>

1.3.2

</td>

<td>

</td>

<td>

3.4.3

</td>

<td>

</td>

</tr>

<tr>

<td>

3.4.2 (Helios SR1)

</td>

<td>

</td>

<td>

3.4.2

</td>

<td>

3.4.2

</td>

<td>

1.3.2

</td>

<td>

</td>

<td>

3.4.2

</td>

<td>

</td>

</tr>

<tr>

<td>

[3.4](http://eclipse.org/mylyn/doc/plan-3.4.html) (Helios)

</td>

<td>

</td>

<td>

3.4

</td>

<td>

3.4

</td>

<td>

1.3

</td>

<td>

</td>

<td>

3.4

</td>

<td>

</td>

</tr>

</table>

## What versions of Eclipse are supported?

See the [download page](http://eclipse.org/mylyn/downloads/).

<table>

<th>

Eclipse Version

</th>

<th>

Mylyn Version

</th>

<tr>

<td>

4.5

</td>

<td>

3.16 and later

</td>

</tr>

<tr>

<td>

4.4

</td>

<td>

3.10 - 3.18

</td>

</tr>

<tr>

<td>

4.3

</td>

<td>

3.10 - 3.16

</td>

</tr>

<tr>

<td>

4.2 (Juno)

</td>

<td>

3.7 - 3.10

</td>

</tr>

<tr>

<td>

4.1

</td>

<td>

Not Supported

</td>

</tr>

<tr>

<td>

4.0

</td>

<td>

Not Supported

</td>

</tr>

<tr>

<td>

3.8

</td>

<td>

3.7 and later

</td>

</tr>

<tr>

<td>

3.7 (Indigo)

</td>

<td>

3.5 - 3.9

</td>

</tr>

<tr>

<td>

3.6 (Helios)

</td>

<td>

3.3 - 3.8

</td>

</tr>

<tr>

<td>

3.5 (Galileo)

</td>

<td>

3.2 - 3.6

</td>

</tr>

<tr>

<td>

3.4 (Ganymede)

</td>

<td>

2.1 - 3.4

</td>

</tr>

<tr>

<td>

3.3

</td>

<td>

2.0 - 3.2

</td>

</tr>

<tr>

<td>

3.2

</td>

<td>

1.0 - 2.0

</td>

</tr>

<tr>

<td>

3.1

</td>

<td>

0.6.0

</td>

</tr>

</table>

Mylyn also relies on a web browser that works with the Standard Widget
Toolkit; Windows and MacOS users are fine, but Linux users might have to
download another browser. See [the SWT Browser
guide](http://www.eclipse.org/swt/faq.php#browserlinux) for which
browsers will work. See [installing on
Linux](Mylyn/FAQ#Installing_on_Linux "wikilink") for instructions.

## Which repositories are supported?

See the [New & Noteworthy](http://eclipse.org/mylyn/new/) for the
current supported repository versions.

#### Mylyn 3.8

  - Eclipse 3.6, 3.7, 3.8, 4.2

<!-- end list -->

  - Bugzilla 3.6, 4.0, 4.2
  - Trac 0.11, 0.12
  - Hudson 2.1.2, 2.2.0
  - Jenkins 1.424.6
  - Gerrit 2.2.2, 2.3

#### Mylyn 3.7

  - Eclipse 3.6, 3.7

<!-- end list -->

  - Bugzilla 3.6, 4.0, 4.2
  - Trac 0.11, 0.12
  - Hudson 2.1.2, 2.2.0
  - Jenkins 1.424.6
  - Gerrit 2.2.1, 2.2.2

#### Mylyn 3.6

  - Eclipse 3.5, 3.6, 3.7

<!-- end list -->

  - Bugzilla 3.0, 3.2, 3.4, 3.6, 4.0
  - Trac 0.10, 0.11, 0.12
  - Hudson 1.367, 2.0, 2.1
  - Jenkins 1.367
  - Gerrit 2.1.5

#### Mylyn 3.5

  - Eclipse 3.5, 3.6

<!-- end list -->

  - Bugzilla 3.0, 3.2, 3.4, 3.6, 4.0
  - Trac 0.10, 0.11, 0.12
  - Hudson 1.367
  - Jenkins 1.367
  - Gerrit 2.1.5

#### Mylyn 3.4

  - Eclipse 3.4, 3.5, 3.6

<!-- end list -->

  - Bugzilla 3.0, 3.2, 3.4, 3.6, 4.0
  - Trac 0.9, 0.10, 0.11, 0.12

## What version of Java is required?

Each Mylyn version has its own specified Java requirements which can be
found on the version's review pages. For example,
[Mylyn 3.19](https://projects.eclipse.org/projects/mylyn/releases/3.19/review)
requires Java 7 or later.

To check the version of the Java virtual machine that Eclipse was
launched with go to *Help → About Eclipse SDK → Configuration Details*
and verify that it meets those requirements.

Mac users should refer to the last comment on
[bug 1163477](https://bugs.eclipse.org/bugs/show_bug.cgi?id=116347#c4)
for instructions on how to change the 1.4 default.

  - If you do not have the required Java version, you can download it
    from [Oracle’s web site](https://java.com/en/download/).
  - If you have more than one VM, you need to specify that Eclipse
    should use the correct JDK VM.

In Unix, set the environment variable `JAVA_HOME` to the root of the JDK
installation and/or set the `PATH` variable to put the JDK executable
directory before any other VM executable directories. For example, under
`bash` in Unix:

`export JAVA_HOME="`*`(location``   ``of``   ``JDK``   ``root)`*`"`
`export PATH=$JAVA_HOME/bin:$PATH`

<b>We do [not
recommend](https://bugs.eclipse.org/bugs/show_bug.cgi?id=140955) using
JDK 1.6 on Eclipse 3.1.</b> (It works fine with Eclipse 3.2 or 3.3.) To
use JDK 1.6 on Eclipse 3.1, you must add the following line to your
`config.ini`file:

`org.osgi.framework.executionenvironment=OSGi/Minimum-1.0,OSGi/Minimum-1.1,JRE-1.1,J2SE-1.2,`
`J2SE-1.3,J2SE-1.4,J2SE-1.5,JavaSE-1.6`

## What version of Mylyn is distributed with the Eclipse downloads?

The [default Eclipse downloads](http://www.eclipse.org/downloads/)
contain the following Mylyn redistributions. Since the redistributed
versions can be missing important bug fixes or feature additions, we
recommend using the [latest version of
Mylyn](http://www.eclipse.org/mylyn/downloads).

  - Eclipse IDE for Java Developers: all of Mylyn except Team
    integration (e.g. automatic change sets) integration. Install the
    Eclipse CVS integration and then install the latest Mylyn build to
    get this component.

<!-- end list -->

  - Eclipse IDE for Java EE Developers: all of Mylyn redistribution,
    install manually

<!-- end list -->

  - Eclipse IDE for C/C++ Developers: no Mylyn redistribution, install
    manually

<!-- end list -->

  - Eclipse for RCP/Plug-in Developers: all of Mylyn redistributed

<!-- end list -->

  - Eclipse Classic: no Mylyn redistribution, install manually

## My tasks or queries disappeared, what do I do?

This happens if Mylyn failed to install. First ensure that you have a
correct install by following the instructions in the next section. After
that, if you still do not see your tasks use the *Task List* view menu →
*Restore Tasks From History…* command (also available via *File → Import
→ Task List*.

## General Installation Troubleshooting

**I’m being asked to restart Eclipse, should I?** Upon installing you
will get a dialog box asking if you would like to restart Eclipse. We
recommend that you select *Yes*.

**I’ve installed Mylyn ; why can’t I see anything different?**

The two most likely possibilities are:

1.  You don’t have any Mylyn views open. Select *Window → Show View →
    Other*, then select *Mylyn* and you should see the available Mylyn
    Views.
2.  If you still don’t see anything, then perhaps you aren’t using the
    required JDK VM. See [configuring
    Java](Mylyn_Installation_Guide#Download_and_configure_Java "wikilink").

**What does “`Root exception: java.lang.UnsupportedClassVersionError:
org/eclipse/mylar/tasklist/MylarTasklistPlugin (Unsupported major.minor
version 49.0)`” mean?**

It probably means that the virtual machine is JDK1.4 or lower. See
[download and configure
Java](Mylyn_Installation_Guide#Download_and_configure_Java "wikilink").

**What does “Could not create Browser page: No more handles
(`java.lang.UnsatisfiedLinkError: …`)” mean?**

It probably means that you are running Linux and don’t have Eclipse and
a Web browser configured to work together. See [installing on
Linux](Mylyn/FAQ#Installing_on_Linux "wikilink").

**What does “Could not create Bugzilla editor input” and
“`java.io.IOException`: SAX2 driver class
`org.apache.xerces.parsers.SAXParser` not found” mean?**

It probably means that you are on MacOS, and for some reason are missing
Xerces from the Mac JDK1.5. You will probably need to add it to your
default classpath. Please refer to and comment on
[bug 144287](https://bugs.eclipse.org/bugs/show_bug.cgi?id=144287) if
you see this problem.

To ensure that you are using the required VM refer to the last comment
on
[bug 1163477](https://bugs.eclipse.org/bugs/show_bug.cgi?id=116347#c4)
for instructions on how to change the 1.4 default.

*' Startup warnings*'

If you see startup errors or warnings such as `BundleException` or
timeout messages restart Eclipse with the `-clean` flag either on the
command line, in your shortcut link, or by temporarily it into the
`eclipse/eclipse.ini` file. These warnings do not cause any bad
behavior, but this bug has been fixed in all Mylyn builds after 2.1. The
warnings have this form:

` !MESSAGE While loading class "org.eclipse.mylar.tasks.ui.TasksUiPlugin", thread "Thread`
` [main,6,main]" timed out waiting (5000ms) for thread "Thread[Worker-3,5,main]" to finish`
` starting bundle "update@plugins/org.eclipse.mylar.tasks.ui_2.0.0.v20070514-1800.jar [809]". `
` To avoid deadlock, thread "Thread[main,6,main]" is proceeding but `
` "org.eclipse.mylar.tasks.ui.TasksUiPlugin" may not be fully initialized.`

## Installation Troubleshooting on Eclipse 3.4 and later

Ensure that all required update sites are enabled under Help \> Software
Updates \> Available Software \> Manage Sites:

  - <http://download.eclipse.org/mylyn/releases/latest>
  - <http://download.eclipse.org/mylyn/incubator/3.13>

Then follow these steps:

1.  Use Help \> Software Update \> Update to ensure that the latest
    version of all features is installed
2.  Install again
3.  If Install fails with a "No repository found containing..." message,
    remove and re-add the update site that hosts the feature for which
    the download is failing
4.  Install again
5.  If the update fails with a "Cannot complete the request..." message,
    uninstall Mylyn and all Mylyn dependencies
6.  Install again

### Why does the installation fail with *No repository found*?

The message indicates that the Eclipse provisioning system P2 has found
meta data to install a plug-in but can not locate an artifact repository
that provides the required downloads. To recover please remove the Mylyn
update sites under *Help → Software Updates… → Available Software →
Manage Sites*. Then re-add the sites which will refresh the meta data
and artifacts available on the update sites.

Also see steps under [\#Installation Troubleshooting on Eclipse 3.4 and
later](#Installation_Troubleshooting_on_Eclipse_3.4_and_later "wikilink").

### Why does update fail with *Cannot complete the request*?

If any of the installed features have unsatisfied dependencies or if
features where previously installed from the extras or incubator update
site P2 may fail with an error similar to the ones below. Try these
steps to recover:

1.  Ensure that the Mylyn for Eclipse 3.4 and Mylyn Extras sites are
    enabled in Software Updates \> Available Software \> Manage Sites
2.  Select Update from Software Updates \> Installed Software
3.  Retry the installation

<!-- end list -->

```
 Cannot complete the request. See the details.
 Mylyn Focused UI (Recommended) is already installed, so an update will be performed instead.
 Mylyn Task List (Required) is already installed, so an update will be performed instead.
 Mylyn Bridge: Eclipse IDE is already installed, so an update will be performed instead.
 Mylyn Bridge: Java Development is already installed, so an update will be performed instead.
 Mylyn Bridge: Plug-in Development is already installed, so an update will be performed instead.
 Mylyn Bridge: Team Support is already installed, so an update will be performed instead.
 Mylyn Connector: Bugzilla is already installed, so an update will be performed instead.
 Cannot find a solution where both Match[requiredCapability: org.eclipse.equinox.p2.iu/org.eclipse.mylyn.monitor.ui/[3.0.3.v20081015-1500 -e3x,3.0.3.v20081015-1500-e3x]] and Match[requiredCapability: org.eclipse.equinox.p2.iu/org.eclipse.mylyn.monitor.ui/[3.0.1.v20080721-2100-e3x,3.0.1.v20080721-2100-e3x]]can be satisfied.
 […]
```

`Cannot find a solution satisfying the following requirements org.eclipse.ui [3.4.2.M20090204-0800].`

Also see steps under [\#Installation Troubleshooting on Eclipse 3.4 and
later](#Installation_Troubleshooting_on_Eclipse_3.4_and_later "wikilink").

## Installation Troubleshooting on Eclipse 3.3 and earlier

''' Update failures '''

First, try running the update again via *Help → Software Updates →
Search for new features…* and ensure that all of the Mylyn features have
been updated.

On Eclipse versions earlier than 3.3 (final) use **only the “Search for
new features…”** option when updating Mylyn. If you use “Search for
updates…” the Update Manager will allow a partial install that can cause
Mylyn to fail to start, and you will need to run update again. See the
*feature configuration problem* section below for details. If you
encounter this problemm consider voting for Platform
[bug 132450](https://bugs.eclipse.org/bugs/show_bug.cgi?id=132450).

If you have **updated your Eclipse 3.3 to an Eclipse 3.4 milestone**,
you will not be able to update the 3.3 copy, because Mylyn has two
separate downloads for Eclipse 3.3 and 3.4. Also, not all of the 3.3
version of Mylyn will work in Eclipse 3.4. Install the latest 3.4
version from: <http://www.eclipse.org/mylyn/downloads/>

''' Java Persistence API Tools error when updating the JEE Eclipse
Package '''

If you are trying to install additional features and get this error you
have hit
[bug 194959](https://bugs.eclipse.org/bugs/show_bug.cgi?id=194959) which
should be resolved soon. The work-around is to check off the *Europa
Discovery Site* and install the first two components of the *Data Tools
Platform*.

**Subclipse related problems**

If you see the following message:

`  Subclipse Mylyar Integration (1.0.1) requires plug-in "org.eclipse.mylar.tasks.core (0.9.2)",`
`  or later version`

You need to uninstall the old (pre 2.0) version of Subclipse and Mylar
integration. Most users should not need to do this since the old Mylar
1.x version disabled itself after the update to 2.0. But if you see this
error uninstall via:

  - Help → Software Updates → Manage Configuration
  - Uninstall the Subclipse Mylar Integration (1.0.1)
  - Uninstall the old version of Mylar

''' Incompatible VM (e.g. JDK 1.4) '''

If you are using the wrong VM, you’ll see errors like the following in
your log file.

`Root exception: java.lang.UnsupportedClassVersionError:`
`org/eclipse/mylar/tasklist/MylarTasklistPlugin (Unsupported major.minor version 49.0)`

See [Configure Java](#What_version_of_Java_is_required.3F "wikilink") to
fix this problem.

''' Incompatible version of Eclipse '''

Separate versions and update sites exist [for Eclipse 3.1
and 3.2](http://eclipse.org/mylyn/dl.php)), in which case you may see
errors like the following in your <workspace>`/.metadata/.log`file or in
a Mylyn view:

`java.lang.NoSuchMethodError: org.eclipse.ui.internal.dialogs.FilteredTree.getFilterControl()`
`The activator org.eclipse.mylar.java.MylarJavaPlugin for bundle org.eclipse.mylar.java is invalid`

''' Mylyn feature configuration problem '''

If the above do not address the issue, the easiest thing to do is
uninstall any old versions and update to the latest Mylyn. Your tasks
won’t be lost, because by default they are stored in the
<workspace>`/.metadata/.mylyn` folder which will be read next time Mylyn
starts correctly.

  - First, uninstall the old version of Mylyn using *Help → Software
    Updates → Manage Configuration*.
  - You need to Disable all Mylyn features by right-clicking them.
  - Allow Eclipse to restart after the last is disabled.
  - After restart, ensure that the 3rd toolbar button is pressed (figure
    below) so that you see the disabled features to uninstall.
  - Uninstall all the disabled features using the popup menu.

If you don’t uninstall, the the Update Manager will think that you have
the latest and tell you that there are no updates.

<b>Note: manually removing the plug-ins and features can lead to
configuration errors.</b>

After uninstalling, update Eclipse by adding the correct update site
specified at on the [download page](http://eclipse.org/mylar/dl.php),
and after that automatically or manually updating will install the
correct version.

![Image:mylar-eclipse-manage-configuration.gif](mylar-eclipse-manage-configuration.gif
"Image:mylar-eclipse-manage-configuration.gif")

**What do I need to do in installation to be able to use Mylyn task
management features with bug/task/issue trackers?**

When you install, make sure that you select a connector for your
bug/task/issue tracking software. For example, to use Bugzilla, you have
to install the Bugzilla connector component.

**What does the error “Network connection problems encountered during
search” mean?**

If you get that message while trying to download Mylyn, it means that
Eclipse couldn’t find the location you entered. This might be because
you copied something incorrectly (watch for extra characters -- even
extra spaces can cause errors), or because the site went down. You may
be able to see if the site is up or down by copying the URL into your
Web browser.

'''What does the “Update manager failure” message mean? '''

It means that Eclipse could not access the update site, or that it got
confused about the configuration state of your Eclipse. First try
updating again to see if the update site is accessible.

If you are trying to update the JIRA connector you can also try
de-selecting that feature in case the `Tigris.org` update site is not
accessible. Using *Search for new features to install…* when installing
can help to avoid this problem. If that does not work see the feature
configuration troubleshooting below.

**Why am I getting messages in my <workspace>`/.metadata/.log` or my
Mylyn view that say things like “`java.lang.NoSuchMethodError:
org.eclipse.ui.internal.dialogs.FilteredTree.getFilterControl()`” and
“The activator `org.eclipse.mylar.java.MylarJavaPlugin` for bundle
`org.eclipse.mylar.java` is invalid”?**

This probably means that your Mylyn download version didn’t match your
Eclipse download version. Note that [the download
site](http://eclipse.org/mylar/dl.php) has different downloads for
Eclipse 3.1 and Eclipse 3.2.

To fix this problem, see the [uninstallation
guide](Mylyn_Uninstallation_Guide "wikilink"), then re-install from [the
correct download site](http://eclipse.org/mylar/dl.php).

**Why am I getting messages in my <workspace>`/.metadata/.log` or my
Mylyn view that say things like “`java.lang.NoSuchMethodError:
org.eclipse.mylyn.internal.context.core.InteractionContextManager.getScalingFactors()`”?**

This could mean that some of your Mylyn plugins are on different
versions. Use the update manager (“*Search for new features to
install…*”) to obtain the latest versions of the Mylyn features.

**Why doesn’t the Eclipse Update Manager display the latest versions of
the Mylyn features?**

It does. Note, however, that if you select both the Mylyn site and the
Weekly Builds site, using “*Search for new features to install…*”, you
must uncheck the “*Show the latest version of a feature only*” checkbox
in order to see the updates available on both sites.

**I’ve just updated to Mylyn 2.0 and I don’t see any tasks in my Task
List**

As part of the update to Mylyn 2.0 the old data folder has been migrated
to <workspace folder>/.metadata/.mylyn from the old location
<workspace folder>/.mylar. IF for some reason migration failed (.mylar
folder still exists), simply shut down Eclipse and manually move your
old <workspace folder>/.mylar folder to
<workspace folder>/.metadata/.mylyn (note the name change to .mylyn)

**Error: Network connection problems encountered during search** Eclipse
couldn’t find the location you entered. This might be because you copied
something incorrectly (watch for extra characters -- even extra spaces
can cause errors), or because the site went down. You might be able to
see if the site is down by copying the URL into your Web browser.

**Error: Update manager failure** Eclipse could not access the update
site, or that it got confused about the configuration state of your
Eclipse. First try updating again to see if the update site is
accessible. If you are trying to update the JIRA connector you can also
try de-selecting that feature in case the Tigris.org update site is not
accessible. Using use *Search for new features…* when installing can
help to avoid this problem. You will probably get a warning that **the
feature is unsigned**. If you trust that hackers have not befouled the
Mylyn plug-in, select *Install All*.

## Why can't I update Mylyn 3.0 to a newer release?

The update site link in the 3.0 and 3.0.1 features for Eclipse 3.3
points to the Mylyn for Eclipse 3.4 update site (). An attempt to update
will result in an error: “Mylyn Task List (Required)
(3.0.1.v20080721-2100-e3x) requires plug-in "org.eclipse.ui
(3.4.0.I20070918)", or later version.”

To resolve the error follow these steps:

1.  Open update **Help → Software Updates → Find and Install…**
2.  Select **Search for new features…** and **Next**
3.  **Uncheck Mylyn**. Add a **New Remote Site**:
      - Name: **Mylyn for Eclipse 3.3**
      - URL: **<http://download.eclipse.org/tools/mylyn/update/e3.3>**.

Make sure the new site is selected and select Finish to proceed with the
update.

## Installing on Linux

### How can I get the SWT internal browser to work under Linux?

Mylyn uses the Standard Widget Toolkit Browser, and users have
experienced problems with the SWT Browser on Linux. This is not a Mylyn
specific problem and also occurs if you try to use Eclipse’s Browser
view. To test to see if your browser is properly configured, select
*Window → Show View → Other → General → Internal Web Browser*, then try
to load a web page. If the internal browser is problematic, consider
enabling the external default browser (i.e. Firefox) via *Window →
Preferences → General → Web Browser* and select the **Use external Web
browser** option.

### I’m getting a “Could not create Browser page: No more handles” error

When the Browser is not properly configured exceptions such such as
“Could not create Browser page: No more handles
(`java.lang.UnsatisfiedLinkError: …`)” will appear when attempting to
open tasks. See [the SWT Browser
guide](http://www.eclipse.org/swt/faq.php#browserlinux) for which
browsers will work.

### I’m having unstable performance on Linux with a Sun JVM are there options?

For those experiencing unstable performance with Linux using the Sun
JVM, try the [IBM
JVM](http://www-128.ibm.com/developerworks/java/jdk/linux/download.html),
which will require you to register with IBM prior to download. We’ve
also had good reports from those using JRockit JVM.

### Memory consumption problem with internal browser on Linux-GTK

If you are experiencing abnormal memory consumption upon launching the
internal browser (or opening repository tasks), try shutting down
eclipse, renaming/moving your `~/.mozilla/eclipse` folder and
relaunching eclipse. (see
[bug\#172782](https://bugs.eclipse.org/bugs/show_bug.cgi?id=173782))

### Error: No more handles error

`(java.lang.UnsatisfiedLinkError: no swt-mozilla-gtk-3449 or swt-mozilla-gtk in swt.library.path, java.library.path or the jar file)`

To resolve this error install a package that provides the Gecko engine
library. On Ubuntu and Debian the package is called libxul0d.

### Recommended Settings for GTK

[This
article](http://blog.xam.dk/archives/81-Making-Eclipse-look-good-on-Linux.html)
describes how to improve the visual appearance of Eclipse on GTK.

### Recommended GTK Setup for KDE

The recommended GTK theme to use for KDE (and KDE based distributions
like Kubuntu) is the “Human” theme. (Possibly, this is also a good
recommendation for GNOME. GNOME users, please comment.)

With Debian based distributions (e.g. Ubuntu), this theme can be
installed with

` aptitude install human-theme`

The appearance of GTK applications is controlled by the KDE System
Settings / Control Center in the section “Appearance”.

  - GTK Styles and Fonts: GTK Styles: Select “Use another style
    \[Human\]”

<!-- end list -->

  - Colors: At bottom: \[x\] Apply colors to non-KDE applications

These changes are applied to these two GTK configuration files,
respectively:

  - `$HOME/.gtkrc-2.0-kde`
  - `$HOME/.kde/share/config/gtkrc-2.0`

### Solving issues with KDE environment variable settings

Most of the [known UI issues
below](#Known_UI_issues_with_KDE "wikilink") are due to a broken
environment variable setting. The environment variable `GTK2_RC_FILES`
contains a search path to find the GTK configuration files to be used by
the GTK application and can be checked with

` env | grep GTK2_RC_FILES`

The correct setting is obtained by

` export GTK2_RC_FILES=$HOME/.gtkrc-2.0-kde:$HOME/.kde/share/config/gtkrc-2.0 `*`#``
 ``Bourne``   ``shell`*
` setenv GTK2_RC_FILES $HOME/.gtkrc-2.0-kde:$HOME/.kde/share/config/gtkrc-2.0 `*`#``
 ``C``   ``shell`*

**Important note:** The used environment setting seems to differ
depending on the way KDE starts the application: from Konsole, using
“Run Command…”, using a desktop icon etc. Please use this simple
script to check the different ways:

` #!/bin/bash`
` env | grep GTK2_RC_FILES >/tmp/GTK2_RC_FILES.env`

and look at the resulting output in `/tmp`.

Consider filing a bug against the distribution showing this inconsistent
behaviour.

### Known UI issues with KDE

There a couple of bugs related to UI features not working in specific
Linux distributions:

  - [176716: Task colors are not
    displayed](https://bugs.eclipse.org/bugs/show_bug.cgi?id=176716)
  - [173928: Task acivate button does not work under
    linux](https://bugs.eclipse.org/bugs/show_bug.cgi?id=173928)

Debian 3.1 (sarge) with KDE and standard X11 installation (XFree86)
works fine for all three issues.

Debian testing (etch) with KDE and new X11 installation (X.Org) has
issues with the color display (bug 176716 and 135928), but the Task
Activate button works.

Kubuntu Dapper 6.06 with KDE and X.Org triggers all above issues. An
upgrade to Edgy enables Task Color display and the date picker
selection. To get the Task Activation button working you have to use
Edgy and Eclipse 3.3M5eh (or newer).

Kubuntu Gutsy 7.10 has issues with the color display (bug 176716). A
workaround is to change the GTK-Style to “Human”. More details and
another solution in the comments of bug 176716.

## Installing on MacOS

If you see errors like the following it may be due to Xerces missing
from the Mac JDK so you may need to add it to your default classpath.
Please refer to and comment on
[bug 144287](https://bugs.eclipse.org/bugs/show_bug.cgi?id=144287) if
you see this problem.

`   Could not create Bugzilla editor input`
`   java.io.IOException: SAX2 driver class org.apache.xerces.parsers.SAXParser not found`

To ensure that you are using the 1.5 VM refer to the last comment on
[bug 1163477](https://bugs.eclipse.org/bugs/show_bug.cgi?id=116347#c4)
for instructions on how to change the 1.4 default.

## Configuration Troubleshooting

### The default Key Mappings aren’t working correctly, what can I do?

If default key mappings aren’t working, try doing the following to reset
them:

  - *Window → Reset Perspective*
  - *Then: Window → Preferences → Keys → Restore Defaults*

#### Linux key mappings a problem?

If you are running Mylyn on X-Windows, for example on Linux, FreeBSD,
AIX and HP-UX, some keyboard bindings may not work by default.

If the `Ctrl+Alt+Shift+Arrow Up` shortcut for *Mark as Landmark* does
not work do the following:

  - *Menu Bar → Desktop → Control Center → Keyboard Shortcuts → Move one
    workspace up, Move one workspace down*: disable both.

If `Alt+Click` quick unfiltering does not work try one of the following:

  - Hold down the `Windows` key while holding `Alt`, if available
    (ironic, but unsurprisingly this key is not usually mapped on
    Linux).
  - Disable the `Alt+drag to move` functionality:

GNOME Desktop

1.  Open a terminal and run `gconf-editor`
2.  Go into: `/apps/metacity/general`
3.  Edit the `mouse_button_modifier` field. Setting it to nothing
    disables it. You can use <Super> to set it to the windows key.
4.  Exit `gconf-editor`.

KDE Desktop

1.  Run the *KDE Control Center*.
2.  Go to the *Desktop/Window Behavior* panel and select the *Window
    Actions* tab.
3.  Down in the *Inner Window, Titlebar & Frame* area, change the
    *Modifier Key* option from `Alt` to `Meta`.

### How do I enable spell checking in Eclipse 3.2 and older?

On Eclipse versions earlier than 3.3, the spell checking must be set up
manually. Spell checking is supported in the task editor for local tasks
and for connectors that support rich editing (e.g. Bugzilla, Trac).

  - To install spell checking for editors that support it you need to
    enable the preference in *General → Editors → Text Editors →
    Spelling*.
  - You also need to install a dictionary, some instructions are
    [here](http://www.javalobby.org/java/forums/t17453.html). A word
    list is available [here](http://wordlist.sourceforge.net/) as well.

![Image:mylar-spell-checking-preference.gif](mylar-spell-checking-preference.gif
"Image:mylar-spell-checking-preference.gif")

### How can I change the number of editors left open before Mylyn starts closing editors?

Turn off or increase the number of editors to leave open using
*Preferences → General → Editors → Number of opened editors before
closing*. Since Mylyn will manage the open editors with task activation,
this number can be set higher or you can disable automatic closing
entirely.

### Do I need the Outline View when running Mylyn?

No, not really. The Package Explorer and folded signatures should
provide enough context for you. If, at some point, you really need to
see an Outline View, you can always enter (Ctrl+O) to show the in-place
Outline View.

### What does the message “content assist proposals no longer appear” mean?

This usually happens when uninstalling when using Eclipse 3.2. Make sure
that the “Java Completions” and “Java Types” proposal categories are
included in the default proposals via: *Preferences → Java → Editor →
Content Assist → Advanced → Restore Defaults*. Also see: [content assist
troubleshooting](Mylyn_FAQ#Content_assist_troubleshooting "wikilink").
This [bug](https://bugs.eclipse.org/bugs/show_bug.cgi?id=140416) has
been fixed in Eclipse 3.2.1.

### Why do I get errors like “HTTP Response Code 407” or “Proxy Authentication Error” when accessing repositories through a proxy server?

It is likely that you need to configure these proxy server settings.
Select *Window → Preferences → General → Network Connections*, and
update the section in the “Proxy settings” section of the form.

### I can’t use `Ctrl+Alt+Shift+Arrow Up` for'' Mark as Landmark''. What do I do?

This is usually a Linux/GNOME problem, where the Gnome keyboard
shortcuts are interfering with the Eclipse shortcuts. Go to the Keyboard
shortcuts (which might be something like *Desktop → Control Center →
Keyboard Shortcuts* or *System → Preferences → Keyboard Shortcuts*) and
disable both of these shortcuts:

  - Move one workspace up
  - Move one workspace down

See also: [keyboard mappings on
Linux](Mylyn/FAQ#Linux_key_mappings_a_problem.3F "wikilink").

### Why do I get an error when accessing secured web sites?

The internal browser may display an error if the web site certificate is
not trusted and block access to the site:

`(Error code: sec_error_unknown_issuer)`

On Linux start `firefox -profile ~/.mozilla/eclipse -no-remote` from the
command line and open the web site in Mozilla Firefox. Add an exception
for the web site and restart Eclipse. The site should now be accessible
from Eclipse.

**Notes**

1.  `-no-remote` is added because it would otherwise open a new window
    in the running process. You’re probably viewing this page in
    firefox, so the command above will not work without `-no-remote`.
2.  Replace `firefox` by the exact command that you use to start your
    Mozilla browser.

## Uninstall troubleshooting

We recommend **uninstalling in Eclipse** via the *Help → Software
Updates → Manage Configuration* dialog. If you get an error message when
trying to uninstall, you will need to first uninstall dependencies that
use Mylyn. These include things like the Subclipse Mylyn integration and
the Bugzilla Connector.

You can also **uninstall manually** by deleting all of the Mylyn
plug-ins and features from the `eclipse/plugins` and `eclipse/features`
directory make sure to delete all of the plug-ins and then restart
Eclipse with the -clean option (e.g. by inserting it into a shortcut or
the `eclipse.ini` file.

On **Eclipse 3.2:** if after uninstalling **content assist proposals no
longer appear** you need to ensure that the *Java Completions* and *Java
Types* proposal categories are included in the default proposals via:
*Preferences → Java → Editor → Content Assist → Advanced → Restore
Defaults*. Also see: [content assist
troubleshooting](Mylyn_FAQ#Content_assist_troubleshooting "wikilink").
This [bug](https://bugs.eclipse.org/bugs/show_bug.cgi?id=140416) has
been fixed in Eclipse 3.2.1.

On **Eclipse 3.1:** you may need to reset the Java editor to be default
for `.java` again via: *Preferences → General → Editors → File
Associations*

## Why am seeing `java.lang.OutOfMemoryError: PermGen space` errors?

If your Eclipse crashes, or you see the above error after installing
Mylyn or other plug-ins, you have most likely hit the infamous
MaxPermSize bug. This is not a Mylyn specific problem, but a general
problem with the Sun Java VM that is often triggered on Eclipse 3.2 and
later, if you have many plug-ins installed.

To fix it simply add the following to your launch arguments. This is
usually to your shortcut:

`   -vmargs -XX:MaxPermSize=128m`

Or to the `eclipse/configuration/config.ini` file:

`   -XX:MaxPermSize=128m`

Note: For Eclipse 3.4 with the Equinox P2 profile-based provisioning
support, this setting can also be modified in the current P2 profile.
With a default installation of the SDK, see:

@config.dir/../p2/org.eclipse.equinox.p2.engine/profileRegistry/<name>.profile/<timestamp>.profile

For more information, see:
<http://wiki.eclipse.org/Equinox_p2_Admin_UI_Users_Guide>

If you are using a very large number of plug-ins (e.g. WTP) and still
get this error you may need to increase the number to 256M. Note that on
some VMs the size may need to be a power of 2 and may drop down to the
default (e.g. 32M) if it is not accepted.

Eclipse 3.3.1 users: note note that due to Platform  you need to use the
instructions above and cannot set the size using
`-launcher.XXMaxPermSizeL`, which will be ignored.

For more information see the [Eclispe FAQ
entry](FAQ_How_do_I_increase_the_permgen_size_available_to_Eclipse? "wikilink").
Details of the problem are on [Platform
bug 92250](https://bugs.eclipse.org/bugs/show_bug.cgi?id=92250).

## What is Mylyn’s performance profile?

Mylyn should have **no noticeable effect** on Eclipse’s speed or memory
usage, no matter how large your workspace is. You do not need to
increase the amount of memory Eclipse runs with to use Mylyn. Any
performance issue should be [reported as a
bug](https://bugs.eclipse.org/bugs/enter_bug.cgi?product=Mylyn).

The current **performance profile** is:

1.  Mylyn only runs if a task is active, and has no impact on Eclipse if
    no task is active.
2.  Task context models have negligible memory overhead.
3.  When a task is active, additional view refresh is required to update
    the views based on interest model changes. This should not be
    noticeable on Windows where refresh is very quick, but could be more
    noticeable on other platforms.
4.  The time to activate a task context is dominated by the time it
    takes Eclipse to open the editors in the context. You can set the
    preference for how many editors to open in the Mylyn preference page
    (e.g. setting to 1 will dramatically reduce activation time, but
    also remove the benefit of having open editors correspond to the
    task context). You can also turn off editor management entirely in
    the Mylyn Tasks view pull-down.
5.  Eclipse startup is slowed down by (4) if a task is active when
    Eclipse is shut down.
6.  The low priority background searches that the Active Search view
    runs can be noticeable on slower machines.

**If you are seeing performance problems, this is either a bug, or
caused by other performance problems in other Eclipse plug-ins**'. If
you are performance problems we suggest increasing the amount of memory
available to Eclipse. This is especially useful for very large Java
project workspaces, on which the size of JDT’s element cache will grow
proportionally to the amount of available memory. The setting we
recommend for launching workspaces with a couple hundred large projects
is:

` -Xmx768M -XX:MaxPermSize=128M`

**If you are seeing content assist timeouts** that indicate the Mylyn
proposal computer did not complete quickly enough, note that the problem
is not with Mylyn, but with the standard content assist mechanism timing
out due to an intensive computation (eg, a large number of matches). In
this scenario switching or [disabling the Mylyn proposal
computers](Mylyn_FAQ#Content_assist_troubleshooting "wikilink") does not
help improve performance, although it will get rid of those messages.

# Task List

## How do I restore my tasks from backup?

The task list can be restored from automated backup via the Task List
view’s drop down view menu and selecting Restore Tasks from History…

## How do I clear outgoing changes on a task?

If a task has outgoing changes you wish to discard, right click on the
task and select Mark as → Clear Outgoing. If a mid-air collision occurs,
press the Synchronize button in the Task editor toolbar to bring in the
incoming changes. Your outgoing changes will remain.

## Why do my tasks not appear in the Task List?

The task list has filtering mechanisms that can limit the items visible
in the task list. If a task is missing from the task list, use the
following steps to remove all filters:

![Image:Tasklist-filter.png](Tasklist-filter.png
"Image:Tasklist-filter.png")

1.  Check the filter settings in the view menu. Make sure Filter
    Completed tasks is not enabled and all items are checked in the
    Filter Priority Lower Than menu.
2.  If the Go Up To Root icon is visible in the toolbar, select it to
    make all items in the task list visible.
3.  If the Focus on Workweek button is pressed, select it to unfilter
    the task list.
4.  If text is typed in the Find, use the clear button next to the find
    box.
5.  Switch to All to make all all working sets visible.

## Why do tasks appear in the *Unmatched* container?

The *Unmatched* containers will automatically appear if a task needs to
be shown but is not matched by any query. This is needed to ensure that
the corresponding tasks do not disappear, for example, if the query is
set up to only match resolved/completed tasks (a usage anti-pattern,
since Mylyn has other mechanisms for preventing completed tasks from
showing in the Task List).

In order to ensure that you do not miss reminders or notifications the
following tasks will always be shown in the Task List, even if they have
been removed from a category or a query:

  - Tasks scheduled for this week or overdue. Remove these by using the
    *Schedule* pop-up menu option to defer them to a future week or to
    clear the schedule.
  - Repository tasks that have incoming changes, such as comments.
    Remove these by reading them or marking them as “read” via the *Mark
    → Read* pop-up menu.

To **get rid of tasks in the *Unmatched* container** you can:

  - Create a new query that matches the tasks.
  - Right-click on one or more tasks to delete them.

Recommended Mylyn usage is to keep the *Unmatched* container empty. For
query setup recommendations see the sidebar at:
<http://www.ibm.com/developerworks/java/library/j-mylyn1/?ca=dgr-eclipse-1>

## How do I change the Task List colors?

Use *Window → Preferences → General → Appearance → Colors and Fonts*.

## The Unmatched category contains many irrelevant tasks, how do I clean it up?

If you created very broad queries you could end up with thousands of
tasks in your Unmatched containers. Other than clearing the
`workspace/.metadata/.mylyn/tasklist.xml.zip` and
`workspace/.metadata/.mylyn/offline` folder (note that this will
entirely reset your Task List) the easiest option is to:

  - Clean up your queries to include only tasks of interest (note that
    including completed/resolved tasks is recommended).
  - Turn off *Focus on Workweek* in the *Task List*.
  - Delete all of the unneeded tasks from within the Unmatched
    containers. Note that if the tasks are not matched by queries they
    will be deleted permanently and any local notes or scheduling
    information that you have added to them will be lost.

## How does Mylyn count the active time for a task?

Whenever you work on a task, Mylyn accumulates the time you spend
actively working on a task. This time can be viewed in the *Personal
Planning* section of the *Task Editor*. When you are not interacting
with Eclipse, the timing automatically times out after 3 minutes by
default. This means that activity outside of Eclipse will not be
captured when you work on the task and that the timings in Mylyn are a
lower bound of the total time spent on the task (capturing timings for
work done outside of Eclipse involves OS specific extensions).

## How do I prevent long-running tasks from adding to the progress bar?

If you have many long-running or recurring tasks scheduled for this
week, they can affect the *Task List* weekly progress bar. This can be
misleading as they may never be completed. The current work-around to
prevent long-running tasks from being included in the weekly progress
bar is to schedule their estimated time to be 0 (zero). Alternatively,
you can schedule only the amount of time you plan on spending on that
task this week.

## Does the Task List replace the Eclipse Tasks view?

The SDK’s *Tasks* view is used for showing markers such as ‘todo’ tags
which indicate a local problem with a resource, similar to a compiler
warning. As such, these ‘tasks’ are at a much finer granularity than
Mylyn’s tasks, and one task could involve cleaning up multiple todos. In
order to make working with only the markers in a particular task
context, e.g. for clean-up before committing, the *Apply Mylyn* filter
is available for both the *Problems* and the *Tasks* views.

## What if I use multiple workspaces?

Mylyn’s support for multiple workspaces is currently limited (see
[bug 130658](https://bugs.eclipse.org/bugs/show_bug.cgi?id=130658) for a
discussion) because the Task List is considered to be specific to the
person, and not to the workspace. In addition, Eclipse’s support for
multiple workspaces is limited to import/export based usage, and Mylyn
inherits this limitation. We highly recommend configuring your Eclipse
workspace to use working sets instead of relying on multiple workspaces.

If using a single workspace is not possible you can do the following,
Mylyn does provide an advanced facility for using the same data
directory that’s outside of the workspace. However, this is not
generally recommended because it can cause you to overwrite an existing
Task List if both workspaces are launched at the same time.

  - In *Preferences → Tasks → Task List* set the *Data Directory* to be
    a shared location, and do this for both workspaces.
  - Be sure to avoid launching both Eclipse workspaces at the same time,
    as changes in one workspaces could overwrite the Task List in the
    other workspace.
  - If you upgrade Eclipse or move your workspace and don’t see your
    tasks, check the *Data Directory* setting.

Note that using *File → Import → Task Data* is another way to get an
existing *Task List* into your workspace. If you use this mechanism for
sharing the *Task List* between workspaces you should export the *Task
List* when switching, because in this mode you are working with two
separate *Task List*s. While much of the task state that yo uwork on is
stored in shared task repositories, all read state, activity history,
planning information and local tasks are maintained in the *Task List*
and as such it can become cumbersome to end up with two different lists
to manage.

See also:

  - John O’Shea’s blog: [Eclipse workspaces containing projects with
    overlapping locations, and
    Mylar](http://www.xlml.com/aehso/2007/02/02/eclipse-workspaces-containing-projects-with-overlapping-locations-and-mylar/)

## How do I export my task and repository data?

Export via File → Export → Mylyn → Task Data (Mylin 3: File → Export →
Tasks → Task List and Contexts)

## Why does Mylyn use the term “task”?

There are many work items that make up the developer’s workday. Many
issue trackers and project management tools refer to these as: bugs,
defects, actions, tickets, stories, enhancements, and the list goes on.
We refer to all such work items as “tasks” because the word tasks is
short and commonly used in time management tools. Task Repository
connectors can customize the presentation of tasks, for example,
indicating which is a defect and which is an action item.

## Why are closed tasks not greyed out on Linux?

If you are running Eclipse from KDE go to KControl → GTK Styles and
Fonts and select “Use another style” in the GTK Styles section ().

See the [Recommended GTK Setup for
KDE](Mylyn/FAQ#Recommended_GTK_Setup_for_KDE "wikilink") if the style
selection does not work.

## Why is starring tasks not supported?

The current mechanism for starring tasks is to schedule them for
*Today*, which has a very similar effect to starring in other UIs. If
you schedule a task for today, the task will stand out as blue and
always show (i.e., have guaranteed visibility when the Task List is
focused). If that’s too visible, you can schedule it for *This Week*, in
which case the task will always show but not turn blue.

The alternative to mark a shared task as outgoing by adding text into it
and (e.g. “\[review\]”). The ougtoing change will also give the task
guaranteed visibility. This is currently the only work-around for
‘starring’ completed tasks.

The task-focused interface consider tasks orthogonal to resources (e.g.,
files and web pages). Resources make sense to star/bookmark, since their
primary residence is in some structural hierarchy (e.g. folders or a
type hierarchy). Starring provides a mechanism for locating the most
relevant parts of a large hierarchy (at the cost of having our
starred/bookmark lists bloat and become yet another thing to manage).
Tasks are inherently different than resources because their primary
residence is in time (e.g. due dates, milestones, things completed in
the past). As such, the equivalent of starring for tasks is to schedule
them to be viewed in the “current” time window (e.g. today or this
week). For a discussion on this refer to .

# Task Editor

## When I submit a new bug to eclipse.org the priority isn’t updated?

Eclipse.org’s Bugzilla repository forces all new bug reports to priority
3 (P3) regardless of what is selected in Mylyn. Eventually we will
disable this field in the new bug editor for bugs.eclipse.org and
provide a tooltip with explanation (  ).

## Why am I seeing strange boxes where I expect to see proper characters?

If for example you aren’t seeing the proper single quote chacters in the
summary of
[bug\#197644](https://bugs.eclipse.org/bugs/show_bug.cgi?id=197644),
check that the encoding is set correctly for the repository in the
asociated Task Repositories view (Properties → Additional Settings →
Character Encoding). For bugs.eclipse.org/bugs set your charcter
encoding to *ISO-8859-1*.

## How can I view images or screenshots that are attached to an image?

By default Eclipse does not provide a built-in image viewer so images
can either be opened with a browser or saved to disk and opened in a
native image viewer. Alternatively Eclipse extension such as QuickImage
can be installed which support opening images within Eclipse.

# Task Repositories

## What if I’m not using a Task Repository?

Mylyn does not require the use a of a task repository and can be used
entirely with the *Local Tasks* repository that it comes bundled with.
However, if working with a team, a shared *Task Repository* provides the
key infrastructure needed to let your team work in a Task-Focused way
via Mylyn’s collaborative facilities.

Those not currently using another supported *Task Repository* should
consider the repositories currently [supported by
Mylyn](http://www.eclipse.org/mylyn/downloads/) as well as those
supported by the [third party Mylyn
extensions](http://wiki.eclipse.org/index.php/Mylyn_Extensions).

## What if Mylyn doesn’t support my task/bug/issue/ticket repository?

To see support for your repository faster, do a search of the open
repository connector requests and [vote for the corresponding
bug](https://bugs.eclipse.org/bugs/buglist.cgi?query_format=advanced&short_desc_type=anywordssubstr&short_desc=%5Bconnector%5D&product=Mylyn&long_desc_type=allwordssubstr&long_desc=&bug_file_loc_type=allwordssubstr&bug_file_loc=&status_whiteboard_type=allwordssubstr&status_whiteboard=&keywords_type=allwords&keywords=&bug_status=NEW&bug_status=ASSIGNED&bug_status=REOPENED&emailtype1=substring&email1=&emailtype2=substring&email2=&bugidtype=include&bug_id=&votes=&chfieldfrom=&chfieldto=Now&chfieldvalue=&cmdtype=doit&order=Reuse+same+sort+as+last+time&field0-0-0=noop&type0-0-0=noop&value0-0-0=)
if your tracker is there, or [create a new
bug](http://www.eclipse.org/mylar/bugs.php).

[Generic Repository
Connector](Mylyn/User_Guide#Generic_Web_Templates_Connector "wikilink"),
allows creating Queries to the web-based issue tracking repositories and
get list of issues from the web UI into the Task List.

It is also possible to link a *local task* with the web page in
web-based repository via the Mylyn Web integration.

**To create a task from any web-based repository:**

  - Drag the URL from the address bar of the browser, or from a
    hyperlink in a bug listing to the *Mylyn Tasks* view. This will
    create a task for the bug, link it to the page, and populate the
    description with the title of the corresponding page. **In
    Mozilla:** simply drag the URL. **In Internet Explorer:** you must
    have `Ctrl` pressed in order for Eclipse to recognize the drop.
  - **Alternatively,** you can copy the URL, press the *New Task* button
    on the *Mylyn Tasks* view. This has the same effect as above but you
    can edit the description after retrieving it.
  - Opening the task will now open the corresponding issue. You can also
    `right+click` the task and select *Open in External Browser*.

![Image:mylar-tasklist-weblink-editor.gif](mylar-tasklist-weblink-editor.gif
"Image:mylar-tasklist-weblink-editor.gif")

## Why were my repository credentials reset?

If you upgrade Eclipse or your Java VM, you will need to reset your
credentials in the *Task Repositories* view because these are stored in
the secure Eclipse workbench keyring. Also see
[bug 149607](https://bugs.eclipse.org/bugs/show_bug.cgi?id=149607). If
you are migrating **from Eclipse 3.2 to 3.3** note that you will need to
use a different update site, which is listed here:
<http://eclipse.org/mylyn/dl.php>

## Why are my updated repository attributes not showing up?

Your server’s repository attributes can change frequently, for example,
there can be a new "milestone" or "version" added to the Bugzilla
repository with each release. When the *Preferences → Mylyn → Task List
→ Synchronization* setting is enabled, every 10th synchronization will
update the attributes from the repository. If you do not have this
setting enabled, your can force the update via the *Update Attributes*
action on the task repositories’ context menu in the *Task Repositories*
view. Note that you will need to reopen a task editor to see the updated
attributes. If you instead update via the button on the *Attributes*
section of the *Task Editor* the attribute settings will be reloaded
without needing to reopen.

**bugs.eclipse.org users**: Note that the attributes listing on
eclipse.org is mirrored, and the mirrors are only updated 24 hours. As
such, you may need to wait up to 24 hours for the new attributes to show
up.

## Authentication Troubleshooting

You must ensure repository credentials are filled out correctly. Refer
to the diagram below:

[right](image:_AuthenticationTroubleshooting2.png "wikilink")

1.  Enter the repository URL (i.e. <https://bugs.eclipse.org/bugs>) and
    an optional label
2.  Credentials
      - Usually email address and password
      - Some sites, such as `dev.eclipse.org`, use anonymous logon with
        password left blank.
3.  Http Authentication (optional)
      - Some sites are protected by either BASIC or DIGEST http
        authentication. If this is the case, enter appropriate
        credentials here.
      - One way to test if the site requires http authentication is to
        point your browser at the repository. If you are presented with
        an authentication dialog popup, the site is likely protected by
        http authentication.
4.  Proxy Server Configuration (optional)
      - By default Mylyn uses the Platform’s Install/Update proxy
        settings. Uncheck this box if you wish to use an alternative
        proxy.
      - If the proxy requires authentication, this is where you enable
        and enter your proxy credentials.
      - If you are experiencing connection problems, ensure your
        Install/Update proxy settings are valid or the repository
        specific settings are correct
      - Mylyn has been tested with HTTP proxy servers. Currently SOCKS
        is not supported.
5.  Validate Settings
      - Press the *validate* button to test the settings
      - If you are seeing errors like “HTTP Response Code 407” or “Proxy
        Authentication Error” it is likely that you need to configure
        proxy settings as described above.
      - If your sever uses a certificate and fails to connect, e.g. you
        see exceptions `sun.security.validator.ValidatorException: PKIX
        path building failed` then you need to point Eclipse at your
        certificate, see below.

### Certificate authentication

Mylyn supports authentication with certificates from a Java keystore.
The path and password to the keystore need to be specified in system
properties. These can be set in the eclipse.ini in your eclipse install
directory:

`-vmargs`
`…`
`-Djavax.net.ssl.keyStore=/path/to/.eclipsekeystore`
`-Djavax.net.ssl.keyStorePassword=123456`

If your keystore does not have the default type (JKS) you can specify a
different type:

`-Djavax.net.ssl.keyStoreType=PKCS12`

#### Creating a keystore

If you do not have a client certificate you can create one and have it
signed by a CA:

`keytool -genkey -keyalg DSA -keysize 1024`

Use this command to create a new certificate signing request:

`keytool -certreq > client.csr`

Submit the client.csr file to your CA for signing. The CA’s certificate
as well as your signed certificate that is returned by the CA need to be
imported into the keystore:

`keytool -importcert -alias ca -file ca.crt`
`keytool -importcert -file client.crt`

See [this
page](http://java.sun.com/j2se/1.5.0/docs/guide/security/SecurityToolsSummary.html)
for links to the keytool documentation.

### NTLM authentication

For NTLM authentication to work a special format for the username needs
to be used where *DOMAIN* needs to be replaced by the Windows login
domain:

`DOMAIN\username `

The built-in NTLM support of the JDK which is used by Eclipse does **not
work** with Mylyn since it uses the HttpClient library to access
repositories. Limitations in regard to NTLM authentication are
documented in the [NTLM
FAQ](http://wiki.apache.org/jakarta-httpclient/FrequentlyAskedNTLMQuestions)
and also discussion on .

  - If your repository uses MS NTLM authentication and only standard
    http authentication is being passed to the repository this can
    result when the local hostname cannot be resolved. Ensure your
    machine’s hostname is set correctly and resolves to a valid address.
  - It is not possible to use NTLM authentication for the proxy as well
    as for the repository.

If NTLM authentication fails the **[NTLM Authorization Proxy
Server](http://ntlmaps.sourceforge.net/)** has been reported to **work**
with Mylyn.

## Network Troubleshooting

### Performance Problems with HTTPS

The built-in SSL support of the JDK will to a name lookup for each new
connection. In case your network setup cannot resolve the host name
(e.g. no proper name server), this lookup will time out, delaying the
whole job. If setting up a name server is not an option, a work around
would be to edit your local hosts file, and add the server IP there
(and, if possible, add your computer's IP to the server's hosts file).

### Error "Received fatal alert: bad_record_mac" when using https

The SSL handshake can [fail with some
servers](http://docs.oracle.com/javase/1.4.2/docs/guide/plugin/developer_guide/faq/troubleshooting.html)
and result in an exception when connecting. If you are experiencing a
bad_record_mac error set the following [system
property](http://wiki.eclipse.org/Mylyn/FAQ#System_Properties) in the
eclipse.ini: `-Dorg.eclipse.mylyn.https.protocols=SSLv3`

## Why are task hyperlinks not working?

For task hyperlinks in textual editors (e.g. Java editor) and other text
viewers (e.g. History view comments) you must associate the project that
contains the resource to the task repository.

  -
    *Project association can also come from 3rd party metadata trough
    the contrubuted [extension
    point](Mylar_Integrator_Reference#Mapping_from_projects_to_Task_Repositories "wikilink").
    [Subclipse](http://subclipse.tigris.org/) and [Maven integration for
    Eclipse](http://docs.codehaus.org/display/M2ECLIPSE/Integration+with+Mylyn)
    plugins contributing it. See few more details
    [here](http://jroller.com/page/eu?entry=linking_projects_from_the_eclipse).*

Note that to view a hyperlink you must hold down the `Ctrl` key when
hovering over the reference to the task. References to tasks are
connector specific and the common reference is found on the top left of
the task editor and other conventions tend to follow those used in the
web UI (e.g. “bug 123” for Bugzilla, “ABC-123” for JIRA).

![Image:mylyn-project-repository-association.gif](mylyn-project-repository-association.gif
"Image:mylyn-project-repository-association.gif")

# Bugzilla Connector

## What versions are supported?

  - We **recommend** using the latest
    [release](http://www.bugzilla.org/download/) of Bugzilla (3.4.x).

<!-- end list -->

  - Bugzilla 3.0.9 and higher is **officially supported**.

<!-- end list -->

  - Bugzilla 2.18.6 is the lowest version of Bugzilla the connector is
    **known to work with**. If you are getting errors that indicate
    failure to update attributes this may be due to use of an older
    Bugzilla.

<!-- end list -->

  - If you are using **Bugzilla 2.18** and are getting **mid-air
    collisions** this is likely due to incorrectly formatted timestamp
    field in the underlying bugs database table
    ([bug 149513](https://bugs.eclipse.org/bugs/show_bug.cgi?id=149513)).
    This can be resolved by upgrading to a more recent release of
    Bugzilla server.

### Tips for server administrators

Mylyn periodically checks config.cgi to retrieve the repository
configuration. On Eclipse.org this resulted in heavy CPU Load for the
regeneration and a big surge in band width use.

  - This configuration seldom changes so can be cached and served from a
    file instead of being regenerated every time. While the size of this
    file tends to be small when hosting less than a dozen projects, it
    can be large on repositories holding large numbers of projects, e.g.
    900K on bugs.eclipse.org.
  - Generated bugzilla output contains a lot of unnecessary whitespace
    which can be trimmed before caching. For bugs.eclipse.org this
    reduces the file to about <em>660K</em>.
  - The remaining file contains a lot of redundancy so can be gzipped
    for further reduction. On bugs.eclipse.org this leaves about *28K*,
    a considerable saving.

Mylyn has been modified to accept gzip encoding on all requests, and
will do content negotiation. See
[bug 205708](https://bugs.eclipse.org/bugs/show_bug.cgi?id=205708).

**To add caching for your Bugzilla repository:**

  - Change the name of config.cgi to config-stock.cgi and get the
    caching code in a new config.cgi.
  - The current version of this caching config.cgi script is hosted at:

` via CVS: :pserver:anonymous@dev.eclipse.org:/cvsroot/technology/org.eclipse.phoenix/infra-scripts/bugzilla/`
` or: `<http://dev.eclipse.org/viewcvs/index.cgi/org.eclipse.phoenix/infra-scripts/bugzilla/?root=Technology_Project>

  - Modifications on this script are followed on
    [bug 205416](https://bugs.eclipse.org/bugs/show_bug.cgi?id=205416)

## Why are queries failing?

  - If **queries are not working** correctly ensure that you have the
    right Bugzilla server version selected for the corresponding
    repository: *Task Repositories (View) →* right+click the repository
    *→ Properties*. For supported versions see the [download
    page](http://www.eclipse.org/mylar/dl.php). If the repository is
    still not functioning it may be due to authentication or
    connectivity problems. If that does not resolve the problem please
    post a message to the newsgroup or [submit a
    bug](http://www.eclipse.org/mylar/bugs.php).

## Why do I see my old username?

If you change the username/email address on your Bugzilla account you
may notice that some tasks still have the old username/email. Explicitly
synchronize the task via the *Task List* popup menu or *Task Editor*
toobar in order to update your username.

## Why do tasks fail to open?

  - If upon opening a bug, the Bugzilla tab only displays a warning
    “**Could not download task data, possibly due to timeout or
    connectivity problem. Please check connection and try again.**”,
    ensure that your repository is returning XML data by pointing your
    browser to <your-repository-url>`/show_bug.cgi?id=1&ctype=xml` to
    show the contents of bug 1 in XML form. The Bugzilla client requires
    that bugs be accessible in XML form. If the repository doesn’t
    support xml then it is likely that the repository is too old (Mylyn
    currently supports Bugzilla 2.18 and later).

<!-- end list -->

  - If **reports fail to load** or **reports fail to synchronize** (task
    description remains *italic*), check the error log for a “**File not
    found**” error pointing to `bugzilla.dtd` or a “**Failed to retrieve
    products from server**” error message, these can result when
      - the `urlbase` parameter is not set on the bugzilla server
      - your `urlbase` parameter is incorrect, e.g. it contains
        `index.cgi`
      - your bugzilla installation is missing the `bugzilla.dtd` file.
        See:
        [bug\#161759](https://bugs.eclipse.org/bugs/show_bug.cgi?id=161759)

<!-- end list -->

  - If **attributes are missing options** in the bug editor (ie. missing
    a recently added milestone,
    [bug\# 155431](https://bugs.eclipse.org/bugs/show_bug.cgi?id=155431)):
      - Update attributes by choosing *Update Attributes* from the
        context menu in the *Task Repositories* view
      - Synchronize the task in the Task List
      - Reopen the task - new options should be available.

## Why do tasks fail to submit?

  - **Error upon submit: unable to make any match for name/email
    entered.** If your bugzilla is configured for user names rather than
    full email address the QA Contact field will cause the submit to
    fail
    ([bug\# 166555](https://bugs.eclipse.org/bugs/show_bug.cgi?id=166555)).
    To resolve, select ‘Local users enabled’ option on the Repository
    Configuration page.

<!-- end list -->

  - If tasks **fail to submit** with credentials error, but the
    repository validates fine, make sure that you’ve correctly setup
    your account’s username and password and are not using the HTTP
    authentication fields instead.
      - Click on the "Submit disabled, please check Credentials and
        refresh" error, which is a link to the Task Repository page for
        Bugzilla, for example. Also accessible via the "Bugzilla" link
        at the top of the task page. Removing and re-adding the password
        for your User ID may help remove this error.

<!-- end list -->

  - If tasks **fail to submit** with credentials error, but the
    repository validates fine, make sure that you’ve correctly setup
    your bugzilla instance’s cookie domain under the required settings.
    The cookie domain must lead with a dot.

<!-- end list -->

  - If **attachments are failing to submit** and you see that after
    processing the attachment, the bugzilla bug shows a size of “bytes”
    (no numbers), your database may be dropping the packet sending the
    file. **On MySQL**, check the [max_allowed_packet
    directive](http://dev.mysql.com/doc/refman/5.0/en/packet-too-large.html).
    You may see errors like: `DBD::mysql::st execute` failed: Got a
    packet bigger than 'max_allowed_packet' bytes \[for Statement
    “INSERT INTO attach_data (id, thedata) VALUES (38, ?)”\] at
    `/path/to/bugzilla/attachment.cgi` line 993. Also, **check the
    maximum attachment size** in *Bugzilla Parameters → Attachments*.

<!-- end list -->

  - If a submit fails with an **Invalid Username or Password** error
    even though repository settings do validate, make sure that cookies
    could be set. See also
    [bug 175502](https://bugs.eclipse.org/bugs/show_bug.cgi?id=175502)

## What time zone is used in the task editor?

  - The **times** that appear in the Bugzilla bug editor (ie. created,
    modified) are in your local machine’s time zone.

## Known limitations

  - The `usermatchmode` is not currently supported
    ([bug 168204](https://bugs.eclipse.org/bugs/show_bug.cgi?id=168204))
    and as such full email addresses need to be used.

<!-- end list -->

  - The `usevisibilitygroups` parameter is not supported
    ([bug\#180876](https://bugs.eclipse.org/bugs/show_bug.cgi?id=180876)).
    Group assignment will currently be lost if updated using the
    Bugzilla rich task editor.

<!-- end list -->

  - Version 1.0 of Mylyn presents an error message upon new comment
    submission to Red Hat’s public Bugzilla repository. The comment is
    in fact posted. This issue is resolved in Mylyn 2.0M2 and higher.
    ([bug\#183251](https://bugs.eclipse.org/bugs/show_bug.cgi?id=183251))

<!-- end list -->

  - The server setting "Timezone used to display dates and times" must
    be set to "Same as Server," otherwise you will get a security token
    error when performing any submit operation other than submitting a
    new bug. This may also manifest as a midair collision.
    ([bug\#429523](https://bugs.eclipse.org/bugs/show_bug.cgi?id=429523))

# JIRA Connector

Atlassian has ended support for the Atlassian JIRA connector See [this
blog
post](https://developer.atlassian.com/blog/2015/06/discontinuing-ide-connectors-support/)
for more details.

# Trac Connector

## What are the server requirements?

The Trac connector supports two different access methods: The
recommended XML-RPC mode offers complete integration with Mylyn but
requires additional setup and privileges which may not be available to
all users. Web mode offers less functionality but will work with any
public Trac repository.

#### XML-RPC (recommended)

Requirements:

  - Trac 0.10 or later
  - [XmlRpcPlugin](http://trac-hacks.org/wiki/XmlRpcPlugin) rev. 1950 or
    later

This access method offers editing of tasks in a rich editor, attachment
support and offline editing. It requires the
[XmlRpcPlugin](http://trac-hacks.org/wiki/XmlRpcPlugin) for Trac to be
enabled for the accessed repository. The XmlRpcPlugin provides a remote
interface to the Trac repository and is distributed separately from Trac
(see [\#217](http://trac.edgewall.org/ticket/217)). See these [install
instructions](http://trac-hacks.org/wiki/XmlRpcPlugin#Installation) for
requirements and documentation.

In order to access the repository through XML_RPC each user needs to
have the corresponding permission which can be configured through Trac's
admin tool:

`trac-admin `</path/to/projenv>` permission add `<user>` XML_RPC`

#### Web

Requirements:

  - Trac 0.9 or later

In this mode the standard Trac web interface is used for repository
access. Tickets may be created and edited through a web browser. Offline
editing and attachments are not supported.

## Recommended Trac version

Mylyn works with any stable Trac release that is version 0.9 or later
(see below for known limitations). Mylyn works best when used with
Trac’s XML-RPC Plugin (see above) but we do not recommend a particular
Trac version.

The Trac connector tests are run against these Trac versions:

  - Trac 0.11.6, XML-RPC Plugin 1.0.6 (r7194)
  - Trac 0.10.5, XML-RPC Plugin 0.0.2 (r2125)
  - Trac 0.9.6 (support ended with Mylyn 3.3)

## Does Mylyn support Trac 0.11?

When Mylyn 3.2.1 or later is used with the latest version of the [Trac
XmlRpcPlugin](http://trac-hacks.org/wiki/XmlRpcPlugin) from [SVN
trunk](http://trac-hacks.org/svn/xmlrpcplugin/trunk/) the Mylyn Trac
connector is fully functional (.

## Why do I get an HTTP Error 500 Internal server error when creating a ticket that contains non-ASCII characters?

Problems related to character encodings have been reported when Trac is
run with Python 2.3. Upgrading to Python 2.4 may help to resolve this.
Please comment on [bug
\#188363](https://bugs.eclipse.org/bugs/show_bug.cgi?id=188363) if you
encounter an internal server error when creating a ticket that contains
non-ASCII characters.

## Known limitations

  - Trac 0.10.1
      - Known incompatibility with Trac XML-RPC Plugin. See
        [bug 164272](https://bugs.eclipse.org/bugs/show_bug.cgi?id=164272)
        for details.
  - Trac 0.10.3
      - Known incompatibility with old versions of the Trac
        HttpAuthPlugin (fixed in revision 1890 or later). The plug-in
        enables basic auth for XML-RPC when Trac AccountManagerPlugin
        for form based authentication is used. See
        [bug 168413](https://bugs.eclipse.org/bugs/show_bug.cgi?id=168413)
        for details.
  - Trac 0.11
      - Known incompatibility with XML-RPC Plugin version 1.0.2 - 1.0.5.
        Using 1.0.6 or later is recommended.

## Why are tasks opened in a web browser and not in the rich editor?

Please make sure that the access type in the repository properties is
set to XML-RPC. This requires Trac 0.10 and XML-RPC (see above).

## Which URLs does Mylyn access in a Trac repository?

XML-RPC:

  - The expected URL is either /xmlrpc or /login/xmlrpc (if login
    credentials are provided)

Web:

  - Authentication: /login
  - Querying: /query?format=tab…
  - Synchronizing ticket details: /ticket/…
  - Getting repository configuration to populate query dialog: /query or
    /newticket

The web mode relies on screen scraping and is likely to fail if the
design (i.e. HTML output) of the Trac repository is heavily customized.

## Problems opening the web editor on Linux

If you’re having problems opening the web task editor on Linux and the
message **Could not create Browser page: XPCOM error -2147221164**
appears in the error log, try installing the packages **xulrunner** and
**xulrunner-gnome-support** on your Linux distribution.

## Which Trac Plugins are supported by Mylyn?

  - [XML-RPC Plugin](http://trac-hacks.org/wiki/XmlRpcPlugin) for
    rich-editing and attachment support
  - [Account Manager
    Plugin](http://trac-hacks.org/wiki/AccountManagerPlugin) for
    form-based authentication (Mylyn 2.0 or higher)
  - [Master Tickets
    Plugin](http://trac-hacks.org/wiki/MasterTicketsPlugin) for sub-task
    support (Mylyn 2.3 or higher)

# Web Templates Connector

## Where can I find the Web Templates connector?

It is available from the incubator update site. Please see
<http://www.eclipse.org/mylyn/downloads/> for a list of update sites.
(http://www.eclipse.org/mylyn/downloads is not an update site itself.)

## Why can’t I connect using one of the existing templates?

The Web Connector have a “Preview” button in “Advanced Configuration”
section in the “Query” preferences dialog. If you get an error or
preview table does not show the expected list, you can use “Open” button
to verify if web page downloaded by the Web Connector is correct.

Alternatively, you can use Query Pattern like
({Description}.+?)({Id}\\n) to see content of the retrieved page in
preview table and compare it with the source of the web page for the
same url loaded into the web browser.

If retrieved web page is correct, but “Preview” don’t show expected
results you need to check the “Query Pattern”. A popular mistake is an
unmasked ‘?’ that separates request parameters in the url). For example:

    <a href="show_bug.cgi\?id\=(.+?)">.+?<span class="summary">(.+?)</span>

If you don’t see the correct web page, check the following:

  - query URL or substituted parameters are correct
      - **Note:** only the parameters are URL-encoded, e.g. the query
        URL `x:${y}` with the substituted parameter `${y}` set to `a:b`
        gets “`x:a%3Ab`” (only the substituted parameters are URL
        encoded
  - web application require user to login and login configuration in the
    Web Connector repository configuration is correct (see Web Connector
    repository settings)

To debug web application auth further, you could use the wget tool (on
Windows it available as a standalone command line tool and also included
with Cygwin) and run the following command:

    wget -v -d -o query.log -O query.html "http://your.query.url"

If repository require basic http auth, you’ll need to use
*--http-user=USER* and *--http-password=PASS* options.

Then open file *query.html* in the web browser and check if it show list
of issues you need to fetch from the web server. If it does have correct
list, then there could be a problem with query pattern used for parsing.

If *query.html* does not show expected list of issues you can check
*query.log* for server responses and try to identify if server require
authentication, redirecting your requests somewhere or issue any other
errors.

## Known limitations

  - In Mylyn 1.0: if a web server responds by requesting a redirect to
    an absolute URL while fetching a resource, the connector falsely
    prepends “/” to the URL and the request will fail. The workaround is
    to use final url where redirect is pointing to (you can find it as
    describe above). See
    [bug 167282](https://bugs.eclipse.org/bugs/show_bug.cgi?id=167282)
    for details.

## Where can I find additional templates?

  - [Instructions for Google
    Code](http://alblue.blogspot.com/2009/04/google-code-and-mylyn-redux.html)

# Task-Focused UI

## What is the Task-Focused UI?

When you activate a task, Mylyn automatically maintains a task context
by monitoring your interaction. The task context provides a predictable
degree-of-interest weighting of the relevance of the elements (files,
classes, methods, etc.) and relations that you work with to the active
task. The Task-Focused UI uses the task context to reduce information
overload and to automate the management of editors, views, change sets
and other UI elements. This increases productivity while working on the
task and also makes it much easier to multitask because you can switch
task contexts with a single click.

Here are some of the ways the context is used to focus the UI on the
active task:

  - Filtering uninteresting elements from views (e.g. the Package
    Explorer) and decorating the most interesting elements
  - Automatic expansion management in views
  - Automatic code folding in editors
  - Reordering of content assist proposals
  - Automatic management of open editors
  - Automatic change set management
  - Commit message auto-population

## Why do files disappear from Focused views when I close them?

By default Mylyn automatically manages the set of open files to match
the task context, so that you don’t have to. This ensures that the
editor list (viewable via mechanisms like Ctrl+E) corresponds to what
you in views like the *Package Explorer* when they are in Focused mode.
When you close a file manually, you express that it is uninteresting,
and as such it will be removed from the task context. It will also
disappear from the corresponding automatically managed change sets for
the same reason. This behavior can be turned off via *Preferences →
Mylyn → Context → Manage open editors to match task context*. However,
it is highly recommended since Mylyn will prevent the number of editors
from bloating by automatically closing editors for elements that have
decayed in interest, and always keep the editors for interesting
elements open.

## Why did all my editor tabs disappear?

When you deactivate a task, all editors will be closed, and then when
you reactivate the task all the windows will be open again. Try it, it’s
fun.

Mylyn actively manages your open editors with task context. It takes
some getting used to, but enables switching between tasks when you are
multitasking without cluttering your editor tabs. This editor management
can be disabled via *Window → Preferences → Mylyn → Context*. However,
before disabling it consider reading the *“Managing open editors…”*
section of [Task-focused programming with
Mylar](http://www-128.ibm.com/developerworks/java/library/j-mylar2/index.html#N10116).

## How do I get rid of an element if it is not interesting?

When a view is focused elements will disappear on their own if they are
not repeatedly selected via a mechanism called interest decay. Note that
decay does not use the wall clock, but instead relies on the number of
selections that you have made when working on that task to determine
which elements disappear. This helps make it feel very predictable.

If you want want to force one or more elements to disappear from the
context use the **Remove from Focus** action on the context menu. Note
that the element will still be part of the task context since it was
previously part of the interaction.

If you want to permanently delete the element from the interaction
history use the **Remove from Context** action on the **Context** tab of
the **Task Editor**. For example, if a company private element was part
of a task context that is to be shared with a public repository, this
action can be used to clean it up before sharing. Note that elements
will be removed from the task context recursively.

## Which Focused UI features can I turn off?

**All of them.** When no task is active neither are any of Mylyn’s
features. When working with task contexts Mylyn’s Focused UI features
are all optional and in general configurable. While many find it the key
benefit of Mylyn, the entire Focused UI is optional and can be
uninstalled via *Help → Software Updates → Manage Configuration*.

The following table summarizes how the key features can be toggled:

| **UI Mechanism**                | **Example/description**         | **Toggle using**                                                                                        |
| ------------------------------- | ------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Interest filtering              | Package Explorer                | *Focus on Active Task* button on view toolbar                                                           |
| Automatic toggling of filtering | Package Explorer                | ''Preferences → Mylar → Context → Toggle focused mode..                                                 |
| Interest decoration             | Bolding of landmark elements    | *Preferences -\> General -\> Appearance -\> Label Decoration*                                           |
| Content assist                  | Ranking of interesting elements | Eclipse 3.2: *Java -\> Editor -\> Content Assist -\> Work in Progress -\>* turn off Mylyn, turn on Java |
| Active change sets              | Grouping of changes by tasks    | *Preferences -\> Mylyn -\> Team*                                                                        |
| Editor management               | Auto opening/closing of editors | *Preferences -\> Mylyn -\> Editor Management*                                                           |
| Active views                    | Active Search and Hierarchy     | Only on if view is active                                                                               |

For additional configuration options see the *Mylyn* and *General →
Appearance* preference pages.

**Note**: if you have turned off automatic focusing of views consider
using the *Navigate → Quick Context View* facility.

## Why can’t I Alt+Click to references libraries?

Due to , if you have the “Show ‘Referenced Libraries’ Node” option
enabled in the view menu of the *Package Explorer* you will not be able
to Alt+click to library nodes if there isn’t a library visible already.
Disable this option to make Alt+Click work.

## Why is the *Link with Editor* button disabled?

Mylyn automatically turns on editor linking when the view is focused,
since the main use case for turning it off (having the view jump around)
is remedied by focusing the view. In other words, the button is pressed
for you automatically and we need to ensure that it cannot be manually
unchecked, which is why it appears disabled.

## What happened to the Active Search and Active Hierarchy views?

These views were not included in the Mylyn 1.0 release because they
never made it beyond the experimental phase.

  - The *Active Search* view has not been sufficiently tuned to adapt to
    the lifecycle of a task context, and as a result requires manual
    manipulation of the degree-of-separation scope as you work on
    long-running tasks. Otherwise it becomes overloaded with elements.
    In addition, it is not yet clear whether an additional view is the
    right UI for this facility, and it is hard to find room for an
    additional view of this size on screen resolutions of 1600x1200 and
    smaller.
  - The *Active Hierarchy* view is also hard to allocate space for,
    especially when using the in-place hierarchy (Ctrl+T) on a landmark
    can be a quick way to see the relevant part of the task context’s
    hierarchy.

These features still show promise in displaying task context and saving
repetitive searches, so we have not removed them. They have instead
moved to the Mylyn Sandbox, and can be used and experimented with by
following the [instructions on the Contributors
page](http://wiki.eclipse.org/index.php/Mylyn_Contributor_Reference#Sandbox).
For feedback on these views please use the corresponding bug reports or
newsgroup.

## Why does startup of org.eclipse.mylyn.context.ui take so long?

If you are seeing the Eclipse splash screen stall for 10s of seconds
while loading org.eclipse.mylyn.context.ui remove
`workspace/.metadata/.plugins/org.eclipse.core.runtime/.settings/org.eclipse.mylyn.resources.ui.prefs`
as a work-around. This files stores editor mementos and can sometimes
grow very large and affect startup time. This issue is being tracked on
.

# Context and Timing data

## How do I prevent code checked out from polluting my task context?

When checking out a new project, you must first deactivate the active
task. Otherwise all newly created files will become interesting.

## Why do I see strange elapsed times on my Planning tab?

Some platform/jvm combinations can fill with invalid timestamps. This is
known to have happened on Mac OSX 10.4 with Java 1.5. See
[bug 207419](https://bugs.eclipse.org/bugs/show_bug.cgi?id=207419). To
resolve you can try and manually edit
<workspace>/.metadata/.mylyn/contexts/activity.xml.zip.

## Is the backwards compatibility and refactoring of task context handled?

  - The Task List and Context Store are compatible across all
    currently-supported Eclipse versions. This means that you can use
    the same .mylyn data in both Eclipse 3.x.

<!-- end list -->

  - If elements have been renamed they may not appear as interesting
    when the context is activated.

# Java Development

## Content assist troubleshooting

Mylyn uses custom Content Assist processors in order to rank and
separate elements in the current task context. To see proposals ranked
according to interest you must have the *Java Proposals (Task-Focused)*
checkbox enabled in the list below and other Java proposals unchecked,
otherwise you will see duplicates.

**If you do not see any proposals, check this list** to ensure that
either the Mylyn or the plain proposals are enabled. You always recover
by disabling Mylyn's content assist through pressing "Reset Defaults" in
the preferences under Window → Preferences → Java → Editor → Content
Assist → Advanced.

![Image:Mylyn-content-assist-prefs.png](Mylyn-content-assist-prefs.png
"Image:Mylyn-content-assist-prefs.png")

**Why do I see duplicate proposals?**

Ensure that you have only the *Task-Focused* proposals kinds enabled in
*Window → Preferences → Java → Editor → Content Assist → Advanced*,
otherwise you will see duplicates.

If you use proposals via Ctrl+Shift+Space instead of the typical
Ctrl+Space you will see duplicates. Vote for JDT/Text
[bug 147781](https://bugs.eclipse.org/bugs/show_bug.cgi?id=147781) if
you use this mechanism. Also see:
[bug 129080](https://bugs.eclipse.org/bugs/show_bug.cgi?id=129080)

**Why do I get an error message when using content assist?**

If after invoking Content Assist you see an error message dialog that
states:

`The extension took too long to return from the 'computeCompletionProposals()' operation`

this is most likely due to something interrupting the proposal operation
(e.g. garbage collection). Ignore it if it does not recur, increase
Eclipse’s memory if it does (e.g via `-Xmx384M` command line argument).
See [bug 141457](https://bugs.eclipse.org/bugs/show_bug.cgi?id=141457)
for more details.

Note that Mylyn should only add a trivial amount of overhead to content
assist computation, however, the standard content assist mechanism will
not report timeouts of this sort (i.e. taking longer than 5s to compute
proposals). If the system that you are working on is so large that
increasing memeory does not reduce the timings to avoid the message, you
could also consider disabling the Mylyn-specific content assist, as
described above, but if doing so please comment on .

![Image:mylyn-content-assist-timeout.gif](mylyn-content-assist-timeout.gif
"Image:mylyn-content-assist-timeout.gif")

## Why do interesting elements not show in the Project Explorer?

The *Package Presentation → Hierarchical* mode is not supported on the
*Project Explorer* view in Eclipse 3.2 through 3.3M3 and possibly later
versions
[bug 161362](https://bugs.eclipse.org/bugs/show_bug.cgi?id=161362). Use
the view menu to set *Package Presentation → Flat* as a work-around.

## How do I stop declarations from showing in the Package Explorer?

If you don’t like Mylyn’s constant showing of Java members in the
*Package Explorer*, select the drop-down menu, then *Filters…* and
enable the *Mylyn Java Declarations Filter*. It will then stick in the
menu in case you want to toggle between modes.

Note that this will hide interest information about members that aren’t
in your current file (e.g. showing you which methods are landmarks).
This means that you will need to commit those methods to memeory, and
the next time that you start working on the task you will have the
burden of figuring out what they are. On smaller screen resolutions this
mode can be useful, but also consider turning the Package Explorer into
a fast view.

![Image:mylar-java-filtering-declarations.gif](mylar-java-filtering-declarations.gif
"Image:mylar-java-filtering-declarations.gif")

## Why does nothing show up in the Active Search or Active Hierarchy?

As you work, elements become Landmarks (bold decoration), and these
elements populate the *Active Search* and *Active Hierarchy* views. To
force an element to populate the views manually, make it a Landmark by
`right+clicking` or hitting `Ctrl+Alt+Shift+UpArrow`.

## Known limitations

  - [Bug 106678](https://bugs.eclipse.org/bugs/show_bug.cgi?id=106678):
    The Project Explorer’s Hierarchical Java package presentation layout
    is not supported on Eclipse 3.3Mx, and interesting elements will be
    hidden if enabled. Work-around is to use the default Flat package
    presentation.

# Team Support

## My change set is missing or doesn’t contain elements it should. Help\!

If a task change set disappears or is missing items, toggle the
Incoming/Outgoing mode of the Synchronize view via its toolbar button.

## Why does task change set not appear when I modify files?

A task change set should appear if you activate a task and modify a file
connected to a compatible source repository (e.g. CVS, SVN). If it does
not try the following:

  - Ensure you have installed the [*Mylyn Bridge: Eclipse IDE*
    feature](http://www.eclipse.org/mylyn/downloads/). Note that
    previously this feature was named Eclipse SDK and not distributed
    with the Java-only Eclipse download
    ([bug 191793](https://bugs.eclipse.org/bugs/show_bug.cgi?id=191793)).

<!-- end list -->

  - If you are using Subclipse or Subversive, make sure you have the
    respective integration for Mylyn installed. Note that change sets
    are not currently supported in the EGit connector.

<!-- end list -->

  - Verify that the [configured *Synchronize View* is configured for
    change sets](Mylyn/User_Guide#Task-focused_Change_Sets "wikilink").

<!-- end list -->

  - Verify that Mylyn Tasks UI and Mylyn Team UI are enabled under
    General → Startup and Shutdown in the Eclipse preferences.

If the above are working but the change set appears to be missing
relevant files:

  - You may be seeing the *Synchronize* view’s refresh problem
    ([bug 142395](https://bugs.eclipse.org/bugs/show_bug.cgi?id=142395)).
    Toggle from *Incoming/Ougtoing* to *Incoming* mode and back again to
    refresh the view.

<!-- end list -->

  - If the files or change set are still missing deactivate and
    reactivate the task to force a full refresh.

## Why do files disappear from the change set when I close them?

If you have the *Preferences → Mylyn → Context → Manage open editors to
match task context* option enabled, Mylyn will perform editor management
so that you don’t have to. Closing a file makes it less interesting, and
causes it to disappear from the active task context, and hence from the
change set. This option prevents you from having to manage the set of
open files, will automatically close editors for files that become
uninteresting, and will ensure that the open editors match the task
context.

## Why am I missing elements when I retrieve someone else’s context?

To identify elements within a project, Mylyn relies on the name of the
project being consistent across workspaces. If the project name in the
workspace that the context was created with is different than its name
in your workspace, the task context will not show elements within that
project
([bug 164058](https://bugs.eclipse.org/bugs/show_bug.cgi?id=164058)).
The other case where context can be lost is if the elements change names
outside of the workspace (
[bug 164243](https://bugs.eclipse.org/bugs/show_bug.cgi?id=164243)).

The work-around is to use the same project names across your team’s
workspaces. We recommend the following two approaches for standardizing
on project names:

  - Use **Team Project Sets**: these are a very useful Eclipse facility
    that allows your entire team to check out numerous projects from
    version control by importing a single file. Create a project set via
    *File → Export → Team Project Set*, host this file somewhere
    accessible, then have others import vai *File → Import → Team
    Project Set*.
  - Have developers check out projects into their workspace without
    renaming them. The above is a shortcut for doing this. If
    alphabetical sort order in the *Package Explorer* is a problem,
    organize your projects via *Project Explorer → view menu → Top Level
    Elements → Working Sets*.

# WikiText

## What is WikiText?

WikiText is a set of plug-ins for Eclipse that provide lightweight
markup (wiki) parsing, editing and display capabilities to the Eclipse
platform and Mylyn. WikiText provides a parser for wiki markup and
converts the markup to HTML, Docbook, DITA, or Eclipse Help format,
either via the API or by using Ant tasks. WikiText also provides UI
components (such as an editor) integrating with Eclipse and the Mylyn
task editor.

## Where can I get WikiText?

WikiText is available on the Mylyn update site. Unreleased weekly builds
are also available via the Mylyn Weekly Builds update site. See the
[Mylyn Downloads](http://www.eclipse.org/mylyn/downloads/) for details.

A stand-alone WikiText package is also available for download from the
[Mylyn Downloads](http://www.eclipse.org/mylyn/downloads/) page.

Incubation features and unreleased builds are available from the
[nightly update
site](http://download.eclipse.org/mylyn/snapshots/nightly/docs) by
installing the WikiText Extras feature. These builds should be used with
caution as they are untested and potentially unstable.

## How does WikiText integrate with Mylyn?

WikiText extends the Mylyn task editor to be markup-aware. Comments and
description text is formatted according to the configured markup
language. The description and comment editors are aware of markup and
provide content assist, markup help and preview.

More details can be found here: [Rich Editing for Tasks via Mylyn
WikiText (Mik
Kersten)](https://www.tasktop.com/blog/rich-editing-tasks-mylyn-wikitext)

## How do I enable/disable WikiText extensions to Mylyn?

This is done on a per-repository basis. When WikiText is installed it is
automatically enabled for all configured task repositories for which
there is a default markup language setting.

To change the default settings open the Mylyn <i>Task Repositories</i>
view, right-click your task repository and select <i>Properties</i> from
the context menu. In the properties dialog choose the <i>Editor</i>
settings (you may need to click on it to expand the section).

To disable WikiText for your repository, select <i>Plain Text</i>.

To enable WikiText for your repository, select the desired markup
language. The default markup language if available for your repository
is labeled <i>(default)</i>

## Where can I find WikiText documentation?

WikiText documentation is installed into the Eclipse help system when
WikiText is installed. To see the WikiText documentation open Eclipse,
from the <i>Help</i> menu open <i>Help Contents</i>. You will find the
<i>WikiText User Guide</i> under <i>Tasks</i> in the table of contents.
If you're interested in integrating with WikiText then take a look at
the <i>WikiText Developer Guide</i>.

The same WikiText documentation is also available in the stand-alone
distribution and online:

  - [WikiText User
    Guide](http://help.eclipse.org/luna/topic/org.eclipse.mylyn.wikitext.help.ui/help/Mylyn%20WikiText%20User%20Guide.html)
  - [WikiText Developer
    Guide](http://help.eclipse.org/luna/topic/org.eclipse.mylyn.wikitext.help.ui/help/devguide/WikiText%20Developer%20Guide.html)

## How do I run the WikiText Ant tasks?

The WikiText documentation provides detailed information on how this is
done in the <i>WikiText User Guide</i>.

## Can I use WikiText without Eclipse?

Yes, the WikiText markup parser and Ant tasks may be used outside of
Eclipse without reference to any Eclipse classes.

Detailed information about using WikiText APIs is available within the
<i>WikiText Developer Guide</i>. Information about using WikiText Ant
tasks is available within the <i>WikiText User Guide</i>.

## What output can WikiText create?

WikiText can create HTML, Eclipse Help, DITA, DocBook and XSL-FO from
wiki markup. Using the WikiText APIs you can also extend WikiText to
create other output formats. DITA, DocBook and XSL-FO can all be used to
create PDF. More information is available in the <i>WikiText User
Guide</i>.

## What wiki markup languages does WikiText support?

WikiText can parse the following markup languages:

  - Confluence
  - MediaWiki
  - Markdown
  - Textile
  - TracWiki
  - TWiki

Additionally the following markup languages are in incubation status,
available from the WikiText [nightly update
site](http://download.eclipse.org/mylyn/snapshots/nightly/docs):

  - Creole (see [Mylyn WikiText Creole
    HOWTO](Mylyn/WikiText/Creole "wikilink"))
  - AsciiDoc (see [AsciiDoc HOWTO](Mylyn/WikiText/AsciiDoc "wikilink"))
  - A Markdown implementation that conforms to the
    [CommonMark](http://commonmark.org) specification

WikiText is also designed to make it easy to add support for new markup
languages.

## Why doesn't the preview tab show up in the WikiText editor?

The preview tab is not shown if the SWT browser is not configured
correctly. See [The SWT
FAQ](http://www.eclipse.org/swt/faq.php#browserspecifydefault) for
details.

## Where can I find out more about WikiText?

  - [Mylyn WikiText 1.0 Released (David
    Green)](http://greensopinion.blogspot.com/2009/03/mylyn-wikitext-10-released.html)
  - [Rich Editing for Tasks via Mylyn WikiText (Mik
    Kersten)](http://tasktop.com/blog/eclipse/rich-editing-for-tasks-via-mylyn-wikitext)
  - [Getting started with WikiText (Peter
    Friese)](http://www.peterfriese.de/getting-started-with-wikitext/)
  - [Advanced WikiText (Peter
    Friese)](http://www.peterfriese.de/advanced-wikitext/)
  - [DocumentationGuidelines/Example](DocumentationGuidelines/Example "wikilink")
  - [Mylyn WikiText Produces PDF (David
    Green)](http://greensopinion.blogspot.com/2009/04/mylyn-wikitext-produces-pdf.html)
  - [Mylyn WikiText wiki](Mylyn/WikiText "wikilink")
  - [WikiText & Eclipse: Making Documentation Easier (Jon
    Dowdle)](http://jdowdle.com/wp/2010/04/wikitext-eclipse-creating-documentation/)
  - [Diagrams in wiki markup with Mylyn WikiText, DOT, and Zest (Fabian
    Steeg)](http://fsteeg.wordpress.com/2010/02/07/diagrams-in-wiki-markup-with-mylyn-wikitext-dot-and-zest/)
  - [The original WikiText incubation project
    page](Mylyn/Incubator/WikiText "wikilink")
  - [Textile-J Is Moving to Mylyn
    WikiText](http://greensopinion.blogspot.com/2008/08/textile-j-is-moving-to-mylyn-wikitext.html)

# Integration with other tools

See the **[Mylyn Extensions](Mylyn/Extensions "wikilink")** page for a
listing of integration downloads.

Mylyn relies on [Bridges](Mylyn/Architecture "wikilink") to integrate
the context model with the structure and UI features of domain-specific
tools. To create a Bridge, see [Creating
Bridges](Mylyn/Integrator_Reference#Creating_Bridges "wikilink").

The core set of Bridges supports the Eclipse SDK (i.e. has bridges for
Java, JUnit, PDE, Ant and Resources). The Resources Bridge enables a
basic level of interoperability with other tools that use files (e.g.
`.php, .cpp`), and enables Mylyn filtering to work for generic views
that show those files (i.e. the *Project Explorer*, *Navigator*) and any
corresponding markers (i.e. the *Problems* and *Tasks* views). This is
only the most basic context model integration, and does not offer the
benefits of a specialized structure bridge, such as making declarations
part of the context and providing *Active Search* facilities. Without a
Bridge Mylyn cannot be applied to tool-specific views.

**If you would like to see support for a particular tool**, first do a
search of the open bridge requests and [vote for the corresponding
bug](https://bugs.eclipse.org/bugs/buglist.cgi?query_format=advanced&short_desc_type=anywordssubstr&short_desc=%5Bbridge%5D&product=Mylyn&long_desc_type=allwordssubstr&long_desc=&bug_file_loc_type=allwordssubstr&bug_file_loc=&status_whiteboard_type=allwordssubstr&status_whiteboard=&keywords_type=allwords&keywords=&bug_status=NEW&bug_status=ASSIGNED&bug_status=REOPENED&emailtype1=substring&email1=&emailtype2=substring&email2=&bugidtype=include&bug_id=&votes=&chfieldfrom=&chfieldto=Now&chfieldvalue=&cmdtype=doit&order=Reuse+same+sort+as+last+time&field0-0-0=noop&type0-0-0=noop&value0-0-0=)
if your tool is there, or [create a new
bug](http://www.eclipse.org/mylyn/bugs.php). Also consider adding your
experiences to the
["Integration..."](Mylyn/FAQ#Integration_with_other_tools "wikilink")
section of the Mylyn FAQ.

## Using Mylyn with WTP

Context modeling works at the file level, noting the limitation of
[bug 144882: interest filter fails on WTP Dynamic Web
Project](https://bugs.eclipse.org/bugs/show_bug.cgi?id=144882)

## External builders

If an external builder (e.g. Maven, pydev, or other Ant-based builders)
is producing output files that are being automatically added to your
context because they are not being marked "derived" as with
Eclipse-based builders. You may note that such files are always show as
interesting when they are generated or updated and can not be filtered
away, since Mylyn expects all files that have changed as part of the
task context to have interest.

In this case you can explicitly exclude these files from being added to
the task context the *Preferences -\> Mylyn -\> Resources* page. For
example, if the output folder of the builder is "target", you could set
this the following way. Similarly, you could add a filter for "\*.pyc"
to exclude all files generated with that extension.

Source code generators can be considered analogous since they produce
intermediate files. However, if you want to inspect the results of the
source code generation after it is done you can avoid setting the
exclusion. Note that if a large number of files was generated not all
generated files may be unfiltered.

![Image:mylar-resource-exclusion.gif](mylar-resource-exclusion.gif
"Image:mylar-resource-exclusion.gif")

# Misc

## Performance

### Retrieval of repository configuration

In order to present the valid options for attributes in the Task Editor,
the repository 'configuration' must be retrieved from the repository.
The default connector implementation requests a new configuration every
24hrs. In the case of Bugzilla, this is further refined by first
performing a head request on the configuration to see if the
Last-Modified header has changed. If so, the repository configuration is
retrieved. Additionally, Eclipse.org's webmaster has redirected the
config.cgi request to a static page, eliminating the processing overhead
server side. For details on server side optimization of Bugzilla see
[Mylyn_FAQ\#Tips_for_server_administrators](Mylyn_FAQ#Tips_for_server_administrators "wikilink").

## Command Line

The system properties below can used to change the behavior of Mylyn. To
set a property pass it on the command line when starting Eclipse:
`eclipse -argument`.

<table>
<tbody>
<tr class="odd">
<td><p>Argument</p></td>
<td><p>Mylyn Version</p></td>
<td><p>Description</p></td>
</tr>
<tr class="even">
<td><p><code>-no-activate-task</code></p></td>
<td><center>
<p>3.1</p>
</center></td>
<td><p>Disables task activation on startup. The last active task is not re-activated on startup if a workspace crash is detected.</p></td>
</tr>
</tbody>
</table>

## System Properties

The system properties below can used to change the behavior of Mylyn. To
set a property pass it on the command line when starting Eclipse:
`eclipse -vmargs -Dorg.eclipse.mylyn.property=value`. To pass a
parameter to tests run by maven, pass it like this in the maven
properies: `test.uservmargs=-Dorg.eclipse.mylyn.tests.all=true`.

<table>
<tbody>
<tr class="odd">
<td><p>System Property</p></td>
<td><p>Mylyn Version</p></td>
<td><p>Default</p></td>
<td><p>Description</p></td>
</tr>
<tr class="even">
<td><p><code>org.eclipse.mylyn.linkProviderTimeout</code></p></td>
<td><center>
<p>3.1</p>
</center></td>
<td><p>5000</p></td>
<td><p>Number of milli-seconds before link providers are timed out. Set to -1 to disable link providers timing out.</p></td>
</tr>
<tr class="odd">
<td><p><code>mylyn.discovery.directory</code></p></td>
<td><center>
<p>3.2</p>
</center></td>
<td><p><a href="http://www.eclipse.org/mylyn/discovery/directory.xml">http://www.eclipse.org/mylyn/discovery/directory.xml</a></p></td>
<td><p>URL for the discovery directory.</p></td>
</tr>
<tr class="even">
<td><p><code>org.eclipse.mylyn.wikitext.tests.disableOutput</code></p></td>
<td><center>
<p>3.4</p>
</center></td>
<td><p>false</p></td>
<td><p>Set to true to suppress output on the console when running Mylyn Docs tests.</p></td>
</tr>
<tr class="odd">
<td><p><code>org.eclipse.mylyn.tests.all</code></p></td>
<td><center>
<p>3.7</p>
</center></td>
<td><p>false</p></td>
<td><p>Set to true to run connector tests against all fixtures. The default is to run tests against the default fixture only.</p></td>
</tr>
<tr class="even">
<td><p><code>mylyn.test.server</code></p></td>
<td><center>
<p>3.7</p>
</center></td>
<td><p>mylyn.org</p></td>
<td><p>Host name of server that hosts test repositories.</p></td>
</tr>
<tr class="odd">
<td><p><code>mylyn.tests.configuration.url</code></p></td>
<td><center>
<p>3.10</p>
</center></td>
<td></td>
<td><p>A repository URL. If specified, only this fixture will be run.</p></td>
</tr>
<tr class="even">
<td><p><code>mylyn.test.exclude</code></p></td>
<td><center>
<p>3.7</p>
</center></td>
<td></td>
<td><p>This is a comma separated list of test repository URLs that should be excluded when running tests. Example: <a href="http://mylyn.org/bugs36,http://mylyn.org/bugs40">http://mylyn.org/bugs36,http://mylyn.org/bugs40</a></p></td>
</tr>
<tr class="odd">
<td><p><code>org.eclipse.mylyn.https.protocols</code></p></td>
<td><center>
<p>3.7</p>
</center></td>
<td></td>
<td><p>A comma separated list of <a href="http://docs.oracle.com/javase/1.4.2/docs/guide/plugin/developer_guide/faq/troubleshooting.html">SSL protocols</a> that should be enabled when connecting through https. Example: SSLv3</p></td>
</tr>
<tr class="even">
<td><p><code>mylyn.test.skipBrowserTests</code></p></td>
<td><center>
<p>3.10</p>
</center></td>
<td><p>false</p></td>
<td><p>Set to true to skip browser tests that may cause JVM to crash. See  for more info.</p></td>
</tr>
<tr class="odd">
<td><p><code>org.eclipse.mylyn.http.connections.per.host</code></p></td>
<td><center>
<p>3.12</p>
</center></td>
<td><p>100</p></td>
<td><p>The maximum number of connections to be used per host by HTTP connection managers.</p></td>
</tr>
<tr class="even">
<td><p><code>org.eclipse.mylyn.http.total.connections</code></p></td>
<td><center>
<p>3.12</p>
</center></td>
<td><p>1000</p></td>
<td><p>The maximum number of connections allowed by HTTP connection managers.</p></td>
</tr>
</tbody>
</table>

## How can I report a dead-lock or a problem about a stalled UI?

The recommended way is to file a bug with a full thread dump using
jstack which is part of the Java Development Kit 6. These wiki pages
have more details on using jstack on different platforms:

  - [How to report a
    deadlock](http://wiki.eclipse.org/How_to_report_a_deadlock)
  - [Debugging
    Mylyn](http://wiki.eclipse.org/Mylyn_Contributor_Reference#Debugging)

## How do I enable debugging output for network communications?

Add the following lines to the `eclipse.ini` file in your eclipse
directory to enable tracing of header information for HTTP requests. Log
output is written to the console eclipse was started from. Make sure to
add these after the line that says **`-vmargs`**. Add a `-vmwargs` line
if there is none in the file.

`-Dorg.apache.commons.logging.Log=org.apache.commons.logging.impl.SimpleLog`
`-Dorg.apache.commons.logging.simplelog.showlogname=true`
`-Dorg.apache.commons.logging.simplelog.defaultlog=off`
`-Dorg.apache.commons.logging.simplelog.log.httpclient.wire.header=debug`
`-Dorg.apache.commons.logging.simplelog.log.org.apache.commons.httpclient=off`
`-Dorg.apache.commons.logging.simplelog.log.org.apache.axis.message=debug`
`-Dorg.apache.commons.logging.simplelog.log.org.apache.http=debug`
`-Dorg.apache.commons.logging.simplelog.log.org.apache.http.wire=error`

To also enable logging of message content, also add this lines:

`-Dorg.apache.commons.logging.simplelog.log.httpclient.wire.content=debug`
`-Dorg.apache.commons.logging.simplelog.log.org.apache.http.wire=debug`

## How do I enable debugging output for plug-ins?

Create a **`.options`** file in your eclipse directory and enable
tracing by including the corresponding lines which set the tracing
setting for a particular concern to true:

**JIRA**

`org.eclipse.mylyn.jira.core/debug/connector=true`
`org.eclipse.mylyn.jira.core/debug/dataHandler=true`
`org.eclipse.mylyn.jira.core/debug/repository=true`

**Trac**

`# trace authentication requests`
`org.eclipse.mylyn.trac.core/debug/authentication=true`
`# trace XML-RPC calls`
`org.eclipse.mylyn.trac.core/debug/xmlrpc=true`

Then start eclipse with **`-debug`**. You can also optionally pass a
filename to `-debug` if your `.options` file is not located in the
eclipse directory.

See also
[FAQ_How_do_I_use_the_platform_debug_tracing_facility%3F](FAQ_How_do_I_use_the_platform_debug_tracing_facility%3F "wikilink").

## Which usage monitoring framework should I use?

Three usage data collection frameworks have been created for Eclipse:

1.  [Eclipse Instrumentation
    Framework](http://dev.eclipse.org/viewcvs/index.cgi/platform-ui-home/instrumentation/index.html?revision=1.12):
    created as part of Platform UI, not released, not currently
    maintained
2.  [Mylyn Monitor UI Usage
    Reporting](Mylyn_Integrator_Reference#Monitor_API "wikilink"):
    created in 2004, maintained as part of the Mylyn project, first
    released in 2005
3.  [Usage Data
    Collector](http://www.eclipse.org/epp/usagedata/index.php):
    maintained as part of the EPP project, first released in 2008

While (1) and (3) are work in a similar way, there is a significant
difference between the approach used by the Mylyn Monitor and the other
usage data collectors. Instead of gathering statistics, the Mylyn UI
Usage Reporting component uses the interaction history that is captured
by the Mylyn Monitor. This is the same interaction history stream that
is used to determine the interest level of elements in Mylyn’s
Task-Focused UI and has been refined by long-term use of Mylyn’s
Task-Focused UI. The UI Usage Monitor is extensible, de-coupled from the
other parts of Mylyn and can be used independently.

There are several main benefits to the approach of capturing a full
interaction history stream instead of reporting on particular
statistics.

  - Since all of the interaction information is captured on the client,
    server-side reporting facilities can report on usage statistics that
    were not defined at deployment time. For example, during one of the
    Mylyn studies we did not decide to monitor which views were opened
    within which perspective. Since we had the full interaction
    histories this reporting was easy to add.
  - Interaction histories make it possible to report not just on the
    usage of the UI, but on the state of the UI at any given time. For
    example, in one study we wanted to know what actinos the user did
    after invoking a build and which views were visible while the
    invoked that action.
  - An explicit interaction history makes it easier to avoid and debug
    privacy problems. The Mylyn Monitor has a robust facility for
    filtering, encrypting and obfuscating data from interaction
    histories.

For an example study see:
<http://kerstens.org/mik/publications/mylar-ieee2006.pdf>

## How does Mylyn relate to IBM’s Jazz?

At the EclipseCon and JavaONE 2006 conferences IBM demonstrated previews
of Jazz, a collaborative team server and Eclipse-based client. Articles
have remarked on the similarities between Mylyn and Jazz because both
integrate tasks into Eclipse (Jazz’s “work items” and Mylyn’s “tasks”),
and both provide change sets grouped by task. But there are both
significant differences and complementary aspects to the two approaches.
A key goal of Mylyn is to provide an open source framework to support
integration of task management with *existing issue trackers and source
repositories*. According to the presentations, components that come with
Jazz include include a *next-generation issue tracker and source
repository* and related lifecycle management tools such as project
health. In addition, a driving and unique goal of Mylyn is to focus the
UI around a usage-based and degree-of-interested weighted task context,
which is complementary to the Jazz platform. Just as it integrates with
Mylyn’s Task List, Mylyn’s Task Focused UI and task context model
components are possible to integrate with other kinds of task management
systems, such as the one provided by Jazz.

Update: at EclipseCon 2007 the IBM Jazz team showed a Mylyn connector
for Jazz.

[Category:FAQ](Category:FAQ "wikilink")
[Category:Mylyn](Category:Mylyn "wikilink")