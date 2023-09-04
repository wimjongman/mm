[category:Mylyn](category:Mylyn "wikilink")

Here are my findings from trying to setup Gerrit 2.6 with Mylyn Reviews
(while tackling )

### Glimpse at the code

  - The connector already uses some REST API, e.g. for querying changes
  - Form based login (GET /login/mine with creds set) still works, the
    login cookie seems to be properly set. The client is asked to
    redirect (302), but it looks this can be safely ignored. Providing
    invalid creds results in an auth failure, good.
  - GerritClient (used for calling RPC API) expects JSON responses: see
    `org.eclipse.mylyn.internal.gerrit.core.client.GerritService.invoke(Object,
    Method, Object[])`
  - Current support for different Gerrit versions:
      - there are places where GerritClient fallbacks to REST e.g.
        calling `GerritClient#executeQueryRest` from
        `GerritClient#queryMyReviews`
      - OTOH, there is a fallback to Gerrit \<=2.2.1 in
        `GerritClient#getVisibleProjects(IProgressMonitor,
        GerritConfig)`
      - it looks like the client cannot decide if fallbacks should be
        used for supporting newer or older versions of Gerrit

### Running tests

  - Some tests fail because getVisibleProjects (RPC) gets `"Invalid
    xsrfKey in request"` response while refreshing repo config
  - Tests from `GerritReviewRemoteFactoryTest` and
    `PatchSetRemoteFactoryTest` fail waiting for a response

