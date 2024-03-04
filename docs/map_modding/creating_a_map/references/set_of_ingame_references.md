# Set of In-Game References

With the Editor, we provide the set of references that were used for the creation of original game levels. You can use these references for your custom maps.

By default, all these references are packed. To unpack them, select **File \> Unpack references** from the main menu.

After doing this, the system will ask you to confirm unpacking by displaying the Yes/No dialog with the following message:  
*Are you sure you want to unpack references, current changes will be erased?* 

If you have already unpacked these references before and *have changed some of them*, your changes to them will be lost if you confirm unpacking. If you have not unpacked them before, have not changed them, or have your changes backed up somewhere outside the default in-game references folders, asnwer "Yes".

After confirming unpacking and a small delay, you will see a collection of new folders in your `prebuild` folder. 

For example:

-   For *Expeditions*: `usa`, `rus`.

-   For *SnowRunner*: `usa_6`, `usa4`, `usa4`, `usa`, `us`, `rus`, `rus3`, `rus4`, and so on.

If you open these folders in Windows Explorer, you will see that they contain the regular source files of the references (the XML file + folder for each reference).

References from this set are added to the map absolutely the same way as the regular references.

Before adding a reference from this set to the map, you may want to compile it:

1.  Open its source file in the Editor (this can be done from the **File View** panel).

2.  Perform the **Rebuild Terrain** operation.

**TIP**: if necessary, you can skip the compilation of the reference, and simply add it to the map without opening its source map and rebuilding. However, in this case, the preview texture of the reference will be white. But, the reference in the final packed map will look the same.

