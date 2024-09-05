# Custom Inventory Items: Overview

*This feature is valid for Expeditions only.*

**NOTE**: In the current version of Expeditions, there is an issue that saving a custom inventory item may not work when the item is created *for the first time*. As the result of this issue, you will see the "*Can’t open file: ...*" message. This issue occurs because the `Media\Mods` folder is not created automatically. The temporary solution for this is to create this folder manually. Or, as an alternative, create and *pack* any map. This issue is known and will be fixed in the next versions of the Editor.

## What is an Inventory Item?
Inventory items are various tools, equipment and other items that can be either stored in the truck's Inventory or are available from the Radial menu. You can transfer inventory items from other zones or trucks to the Inventory.

Some of these items are directly usable – i.e., the player can press a button to "use" them from the Inventory. By doing this, the player will execute a certain predefined game logic with the parameters that can be tuned. For example, you can "use" such items as a *Drone* or an *Anchor* and, during modding, you can tune their parameters. 

Other items are not directly "used", but are used in objectives. For example, you can set up an **objectConstruction** stage to deliver a *Camera Trap* item to some zone and, upon its delivery, change the **_objective** model on the scene using **Model Building Settings** to show the deployed camera. Or, you can set up a task to simply deliver some inventory item to a certain zone, without any visual changes.

The list of possible custom inventory items includes custom Drones, Binoculars, Anchors, Quest Items, Treasure Items, and so on.

**WARNING**: The creation of custom *Drone*, *Echo Sounder*, and *Binoculars* items is currently not supported. Please do not create the mods of these items since currently they lead to errors. This issue is known and these items will be supported for sure in the future releases of the game.

## Limit on Number of Enabled "canTakeInHq" Mods
In the current version of the game, there are 16 slots for inventory items and 16 slots for sideboard items available in Headquarters. Players can take various items from these slots when preparing for the Expedition.

Some of these slots are used for the in-game (pre-built) items, and some slots can be used for the custom items, created in the Editor. Thus, there are limits on the number of *simultaneously* enabled mods of items that are available in Headquarters (i.e., on mods that have the [**canTakeInHq**][properties] option enabled).

The limits on *simultaneously* enabled mods with **canTakeInHq** = `true` are the following:

