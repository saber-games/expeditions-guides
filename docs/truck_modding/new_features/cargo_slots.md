# Cargo Slots

*(NEW) This feature is valid for Expeditions only.*

*Cargo Slots* are slots located in the sideboard of the truck and intended for the transportation the [Heavy Inventory Items](./../../custom_gameplay_entities/inventory_items/custom_inventory_items_overview.md) and [predefined amounts of Fuel, Repair parts, and Spare wheels](#note-of-fuel-repair-parts-and-spare-wheels).

**NOTE**: Cargo Slots should not be mixed up with [Inventory Slots](./inventory_slots.md) and with [Slots for Consumables](./consumables.md). 

To enable these Cargo Slots for your Sideboard addon, you need to perform 3 steps, see below.

## Step 1. Visual Meshes of "Packed" Inventory in the FBX  
You neeed to model meshes displaying *abstract* "packed" inventory loaded to these slots within the FBX of the addon. These visual meshes need to be abstract since you do not know what particular inventory the player will load into these slots.

Moreover, these meshes must correspond *not* to a single slot loaded by "packed" inventory, but to gradually filled side board. I.e., the 0 mesh will correspond to an empty sideboard, the 1st mesh will correspond to the 1st slot filled with the abstract inventory, the 2nd one – to the *1st and 2nd slots* filled with inventory, the 3rd one – to the *1st, 2nd, and 3rd slots* filled with it, etc.

## Step 2. Links to these meshes in the XML of the addon
In the XML of the addon, within the `<TruckAddon>` tag, you need to link to these visual meshes and specify at what state of filled slots they should be filled.

This is done using [`<HeavyInventorySlotsMeshes>`](./../tags_and_attributes_of_trucks/truckaddon/heavyinventoryslotsmeshes/index.md) and [`<Mesh>`](./../tags_and_attributes_of_trucks/truckaddon/heavyinventoryslotsmeshes/mesh/index.md) tags: 

```xml
  <HeavyInventorySlotsMeshes>
    <Mesh Frame="cover_state_00" HideThreshold="0" />
    <Mesh Frame="cover_state_01" HideThreshold="1" />
    <Mesh Frame="cover_state_02" HideThreshold="2" />
    <Mesh Frame="cover_state_03" HideThreshold="3" />
    <Mesh Frame="cover_state_04" HideThreshold="4" />
  </HeavyInventorySlotsMeshes>
```

## Step 3. Enabling these slots in the XML of the addon  
In the XML of the addon, within the `<GameData>` tag, you need to specify the total quantity of these slots in the [`<SideboardSlots>`](./../tags_and_attributes_of_trucks/truckaddon/gamedata/sideboardslots/index.md) tag:

```xml
<SideboardSlots Quantity="4" />
```
That's all for setting them up.

## Note of Fuel, Repair parts, and Spare wheels
Fuel, Repair parts, and Spare wheels added to Cargo Slots are different from the Fuel, Repair parts, and Spare wheels as [Consumables](./consumables.md) from the modding perspective (only). 

Fuel, Repair parts, and Spare wheels items that are added to Cargo Slots are predefined and cannot be modified. 

However, you can create their custom entities as [Consumables](./consumables.md). I.e., you can add them as special addons to the truck that have some visual mesh in a FBX and all XML files of the addon, require some another addon for installation, and are installed to a certain Socket on the truck. See [Addon Changes](./addon_changes.md) and [Consumables](./consumables.md) for details.


