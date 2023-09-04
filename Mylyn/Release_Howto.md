[category:Mylyn](category:Mylyn "wikilink")

# <font color=red>Before the Release</font>

## Prepare Source Code

### Internationalize Messages

  - Run Source \> Find Broken Externalized Strings over all bundles
  - Run Source \> Externalize Strings over all bundles

### Update User Guide from the Wiki

  - Run `org.eclipse.mylyn.help.ui/build-helper.xml` as an Ant Build
    (ensure WikiText is checked out into your workspace)
  - Review the user guide and commit changes

### Update Copyright Notices

  - Update the year in the about.ini to the current year
  - Update the year in all feature.xml files to the current year for
    changed features
  - Update the year in copyright notices of changed source files:
    Install platform releng tools (available from the update site
    <http://download.eclipse.org/eclipse/updates/4.3>), Project context
    menu \> Fix Copyrights

## Release Review & IP Log

See <https://www.eclipse.org/projects/handbook/#release> for details.
*At least one release each year must have a release review, PMC
approval, and IP log submission. These are not required for subsequent
releases happening up to 1 year after the review.* Note that a [release
record](https://projects.eclipse.org/projects/mylyn/governance) is
always required (except for service releases).

### Submit IP Log for Review *at least 2 weeks before release*

  - Check the [downloads
    area](http://eclipse.org/projects/tools/downloads.php?id=mylyn).
    **The tool is
    [deprecated](https://dev.eclipse.org/mhonarc/lists/cross-project-issues-dev/msg15618.html)
    and a replacement is coming.**
      - Check that all Orbit bundles are tracked in approved CQs
      - The following missing CQ's are expected due to limitations of
        the project downloads scanner:

`axis-ant.jar (No CQ found)`
`axis.jar (No CQ found)`
`epub-ant.jar (No CQ found)`
`htmltext.jar (No CQ found)`
`jaxrpc.jar (No CQ found)`
`junit.jar (No CQ found)`

  - Submit IP log by going to
    <https://projects.eclipse.org/projects/mylyn/>, logging in,
    expanding the "Committer Tools" block and clicking "Generate IP
    Log."

### Seek PMC Approval for Release *at least 2 weeks before release*

  - email link to review documentation to <mylyn-pmc@eclipse.org>

### Schedule Release Review *at least 1 week before release*

Note: reviews are supposed to conclude on the first and third Wednesdays
of the month, so keep that timing in mind.

  - Once PMC and IP log approval are secured, send links to review
    document and mailing list discussion showing PMC approval to
    <emo@eclipse.org>

# <font color=red>Create Release Candidate Build</font>

## Update Target

See
[Mylyn/Build_Infrastructure\#Updating_Eclipse_Platform_Dependency_Versions](Mylyn/Build_Infrastructure#Updating_Eclipse_Platform_Dependency_Versions "wikilink")
to update versions of Eclipse Platform dependencies.

  - Orbit may provide multiple copies of the *same version* of a library
    with *different qualifiers*. For each dependency consumed from
    Orbit, make sure we are consuming the latest qualifier of whatever
    version we are using, by updating the current and staging targets to
    the latest Orbit version from
    <http://download.eclipse.org/tools/orbit/downloads/> and updating
    any **qualifiers** that have changed (do not update version
    numbers):

`cd ~/releng/bin`
`./extractVersionsFromUpdateSite.sh ../../org.eclipse.mylyn-target/mylyn-e4.4.target ~/downloads/tools/orbit/downloads/drops/R20150519210750/repository/`

Copy the desired suggestions to the target file.

## Create a Branch (Major Release Only)

  - Branch integration repository. Note: replace clone command with "git
    pull" if repository is already cloned.

`git clone `<ssh://git.eclipse.org/gitroot/mylyn/org.eclipse.mylyn.all>` src-3_6_x`
`cd src-3_6_x`
`git checkout -b m_3_6_x`
`git submodule init`
`git submodule update`

  - Branch each sub-project. Remember to increment the Eclipse version
    each year.

`git submodule foreach git checkout master`
`git submodule foreach git pull`
`git submodule foreach git checkout -b m_3_6_x master`

  - Copy .gitmodules from previous branch and update the branches to the
    current branch

`git checkout m_3_5_x .gitmodules`

  - Push changed .gitmodules file to new m_3_6_x branch
  - Push submodule branches

`git submodule foreach git push origin m_3_6_x:m_3_6_x`

  - configure mylyn-3.6.x-release job on Hudson
      - set BRANCH parameter m_3_6_x
      - edit the build schedule so it won't build automatically after
        this point
  - configure mylyn-3.6.x job at <http://ci.mylyn.org/> to build from
    m_3_6_x branch

## Build

  - If building from a branch, make sure that all needed changes are on
    the branch and that the o.e.m.all repository is up to date. It
    doesn't always update automatically.
  - [Release builds
    (Hudson)](https://hudson.eclipse.org/mylyn/view/Releases/)
      - Check publish
      - Once the build is complete, check the test results from the
        downstream jobs
  - ensure that <http://ci.mylyn.org/job/update-simrel-contribution/>
    build runs and resulting review(s) are merged to update the B3
    aggregation file before the SimRel +3 build cutoff (Wednesdays
    around 5pm EST)

## Update Discovery Jar

  - Update siteUrls and statsUrls in
    `org.eclipse.mylyn/org.eclipse.mylyn.discovery-directory/plugin.xml`
    to have the correct version
  - Check that the listings (supported versions) are up to date.
  - Commit the changes
  - Run <https://ci.eclipse.org/mylyn/job/update-discovery/> to build
    and publish the jar

## Test Install

  - Do a test install from
    <http://download.eclipse.org/mylyn/snapshots/weekly> or
    <http://download.eclipse.org/mylyn/drops/> NOTE: These are only
    links to the zip files, the update site URL has the form
    <http://download.eclipse.org/mylyn/drops/3.24.2/v20180905-2014/>
  - Test that any changes to discovery show up (it may take a while for
    the new jar to propagate to
    [mirrors](https://www.eclipse.org/downloads/download.php?file=/mylyn/discovery/org.eclipse.mylyn.discovery-3.13.jar))

# <font color=red>Publish Release Build</font>

## Prepare Final Release Build

If you want to include any changes made since the repository was
branched:

  - cherry-pick the changes or fast-forward the branches
  - update the submodule commit references on the o.e.m.all repository
  - do another [build](#Build "wikilink")
  - verify that the build installs.

## Tag Sources

  - Tag the release as R_x_y_z (and R_x_y_z_e_3_3 if plug-ins
    are branched)

`git submodule foreach git tag R_3_6_3`
`git tag R_3_6_3`

  - Tag sub-projects with their respective versions as vx.y.z (e.g.
    v0.8.1):

`org.eclipse.mylyn.builds`
`org.eclipse.mylyn.reviews`
`org.eclipse.mylyn.versions`

  - Push tags

`git submodule foreach git push --tags`
`git push --tags`

## Prepare Download Area

  - Run <https://ci.eclipse.org/mylyn/job/prepare-download-area/>

## Update Release Repository Content

*Note: This is the step that should wait until the official release day.
That way the artifacts can be published early so they have time to
mirror, but they won't be
[visible](https://wiki.eclipse.org/SimRel/Simultaneous_Release_FAQ#How_is_a_final_build_made_.22invisible.22_until_release.3F)
until this step is done.*

  - *major releases* Create composite for the release **in the git
    repository, on the master branch**:

`cd org.eclipse.mylyn/org.eclipse.mylyn-downloads/releases/`
`cp -r 3.5 3.6`
`emacs 3.6/composite.index`

  - *major releases and SRs for the latest major release* Update release
    composite sites **in the git repository, on the master branch**:

`cd org.eclipse.mylyn/org.eclipse.mylyn-downloads/releases/`
`rm -rf latest; cp -r 3.6 latest`

  - Commit the changes and run
    <https://hudson.eclipse.org/mylyn/view/Releases/job/update-repositories/>
    to update the composite sites. **You must run the job even if the
    composite.index did not change.**

## Update Website

  - Update the version number on download page
  - Create a new section on download archive page
  - *major releases* Add a link to the new API baseline on the download
    archive page and update your development environment with the new
    baseline
  - Create a New & Noteworthy for the release
      - create new/new-3.7.html
      - add section to new/all.php
      - update version in new/index.php
  - Update the Releases section at <http://eclipse.org/mylyn/>
  - Update <http://eclipse.org/mylyn/updates.xml>
  - *Major Release* Create a discovery/directory-XX.xml for the next
    Mylyn version in the website Git.

## Announce Release

  - Send announcement to
    [mylyn-announce](http://dev.eclipse.org/mhonarc/lists/mylyn-announce/maillist.html)
  - Post announcement to [news
    group](http://www.eclipse.org/forums/index.php?t=thread&frm_id=83)

## Update Marketplace Listings

  - *major releases*
    [Mylyn](http://marketplace.eclipse.org/content/mylyn)
  - *major releases* [Trac
    Connector](http://marketplace.eclipse.org/content/mylyn-trac-connector)

# <font color=red>After the Release</font>

## Update Targets

Update the targets if this was not already done above.

## Update Versions

  - *service release only* Add SR branch to
    [mylyn-snapshot-publish](https://hudson.eclipse.org/mylyn/job/mylyn-snapshot-publish/)
    "Branches to build"
  - Update local repositories, replacing "master" with the branch, e.g.
    "e_4_8_m_3_24_x":

`cd org.eclipse.mylyn.all`
`git checkout master`
`git pull`
`git submodule foreach git reset --hard`
`git submodule foreach git checkout master`
`git submodule foreach git pull`

  - *major release* Update CoreUtil.FRAMEWORK_VERSION
  - *major release* Edit discovery label and URL in
    `org.eclipse.mylyn-feature/feature.xml`
  - Edit versions in
    `org.eclipse.mylyn/org.eclipse.mylyn.releng/bin/update-versions.sh`.
    For *first Service Release on the branch only*, also uncomment
    updateSnapshotSitesForSR <VERSION>.
      - Update the bug number and version number variables in the script

`org.eclipse.mylyn/org.eclipse.mylyn.releng/bin/update-versions.sh`

  - Push reviews to Gerrit (i.e. using EGit with Gerrit config or using
    "git push origin HEAD:refs/for/<branch>") in dependency order. After
    each set of reviews is merged, wait for the corresponding [nightly
    builds](https://hudson.eclipse.org/mylyn/view/Nightlies/) to publish
    new snapshots before pushing the next set of reviews (for SRs, need
    to run the release build (e.g. 3.14.x) to publish snapshots). Push
    sets of reviews in this order:

<!-- end list -->

1.  org.eclipse.mylyn, org.eclipse.mylyn.all (wait for or trigger
    mylyn-snapshot-publish before continuing)
2.  commons
3.  tasks, versions
4.  context, reviews
5.  builds

<!-- end list -->

  - *major release* Update the default value of the BRANCH parameter of
    <http://ci.mylyn.org/view/Snapshots/job/update-simrel-contribution/>
    with the branches that should get the next Mylyn version, or disable
    the job if no SimRel will include this version. This will normally
    be "master" (contribute to the next release of Eclipse), but can
    have a space-delimited list of other eclipse versions to contribute
    to. E.g. if the next Mylyn release will happen before the next
    Eclipse Neon update release, the parameter should be set to "master
    Neon_maintenance".

## Create Download Area

  - run <https://ci.eclipse.org/mylyn/job/create-download-directory>
  - *June release* Create composite site for next Eclipse release **in
    the git repository, on the master branch**

`cp -r org.eclipse.mylyn/org.eclipse.mylyn-downloads/releases/luna org.eclipse.mylyn/org.eclipse.mylyn-downloads/releases/mars`

  - *major release* Update composite site indices **in the git
    repository, on the master branch**

`emacs org.eclipse.mylyn/org.eclipse.mylyn-downloads/snapshots/*/composite.index`

  - Commit the changes and run
    <https://hudson.eclipse.org/mylyn/view/Releases/job/update-repositories/>
    to publish them.

## Create Build Jobs

  - Create mylyn-3.7.x-release job on the HIPP by cloning the previous
    release job
      - Configure job to build from master branch, trigger downstream
        jobs on master branch, and run weekly
      - Configure job to use target for latest Eclipse version by
        specifying that profile in the goals (e.g. -Pmars)
      - start a build so the composite sites will be populated
  - Create a mylyn-3.7.x job at <http://ci.mylyn.org/> and configure it
    to build from the master branch
  - <s>update default target of
    <http://ci.mylyn.org/job/mylyn-all-snapshot/> to next Eclipse
    release</s>
  - update targets of
    <https://hudson.eclipse.org/mylyn/job/mylyn-integration/> and
    <http://ci.mylyn.org/job/mylyn-3.20.x> to have the last Eclipse
    major version, the next Eclipse major version, staging, and
    maintenance (when the maintenance repository exists), e.g. mars neon
    maintenance staging

## Update Snapshot Sites

  - wait for the new release build to complete
  - Run
    <https://hudson.eclipse.org/mylyn/view/Releases/job/update-repositories/>

## Update Oomph Setup

  - switch to the new API baseline
  - add new build jobs

## Add Bugzilla Versions and Milestones

  - [Add Bugzilla
    Milestones](https://dev.eclipse.org/committers/bugs/bugz_manager.php)
    for the next release
  - *major release* Add Bugzilla Version for the current release
  - *major release* move all bugs from "next" milestones to the new
    milestones:
      - <https://bugs.eclipse.org/bugs/buglist.cgi?list_id=10853667&product=Mylyn&query_format=advanced&target_milestone=Next&tweak=1>
      - <https://bugs.eclipse.org/bugs/buglist.cgi?list_id=10840631&product=Mylyn%20Tasks&query_format=advanced&target_milestone=Next&tweak=1>
      - <https://bugs.eclipse.org/bugs/buglist.cgi?list_id=10152343&product=Mylyn%20Commons&query_format=advanced&target_milestone=Next&tweak=1>
      - <https://bugs.eclipse.org/bugs/buglist.cgi?list_id=10152343&product=Mylyn%20Context&query_format=advanced&target_milestone=Next&tweak=1>
      - <https://bugs.eclipse.org/bugs/buglist.cgi?list_id=10152351&product=Mylyn%20Reviews&query_format=advanced&target_milestone=Next&tweak=1>

## Update Project Plan

  - *major release* Update release plans in
    <https://projects.eclipse.org/projects/mylyn/documentation>
  - Create release bug for the next release
  - Add release to [Mylyn
    calendar](https://calendar.google.com/calendar/embed?src=kq3ed9c0latktst29lrl8nffu0@group.calendar.google.com&ctz=America/Vancouver)
  - Send announcement to the mylyn-dev list with the date and a link to
    the release bug so people can follow along

-----

# Service Releases

The steps for service releases are as follows. See above for details on
each step. If the major release being SRed has not been completed,
ensure that the steps "Create a Branch" and "Prepare Download Area" are
complete before beginning the SR process.

1.  [Mylyn/Release_Howto\#Create_Download_Area](Mylyn/Release_Howto#Create_Download_Area "wikilink")
2.  [Mylyn/Release_Howto\#Update_Versions](Mylyn/Release_Howto#Update_Versions "wikilink")
3.  Cherrypick changes
4.  [Mylyn/Release_Howto\#Build](Mylyn/Release_Howto#Build "wikilink")
5.  [Mylyn/Release_Howto\#Test_Install](Mylyn/Release_Howto#Test_Install "wikilink")
6.  Update SimRel: if SR will be contributed to SimRel, manually run
    <http://ci.mylyn.org/view/Snapshots/job/update-simrel-contribution/>
    with the drop and branches that should get the SR.
7.  [Mylyn/Release_Howto\#Tag_Sources](Mylyn/Release_Howto#Tag_Sources "wikilink")
8.  [Mylyn/Release_Howto\#Prepare_Download_Area](Mylyn/Release_Howto#Prepare_Download_Area "wikilink")
9.  [Mylyn/Release_Howto\#Update_Release_Repository_Content](Mylyn/Release_Howto#Update_Release_Repository_Content "wikilink")
10. [Mylyn/Release_Howto\#Update_Website](Mylyn/Release_Howto#Update_Website "wikilink")
11. [Mylyn/Release_Howto\#Announce_Release](Mylyn/Release_Howto#Announce_Release "wikilink")

# Notes

  - <https://hudson.eclipse.org/mylyn/view/Releases/job/update-repositories/>:
    need to run this every time after deleting drops to make sure there
    are no stale references
  - Most of the examples assume you are releasing Mylyn 3.6 and then
    preparing for the 3.7 release
  - In this document, *major release* generally means anything other
    than a service release
  - A version of this document including instructions specific to Mylyn
    Incubator is available at
    <https://wiki.eclipse.org/index.php?title=Mylyn/Release_Howto&oldid=404098>
    (search the page for "incubator")