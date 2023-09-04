See also: [helpwanted
bugs](https://bugs.eclipse.org/bugs/buglist.cgi?keywords=helpwanted;query_format=advanced;bug_status=UNCONFIRMED;bug_status=NEW;bug_status=ASSIGNED;bug_status=REOPENED;classification=Mylyn),
[eclipse dev](http://www.eclipse.org/eclipse/development/index.php),
[source repository](http://git.eclipse.org/c/mylyn/), [website
repository](http://dev.eclipse.org/viewcvs/index.cgi/www/mylyn/?root=Eclipse_Website)

## Project Structure

The Mylyn project is structured into sub-projects that address different
areas of Application Life-cycle Management. Please see
[Mylyn/Charter](Mylyn/Charter "wikilink") for the top-level project
charter.

Artifacts are published in a number of
[Mylyn/Repositories](Mylyn/Repositories "wikilink"). The [main
repository](http://eclipse.org/mylyn/downloads/) aggregates sub-projects
that participate in Mylyn releases. The participating projects are
listed in the [project
plan](http://www.eclipse.org/projects/project-plan.php?projectid=mylyn).
The main Mylyn update site features are mature components that are
supported by the Mylyn project committers and may be distributed as part
of the [Eclipse Downloads](http://www.eclipse.org/downloads/).

Sub-projects are encouraged to provide a framework component and
reference implementations called *Connectors* that extend Mylyn to
different task management systems and focus the artifacts that you work
with when you activate a task (formerly called *Bridges*).

### Feature Maturity

Mylyn features vary in UI maturity and availability of support. The
following is a guideline for what it takes to move from experimentation
through to maturity. (Note that this is partially based on the [Eclipse
project
lifecycle](http://www.eclipse.org/projects/dev_process/development_process.php#6_2_3_Incubation)
and could converge further with that lifecycle if Mylyn were split into
a separate incubation project or sub-projects.)

**Mature**: packaged Eclipse downloads and available via main update
site

  - UI quality: Eclipse SDK features have set a very high quality and UI
    consistency bar that needs to be met in order to make it possible to
    improve users' productivity with Eclipse.
  - UI simplicity: the Mylyn project's goal is to simplify and
    streamline the user experience. A simple and self-evident UI also
    helps ensure a manageable support burden on the component.
  - Availability of support: the feature must have an owner or
    organization with a long-term commitment to the quality of the
    feature and the ability to provide responsive support for feedback
    on that feature.
  - Responsiveness to feedback: the feature owner and other contributors
    must process and prioritize user feedback and respond to the highest
    priority needs in a timely manner (e.g. blockers and critical bugs
    need to be fixed within one release of being submitted, key
    enhancements help the feature evolve to meet users' needs).

**Incubation**: available via the nightly update site

High quality components that meet most but not all of the above
criteria. To graduate, sufficient community feedback must be available
on the quality and usability of the component (e.g. 100+ resolved bugs)
and committers must vote to determine whether component meets the UI
quality and simplicity guidelines.

**Sandbox**: available via the *Incubation* update site

  - Unsupported components used for experimentation and not intended for
    daily use.
  - Community interest and contributions determine which experimental
    features move from the Sandbox into Extras.

### Creating New Components

Most sub-projects host a framework component and one or more reference
implementations. When new code is brought into Mylyn it may be added as
a sub-project, sub-sub-project or as a component of an existing project.
The right organisational structure depends on the needs of the
development community and the scope and process of the existing
projects. Criteria that could qualify a component to be split out as a
separate project:

  - A component requires incubation status (e.g. for parallel IP) but
    the framework project has already matured.
  - The committer set of the component is not a subset of the committer
    set of the framework project.
  - A component wants to release more frequently than its framework
    project, i.e. it follows it's own project plan.
  - A component publishes its own APIs and its scope and community are
    significant that it requires its separate management structure such
    as a Bugzilla product, news group etc.

## Getting Started

The Mylyn project places a very high value on community contributions.
This document is intended to help those interested in contributing to
Mylyn. It communicates our conventions and discusses ways to get your
contributions prioritized.

### Individual Contributors

A significant portion of Mylyn contributions have been made by
individuals wanting to make the tool or framework work better for them.
There are several ways that individuals can get involved with the
project:

  - **Mentoring**: if you are an experienced user, you can support
    newcommers by providing feedback using the community channels
      - [Mylyn Newsgroup](http://www.eclipse.org/mylyn/community/).

<!-- end list -->

  - **Casual contribution**: we have a large number of very valuable
    casual contributors who provide patches for their pet bugs, or
    enhancements that either they would find valuable or that they want
    to share with others. If you are interested but don't know where to
    start look first through the short list of bugday bugs, and then
    through the longer helpwanted list.
      - **[bugday
        bugs](https://bugs.eclipse.org/bugs/buglist.cgi?keywords=bugday;query_format=advanced;keywords_type=allwords;bug_status=UNCONFIRMED;bug_status=NEW;bug_status=ASSIGNED;bug_status=REOPENED;classification=Mylyn)**:
        a short list of highly relevant bugs for getting started
      - **[helpwanted
        bugs](https://bugs.eclipse.org/bugs/buglist.cgi?keywords=helpwanted;query_format=advanced;keywords_type=allwords;bug_status=UNCONFIRMED;bug_status=NEW;bug_status=ASSIGNED;bug_status=REOPENED;classification=Mylyn)**:
        a longer list of all bugs targeted at community contributions

<!-- end list -->

  - **Working towards commit rights**: The Eclipse and Mylyn development
    processes make it easy to make regular contributions without
    requiring commit rights, but frequent contributors may be interested
    in earning commit rights. Commit rights come with a significant
    overhead of user support as well as the need to follow the project's
    priorities for contributions. They require you to participate in the
    planning and of the project, and allow you influence the direction
    of the tool and framework. If you are interested in becoming a
    committer we recommend letting one of the existing committers know
    so that they can mentor you and help build a trust relationship. It
    can also help to identify a separable component of the project that
    you are interested in taking responsibility for, since Mylyn commit
    rights are assigned per-component.
      - [Committer Due Diligence
        Guidelines](http://www.eclipse.org/legal/committerguidelines.php)
      - [Mylyn Developer Mailing
        List](http://www.eclipse.org/mylyn/community/)
      - [Mylyn Meetings](Mylyn_Meetings "wikilink") are held on a
        monthly conference call and open to all

### Integrators and Vendors

Those building both closed and open source tools on top of Mylyn may be
interested in evolving the Mylyn APIs to ensure that that the framework
meets their needs. We welcome such contributions just as we welcome
individuals making improvements to the tool, since they help make Mylyn
a better framework for all. The Individual Contributor points above
apply to integrators and vendors interested in contributing or earning
commit rights. In addition, the following tips may be of interest:

  - List your extension on the [Mylyn
    Extensions](Mylyn_Extensions "wikilink") page and in the [Eclipse
    marketplace](http://marketplace.eclipse.org/). This will help the
    Mylyn community become aware of the extension.

<!-- end list -->

  - If interested in exploring Mylyn integration, consider dialing into
    the our monthly call and adding an agenda item on the [Mylyn
    Meetings](Mylyn_Meetings "wikilink") page.

<!-- end list -->

  - Vendors are welcome, so make yourself known. We recommend using your
    company name for Bugzilla email addresses. If you have a product
    built on Mylyn and need a bug fixed, we recommend voting for it with
    that email address. The Mylyn project prioritizes bugs according to
    how much overall benefit they will have to users, and as such
    commercial integrations are an important part of that
    prioritization. If the bug does not fit with the project's
    priorities we will encourage you to provide a patch.

<!-- end list -->

  - Consider making a bug titled "support integration with <your tool>".
    We use these bugs for discussing integration issues particular to a
    specific tool or technology and leave them open for ongoing API or
    UI discussion needs.

### Links

  - [Eclipse Code
    Conventions](Development_Conventions_and_Guidelines "wikilink")
  - [Eclipse User Interface
    Guidelines](User_Interface_Guidelines "wikilink")
  - [Documentation Style Guidelines](Eclipse_Doc_Style_Guide "wikilink")
  - [Eating your own dog food
    (Wikipedia)](http://en.wikipedia.org/wiki/Eat_one's_own_dog_food)

## Contributors

### Overall Process

The best way to get your contribution into the code base is to stick to
this workflow:

1.  **Sign** the [CLA](http://www.eclipse.org/legal/CLA.php) by logging
    in at <https://projects.eclipse.org/user/login/sso> (You only need
    to do this once).
2.  **Install** the [Tools](#Contributor_Tools "wikilink"), including
    EGit, Mylyn Bugzilla, and Gerrit.
3.  **Setup** your Eclipse [Environment](#Setting_Up "wikilink").
4.  **Find** or file a [Bug](#Working_with_Bugzilla "wikilink").
5.  **Write** the [Code](#Developing_Code "wikilink").
6.  **Push** a [Review](#Working_with_Reviews "wikilink").

### Contributor Tools

In this guide, we'll be sharing the basics of what you need to know to
work with Bugzilla tasks, EGit changes and Gerrit reviews, along with
recommendations about best practices for using these tools.

For more information on how to work with EGit and Gerrit Reviews, refer
to the Eclipse help documentation. (At the time of this writing, some of
those documents are a bit out of date. The tooling has improved
signficantly and much of the workflow is much simpler now.) There are
also a number of excellent tutorials (google "eclipse gerrit"),
including [this
one](https://www.eclipse.org/community/eclipse_newsletter/2013/september/article4.php).

#### Using Mylyn

All contributions to Mylyn need to be made using Mylyn since it links
source changes to tasks and contexts, making open development and
collaboration easier. Using Mylyn ensures that:

  - All Bugzilla reports have a corresponding task context, making them
    easy to reopen or pick up by you and by others.
  - All Reviews match up to a single Bugzilla report, making it easy to
    navigate from changes to bugs.

#### Installing

All the tools we need are conveniently available as part of many of the
standard Eclipse distributions. You can also install the tools from
their respective p2 repositories into any Eclipse instance using Install
New Software from the Help menu. Using the repositories below will help
ensure that you have the latest and greatest versions of each tool.

  - EGit p2 repository - <http://download.eclipse.org/egit/updates>
      - Eclipse Git Team Provider
      - Task Focused Interface for Eclipse Git Team Provider
  - Mylyn p2 repository -
    <http://download.eclipse.org/mylyn/releases/latest>
      - Mylyn Tasks Connector: Bugzilla
      - Mylyn Context Connector: Eclipse IDE
      - Mylyn Builds Connector: Hudson/Jenkins
      - Mylyn Reviews Connector: Gerrit
      - Mylyn Versions Connector: Git

### Setting Up

#### Register a Gerrit Account

To use the review server a few steps are required:

  - Register an Eclipse.org account at
    [dev.eclipse.org](https://dev.eclipse.org/site_login/createaccount.php).
    The same account is used for
    [Bugzilla](https://bugs.eclipse.org/bugs) and
    [Gerrit](https://git.eclipse.org/r).
  - [Login](https://git.eclipse.org/r/) to Eclipse Gerrit.
  - [Upload your public
    ssh-key](https://git.eclipse.org/r/#/settings/ssh-keys) for
    authentication.

You are now ready to submit changes to Gerrit.

#### Connect to Bugzilla

All Eclipse projects use Bugzilla for issue tracking. Mylyn makes
connecting to Bugzilla easy.

1.  Connect to the Eclipse Bugzilla Repository:
    1.  Click the "Add Task Repository" button in the Task Repositories
        View.
    2.  Select Bugzilla.
    3.  In the Server section, Select Eclipse.org from the drop down
        menu.
    4.  Add the credentials you created above and click "Finish".
2.  Setup a query for your Reviews:
    1.  Right-Click in the Task List and select "New" -\> "Query..."
    2.  Select the Repository you just created, click through to "Create
        Query using Form".
          - To find bugs to work on, select some items in Product. For
            example "Mylyn Tasks".
          - You could narrow this further, by selecting Components you
            are interested in or bugs with Status "New".
          - Under "More Options", try adding the "helpwanted" keyword to
            find bugs that the Mylyn team has identified as good for
            contributors to tackle.

#### Connect to Gerrit and Git

If you are using Gerrit version 2.13.8 or later, you may encounter an
error : Failure to obtain Gerrit configuration this is due to Gerrit
2.13.8 has not been tested with this version of Mylyn. It may not be
fully supported. In this case go to Option B Import using Git Repository
window. Otherwise continue here with Option A Import using Task
Repository.

\- Option A := Import using Task Repository.

1.  Connect to the Gerrit Repository:
    1.  Click the "Add Task Repository" button in the Task Repositories
        View.
    2.  Select Gerrit Code Review.
    3.  Enter the server address: <https://git.eclipse.org/r>
    4.  Add your credentials and validate.
2.  Setup a query for your Reviews:
    1.  Create a New Query in the Task List using the repository and "My
        Changes".
    2.  There won't be anything there yet of course. To get an idea of
        what the reviews process looks like, try "Open Changes by
        Project" and search for a Mylyn project that interests you.
    3.  Or, try the new [Gerrit
        Dashboard](https://www.eclipse.org/mylyn/new/new-3.11.html#gerrit)\!
3.  Import the source code:
    1.  Under File \> Import select "Projects from Git" and select
        Gerrit from the list on the next page.
    2.  Select the repository you're interested in from the list of Git
        repositories hosted on the Eclipse.org Gerrit instance. If you
        want to contribute to Mylyn Tasks for example, select the
        mylyn/org.eclipse.mylyn.tasks repository.
    3.  The repository is automatically cloned and we can select all
        projects to import on the last page. (If an error is displayed
        that the SSH key is invalid or missing it needs to be generated
        first in the Eclipse preferences under General \> Network
        Connections \> SSH2 and uploaded to Gerrit. See
        [above](#Register_a_Gerrit_Account "wikilink"))
    4.  Note that once all projects have been imported you can get rid
        of any API baseline errors by opening the Eclipse preferences
        and selecting the Plug-in Development \> API Baselines page and
        setting Missing API baseline to Ignore.

\- Option B := Import using Git Repository window.

1.  In Eclipse go to Git Repositories Window -\> Clone a Git Repository
    -\> CloneURI
2.  Use the username (not your eclipse.org email username but the one
    defined on your profile) with a clone url found on
    <https://git.eclipse.org/c/mylyn/org.eclipse.mylyn.docs.git/>
3.  Set the Gerrit Configuration.
    1.  Git Repositories window, right click Repository, click
        Properties.
    2.  Under Configuration tab, look for remote \> origin \> url.
    3.  Enter the Eclipse git url (e.g,
        <ssh://username@git.eclipse.org:29418/mylyn/org.eclipse.mylyn.docs.git>)
    4.  Click Apply and OK.
4.  Right clicking on the repository and Import projects (If an error is
    displayed that the SSH key is invalid or missing it needs to be
    generated first in the Eclipse preferences under General \> Network
    Connections \> SSH2 and uploaded to Gerrit. See above)
5.  Note that once all projects have been imported you can get rid of
    any API baseline errors by opening the Eclipse preferences and
    selecting the Plug-in Development \> API Baselines page and setting
    Missing API baseline to Ignore.

### Working with Bugzilla

#### Key Points

  - For contribution ideas see
    [\#Individual_Contributors](#Individual_Contributors "wikilink") to
    find an enhancement or defect that interests you, file a new bug of
    your own, or email
    [mylyn-dev](https://dev.eclipse.org/mailman/listinfo/mylyn-dev) for
    ideas. Often the best contributions come from people who have an
    "itch to scratch".
  - *Before* starting work:
    1.  Comment on the corresponding bug, stating your interest and
        asking whether a committer or another contributor has any
        suggestions for the implementation approach.
    2.  Propose a design, mentioning the key use cases, implementation,
        tests coverage, and UI changes or additions (if applicable).
        (You might skip this step if the required fix or proposed
        behaviour is clear.)
    3.  Assign yourself to the bug.

#### Voting

Votes track the general interest in a particular bug. Bugs with more
votes are more likely to get fixed. We encourage all in the community to
vote for bugs, since it helps committers and contributors prioritize
work.

### Developing Code

#### Key Points

  - Follow [Eclipse code
    conventions](Development_Conventions_and_Guidelines "wikilink").
  - Ensure you've provided complete unit test coverage.
  - Small is good\! More focused changes will be reviewed more quickly
    and have a much better chance of being merged without major changes.
    If the bug you're working on involves complex changes, consider
    breaking your changes up into bite-sized pieces rather then tackling
    the whole thing in one review.

#### Writing Tests

When writing tests look for the `All`<component>`Tests` class in the
`tests` plug-in for that component, identify a test that is similar to
the functionality that you are adding, and use that test as an example
of how to add additional coverage. Ensure that your test covers the
addition or change to the existing functionality. For API changes it is
often sufficient to have the public method covered.

Tests can sometimes take longer to write then the change itself\! If you
get stuck, ask a committer to assist you in designing tests appropriate
to your case.

Working with mock test harnesses and UI can be especially challenging.
Writing tests for UI components often involves a combination of unit and
black-box testing. For example we might rely on other parts of the Mylyn
UI (e.g. the Task List view). Consider the case of adding functionality
for pre-selecting a repository in the New Task dialog. Writing a test
might take the following form (refer to
`NewTaskWizardRepositorySelectionTest`):

  - Create a mock repository
  - Add a task to the mock repository
  - Set the selection on the Task List (new functionality uses this
    selection)
  - Invoke the wizard and assert that the selection was set correctly on
    the viewer (wizard is a black box, all we care about is the contents
    of the viewer)
  - Dispose the wizard dialog, remove the mock repository and the mock
    task

When writing UI tests note that asynchrous updates, such as refresh, can
make testing *very* challenging. Note that several UI components have a
method on them to set synchronous execution for the purpose of testing,
and if such a method is lacking it can be added.

#### Graphics

If contributing a feature with icons or other graphics feel free to ask
a committer to generate the graphic for you. If interested in
contributing graphics you can find all of the source files (e.g.
Photoshop) here: `mylyn/graphics/ui`.

### Working with Reviews

The review process is the most important tool we use to ensure that
Mylyn code is as high quality as possible. It can also be pretty
intimidating for new contributors. But it shouldn't be. Think of it as
an opportunity to gain from the experience of other developers. And to
keep things in perspective, remember that many thousands of other
developers might be made more happy by the change that you make -- or
unhappy if it doesn't work correctly\!

The best thing about the Gerrit based reviews process is that it means
that all code gets reviewed in the same way, regardless of who wrote it.
The only significant differences between contributors and committers are
that only committers can approve commits (vote +2) and single
contributions of over a 1,000 lines of code must go through extra IP
process. (Another reason to keep those commits small.) So even if you
never decide to become a Mylyn committer you can still make significant
improvements to Mylyn\!

#### Key Points

  - Ensure that your commit message is formatted correctly and has all
    of the information needed.
  - Before pushing your commit:
      - Ensure the the code does what you say it does by testing it
        thoroughly.
      - Be your own first reviewer. Go over your commit before pushing
        it. Often a second (or third, or fourth) self-review of the code
        will reveal issues that you'd missed.
  - After pushing your commit:
      - The Eclipse Genie will automatically a comment on the original
        bug with a link to the review (assuming your commit message was
        formatted correctly).
  - After receiving feedback:
      - Don't take reviews personally. Even seasoned Mylyn committers
        should expect to see -1 and -2 reviews. If all of our code was
        perfect the first time, we'd never need reviews. It's helpful
        especially at first to see reviews as a learning process.
      - Do respond to *every* comment. If you disagree with a point,
        that's ok -- explain why you did things the way you did.
      - Be patient and prepared to iterate. While some simple changes
        might get committed in a day or two, complex changes requiring
        input from contributors might require refinement over a few
        weeks. The Gerrit tools make this process much less painful then
        before.
  - After receiving your first +2:
      - Give yourself a well-deserved high-five. You're now a Mylyn
        contributor\!
      - Find another bug\!

#### Hudson Voting on Reviews

When you push a patch set to a review, Hudson will automatically start a
build that checks out your patch set and runs tests. If you are not a
committer or a whitelisted contributor, the build will be aborted with a
message in the console output similar to "Gerrit build started by
unauthorized user jane.user. Committers, verify that the change is safe
to run and then retrigger the build." In that case you'll need to wait
for a committer or a whitelisted contributor to retrigger the build.

#### Committing Changes

1.  Right click and select Team \> Commit on any changed project or
    resource to display the git commit dialog.
2.  If you've activated the task, this will be populated with the
    following items, or you can enter them by hand:
      - The bug ID and a summary.
      - A "Task-Url:" entry active task allowing bugs to be traced to
        tasks.
3.  Click the rightmost two buttons on the commit dialog and the
    remaining two required entries will be added for you:
      - A Gerrit "Change-Id" entry. The entry is required for all
        changes pushed to Gerrit (to enable pushing new patch set
        versions to the same review)
      - A "Signed-off-by" entry. The entry is required as it confirms
        that you are in compliance with the [Certificate of
        Origin](http://www.eclipse.org/legal/CoO.php).
4.  Edit the commit summary to describe the specific change you are
    making. This is not always the same as the bug summary. Your commit
    may only be addressing part of the issue. It is often helpful to
    other developers to add additional lines of description below the
    summary. Leave a one-line gap between the summary and further
    description.
5.  Ensure that the Author and Committer dialog entries match your
    Eclipse credentials. Like this: `Awesome Contributor
    <awesome.contributor@awesome-company.com>`
6.  Click "Commit". You can do a "commit and push" directly, but at
    least until you gain some experience it's probably a good idea to
    double-check your commit before pushing it.
      - Is everything that you expected to be there there?
      - Does the commit message match the example below?

##### Example Commit Message

The following is the
[standard](https://bugs.eclipse.org/bugs/show_bug.cgi?id=420699) commit
message template which can be configured in Window -\> Preferences -\>
Tasks -\> Team:

    ${task.key}: ${task.description}

    Task-Url: ${task.url}

Note that often you'll want to edit the task description.

Here's an example of what a review message should look like:

    999895: Improve sorting in task view

    * Replaced random with alphabetical sorting
    * Minor refactoring

    Task-Url: https://bugs.eclipse.org/bugs/show_bug.cgi?id=999895
    Change-Id: Ieb8caf92cd87899b125b89beb077a1d4f579ff23
    Signed-off-by: Awesome Contributor <awesome.contributor@awesome-company.com>

The dialog should end up looking like this:

![<File:MylynContributorGuideGitCommit.png>](MylynContributorGuideGitCommit.png
"File:MylynContributorGuideGitCommit.png")

#### Pushing Changes

After reviewing your submission, you can push it. There are many
workflows that work well, but here's one relatively fool-proof approach:

1.  Pull or fetch to ensure that origin/master is as up to date as
    possible. This will help avoid future rebase trauma\!
2.  Rebase on top of origin/master.
3.  Ensure that you are on the master branch. (If you're currently
    working on a topic branch, you could do this by checking out the
    master branch and then doing a hard reset to your topic. But make
    sure you've committed your changes first\!)
4.  Right click on any changed project or resource and select Team \>
    Push to Upstream.
5.  After pushing, you might want to create a seperate topic branch to
    help manage your change locally.

#### Subsequent Changes

Handling subsequent changes is easy, as long as you keep things simple
and follow the recommendations below. Otherwise, you might end up doing
a bit of juggling\!

1.  After the initial commit, it is better *not* to rebase against
    master, unless you know there are signficant changes that have been
    committed in the meantime that you need to merge with. Rebasing
    within a review makes it more difficult to track changes between
    patch sets.
2.  Select "Amend Previous Commit", the first button in the commit
    dialog toolbar. This will ensure that the change has exactly the
    information Gerrit is expecting, and means that you won't have to
    deal with annoyances like squashing commits later.
3.  If you can't amend the commit, then ensure that the Change-Id: value
    matches whatever value is already there in the review. This is the
    only way that Gerrit associates your change with a particular
    review.
4.  In either case, you can freely edit the commit message to reflect
    your evolving change.

If things didn't turn out correctly and you get a reject message or
something else unexpected happens, don't despair. With Git there is
always a way to clean up any kind of mess, though it can take a bit of
perserverance to discover how. The key thing to keep in mind is that
there can only be one commit per review. So if you have multiple commits
related to a change, you need to "squash" them into one change with the
appropriate commit id. Most contributors sooner or later becomes
familiar with the magical command line incantation: `git rebase -i
HEAD~2`. See the git documentation for details. Alternatively, EGit has
a new "Git Interactive Rebase" view that lets you perform this magic
with a visual tool.

If someone else makes a change to your review -- and don't be offended
if they do\! -- and you want to incorporate that change into your
subsequent changes, or if you don'thave the topic branch for one of your
own changes, just do this:

1.  Fetch the change (Patch Set) using the Gerrit task editor.
2.  Checkout the master branch and reset it to the branch you've just
    checked out. (You may want to create a topic branch as well.)
3.  Then you can just amend any subsequent changes exactly as above.

## Committers

Contributors who have made frequent and valuable contributions to Mylyn
can become committers. The [Eclipse
Charter](http://www.eclipse.org/projects/dev_process/Eclipse_Standard_TopLevel_Charter_v1.0.php)
explains how.

### Participation

Committers should:

  - Sign up for all of the project mailing lists.
  - Read the newsgroup regularly, and respond to posts in their area of
    expertise.
  - Respond to mylyn-dev email in their area of expertise.
  - Watch and update all wiki pages related to components that they
    contribute to.

### Communication

Mylyn committers are required to follow these communication guidelines.
Our philosophy is that **the user is always right**, even if it takes
time to figure out how or why they are right. Our project thrives on the
feedback of users, whether they are seasoned experts or newbies.
Feedback defines how the tool should work, how it should be simplified,
and how it should evolve.

  - All feedback contains information, and it is the responsibility of
    committers to turn that information into actions. This can mean
    improving the implementation, simplifying the workflow, clarifying
    the documentation, or noting a duplicate request. Making the actions
    we take clear helps communicate this philosophy to our growing user
    community and encourages high-quality feedback.

<!-- end list -->

  - If users do not provide enough information or do not take the time
    to provide accurate information, they should be prompted to provide
    the necessary details. If they do not do so in a timely manner, the
    feedback is incomplete and can be resolved without taking action.

<!-- end list -->

  - Show respect to others in the community, whether they are making
    correct or incorrect assumptions about the tool or technology. When
    someone makes incorrect assumptions it is because we have not done
    our job well enough, or because the platforms we build on are making
    it hard for us to do our job well enough. Identifying those cases is
    important so that we can provide feedback to those platforms and
    find work-arounds.

<!-- end list -->

  - Never turn feedback or discussion away by
    [flaming](http://en.wikipedia.org/wiki/Flame_war#Causes_of_flaming),
    being condescending, short, or insulting in any community
    communication forum. Forms of humor that work for face-to-face
    communication, such as sarcasm, are usually best avoided because
    they can result in misinterpretation, especially when there is a
    language or cultural barrier.

**Handling Inappropriate Communication**

In the vast majority of cases, following the above guidelines has lead
to the high quality communication that our user and contributor
community has thrived on. However, the openness of our communication
channels has been abused in the past. These scenarios are typically
marked by overly opinionated, non-technical and insulting posts on bugs
in and in other forums. The communication may have technical elements or
technical points, but the points are communicated in an overly
opinionated way with a disregard for the opinions of others involved in
the dialog. If encountering such communication, make sure to read the
[Wikipedia Entry on Flaming](http://en.wikipedia.org/wiki/Flame_war),
especially the "Causes of flaming" section.

Note that invoking the process listed below should be the exception, and
not the rule. Projects with like-minded committers can experience the
[Groupthink](http://en.wikipedia.org/wiki/Groupthink) bug, which is why
high quality open communications channels are so important to helping
the project evolve. However, abuse undoes the openness that we strive
for by making the channels intimidating or unfriendly to newcommers.
Follow these steps if you encounter such communication:

  - Make one or two attempts to steer the conversation back on a
    technical path.
  - If that doesn't address the problem, enter the following text as the
    third comment:

` Ignoring comment per: `<http://wiki.eclipse.org/index.php/Mylyn_Contributor_Reference#Communication>

  - Avoid following up again. Send the bug ID to the project lead who
    will assess the problem.

To comment on these guidelines please use

### Bugzilla

  - Any user-reported bug should be resolved by one of: code
    improvements, documentation/FAQ improvements, or being marked a
    duplicate of another bug. All but the last require attaching a
    context.
  - Be judicious in marking bugs for LATER, because this typically
    communicates that the bug will never be resolved. Do this only if
    the bug does not fit in with the current scope of the project but is
    related to the mission. Otherwise mark P4/P5 and "helpwanted" to
    encourage a contribution that is not part of our current
    prioritization and plan.
  - When naming bugs, try to describe the use case or problem instead of
    the implementation unless there is no ambiguity in how the fix
    should be implemented. If the implementation approach helps with
    queries append it.
      - Bad: task list working set
      - Good: support nesting top level task list elements, e.g. via
        working sets

**Severities**

  - Use the Eclipse [bug
    severity](https://bugs.eclipse.org/bugs/bug_status.html#bug_severity)
    with this exception: bugs marked as Trivial are enhancements, that
    can be easily implemented.

**Keywords**

  - `helpwanted`: bugs that are beyond the current priorities for the
    project. Note that some bugs marked for an upcoming milestone can be
    marked as `helpwanted`. This indicates that the project committers
    would like to see the bug solved for the milestone and will actively
    contribute to a solution, but that the bug is more likely to be
    fixed in a timely manner with the help of additional contributors.

<!-- end list -->

  - `bugday`: these are a special category of `helpwanted` bugs that are
    intended to be mast accessible or rewarding for new contributors
    interested in helping the project to tackle. See the [Bug Day
    FAQ](Bug_Day_FAQ "wikilink") for more information. In order to keep
    this list focused on the most relevant bugs it is capped at 24 and
    should be reviewed periodically.

<!-- end list -->

  - `contributed`: bugs that were resolved through a contribution from a
    non-committer.

<!-- end list -->

  - `plan`: bugs that are part of the project plan (see below).

**Tags** The project uses the following tags in the summary of bugs on
bugs.eclipse.org ():

`[activity]      - bugs related to improving work flow`
`[api]           - bugs that require API changes; every API change has a corresponding bug which is tagged that way`
`[bridge]        - requests for structure bridges`
`[connector]     - requests for connectors`
`[context]       - bugs related to the context framework`
`[discussion]    - discussion items`
`[editor]        - bugs related to the Task Editor`
`[e3.2][e3.3]    - bugs specific to a particular version of Eclipse`
`[folding]       - bugs related to active folding`
`[framework]     - bugs that address internal implementation details that do not require API changes`
`[linux]         - bugs specific to Linux (Gtk)`
`[m2.3.1]        - bugs that are fixed in a particular maintenance version of Mylyn`
`[mac]           - bugs specific to Mac OS (Cocoa, Carbon)`
`[multi monitor] - bugs related to multi monitor environments`
`[new uex]       - new user experience`
`[patch]         - bugs that have a patch attached that is pending for review or waiting to be applied; `
`                  the tag is removed after the patch has been applied or if a review requested changes`
`[performance]   - bugs that indicate severe performance problems`
`[planning]      - requests for planning features`
`[refactor]      - request for non-functional refactorings`
`[regression]    - bugs that indicate regressions`
`[sandbox]       - bugs that affect components in the sandbox`
`[standalone]    - bug related to usage of Mylyn outside of the Eclipse environment`
`[update]        - update manager and P2 related bugs`
`[usage]         - usage monitoring related bugs`
`[web connector] - bugs in the Web Templates connector`
`[website]       - bugs related to the web page on eclipse.org/mylyn `*`(use``
 ``Doc``   ``component``   ``for``   ``that?)`*
`[win]           - bugs specific to Windows (Win32, WPF) `
`[workflow]      - requests for integration of task and repository workflow`
`[working sets]  - bugs related to working set support`
`[search]        - bugs related to desktop search (see ``)`

#### Triage

The goal of bug triage to minimize the overhead for committers and to
maintain a manageable backlog. Each (new) bug that is filed is processed
as follows:

  - Major bugs or regressions are marked *P1*. If necessary the bug is
    escalated and scheduled for the current milestone.
  - Other bugs are marked *P2*.
  - Enhancements requests that should be considered for a future release
    are generally marked *P3*.
  - Other enhancement requests are marked *P4* and tagged as
    ''helpwanted '' if they can be resolved through a community
    contribution.
  - If a request is out of scope of the project it is marked *P5* or
    preferably closed. P5 bugs should not be marked helpwanted.

The backlog consists of all tasks scheduled for `--` with a priority of
P2 or higher. User stories are tagged with the plan keyword.

Bugs are assigned as following:

  - mylyn-inbox@eclipse.org: New bugs are and bugs that need user input.
  - mylyn-triaged@eclipse.org: Bugs that have been responded to and
    severity and priority has been set.
  - other: The owner is committed to completing the task for the
    scheduled milestone or within a reasonable time frame in the future
    if the bug is scheduled for --.

#### Planning

The goal of planning is to schedule a list of bugs for the milestone
that concludes the next release cycle. When the milestone is reached all
bugs with a priority of P3 or higher are expected to be completed. It is
important that planning takes existing resources into account to avoid
over-committing. Predictable release deliverables will enable
integrators to plan their own progress based on the Mylyn framework and
aid the growth of the ecosystem.

Before every release planning is done by triaging the entire backlog.
Bugs marked with the plan keyword become part of the official release
plan. Planning bugs marked P1 are committed items, other bugs are
proposed items. Half way through a release cycle the plan is reviewed
and P1/P2 bugs in the backlog are reconsidered for the milestone to
accommodate for regressions and major bugs that were submitted after
initial planning.

#### Resolving

The list of bugs that are scheduled for a milestone serves as a log that
documents changes to release artifacts. In order to preserve historical
information captured by the change log bugs that have been resolved
should not be moved to other milestones once a milestone has been
released.

If a defect reoccurs or a bug requires further work a new bug should be
created and linked to the resolved bug. It is recommended to add a
comment on the resolved bug that points to new bug and describes the
reason for its creation.

### Git

Git repositories can be accessed in Eclipse via
[EGit](http://eclipse.org/egit/). Mylyn uses the following conventions
for Git repositories:

  - It is strongly recommended to rebase before pushing to keep the
    revision history flat as possible:

`git pull --rebase`

The [branch.autosetuprebase
setting](http://kernel.org/pub/software/scm/git/docs/git-config.html)
automates that:

`git config branch.autosetuprebase always`

See also:

  - [Git workflows for CVS
    users](http://wiki.eclipse.org/Platform-releng/Git_Workflows#Cross-referencing_between_bugzilla_and_git)

### Hudson

Mylyn is built regularly by jobs running on the Mylyn HIPP server. See
[Mylyn/Build_Infrastructure](Mylyn/Build_Infrastructure "wikilink") for
details.

**Gerrit Jobs**

[Gerrit jobs](https://hudson.eclipse.org/mylyn/view/Gerrit/) are
triggered when a patch set is pushed to Gerrit. In order to protect
against unauthorized users pushing malicious code to Gerrit and having
it automatically executed by the gerrit-trigger plugin, these builds
will be automatically aborted if the patch set submitter is not a
committer on the project, and is not on a project-specific whitelist. In
that case, a committer or someone on the whitelist will need to review
the contribution to ensure it does not attempt to run malicious code.
They can then retrigger the aborted build and it will run normally.

The whitelist is defined at
/shared/gerrit-contributor-whitelists/mylyn/org.eclipse.mylyn/contributor_whitelist.txt.
Any committer should have write access to the whitelist and should feel
free to add the emails of trusted contributors to the list. Shell access
to build.eclipse.org can be requested via Bugzilla. Alternatively, you
can email mylyn-dev to ask another committer to edit the whitelist.

### Maven

The Mylyn build is based on Maven/Tycho. The minimum required Maven
version is 3.0.

  - The `org.eclipse.mylyn/org.eclipse.mylyn-parent` module specifies a
    parent pom with common settings. This pom is published to the [Mylyn
    Maven
    repository](http://mirrors.ibiblio.org/pub/mirrors/eclipse/mylyn/maven/snapshots/).
  - The `org.eclipse.mylyn/org.eclipse.mylyn-target` module specifies a
    target definitions. These are published to the [Mylyn Maven
    repository](http://mirrors.ibiblio.org/pub/mirrors/eclipse/mylyn/maven/snapshots/).

#### Builds

`mvn package`

To skip execution of tests use `-Dmaven.test.skip=true`

#### Tests

To run tests invoke the following command:

`mvn integration-test`

#### Releases

  - Check out the org.eclipse.mylyn.all project.
  - Run `git submodule init` to initialize sub modules
  - Run `git submodule update` to update sub modules to the latest
    integration build
  - Run `mvn package` to build release artifacts.

The [Release Howto](Mylyn/Release_Howto "wikilink") describes how to
build and publish official Mylyn releases.

#### Profiles

The build defines profiles to build Mylyn against different targets.
Profiles can be activated by passing `-P`<profile> to mvn.

  - `implicit-target` - build against nightly repositories, this is the
    default
  - `explicit-target` - build against a target definitions in
    `org.eclipse.mylyn/org.eclipse.mylyn-target`, needs to be activated
    through property `-Dexplicit-target`
  - `ganymede, galileo, indigo, juno, e4.1, e4.2` - build against a
    specific Eclipse release (requires `-Dexplicit-target`)

#### Properties

Properties control certain aspects of the build such as execution of
tests or optional analysis of source code. Properties can be set by
passing `-D`<property>`=`<value> to mvn. All properties are initialized
to sensible default values and are optional.

  - `tycho-version` - version of Tycho to use for building
  - `analysis.skip` - set to false to run code analysis (default: true)
  - `test.skip` - set to false to run tests (default:
    ${maven.test.skip})
  - `sign.skip` - set to false to run code signing (default: true)
  - `pack.skip` - set to false to run pack repositories (default: false)
  - `promote.skip` - set to false to copy artifacts to download location
    (default: true)

### Code

Mylyn uses the Eclipse code conventions with these minor additions ():

Tags: Mylyn uses the following tags in the code:

  - TODO: The following code needs to be reviewed.
  - TODO API: Indicates that a method or class needs to be reviewed.
  - TODO API x.y: This API is going to change for version x.y. Should
    include a description how it is going to change.
  - TODO e3.4: Make a change in the future specific to an Eclipse
    version.
  - XXX: The implementation uses a temporary work around that should be
    replaced by a proper solution in the future.
  - XXX SDK: The code uses internals of the Eclipse platform.
  - FIXME: Should only be used in very rare cases as a reminder that the
    marked code does not work as expected. Code marked as FIXME should
    not be distributed in a release.
  - FIXME REVIEW: Review the code before the next version is released

#### Creating new plug-ins and features

File a bug that describes the purpose of the new plug-ins and the
proposed names. Then add an item to the monthly meeting agenda to
discuss the request with other committers. Once consensus has been
reached follow the steps below.

To retain consistency of layout and settings, new projects should always
be created by copying an existing project rather than creating plug-in
or feature projects from scratch.

Steps for creating a new plug-in or feature:

1.  Copy an existing project on disk, e.g. to create an
    org.eclipse.myconnector.core bundle do the equivalent of running `cp
    -a org.eclipse.mylyn.bugzilla.core
    org.eclipse.mylyn.myconnector.core`
2.  Edit `pom.xml`, `.project` and `META-INF/MANIFEST` to reflect the
    new bundle id
3.  List the new bundle as a module in the parent pom to include it in
    the build
4.  Use Import Projects from the popup menu in the Git Repositories view
    to add the project to the workspace

For plug-ins these additional steps should be considered:

1.  Add bundle to feature
2.  Add source bundle to SDK feature

For features these additional steps should be considered:

1.  Add feature to site

### Contributions

Contributions are a key part of evolving Mylyn. All committers should
encourage and prioritize contributions.

### IP log

The IP log should always be kept up to date.

[Aggregated IP
log](http://eclipse.org/projects/ip_log.php?projectid=mylyn,mylyn.builds,mylyn.commons,mylyn.context,mylyn.docs,mylyn.reviews,mylyn.tasks,mylyn.versions)

Sub-project IP logs:

[Mylyn
Builds](http://eclipse.org/projects/ip_log.php?projectid=mylyn.builds)
[Mylyn
Commons](http://eclipse.org/projects/ip_log.php?projectid=mylyn.commons)
[Mylyn
Context](http://eclipse.org/projects/ip_log.php?projectid=mylyn.context)
[Mylyn
Docs](http://eclipse.org/projects/ip_log.php?projectid=mylyn.docs)
[Mylyn
Reviews](http://eclipse.org/projects/ip_log.php?projectid=mylyn.reviews)
[Mylyn
Tasks](http://eclipse.org/projects/ip_log.php?projectid=mylyn.tasks)
[Mylyn
Versions](http://eclipse.org/projects/ip_log.php?projectid=mylyn.versions)

#### Applying Patches

(*Note*: the section below is largely supplanted by the new Gerrit based
review system, which takes care of many of these details including
contributor IP approval.)

  - Note that each patch should not contain more than 1000 added lines.
    For larger patches we need to invoke the IP Review process.
  - Contributors frequently write quick patches in order to get
    something working for them. It is the responsibility of the
    committer to either encourage the contributor to improve the
    modularity and test coverage of the patch or to do those themselves
    if this aligns with the projects' priorities. Failing to do so can
    reduce the overall quality of the code and failing to get sufficient
    test coverage reduces our ability to evolve the code.

When applying a patch follow these steps:

**Git**

  - Enter the name of the contributor as the author of the commit
  - Encourage the contributor to update the patch into state where it
    can be applied unaltered.
  - If you need to make addtional changes that are non-trivial (e.g.,
    copyright header fixes) commit the unaltered patch first and then
    make another commit with your changes.
      - If absolutely necessary, a task-branch can be used to group
        commits and improve traceability otherwise commit messages
        should be sufficient to associate bugs with commits.
  - All files altered by a contributor must have a note in the copyright
    header and should have an @author tag if a change was significant.
  - If several authors have worked on a commit consider adding
    *Co-authored-by* headers to the commit message for each author.
  - Also see
    [Development_Resources/Handling_Git_Contributions](Development_Resources/Handling_Git_Contributions "wikilink")
    .

**Bugzilla**

  - Flag the the patch attachment as *iplog+*.
  - Add the *contributed* keyword to the corresponding bug.

### Web Site

  - If you haven't done it already, [upload your SSH public keys to
    Gerrit](https://git.eclipse.org/r/#/settings/ssh-keys) if you wish
    to use SSH
  - Clone
    <ssh://userid@git.eclipse.org:29418/www.eclipse.org/mylyn.git>,
    replacing `userid` with your id
  - You're ready to push your changes to the repo:
      - directly -- `git push origin master` (passing Gerrit review)
      - creating a review -- `git push origin HEAD:refs/for/master`, see
        [Gerrit\#Doing_Code_Reviews_with_Gerrit](Gerrit#Doing_Code_Reviews_with_Gerrit "wikilink")

Note, you need to be a member of the `mylyn` group to push changes to
the website.

## Workspace

The recommended way to work with Mylyn sources is by checking them out
of Git. Doing this makes it easy to try the latest changes and work with
patches and ensures that you can easily browse the source code and
documenation using Eclipse's facilities.

### Setup Using Oomph

You can use the Oomph installer to setup the Eclipse installation and
everything required to get started with Mylyn development. It downloads
Eclipse, sets the API baseline, clones the Mylyn git repo and imports
the projects for you. You can set the Target Platform from Galileo - 3.5
up to the actual version.

1.  Download the Oomph installer, available at
    <https://wiki.eclipse.org/Eclipse_Oomph_Installer>
2.  Start the installer using the *oomph* executable.
3.  At the package selection, click the preference button in the
    top-right corner and select the Advanced Mode button.
4.  If you are behind a proxy, at this point you might want to double
    check your network settings by clicking in the "Network Proxy
    Settings" at the bottom.
5.  Select Eclipse IDE for Eclipse Committers. Click next.
6.  Under Eclipse.org, double-click on the Mylyn components you want to
    use.
    The components have three subentries; if you select one of the
    subentries you do not need to select the parent folder to get the
    source. When you have selected your entries click finish.
    (Note: only Releng did not have the entries and in Tasks there is an
    extra option for the new Bugzilla REST Connector)
      - Bugzilla Bugs where you are owner, reporter, cc or commenter
      - Gerrit reviews where you are owner or reviewer
      - Hudson builds
7.  Enter
      - installation folder name
      - Target Platform (you can us older versions \>= Galileo-3.5)
      - there are some more variables, if you use the installer the
        first time
          - location of the git repositories
          - directory for the API Baseline
          - userid and password for Bugzilla/Hudson
8.  Click Next, Finish.

After the initial setup, you should have a complete Eclipse environment
to work on Mylyn and you can do the following optional steps to finish
setup.

  - [\#Markers](#Markers "wikilink")
  - [\#JUnit_Tests](#JUnit_Tests "wikilink")

### Git Repositories

The source code is hosted in Gerrit which is a code review system for
Git. Each sub-project has a separate repository that is accessible
through the git, ssh and https protocol. For anonymous access use git or
https. Committers need to use ssh or https.

[Web access to the Git repositories](http://git.eclipse.org/c/mylyn/)

**Release Tags:** Each release is tagged with `R_`. For example, Mylyn
2.2.0 for Eclipse 3.4 is tagged as `R_2_2_0` and the branched Eclipse
3.3 plug-ins are tagged `R_2_2_0_e_3_2`.

#### Active branches

  - Mylyn Releng:
      - `master`    3.x stream -
        **<git://git.eclipse.org/gitroot/mylyn/org.eclipse.mylyn.git>**
           [Web](http://git.eclipse.org/c/mylyn/org.eclipse.mylyn.git/)

<!-- end list -->

  - Mylyn Builds:
      - `master`    1.x stream -
        **<git://git.eclipse.org/gitroot/mylyn/org.eclipse.mylyn.builds.git>**
          
        [Web](http://git.eclipse.org/c/mylyn/org.eclipse.mylyn.builds.git/)
  - Mylyn Commons:
      - `master`    3.x stream -
        **<git://git.eclipse.org/gitroot/mylyn/org.eclipse.mylyn.commons.git>**
          
        [Web](http://git.eclipse.org/c/mylyn/org.eclipse.mylyn.commons.git/)
  - Mylyn Context:
      - `master`    3.x stream -
        **<git://git.eclipse.org/gitroot/mylyn/org.eclipse.mylyn.context.git>**
          
        [Web](http://git.eclipse.org/c/mylyn/org.eclipse.mylyn.context.git/)
  - Mylyn Context Model Focusing Tools (MFT):
      - `master`    0.9 stream -
        **<git://git.eclipse.org/gitroot/mylyn/org.eclipse.mylyn.context.mft.git>**
          
        [Web](http://git.eclipse.org/c/mylyn/org.eclipse.mylyn.context.mft.git/)
  - Mylyn Docs:
      - `master`    1.x stream -
        **<git://git.eclipse.org/gitroot/mylyn/org.eclipse.mylyn.docs.git>**
          
        [Web](http://git.eclipse.org/c/mylyn/org.eclipse.mylyn.docs.git/)
  - Mylyn Incubator:
      - `master`    3.x stream -
        **<git://git.eclipse.org/gitroot/mylyn/org.eclipse.mylyn.incubator.git>**
          
        [Web](http://git.eclipse.org/c/mylyn/org.eclipse.mylyn.incubator.git/)
  - Mylyn Reviews:
      - `master`    1.x stream -
        **<git://git.eclipse.org/gitroot/mylyn/org.eclipse.mylyn.reviews.git>**
          
        [Web](http://git.eclipse.org/c/mylyn/org.eclipse.mylyn.reviews.git/)
  - Mylyn Tasks:
      - `master`    3.x stream -
        **<git://git.eclipse.org/gitroot/mylyn/org.eclipse.mylyn.tasks.git>**
          
        [Web](http://git.eclipse.org/c/mylyn/org.eclipse.mylyn.tasks.git/)
  - Mylyn Versions:
      - `master`    1.x stream -
        **<git://git.eclipse.org/gitroot/mylyn/org.eclipse.mylyn.versions.git>**
          
        [Web](http://git.eclipse.org/c/mylyn/org.eclipse.mylyn.versions.git/)

Also see [policy for supported Eclipse
versions](http://wiki.eclipse.org/index.php/Mylyn/Integrator_Reference#Building_on_Mylyn).
Branched projects, if any, are updated with each release.

#### Maintenance Branches

Changes should be committed to master and cherry-picked onto maintenance
branches to be included in service releases.

  - `e_3_8_m_3_8_x`     Mylyn 3.8.x stream (corresponds to Mylyn Docs
    1.7.x)

### Target Environment

Mylyn depends on a number of libraries from other Eclipse projects. The
`org.eclipse.mylyn-target` project provides target environment
definitions that specify all required dependencies. After following the
steps under [Checkout](#Checkout "wikilink") go to *Window \>
Preferences* and open the *Target Platform* page. Select one of the
mylyn target definitions. Generally, *mylyn-dev-base* is the recommended
choice.

  - mylyn-dev-base - Targets the lowest support Eclipse version.
    Includes sources and additional integration features for
    development.
  - mylyn-dev-latest - Targets the highest support Eclipse version.
    Includes sources and additional integration features for
    development.
  - mylyn-e\* - Target defintions used by the build. May only contain
    the minimal requirements excluding sources.

### API Baseline

An API baseline for the latest releases is available from the [download
archive](http://www.eclipse.org/mylyn/downloads/archive.php#baseline).
Follow these instructions to configure the API baseline in your
workspace:

1.  Extract the Mylyn API baseline zip archive
2.  Add the baseline under Windows \> Preferences \> Plug-in Development
    \> API Baselines pointing to the extracted directory

### Markers

The general policy is that plug-ins should not have any errors or
warning markers since these indicate potential problems or API
insufficiencies. In practice, we do not have the capacity to address all
warnings or the cost outweighs the benefit or warnings result out of
intentional design decisions, e.g. usage of deprecated APIs for
maintaining backwards compatibility.

To reduce the number of warnings we have established the following
policies for usage of internal packages:

1.  Plug-ins are allowed to use internals within the boundaries of their
    component (e.g. o.e.m.bugzilla.ui may access internals of
    o.e.m.bugzilla.core). We have generally allowed that through
    x-friends relationships in plug-in manifests.
2.  It's generally okay to use provisional APIs. We have made these
    accessible through classpath filters: Project Properties \> Java
    Build Path \> Libraries \> Plug-in Dependencies \> Access rules.
    It's common that plug-ins have a rule to make
    org/eclipse/mylyn/internal/provisional/\*\* accessible.
3.  In cases where platform internals need to be accessed due to a lack
    of API it's okay to make the specific classes or packages
    accessible. These cases should be documented on .
4.  Test plug-ins are allowed to use all internals.

Additionally, it is recommend to create custom filters in the workspace
to hide remaining warnings that will not get addressed in the short
time. Filter can be configured through the view menu of the Markers
view.

### JUnit Tests

The *bundle*.tests bundles (e.g. org.eclipse.mylyn.tasks.core.tests) are
unit tests; the bundles are fragments to enable unit testing with
package private access. The *component*.tests bundles (e.g.
org.eclipse.mylyn.tasks.tests) are integration tests that run against
the API.

Each component has it's own All<Component>Tests suite. If not familiar
with running PDE JUnit tests, refer to the [Eclipse
Documentation](http://help.eclipse.org/help32/index.jsp?topic=/org.eclipse.pde.doc.user/guide/tools/launchers/eclipse_main.htm).

Tests that connect to repositories require a
*$HOME/.mylyn/credentials.properties* file that specifies authentication
information. The file needs to have the following content:

`user: `<user>
`pass: `<pass>

  - For <user> use *tests@mylyn.eclipse.org*. For <pass> use
    *mylyntest*. If you have any trouble making this work email
    mylyn-dev@eclipse.org.
  - Add the following to the test configuration under Arguments -\> VM
    Arguments: -enableassertions -Xmx384M

Test suites in org.eclipse.mylyn.tests:

  - **`AllTests`**: all automatic tests, should always pass, run as a
    *JUnit Plug-in Test*
  - **`AllHeadlessStandaloneTests`**: do not require workbench, can run
    as *JUnit Test*, subset of `AllTests`
  - **`AllConnectorTests`**: all automatic tests for repository
    connectors, requires network access

Test suites in org.eclipse.mylyn.tests.ui:

  - **`AllUiTests`**: all automatic SWTbot-based UI tests

Test suites in org.eclipse.mylyn.tests.performance:

  - **`AllPerformanceTests`**: all performance tests

### Manual tests

The manual tests can be found on the **[Mylyn
Testing](Mylyn_Testing "wikilink")** page.

  - Component owners are responsible for maintaining their respective
    manual tests and ensuring they are covered two days prior to
    release.

Trac Connector

  - A Trac test repository that offers anonymous access through XML-RPC
    is available at <http://mylyn.eclipse.org/tractest>. Feel free to
    create or modify any tickets.

## Incubator

The Mylyn Incubator is a set of projects and feature contributors use
for experimentation. These features are not intended to be used for
daily development. Incubator features include experimental connectors
and bridges, experimental UI features, and developer tools. To use
Incubator tools either check them out of the version control, or install
them using the Incubator update site.

### Dev tools

  - **Introspect Object** (action): displays the class and other
    relevant information (e.g. degree-of-interest, task synchronization
    state) of any object visible in the workbench. Appears at the end of
    the context menu for any view that accepts an object contributions.

<!-- end list -->

  - **Interest Level Decorator**: displays the floating point interest
    level of elements. Enable via *Decorators* preference page.

<!-- end list -->

  - **Repository Spy**: displays the repositories with all their
    atrtributes in a separate view. Allows the deletion of selected
    properties.

<!-- end list -->

  - **Properties View sources**: Shows properties of items selected in
    the Tasklist View or Task Repositories view in the standard Eclipse
    Properties View.

### Experimental tools

The following experimental views can be opened via the *Experimental*
view category or accessed via the *Tasks -\> Experimental* preference
page.

  - **Context Search**: Automatically finds and displays elements that
    are structurally related to landmarks in the active . These elements
    become part of the task context and have a predicted
    degree-of-interest.

<!-- end list -->

  - **Context Hierarchy**: Displays the Java hierarchy of all landmark
    elements.

<!-- end list -->

  - **Predicted interested for Java errors**: Potentially useful, but
    tends to overload the Package Explorer. If you find this useful for
    long-term use condiser commenting on
    [bug 107542](https://bugs.eclipse.org/bugs/show_bug.cgi?id=107542).

## Tips and Tricks

### User support

  - Every time that you find yourself formulating an answer to a bug
    report, email, or newsgroup post, if the answer is more than a
    sentence, consider updating the FAQ, User Guide, or Integrator
    Reference and pointing to the entry.
  - Every time that resolving a bug does not result in a code change
    that addresses the problem or clarifies the UI, update the FAQ or
    User Guide to make sure that users can self-diagnose the problem.
    This is particularly important for bugs marked INVALID or
    WORKSFORME.

### Code

  - For error handling use `StatusHandler` and pass an `IStatus` object.
    Note that some of the other Mylyn code uses the convenience methods
    on `StatusHandler`, but we are phasing those out because they do not
    pass the plug-in ID that the exception originated from.
  - Use `WorkbenchJob` for running jobs that should only run when the
    workbench is active. Not doing this can cause errors on workbench
    shutdown (e.g.
    [bug 178409)](https://bugs.eclipse.org/bugs/show_bug.cgi?id=178409).
  - When using `String.toLowerCase()`, use
    `String.toLowerCase(Locale.ENGLISH)` to ensure locale safety (see
    [bug 168652](https://bugs.eclipse.org/bugs/show_bug.cgi?id=168652)).
  - Do not use `@Override` annotations on implementing methods, only on
    overriding methods. Doing so violates Java 5
    ([bug 173171](https://bugs.eclipse.org/bugs/show_bug.cgi?id=173171)).
  - Use DateFormat with extra caution. It is not thread-safe and should
    not be saved to fields in classes that can be used from multiple
    threads (UI, asynchonous execution, or jobs).
  - For the sake of multi-monitor setups, use `getMonitor()` instead of
    `getDisplay()` when you want to position a UI element on a specific
    coordinate of the screen.
  - To improve the speed of decorators use setUseHashlookup(true) on all
    structured viewers.

### Bugzilla

  - **Query setup**: If you are added to the cc list on a report that is
    not picked up by your usual queries it may go unnoticed. One trick
    is to create a query for ALL products except the product you usually
    work in (and hence have queries for) and set the cc field of the
    query to your id. Now you will be notified of anybody adding you to
    the cc of a product you don't usually monitor.

### JDT

  - **Including Platform plug-ins in search**: Java search (Ctrl+H \>
    Java Search) will include all plugins in your Plugin-in
    Dependencies. If you want to search other plugins as well, open the
    Plug-ins view, right click on the desired plugin(s) and choose 'Add
    to Java Search'. That plugin will now always be included in your
    java searches.

### Debugging

  - **Task List problems**: do not ask users to send or attach their
    Task List, since it can contain highly sensitive information. If
    needed ask the user to create a new workspace and try to reproduce
    the problem there, ensuring that they have not included any user
    private or company private information, and have them send that.

<!-- end list -->

  - **Plug-ins fail to load**: verify that plug-in dependencies are met
    via the *Validate Plug-in Set* button on the launch configuration
    *Plug-ins* tab.
  - **Startup failure**: If you get an `IStartup` failure message or a
    `ClassNotFoundException` on startup this is often the result of some
    step in the activation of the plug-in failing.
      - Attempt to find the earliest exception thrown within the in the
        plug-in's activation process. For example, this could occur in
        `TasksUiPlugin.start()` or `TasksUiPlugin.`<init>.
      - If the cause of the failure is not straightforward, the problem
        could be due to a class loading race condition. This can
        sometimes be verified by trying a different VM like IBM's or
        BEA's and checking if that resolves the problem. If this is the
        case, please file a bug.
  - **Getting a thread dump** (when Eclipse hangs):
      - On Windows use the tool found at [the adaptj home
        page](http://www.adaptj.com/root/main/download):
          - Follow the link and select button "Launch" and run the
            applet
          - Select menu Process \> Thread Dump
          - In the combo box "Process ID" select the Java VM and click
            OK
      - Or, run Eclipse with the `-debug` option (or use `java.exe`
        instead `javaw.exe` on windows), then
          - On Windows: Hit a `Ctrl-Break` few times on the console
            window during that long synchronization to capture the
            thread dump
      - Or, on Linux: Use `Ctrl-\` on the console or send SIG_QUIT
        signal: ` kill -SIGQUIT  `*`pid`*
      - Or, with jconsole (requires 1.5 jdk, works on any OS):
          - Launch `eclipse -vmargs -Dcom.sun.management.jmxremote`
          - Launch the JDK's jconsole tool. You can attach to the Java
            Process and copy\&paste the thread dump.
      - Use
        [`jps`](http://java.sun.com/j2se/1.5.0/docs/tooldocs/share/jps.html)
        to find the PIDs of Java processes and
        [`jstack`](http://java.sun.com/j2se/1.5.0/docs/tooldocs/share/jstack.html)
        to show the stack trace of Java processes: ` jstack  `*`pid`*
          - Supported starting JDK 5 for UNIX / JDK 6 for Windows
      - See this [Weblog on
        jstack](http://blogs.sun.com/alanb/entry/jstack)
      - Also see [Thread Dump and Concurrency
        Locks](http://weblogs.java.net/blog/mandychung/archive/2005/11/thread_dump_and_1.html)
        for more details.
  - **Startup problems and deadlocks**: for a diagnosis of a potential
    problem see diagnosis on
    <https://bugs.eclipse.org/bugs/show_bug.cgi?id=177048#c3>

[Category:Mylyn](Category:Mylyn "wikilink") [Category:How to
Contribute](Category:How_to_Contribute "wikilink")