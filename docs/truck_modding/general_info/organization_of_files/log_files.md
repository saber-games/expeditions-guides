# Log Files

We recommend you to review the logs of your mod when testing it, even if everything visually looks good.

In some cases, when you are creating a mod, it can have errors that are almost invisible visually, but can be easily tracked in the log.

For example, during the creation of a mod, you can add some custom component to the truck (for example, an improved winch) and accidentally specify different names for it in different XML files. The game will handle this by substituting the target custom component with its default version, so there will not be any obvious errors. But, nevertheless, in the game, such mods can cause errors, and, obviously, they will not work as intended. However, if you check the log while testing this mod, errors of this type can be easily found and fixed.

The game has a specific folder that stores various log information: errors, warnings, and so on. 

This folder is located within the folder of the game in the `Documents` folder:

-   For *Expeditions*:  
    at `Documents\My Games\Expeditions\base\logs\`

-   For *SnowRunner*:  
    at `Documents\My Games\SnowRunner\base\logs\`


This folder contains multiple log files that can be written by different components of the game (the game itself, the editor, etc.) and in different situations (errors while loading a custom map, errors while packing a mod, etc.), and you can use all of them, if necessary. 

However, errors and warnings occurring during the validation or packing a truck mod can be seen in `LegacyLog.txt` in this folder.