-   *For inventory items*: `4` *simultaneously* enabled mods.
-   *For [sideboard](#heavy-inventory-items) items*: `4` enabled mods.

These limits are for the *total* number of such mods, i.e. – for both:

-   *local mods* that are available from [local `.pak` files][local_pak_files];
-   *published mods* that have been downloaded from mod.io and enabled after that.

For example, if you have `2` enabled mods of items that are available in Headquarters from mod.io and `2` local mods of the similar items, creating one more local mod with **canTakeInHq** = `true` or enabling one more such mod from mod.io will break this limit. If the limit is broken and the total amount of simultaneously enabled mods of this type exceeds it, some of these mods will not be displayed in lists of inventory items in HQ.

To fit in this limit, you can either disable some of such mods in Mod Browser, or, if you are intensively working with local mods of such items, delete their generated `.pak` files after local testing.

## Categories of Inventory Items

**NOTE**: Some categories below are *not* necessarily mutually exclusive.

### Items with Abilities
Inventory items can provide the player a certain *ability*, when they are used.
For example, `DRONE` ability type allows the player to use the drone and provides corresponding UI and game logic for that, `JACKSCREW` ability type does the same for the jack screw, etc.

There always must be a particular set of internal game components that support the ability in the gameplay. That's why the list of abilities is fixed. Your custom inventory items can only be based on one of the abilites that already exist in the game. However, you can modify their parameters as you like.

**NOTE**: Items with Abilities need to be created as instances of the corresponding *child-class* of `InventoryItemDesc`. For example, if you are creating a custom *Anchor*, you select `InventoryItemDescAnchor` as the value of **InventoryItemDesc** field when creating it. See [Creation of Custom Inventory Item](./creation_of_custom_inventory_item.md) for details.

**WARNING**: The creation of custom *Drone*, *Echo Sounder*, and *Binoculars* items is currently not supported. Please do not create the mods of these items since currently they lead to errors. This issue is known and these items will be supported for sure in the future releases of the game. 

### Quest Items
Some inventory items do not provide any ability to the player and are only used in certain objectives, as quest items.

For example, you can set up such item as "Treasure Island Map" with an icon and description, but without any other visuals. Then, set up some zone to contain this item. Then, set up a quest to find this zone and deliver this map to some other zone. And, upon the accomplishment of this quest, using the **Blocker Objectives** lists in subsequent objectives, unlock for a player a set of further assignments related to this map.

**NOTE**: Actually, the *Camera Trap* item mentioned [above](#what-is-an-inventory-item) also acts as a quest item. Its has no actual properties except name, description, and icon – the visuals of actual deploying the *Camera Trap* are provided by the **_objective** model mentioned in **Model Building Settings**. The only difference of *Camera Trap* from regular quest items is in the fact that regular quest items are *typically* unique and used within one level only, but the *Camera Trap* can be "used" multiple times and on many levels, if they contain appropriately set up objectives. The same is true for some other items, even the "heavy" ones, e.g., for *Radio station*, or for *Hydro-Monitoring System*.

### Treasure Items
*Treasure Items* are inventory items that are considered "valuable" and can be sold at the end of the Expedition. Their price at this moment is affected by the passive abilities of some Specialists.

These items have **isTreasure** option enabled in their properties. 

**NOTE**: Treasure Items can *not* be available in HQ. Enabling both **isTreasure** and **canTakeInHq** options in the properties of an Inventory Item will lead to an error (crash). 

### Craftable and Recyclable Items
Some of the inventory items can be crafted from *Repair parts* and/or recycled to *Repair parts* in the **Workshop** FOB module.

Particularly, in [general properties](./general_properties_of_inventory_items.md) of an item, the **recycleRepairsCost** (Recycle Price), **craftRepairsCost** (Craft Price), **craftUseCount** (the number of "charges" of in crafted item) parameters are responsible for these mechanics. The special `-1` value in **recycleRepairsCost** or **craftRepairsCost** fields disables recycling or crafting correspondingly.

**NOTE**: Parameters of crafting and recycling work independently. I.e., you can create items that can be crafted, but can not be recycled, and vice versa. 

### Heavy Inventory Items
*Heavy Inventory Items* are items that are considered "heavy" and can be added to the sideboard of the truck only.

These items have **isHeavyItem** option enabled in their properties. 

In the current version of the game, all explicitly usable items (with enabled **isUsable** option) can be used from Inventory or Radial menu *only*. They cannot be used if they are "heavy" and are stored in the sideboard of the truck. I.e., currently, the **isUsable** and **isHeavyItem** options should be treated as mutually exclusive. However, this may be changed in the future versions of the game. And, this rule does *not* apply to heavy items that are not *directly* used, but are used in objectives – like *Radio station* or *Hydro-Monitoring System*, etc. 

For details on setting up the truck's Cargo Slots for Heavy Inventory Items, see [Cargo Slots](./../../truck_modding/new_features/cargo_slots.md).

### Note on Fuel, Repair Parts, and Spare Wheels
But what about *Fuel*, *Repair parts*, and *Spare wheels*? Are they Inventory Items?

No, they are not. You can add some fixed amounts of Fuel, Repair parts, and Spare wheels to [Cargo Slots](./../../truck_modding/new_features/cargo_slots.md), it is true. But these items are predefined and you cannot create a *custom* inventory item (heavy or not) with the "Fuel", "Repair parts", or "Spare wheel" ability.

Please note that this does *not* mean that you can not create custom "Fuel", "Repair parts", or "Spare wheel" entities. For sure, you can. You should just create them as [*Consumables*](./../../truck_modding/new_features/consumables.md). I.e., they should be created as special addons to the truck that have some visual mesh in a FBX and all XML files of the addon, require some another addon for installation, and are installed to a certain Socket on the truck. See [Addon Changes](./../../truck_modding/new_features/addon_changes.md) and [Consumables](./../../truck_modding/new_features/consumables.md) for details.

## Availability 
Custom inventory items can be obtained by the player:

-   In **HEADQUARTERS**, when the player is preparing for the Expedition.

    **NOTE**: The **canTakeInHq** option in the [properties][properties] of the inventory item specifies whether or not it can be obtained in **HEADQUARTERS**.

-   On the particular level, from the **ZonePropertyInventoryStorage** zones.

-   *For craftable items:* On the particular level, in the **Workshop** FOB module, after [crafting](#craftable-and-recyclable-items) them.

## Usage
Inventory items can be used:

-    as usable items from Inventory or Radial menu – This usage will be enabled only if the **isUsable** option is turned on for these items. For example, the player can "use" an item to execute its ability (e.g., Drone).
-    as items that need to be delivered to some zone – I.e., specified as **inventory** within the **objectConstruction** stage.
-    as items required for the particular ability that, in its turn, is required for the particular minigame – I.e., during the setup of the **ZonePropertyMinigame** zone.

## Type
Every inventory item has a type, specified as **type** in its properties.
For example, *Anchor* and *Removable Anchor* are different inventory items, with different identifiers, but have the same **type**. 

The **type** of the inventory item works as its category (or tag). And, inventory items are frequently referenced in other settings by their **type** instead of their identifier. For example, you can specify only the necessary **type** of the inventory item to be dropped in **ZonePropertyInventoryStorage** zones and omit the particular identifier of the item (**itemName**) there, if necessary. 

The set of possible values of **type** is predefined. I.e., you can select there only one of the item types that are already available in the game. However, the creation of new types is not necessary, since the behaivior of the inventory item is mainly affected by other fields. The large number of types visible within the **type** drop-down should not daunt you, since most of theses types correspond to various quest items used by the objectives of the original game. 

**NOTE**: Inventory item's **type** does not directly affect the behavior of this ivenentory item. However, the objective and zone settings frequently refer to it instead of the identifier of the item and this should be taken into account. For example, if you are setting up a delivery of the inventory item in the **objectConstruction** stage, you should be aware that *any* item with the specified **type** may be delivered to accomplish this stage.

## Pipeline for Creating Inventory Items
See [Creation of a Custom Inventory Item](./creation_of_custom_inventory_item.md).


[properties]: ./general_properties_of_inventory_items.md
[local_pak_files]: ./creation_of_custom_inventory_item.md#generated-files



