Atlassian has ended support for the Atlassian JIRA connector See [this
blog
post](https://developer.atlassian.com/blog/2015/06/discontinuing-ide-connectors-support/)
for more details.

## Information for Integrators

The Atlassian update site distributes a feature and plug-in that with
the same bundle ids as the Mylyn JIRA Connector
(org.eclipse.mylyn.jira_feature) but with a higher version (3.4.0) than
the latest available release of the Mylyn JIRA Connector. The stubs do
not contain classes or extension points and effectively disable the
Mylyn JIRA Connector.

Extensions that integrate with the Mylyn JIRA Connector need to specifiy
the following version constraints in the manifest:

`Require-Bundle:  org.eclipse.mylyn.jira.core;bundle-version="[3.3.2,3.4.0)",`
` org.eclipse.mylyn.jira.ui;bundle-version="[3.3.2,3.4.0)"`

Features should specify an equivalent version match:

<import feature="org.eclipse.mylyn_feature" version="3.3.2" match="equivalent"/>

The latest release of the Mylyn JIRA Connector is available from this
archive update site:
archive.eclipse.org/mylyn/drops/3.3.2/v20100222-0100/extras

[Category:Mylyn](Category:Mylyn "wikilink")