If you are having enough trouble that you feel you need to uninstall
Mylar, do so carefully, using the Eclipse uninstall features.
<b>Manually removing the plug-ins and features can lead to Eclipse
configuration errors\!</b>

Note that uninstalling Mylar will not delete all of your tasks: by
default they are stored in the <workspace>/.mylar/tasklist.xml file
which will not be removed in the uninstall process. The next time Mylar
starts, it should read this file correctly.

To uninstall Mylar:

  - First, uninstall the old version of *Mylar using Help -\> Software
    Updates -\> Manage Configuration*.
  - You need to Disable all Mylar features by right-clicking them.
  - Allow Eclipse to restart after the last is disabled.
  - After restart, ensure that the 3rd toolbar button is pressed (see
    the figure below) so that you see the disabled features to
    uninstall.
  - Uninstall all the disabled features using the popup menu.

If you don't uninstall, the the Update Manager will think that you have
the latest and tell you that there are no updates.

To reinstall, update Eclipse by adding the correct update site specified
at on the [download page](http://eclipse.org/mylar/dl.php). Afterwards,
you should be able to follow the directions again at \[Mylar
Installation Guide\].

![Image:mylar-eclipse-manage-configuration.gif](mylar-eclipse-manage-configuration.gif
"Image:mylar-eclipse-manage-configuration.gif")

[Category:Mylyn](Category:Mylyn "wikilink")