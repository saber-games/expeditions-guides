# Parking zones

*This feature is valid for Expeditions only.*

The *ZonePropertyParking* prop is used for setting up the *Expanded parking* (PARKING) [FOB module zone](./zones_of_fob_modules_overview.md).

**NOTE**: Use this prop only to [configure custom FOB Modules][creation_of_custom_fob_module]. Do not assign this prop to common standalone zones. If you do it, this might cause a crash.

This prop is a wrapper over the [*ZonePropertyInventoryStorage*](./../inventory_storage_zones.md) prop that allows you to configure a storage for fuel, repair parts, spare wheels and various inventory items. More precisely, it is a wrapper over its child – the [*ZonePropertyFobModuleStorage*](./fob_module_storage_zones.md) prop.

Settings of this prop are the following:

-   regular fields of [*ZonePropertyInventoryStorage*](./../inventory_storage_zones.md).

-   **moduleId** field from [*ZonePropertyFobModuleStorage*](./fob_module_storage_zones.md). 

    **NOTE**: In the **moduleId** field, you need to specify the [*identifier*][fob_module_identifier] of the *custom FOB module* to link this zone to this FOB module. I.e., in the **moduleId** field you need to specify exactely the same value as you have specified in the **name** field in the general properties of this custom FOB module.

-   and two additional fields:

    -   **additionalRepairAndRefuelAmount** – the additional amount of repairing and refueling that will be applied after recovery of the truck.

    -   **recoveryDiscount** – the discount on the price of recovery of the truck. Possible values: from `0` to `1`. For example, `0.2` corrsponds to `20%` discount.

[fob_module_identifier]: ./../../../../../custom_gameplay_entities/fob_modules/general_properties_of_fob_modules.md
[creation_of_custom_fob_module]: ./../../../../../custom_gameplay_entities/fob_modules/creation_of_custom_fob_module.md