# TOOLS menu

In *SnowRunner* and *Expeditions*, [Proving Grounds][open_proving_grounds] maps that are used for testing trucks have the special **TOOLS** menu, which is displayed at the top right part of the screen.

[*Local mods*][local_mods] of maps – that are loaded from local [`.pak`][paks] files – also have this menu enabled, since it can help in testing them.

For [*published mods*][published_mods] of maps – that are downloaded from mod.io, this menu is disabled by default. 

However, if necessary, you configure the map to keep the **TOOLS** menu even when this map will be published.

To do this:

1.  On the toolbar of the Editor, click the **Zone Settings** button (![](./../../getting_started/ui_overview/media/image158.png)).

2.  In the appearing dialog, at the top of it, enable the **isEnableDevMenu** option.

3.  To save your changes, press CTRL + S or select **File \> Save** in the main menu of this dialog.

**NOTE**: The **isEnableDevMenu** option affects map mods only in their published state. For a local mod of the map, the **TOOLS** menu will be displayed anyway, even when this option is set to `false`.

[open_proving_grounds]: ./../../../truck_modding/getting_started/sample_mod_by_the_game/opening_the_proving_ground.md
[paks]: ./../../packing_and_publishing_maps/packing_maps.md#generated-files
[local_mods]: ./../../packing_and_publishing_maps/testing_maps.md
[published_mods]: ./../../packing_and_publishing_maps/publishing_maps.md