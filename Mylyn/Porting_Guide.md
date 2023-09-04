# General

Mylyn follows the Eclipse conventions for [version
numbering](Version_Numbering "wikilink") and guarantees [binary
backwards compatibility](Evolving_Java-based_APIs "wikilink") for minor
releases. Internals are binary backwards compatible between service
releases.

API enhancements can be tracked by searching the source code for the
corresponding @since JavaDoc tags or by querying for bugs that have
\[api\] in their summary.

# Changes in 3.22

  - Connectors that do not provide a task key no longer have their task
    ID automatically used as the key. Connectors that rely on this
    behaviour should explicitly set the task key to the ID. This change
    actually occurred in Mylyn 3.21 but was not added to this page until
    the 3.22 release.

# Changes in 3.20

  - `AbstractTaskListMigrator` and its related extension point have been
    deprecated. Contributed migrators will no longer be applied when
    loading the Task List ().

# Changes in 3.12

  - The SOAP transport was removed ().

# Changes in 3.11

  - The SOAP transport was deprecated ().

# Changes in 3.10

None.

# Porting from 3.8 to 3.9

## Mylyn Reviews

The Reviews framework has had a major update which resulted in changes
to the core model and API. In consequence, the version was updated to
2.0.

# Porting from 3.7 to 3.8

No API changes that affect integrators.

# Porting from 3.6 to 3.7

## Mylyn Commons

  - Restructuring of Mylyn Commons features

The Mylyn Commons components were restructured and provisional packages
were promoted to API. Several bundle IDs, package names and extension
IDs were changed in the process. Classes in provisional packages were
kept but marked as deprecated and will be removed in a future release.
None of the changes break API backwards compatibility but integrations
that consumed internal packages or extensions points may need to be
adapted.

The following bundles were renamed:

`org.eclipse.mylyn.commons.identity      -> org.eclipse.mylyn.commons.identity.core`
`org.eclipse.mylyn.commons.notifications -> org.eclipse.mylyn.commons.notifications.ui`
`org.eclipse.mylyn.commons.repositories  -> org.eclipse.mylyn.commons.repositories.core`
`org.eclipse.mylyn.commons.team          -> org.eclipse.mylyn.commons.repositories.ui`

A complete list of renamed and added bundles can be found on bug 305782
on
[comment 13](https://bugs.eclipse.org/bugs/show_bug.cgi?id=305782#c13).

The following packages were renamed:

`org.eclipse.mylyn.commons.identity     -> org.eclipse.mylyn.commons.identity.core`
`org.eclipse.mylyn.commons.repositories -> org.eclipse.mylyn.commons.repositories.core`
`org.eclipse.mylyn.commons.ui.team      -> org.eclipse.mylyn.commons.repositories.ui`

The following provisional packages were promoted to API (see ):

`org.eclipse.mylyn.internal.provisional.commons.core        -> org.eclipse.mylyn.commons.core`
`org.eclipse.mylyn.internal.provisional.commons.ui          -> org.eclipse.mylyn.commons.ui`
`                                                           -> org.eclipse.mylyn.commons.workbench`
`                                                           -> org.eclipse.mylyn.commons.workbench.browser`
`                                                           -> org.eclipse.mylyn.commons.workbench.editors`
`                                                           -> org.eclipse.mylyn.commons.workbench.forms`
`                                                           -> org.eclipse.mylyn.commons.workbench.search`
`org.eclipse.mylyn.internal.provisional.commons.ui.actions  -> org.eclipse.mylyn.commons.ui`
`org.eclipse.mylyn.internal.provisional.commons.ui.commands -> org.eclipse.mylyn.commons.workbench.texteditor`
`org.eclipse.mylyn.internal.provisional.commons.ui.dialogs  -> org.eclipse.mylyn.commons.ui.dialogs`
`org.eclipse.mylyn.internal.provisional.commons.ui.editor   -> org.eclipse.mylyn.commons.workbench`

In some cases provisional packages do not map directly to API packages
but classes were distributed among several packages.

The following extension points have moved:

`org.eclipse.mylyn.commons.team.newWizards -> org.eclipse.mylyn.commons.repositories.ui.newWizards`

The following extension IDs have changed:

`org.eclipse.mylyn.commons.team.navigator.Repositories -> org.eclipse.mylyn.commons.repositories.ui.navigator.Repositories`
`org.eclipse.mylyn.commons.team.category               -> org.eclipse.mylyn.commons.repositories.ui.category.Team`

# Porting from 3.0 to 3.6

See the <b>[Mylyn/Porting
Guide/3.x](Mylyn/Porting_Guide/3.x "wikilink")</b>

# Porting from 2.0 to 3.0

See the <b>[Mylyn/Porting
Guide/3.0](Mylyn/Porting_Guide/3.0 "wikilink")</b>

# Porting from 1.0 to 2.0

See the <b>[Mylyn Porting Guide
2.0](Mylyn_Porting_Guide_2.0 "wikilink")</b>

[Category:Mylyn](Category:Mylyn "wikilink")