# Testing Maps

## Overview
Directly after [packing][packing], you can test your map in the game, using local [`.pak` files][pak_files] generated as a result.

## In Expeditions

For *Expeditions*, do the following:

1.  Restart the game. After the restart, the game will find the [`.pak` files][pak_files].

2.  In the main menu of the game, select **NEW GAME**.  
    
3.  You will see a list of saved games. Double-click a necessary slot there (where you want to start a new game on your map) or select it by clicking and press ENTER.

    **WARNING**: If you have selected one of the previously saved games, it will be overwritten and you will see the corresponding warning.

4.  Skip the launch of the *Tutorial*, by pressing ESC in the corresponding pop-up.

5.  You will see a list of saved games. Click a necessary slot there (where you want to start a new game on your map). If necessary, overwrite one of your previously saved games.
Select it and press ENTER.

6.  You will see a list of Regions. Select the **Mods Region**.

7.  After opening the **Mods Region**, you will see a screen with all custom [Expeditions][expeditions_and_contracts] available to you, grouped by their maps.

8.  After selecting the [Expedition][expeditions_and_contracts], you will be taken to the standard flow of preparing for it: selecting Trucks, Inventory, Specialists, and so on. And, after the standard Deploy procedure, you will be spawned to your map.

### Minimum Requirements
In *Expeditions*, to be able to load a standalone map correctly, you need:

-   At least one [Expedition][expeditions_and_contracts] created for this map.
-   At least one [Deploy zone][deploy_zones] on this map.


## In SnowRunner
For *SnowRunner*, do the following:

1.  Restart the game. After the restart, the game will find the [`.pak` files][pak_files].

2.  In the main menu of the game, open **NEW GAME \> CUSTOM SCENARIOS**.  
    On this screen, you will see the name of your map.

3.  Select it and press **ENTER**.

4.  You will see a list of saved games. Click a necessary slot there (where you want to start a new game on your map). If necessary, overwrite one of your previously saved games.

5.  After a loading screen, you will be spawned to your map.

### Minimum Requirements
In *SnowRunner*, to be able to load your map correctly: 

-   You need at least one truck added to your map.
-   This truck must be *Active*. I.e., in the properties of the truck in the Editor, the **Active** parameter must be set to **True**.



[packing]: ./packing_maps.md
[pak_files]: ./packing_maps.md#generated-files
[expeditions_and_contracts]: ./../creating_a_map/objectives/objectives_in_expeditions/expeditions_and_contracts.md
[deploy_zones]: ./../creating_a_map/zones/expeditions_zones/deploy_zones.md