### Using the connector with Gerrit 2.6

  - validating repo as anonymous:
    `{"jsonrpc":"2.0","id":1,"error":{"code":-32603,"message":"No such
    service method"}}`
  - getting configuration before creating a new query: the client tries
    to parse an HTML page in
    `GerritClient.refreshGerritConfig(IProgressMonitor)`, and fails as
    it gets a 302 page in Gerrit 2.6
  - if I ignore the error about config not available I'm able to create
    a query but get an NPE (quick fixed in
    <https://git.eclipse.org/r/#/c/13982/>)
  - ^^^ should I be able to do that in the first place?

### Comments on Gerrit 2.6 Release Notes

Incompatibilities introduced by the new REST API:

> "The structure of the AuditEvent has been extended to support the new
> name-multivalue pairs used in the REST API. **This is breaking
> compatibility with the 2.5 API as it changes the params data type**,
> this is needed anyway as the previous list of Objects was not
> providing all the necessary information of "what relates to what" in
> terms of parameters info."

> "Remove support for deprecated --format option when listing changes.
> Querying changes via REST is now always producing JSON output."

The latter has been already fixed in
<https://git.eclipse.org/r/#/c/14181/>

More info:
<http://gerrit-documentation.googlecode.com/svn/ReleaseNotes/ReleaseNotes-2.6.html#_rest_api>

ID changes, mentioned by Shawn on :

  - Changes:
    <http://gerrit-documentation.googlecode.com/svn/Documentation/2.6/rest-api-changes.html#ids>
  - Projects:
    <http://gerrit-documentation.googlecode.com/svn/Documentation/2.6/rest-api-projects.html#ids>
  - not sure if we care much about Groups and Accounts

I think it's safe to assume that RPC API should still be operational and
it's the REST API (urls and JSON objects) that needs to be taken care
of. However, my guess is that the RPC interface is going to be dropped
once the REST API is stable, so we should be using it wherever possible.

### Draft review

...with quick and dirty fixes <https://git.eclipse.org/r/#/c/13982/>

Applying the changes gives a semi-functional connector: I'm able to
create a Gerrit 2.6 repo as anonymous and add a query. I can even open a
review editor with some UI bits properly populated: e.g. can see Change
Sets and files in them. There's still a bunch of NPE flying around and
authentication looks totally broken.

What the patch covers:

1.  switches RPC interface from `/gerrit/rpc` to `/gerrit_ui/rpc` (no
    backward compatibility\!)
2.  ~~runs queries even when `format` paramater is not supported~~
    already fixed in <https://git.eclipse.org/r/#/c/14181/>
3.  avoids NPE in GerritReviewRemoteFactory since gerrit config cannot
    be retrieved
4.  turns `testPerformQueryAnonymous` and `testGetAccountAnonymous`
    tests green

### What needs to be done

#### For 2.0.1

  - Fix authentication
      - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif")[it
        looks that the `xsrfToken` (which was a copy of the cookie
        value) is gone in 2.6. It has been replaced with
        `X-Gerrit-Auth`](https://git.eclipse.org/r/#/c/14191/)</strike>
  - not able to retrieve server configuration
      - ... even as anonymous user. It does not work for 2.4 either
  - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif") [remote
    usage of deprecated `format` query
    parameter](https://git.eclipse.org/r/#/c/14181)
  - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif") [find out
    the Gerrit version](https://git.eclipse.org/r/#/c/14232/) (was:
    Parsing HTML and getting Gerrit config from HTML page no longer
    works in 2.6),
    [here](https://groups.google.com/forum/#!msg/repo-discuss/OfojHxtmiTk/hNiOWSDK2ZUJ)
    is a better way of doing this, thx Shawn,
      - the most accurate way of doing this, unfortunately available
        only for the latest 2.7
      - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif") [...
        and display a warning if it's not fully supported
        yet](https://git.eclipse.org/r/#/c/14502/)
  - Failing operations
      - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif")
        [publish comments](https://git.eclipse.org/r/#/c/14561/)
      - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif")
        [abandon: a test failing
        in 2.6](https://git.eclipse.org/r/#/c/14625/)
      - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif") [adding
        inline comments](https://git.eclipse.org/r/#/c/14653/)
      - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif") [adding
        reviewers](https://git.eclipse.org/r/14714)
      - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif")
        restoring a change
      - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif")
        submitting a change
      - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif")
        [publish inline comments,
        drafts](https://git.eclipse.org/r/14653)
  - Update expected JSON objects in responses, same for JSON objects
    sent in requests
      - [\#approvalTypes](#approvalTypes "wikilink") [are no longer
        returned as part of
        configuration](https://git.eclipse.org/r/#/c/14589/)
  - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif") make all
    tests green, current status (against a 2.6.1 repository):
      - ~~6 errors~~
          - org.eclipse.mylyn.gerrit.tests.core.[GerritSynchronizationTest](https://git.eclipse.org/c/mylyn/org.eclipse.mylyn.reviews.git/tree/org.eclipse.mylyn.gerrit.tests/src/org/eclipse/mylyn/gerrit/tests/core/GerritSynchronizationTest.java).testSynchronizeTaskUpdated()
          - org.eclipse.mylyn.gerrit.tests.core.GerritSynchronizationTest.testSynchronizeBackgroundQueryTaskUpdated()
          - org.eclipse.mylyn.gerrit.tests.core.GerritSynchronizationTest.testSynchronizeBackgroundTaskUpdated()
          - org.eclipse.mylyn.gerrit.tests.core.GerritSynchronizationTest.testSynchronizeQueryTaskUpdated()
          - [org.eclipse.mylyn.internal.gerrit.core.remote.GerritReviewRemoteFactoryTest](https://git.eclipse.org/c/mylyn/org.eclipse.mylyn.reviews.git/tree/org.eclipse.mylyn.gerrit.tests/src/org/eclipse/mylyn/internal/gerrit/core/remote/GerritReviewRemoteFactoryTest.java).testGlobalComments
          - [org.eclipse.mylyn.internal.gerrit.core.remote.PatchSetRemoteFactoryTest](https://git.eclipse.org/c/mylyn/org.eclipse.mylyn.reviews.git/tree/org.eclipse.mylyn.gerrit.tests/src/org/eclipse/mylyn/internal/gerrit/core/remote/PatchSetRemoteFactoryTest.java).testPatchSetComments
      - ~~2 failures~~
          - [org.eclipse.mylyn.gerrit.tests.core.client.GerritClientTest.testGetVersion()](https://git.eclipse.org/r/#/c/14557/)
          - [org.eclipse.mylyn.internal.gerrit.core.remote.GerritReviewRemoteFactoryTest](https://git.eclipse.org/c/mylyn/org.eclipse.mylyn.reviews.git/tree/org.eclipse.mylyn.gerrit.tests/src/org/eclipse/mylyn/internal/gerrit/core/remote/GerritReviewRemoteFactoryTest.java).testApprovals()
      - running tests against a 2.7-rc1 repo I got 6 errors and 3
        failures, but that's a story for a different
  - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif") add more
    tests
      - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif")
        [abandon a change](https://git.eclipse.org/r/#/c/14559/)
      - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif") [assert
        that a change detail contains
        approvals](https://git.eclipse.org/r/#/c/14589/)
      - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif")
        [restore a change](https://git.eclipse.org/r/#/c/14661/)
      - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif") [add a
        test asserting that a change cannot be rebased when up to
        date](https://git.eclipse.org/r/#/c/14688/)
      - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif") [assert
        that you cannot submit a change without
        approvals](https://git.eclipse.org/r/14663)
      - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif") [add
        tests for adding reviewers](https://git.eclipse.org/r/14704)
      - ![Image:Ok green.gif](Ok_green.gif "Image:Ok green.gif") [add a
        test for loading patch set
        content](https://git.eclipse.org/r/14707)
      - submit a change
  - ![Image:Glass.gif](Glass.gif "Image:Glass.gif") not sure if it makes
    much sense, as it's basically testing Gerrit not Reviews, but we
    could consider adding some simple tests parsing JSON responses (to
    detect breaking changes early)

#### For 2.1

  - (on hold) decouple Remote API from GerritClient, allowing to provide
    different implementations depending on the targeted Gerrit version
      - avoid exception driven logic in GerritClient
      - [Tomek's proposal](https://git.eclipse.org/r/#/c/14229/)
      - [Miles' proposal](https://git.eclipse.org/r/#/c/14241/)

#### approvalTypes

[In 2.6, Gerrit config misses expected `"approvalTypes"`
node](http://gerrit-documentation.googlecode.com/svn-history/r46/ReleaseNotes/ReleaseNotes-2.6.html#_labels),
which causes a RuntimeException in GerritReviewRemoteFactory when
opening a review:

    Caused by: java.lang.RuntimeException: Internal Error, no approval type found for: Verified
        at org.eclipse.mylyn.internal.gerrit.core.remote.GerritReviewRemoteFactory.updateApprovalsAndRequirements(GerritReviewRemoteFactory.java:339)
        at org.eclipse.mylyn.internal.gerrit.core.remote.GerritReviewRemoteFactory.updateModel(GerritReviewRemoteFactory.java:216)
        at org.eclipse.mylyn.internal.gerrit.core.remote.GerritReviewRemoteFactory.updateModel(GerritReviewRemoteFactory.java:1)
        at org.eclipse.mylyn.reviews.core.spi.remote.emf.RemoteEmfConsumer.applyModel(RemoteEmfConsumer.java:234)
        at org.eclipse.mylyn.reviews.core.spi.remote.JobRemoteService$3.run(JobRemoteService.java:95)
        at org.eclipse.ui.internal.UILockListener.doPendingWork(UILockListener.java:164)
        at org.eclipse.ui.internal.UISynchronizer$3.run(UISynchronizer.java:158)
        at org.eclipse.swt.widgets.RunnableLock.run(RunnableLock.java:35)
        at org.eclipse.swt.widgets.Synchronizer.runAsyncMessages(Synchronizer.java:135)
        ... 23 more

This has been temporarily fixed in
<https://git.eclipse.org/r/#/c/14453/>

A response from a 2.5.x server:

    {
        "reportBugUrl" : "http://code.google.com/p/gerrit/issues/list",
        "useContributorAgreements" : false,
        "useContactInfo" : false,
        "allowRegisterNewEmail" : false,
        "authType" : "HTTP",
        "downloadSchemes" : ["DEFAULT_DOWNLOADS"],
        "downloadCommands" : ["DEFAULT_DOWNLOADS"],
        "sshdAddress" : "*:29254",
        "wildProject" : {
            "name" : "All-Projects"
        },
        "approvalTypes" : {
            "approvalTypes" : [{
                    "category" : {
                        "categoryId" : {
                            "id" : "VRIF"
                        },
                        "name" : "Verified",
                        "abbreviatedName" : "V",
                        "position" : 0,
                        "functionName" : "MaxWithBlock",
                        "copyMinScore" : false,
                        "labelName" : "Verified"
                    },
                    "values" : [{
                            "key" : {
                                "categoryId" : {
                                    "id" : "VRIF"
                                },
                                "value" : -1
                            },
                            "name" : "Fails"
                        }, {
                            "key" : {
                                "categoryId" : {
                                    "id" : "VRIF"
                                },
                                "value" : 0
                            },
                            "name" : "No score"
                        }, {
                            "key" : {
                                "categoryId" : {
                                    "id" : "VRIF"
                                },
                                "value" : 1
                            },
                            "name" : "Verified"
                        }
                    ],
                    "maxNegative" : -1,
                    "maxPositive" : 1
                }, {
                    "category" : {
                        "categoryId" : {
                            "id" : "CRVW"
                        },
                        "name" : "Code Review",
                        "abbreviatedName" : "R",
                        "position" : 1,
                        "functionName" : "MaxWithBlock",
                        "copyMinScore" : true,
                        "labelName" : "Code-Review"
                    },
                    "values" : [{
                            "key" : {
                                "categoryId" : {
                                    "id" : "CRVW"
                                },
                                "value" : -2
                            },
                            "name" : "Do not submit"
                        }, {
                            "key" : {
                                "categoryId" : {
                                    "id" : "CRVW"
                                },
                                "value" : -1
                            },
                            "name" : "I would prefer that you didn\u0027t submit this"
                        }, {
                            "key" : {
                                "categoryId" : {
                                    "id" : "CRVW"
                                },
                                "value" : 0
                            },
                            "name" : "No score"
                        }, {
                            "key" : {
                                "categoryId" : {
                                    "id" : "CRVW"
                                },
                                "value" : 1
                            },
                            "name" : "Looks good to me, but someone else must approve"
                        }, {
                            "key" : {
                                "categoryId" : {
                                    "id" : "CRVW"
                                },
                                "value" : 2
                            },
                            "name" : "Looks good to me, approved"
                        }
                    ],
                    "maxNegative" : -2,
                    "maxPositive" : 2
                }
            ]
        },
        "editableAccountFields" : ["FULL_NAME", "USER_NAME", "REGISTER_NEW_EMAIL"],
        "commentLinks" : [{
                "find" : "(I[0-9a-f]{8,40})",
                "replace" : "\u003ca href\u003d\"#q,$1,n,z\"\u003e$\u0026\u003c/a\u003e"
            }, {
                "find" : "(bug\\s+)(\\d+)",
                "replace" : "\u003ca href\u003d\"http://bugs.mylyn.org/show_bug.cgi?id\u003d$2\"\u003e$\u0026\u003c/a\u003e"
            }, {
                "find" : "([Tt]ask:\\s+)(\\d+)",
                "replace" : "$1\u003ca href\u003d\"http://tracker.mylyn.org/$2\"\u003e$2\u003c/a\u003e"
            }
        ],
        "documentationAvailable" : true,
        "testChangeMerge" : false,
        "anonymousCowardName" : "Anonymous Coward"
    }

... and from 2.6:

    {
        "reportBugUrl" : "http://code.google.com/p/gerrit/issues/list",
        "useContributorAgreements" : false,
        "useContactInfo" : false,
        "allowRegisterNewEmail" : false,
        "authType" : "HTTP",
        "downloadSchemes" : ["DEFAULT_DOWNLOADS"],
        "downloadCommands" : ["DEFAULT_DOWNLOADS"],
        "sshdAddress" : "*:29260",
        "wildProject" : {
            "name" : "All-Projects"
        },
        "editableAccountFields" : ["FULL_NAME", "USER_NAME", "REGISTER_NEW_EMAIL"],
        "commentLinks" : [{
                "find" : "(I[0-9a-f]{8,40})",
                "replace" : "\u003ca href\u003d\"#q,$1,n,z\"\u003e$\u0026\u003c/a\u003e"
            }, {
                "find" : "(bug\\s+)(\\d+)",
                "replace" : "\u003ca href\u003d\"http://bugs.mylyn.org/show_bug.cgi?id\u003d$2\"\u003e$\u0026\u003c/a\u003e"
            }, {
                "find" : "([Tt]ask:\\s+)(\\d+)",
                "replace" : "$1\u003ca href\u003d\"http://tracker.mylyn.org/$2\"\u003e$2\u003c/a\u003e"
            }
        ],
        "documentationAvailable" : true,
        "testChangeMerge" : false,
        "anonymousCowardName" : "Anonymous Coward",
        "suggestFrom" : 0
    }