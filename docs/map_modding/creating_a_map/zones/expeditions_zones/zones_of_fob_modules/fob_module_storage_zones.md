# FOB Module Storage zones

*(NEW) This feature is valid for Expeditions only.*

The *ZonePropertyFobModuleStorage* prop is used for setting up such [FOB module zones](./zones_of_fob_modules_overview.md) as:

-   *Base module* (BASE_MODULE)
-   *Gas station* (GAS_STATION)
-   *Repair station* (REPAIR_ZONE)
-   *Warehouse* (EXTRA_STORAGE)
-   *Essentials storage* (DOUBLE_STOCK)

This prop is a wrapper over the [*ZonePropertyInventoryStorage*](./../inventory_storage_zones.md) prop that allows you to configure a storage for fuel, repair parts, spare wheels and various inventory items. 

**NOTE**: All types of FOB Modules listed above use and focus on the certain parameters of [*ZonePropertyInventoryStorage*](./../inventory_storage_zones.md). For example, *Gas station* uses **fuelSlotSettings** of this prop, *Repair station* uses **repairsSlotSettings** and **wheelsSlotSettings**, and so on. 

Along with regular fields of [*ZonePropertyInventoryStorage*](./../inventory_storage_zones.md), this prop also has the **moduleId** field that links this zone to a particular FOB module. In this field, you need to specify the [*identifier*][fob_module_identifier] of this *custom FOB module* to link this zone to this module. I.e., in the **moduleId** field you need to specify exactely the same value as you have specified in the **name** field in the general properties of this custom FOB module.

Depending on the particular FOB module this zone is used for, the name and icon of this zone will be changed.

The **alwaysSpawn** option of this prop is typically enabled for all FOB Modules listed above.

The **isAtDeployZone** option of this prop should be enabled for all types of FOB modules listed above.


[fob_module_identifier]: ./../../../../../custom_gameplay_entities/fob_modules/general_properties_of_fob_modules.md
