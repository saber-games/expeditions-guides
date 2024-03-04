# Linking Mods

*(This topic is valid for Expeditions only.)*

**NOTE**: Currently, linked mods do not always work. This is a known issue, which will be fixed.


## Overview 
When creating mods, you are able to *link* them to each other.

For example, you can create a custom map and use a particular custom inventory item in zones and objectives of this map.
Or, create a map and unlock a particular custom FOB module after accomplishing the particular objective on this map.

However, these enitities (e.g., map and item/module) are provided as different mods, so they *both* need to be downloaded and enabled to work, 

## Types of Linking

### Unlocking Locked Entities
You can lock the following modding entities:

-   Custom **Trucks** – *(Every truck is a separate mod.)* can be locked by the following attributes in the `<GameData>` tag of the XML class of the truck:

    -   `UnlockByExploration` – if you want the player to find it on the map
    -   `UnlockByObjective` – if you want to give it as a reward for the particular objective of the map
    -   `UnlockByRank` – *(not used in Expeditions)*
    -   `LockedUnconditionally` – *(should not be used in modding)*

-   Custom **Truck upgrades and addons** – *(Part of the mod of the truck.)* can be locked by the following attributes in the `<GameData>` tag of the XML class of the truck's component (engine, gearbox, suspension, winch, wheel) or XML class of the addon:

    -   `UnlockByExploration` – if you want the player to find it on the map
    -   `AddonUnlockByObjective` – if you want to give it as a reward for the particular objective of the map
    -   `UnlockByRank` – *(not used in Expeditions)*

-   Custom **Specialists** – *(Every specialist is a separate mod.)* can be locked by the **isLocked** field in their general properties.

-   Custom **FOB Modules** – *(Every specialist is a separate mod.)* can be locked by the **isLockedByDefault** field in their general properties.

All these entities can be unlocked by the particular type of [reward] given after accomplishment of the particular map objective.

### Usage of Custom Inventory Items
Along with unlocking entities, the custom map can use:

-   Custom **Inventory Items** – *(Every item is a separate mod.)* Inventory Items cannot be locked. However, the map can link them by their identifiers in the following fields: 

    -   in the **itemName** field (in **slotsSettings** \> **possibleItems** \> `[N]` \> **itemName**), in the *ZonePropertyInventoryStorage* prop of the Inventory Storage zone.

    -   in the **Inventory Id to bring** field of the **takeInventory** stage.
    -   in the **Inventory Id to bring** field of the **objectConstruction** stage. 


## Pipeline for Linked Items 
For the map and the linked entity to work, you need:

-   *For published mods (i.e., mods from mod.io)*: both mods should be downloaded and enabled.

-   *For local mods (i.e., mods loaded from local .pak files during mod development)*: local mods (local .pak files) should exist for both mods.

    **NOTE**: Local mods of trucks/upgrades do not have .pak files, however, they should be converted to work locally.

If only one of the mods exists, then either the loading the map will result in an error, or the locked item will be locked forever.


## Important Note
However, currently, linked mods do not always work. This is a known issue, which will be fixed.

Locking of trucks and truck's components and addon's should not be used now. Currently, all truck mods and truck components are checked for locks when they are packed. If locks do exist, packing will result in an error. 

That's why we were specifically removing locks from truck's components in [Simple Truck Mod from Scratch][tutorial_step_6] tutorial.

So, currently, there is no ability to pack locked trucks or truck's components. This is done intentionally, to avoid "forever locked" trucks. However, this will be changed in the future, when linking mods will be more stable.
 


[reward]: ./../map_modding/creating_a_map/objectives/objectives_in_expeditions/rewards.md
[tutorial_step_6]: ./../truck_modding/getting_started/simple_truck_mod_from_scratch/step_6_creating_xml_files_of_truck_components.md#modify-the-unlockbyexploration-and-addonunlockbyobjective-attrubutes