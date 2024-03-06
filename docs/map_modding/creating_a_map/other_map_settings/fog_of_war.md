# Fog of War 

When you are creating a custom map, the Fog of War – displayed as the *black* color on the map – is switched off by default. 

I.e, the map's terrain and its objects are displayed in black-and-white color, *greyed*, but visible. 

However, you can enable the black Fog of War for them, if you want to.

To enable the Fog of War for your map:

1.  On the toolbar of the Editor, click the **Zone Settings** button (![](./../../getting_started/ui_overview/media/image158.png)).

2.  In the appearing dialog:
    
    1.  Expand the `<name_of_your_level>` section. 
    2.  Enable the **isNeedToBeCloacked** option, displayed above the **TERRAIN LOCATORS LIST**.

3.  To save your changes, press CTRL + S or select **File \> Save** in the main menu of this dialog.

The information on the status of the fog of war is stored along with the zone properties, in the corresponding `.json` file – see [Zones: Overview][zones_overview_source_files] for details.

[zones_overview_source_files]: ./../zones/zones_overview.md#source-files-location

