This listing is intended for prospective contributors, [Google Summer of
Code](Mylyn/SOC "wikilink") students, and others interesting in becoming
part of the Mylyn contributor community. For an up-to-date listing of
bugs that have been marked for contribution see:

  - **[bugs marked for
    bugday](https://bugs.eclipse.org/bugs/buglist.cgi?query_format=advanced&short_desc_type=allwordssubstr&short_desc=&product=Mylyn&long_desc_type=allwordssubstr&long_desc=&bug_file_loc_type=allwordssubstr&bug_file_loc=&keywords_type=allwords&keywords=bugday&bug_status=NEW&bug_status=ASSIGNED&bug_status=REOPENED&emailtype1=substring&email1=&emailtype2=substring&email2=&bugidtype=include&bug_id=&votes=&chfieldfrom=&chfieldto=Now&chfieldvalue=&cmdtype=doit&order=Reuse+same+sort+as+last+time&field0-0-0=noop&type0-0-0=noop&value0-0-0=)**.
  - **[bugs marked as
    helpwanted](https://bugs.eclipse.org/bugs/buglist.cgi?query_format=advanced&short_desc_type=allwordssubstr&short_desc=&product=Mylyn&long_desc_type=allwordssubstr&long_desc=&bug_file_loc_type=allwordssubstr&bug_file_loc=&keywords_type=allwords&keywords=helpwanted&bug_status=NEW&bug_status=ASSIGNED&bug_status=REOPENED&emailtype1=substring&email1=&emailtype2=substring&email2=&bugidtype=include&bug_id=&votes=&chfieldfrom=&chfieldto=Now&chfieldvalue=&cmdtype=doit&order=Reuse+same+sort+as+last+time&field0-0-0=noop&type0-0-0=noop&value0-0-0=)**.

## Ideas

  - Additional project ideas are listed under
    [Google_Summer_of_Code_2012_Ideas](Google_Summer_of_Code_2012_Ideas "wikilink")

## Enhancements

  - [workflow
    bugs](https://bugs.eclipse.org/bugs/buglist.cgi?query_format=specific&order=relevance+desc&bug_status=__open__&product=Mylyn&content=%5Bworkflow%5D):
    Provide lightweight workflow actions (e.g. trigger a commit when a
    bug is closed). This involves adding workflow support to the Tasks
    framework and implementing task editor actions for for workflow.

<!-- end list -->

  - : Add interest-based folding to WTP's XML editor.

<!-- end list -->

  - : Improve duplicate detection mechanism and heuristics.

<!-- end list -->

  - Improve the new user's experience. This could involve creating a
    welcome page, cheat sheets, and streamlining the process of going
    from installing Mylyn to having a task repository.

<!-- end list -->

  - : provide find functionality for task editor

## Performance

  - Identify key performance
    [bottlenecks](http://wiki.eclipse.org/index.php/Performance_Bloopers)
    and address [existing performance
    bugs](https://bugs.eclipse.org/bugs/buglist.cgi?query_format=advanced&short_desc_type=allwordssubstr&short_desc=%5Bperformance%5D&product=Mylyn&component=Core&component=Doc&component=Java&component=Jira&component=Monitor&component=Tasks&component=Trac&component=UI&component=Web&long_desc_type=allwordssubstr&long_desc=&bug_file_loc_type=allwordssubstr&bug_file_loc=&status_whiteboard_type=allwordssubstr&status_whiteboard=&keywords_type=allwords&keywords=&bug_status=UNCONFIRMED&bug_status=NEW&bug_status=ASSIGNED&bug_status=REOPENED&emailtype1=substring&email1=&emailtype2=notregexp&email2=&bugidtype=include&bug_id=&votes=&chfieldfrom=&chfieldto=Now&chfieldvalue=&cmdtype=doit&order=Reuse+same+sort+as+last+time&field0-0-0=noop&type0-0-0=noop&value0-0-0=)
    by implementing a [performance test
    harness](https://bugs.eclipse.org/bugs/show_bug.cgi?id=116487)

## Connectors

  - [bug 170894](https://bugs.eclipse.org/bugs/show_bug.cgi?id=170894):
    create an example connector project to be used by integrators as a
    template. This connector should be simple, for example, it could
    provide integration with a local comma-delimited value (CSV) and/or
    [Maven tasks
    plug-in](http://maven-plugins.sourceforge.net/maven-tasks-plugin/)
    format as the task repository.

<!-- end list -->

  - [bug 170395](https://bugs.eclipse.org/bugs/show_bug.cgi?id=170395):
    create PDE wizards for automatically generating task repository
    connectors. These would be similar to the current PDE wizards for
    creating plug-in projects and may also use cheat sheets to guide
    developer through the whole process.

[Category:Mylyn](Category:Mylyn "wikilink")