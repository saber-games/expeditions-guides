# Workshop zones

*(NEW) This feature is valid for Expeditions only.*

The *ZonePropertyWorkshop* prop is used for setting up the *Workshop* (WORKSHOP) [FOB module zone](./zones_of_fob_modules_overview.md).

Lists of inventory items that can be crafted and/or recycled within the *Workshop* are determined automatically, based on properties of inventory items. 

Particularly, if **craftRepairsCost** in the properties of an inventory item is specified and not equal to `-1`, the player will be able to craft it in the *Workshop*.

If **recycleRepairsCost** in the properties of an inventory item is specified and not equal to `-1`, the player will be able to recycle it in the *Workshop*.

**NOTE**: You can create your own custom Inventory Items and make them craftable, see [Custom Inventory Items: Overview](./../../../../../custom_gameplay_entities/inventory_items/custom_inventory_items_overview.md).


Settings:

-   **moduleId** – links this zone to the custom FOB module. In this field, you need to specify the [*identifier*][fob_module_identifier] of this custom FOB module. I.e., in the **moduleId** field you need to specify exactely the same value as you have specified in the **name** field in the general properties of this custom FOB module.

-   **repairsCapacity** – the upper limit for the amount *Repair parts* that are the source material for crafting operations performed in the Workshop. The value of `-1` corresponds to no upper limit.

-   **repairslnitialAmount** – the initial amount of *Repair parts* in the Workshop.

-   **zoneDiscoverability** – *(Optional)* settings related to the zone discovery. See [Discoverability of Zones](./../discoverability_of_zones.md). Typically not specified, since it is a FOB module.


[fob_module_identifier]: ./../../../../../custom_gameplay_entities/fob_modules/general_properties_of_fob_modules.md