# Creation of Custom Inventory Item

*This feature is valid for Expeditions only.*

!!! info

    In the current version of Expeditions, there is an issue where saving a custom inventory item may not work when the item is created *for the first time*. As the result, the `Can’t open file: ...` message is displayed. This issue occurs because the `Media\Mods` folder is not created automatically. The temporary solution for this is to create this folder manually. Or, as an alternative, create and *pack* any map. This issue is known and will be fixed in the next versions of the Editor.

## Overview
Custom inventory items are created similarly to custom FOB Modules and Specialists – in the dialog window that is opened by clicking the **EXP MODs creation** (![](./../../map_modding/creating_a_map/media/exp_mods_creation_button.png)) button on the toolbar of the Editor.

1. After selecting the option to create an inventory item from the main menu, you must enter the *identifier* of the custom inventory item in the game. It is specified in the **name** field.
2. Select the *class* of the inventory item in the **InventoryItemDesc** field and specify the properties of the inventory item. These properties vary depending on the selected class. 

!!! note

    Fuel, Repair parts, and Spare wheels are *not* inventory items from the modding perspective. See [Custom Inventory Items: Overview](./custom_inventory_items_overview.md#note-on-fuel-repair-parts-and-spare-wheels) for details.


## Classes of Inventory Items
Classes of inventory items correspond to [abilities][items_with_abilities] that they will use.

Classes that can be selected in the **InventoryItemDesc** field are listed below.

!!! note

    All original in-game items are listed in the [Appendix: Types of Inventory Items][appendix].

### InventoryItemDesc

-   *Class*: `InventoryItemDesc`
-   *Description*: This class should be selected for items *without any ability*. For example, for various [Quest Items][quest_items], [Treasure Items][treasure_items], and so on.
-   *Fields*: No ability-specific fields, only [General Properties][general_properties].
-   *Original in-game items*: Memory Card, Dinosaur bone, Flight Recorder

### InventoryItemDescAnchor

-   *Class*: `InventoryItemDescAnchor`
-   *Description*: This class should be selected for custom Anchors.
-   *Fields*: [General Properties][general_properties] + [Anchor Properties][anchor_properties].
-   *Original in-game items*: Anchor, Removable Anchor  

### InventoryItemDescJackScrew

-   *Class*: `InventoryItemDescJackScrew`
-   *Description*: This class should be selected for custom Jack-Screws.
-   *Fields*: [General Properties][general_properties] + [JackScrew Properties][jackscrew_properties].
-   *Original in-game items*: Jack-Screw  

### InventoryItemDescEcholot

-   *Class*: `InventoryItemDescEcholot`
-   *Description*: This class should be selected for custom Echo Sounders.
-   *Fields*: [General Properties][general_properties] + [Echo Sounder Properties][echo_sounder_properties].
-   *Original in-game items*: Echo Sounder  

!!! warning

    The creation of custom *Drone*, *Echo Sounder*, and *Binoculars* items is currently not supported. Please do not create the mods of these items since they currently cause errors. This issue is known and these items will be supported in the future releases of the game. 

### InventoryItemDescBinocular

-   *Class*: `InventoryItemDescBinocular`
-   *Description*: This class should be selected for custom Binoculars.
-   *Fields*: [General Properties][general_properties] + [Binocular Properties][binocular_properties].
-   *Original in-game items*: Binoculars  

!!! warning

    The creation of custom *Drone*, *Echo Sounder*, and *Binoculars* items is currently not supported. Please do not create the mods of these items since they currently cause errors. This issue is known and these items will be supported in the future releases of the game. 

### InventoryItemDescDrone

-   *Class*: `InventoryItemDescDrone`
-   *Description*: This class should be selected for custom Drones.
-   *Fields*: [General Properties][general_properties] + [Drone Properties][drone_properties].
-   *Original in-game items*: Drone 

!!! warning

    The creation of custom *Drone*, *Echo Sounder*, and *Binoculars* items is currently not supported. Please do not create the mods of these items since they currently cause errors. This issue is known and these items will be supported in the future releases of the game. 


## Pipelines

### Creation

To create a new custom inventory item:

1.  Open the [Editor](https://expeditions-guides-staging.saber.games/map_modding/getting_started/ui_overview/ui_overview/).

2.  Click **EXP MODs creation** (![](./../../map_modding/creating_a_map/media/exp_mods_creation_button.png)) on the toolbar and select **File** \> **New Mod** \> **Inventory Item**.

    ![](./media/custom_inventory_item_1.png)

3.  In the **name** field – enter the identifier of the new inventory Item: this name can contain only Latin characters, digits, and underscores (`_`); it must not contain spaces (` `). Later this name can be used in the [`takeInventory`](https://expeditions-guides.saber.games/map_modding/creating_a_map/objectives/objectives_in_expeditions/stages/takeinventory/) substage, for example. To use your custom item instead of the basic one, make sure to reference it by its name (identifier).

    ![](./media/custom_inventory_item_2.png)

4.  In the **InventoryItemDesc** field – specify the class of the new inventory item.  
    * If your inventory item **should not** use any ability, select the `InventoryItemDesc` class.  
    * If your inventory item **should** use an ability, select the corresponding class in the **InventoryItemDesc** field. See the details [above](#classes-of-inventory-items).

5.  Specify [general properties][general_properties] of the inventory item at the top of the dialog.

6.  If your inventory item uses an ability, specify its [ability-specific properties][ability_specific_properties] below them.

7.  Save your changes by selecting **File** \> **Save** from the main menu.

!!! info

    In the current version of Expeditions, there is an issue where saving a custom inventory item may not work when the item is created *for the first time*. As the result, the `Can’t open file: ...` message is displayed. This issue occurs because the `Media\Mods` folder is not created automatically. The temporary solution for this is to create this folder manually. Or, as an alternative, create and *pack* any map. This issue is known and will be fixed in the next versions of the Editor.

After the creation, you can pack this inventory item to make it available in the game and to be able to upload it to mod.io later on.

#### Source Files
After saving, saved properties of the inventory item can be found in the *folder of this custom inventory item* in `Documents\My Games\Expeditions\Media\Mods\`. 

The name of this folder is formed based on the `InventoryItemDesc_<identifier_of_inv_item>` pattern. For example:  
`\Documents\My Games\Expeditions\Media\Mods\InventoryItemDesc_my_custom_anchor\`

The properties are saved in the `InventoryItemDesc` file in this folder, in the `JSON` format.


### Opening
To open an existing custom inventory item:

1.  Open the Editor. 

2.  Click **EXP MODs creation** (![](./../../map_modding/creating_a_map/media/exp_mods_creation_button.png)) on the toolbar.

3.  In the main menu of the appearing dialog, select **File** \> **Open**.

4.  In the appearing dialog, expand the section named as the class of inventory items (`InventoryItemDesc`).

5.  Select the necessary inventory item in the list and click **OK**.


### Packing
To pack a custom inventory item:

1.  Create or open the custom inventory item.
2.  Select **File** \> **Pack** from the main menu of the dialog.
3.  The message box displays the path to the location of `.zip` files that will be generated for the inventory item. Click **OK** to generate them.

#### Generated Files
During packing, the system generates:

-   The set of `.pak` files – for local testing of the mod.
-   The set of `.zip` files – for uploading to mod.io.

The `.zip` files can be found in the [*folder of this custom inventory item*](#source-files) in `Documents\My Games\Expeditions\Media\Mods\`.

The `.pak` files are stored in the root of `Documents\My Games\Expeditions\Media\Mods\`.

### Local Testing
After packing, your custom inventory item will be available in the game. The game uses the `.pak` files generated during the packing to identify the mod (locally). However, you will need to restart the game for this identification.


### Uploading to mod.io 
Uploading to mod.io is performed similarly to uploading of the truck mods. See [Uploading Mod to mod.io][uploading].


### Subscription and Enabling  
Subscription to the mod and its activation are performed the same way as for truck mods. See [Enabling Mod in the Game][enabling].


[items_with_abilities]: ./custom_inventory_items_overview.md#items-with-abilities
[quest_items]: ./custom_inventory_items_overview.md#quest-items
[treasure_items]: ./custom_inventory_items_overview.md#treasure-items
[general_properties]: ./general_properties_of_inventory_items.md
[ability_specific_properties]: ./ability_specific_properties_of_inventory_items.md
[anchor_properties]: ./ability_specific_properties_of_inventory_items.md#anchor
[jackscrew_properties]: ./ability_specific_properties_of_inventory_items.md#jackscrew-jack-screw
[echo_sounder_properties]: ./ability_specific_properties_of_inventory_items.md#echolot-echo-sounder
[binocular_properties]: ./ability_specific_properties_of_inventory_items.md#binocular
[drone_properties]: ./ability_specific_properties_of_inventory_items.md#drone
[uploading]: ./../../truck_modding/getting_started/sample_mod_by_the_game/uploading_mod_to_mod_io.md
[enabling]: ./../../truck_modding/getting_started/sample_mod_by_the_game/enabling_mod_in_the_game.md
[appendix]: ./appendix_types_of_inventory_items.md