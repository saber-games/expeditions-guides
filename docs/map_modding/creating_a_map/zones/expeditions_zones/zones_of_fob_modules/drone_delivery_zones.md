# Drone Delivery zones

*(NEW) This feature is valid for Expeditions only.*

The *ZonePropertyDroneDelivery* prop is used for setting up the *Cargo drone* (DRONE_BASE) [FOB module zone](./zones_of_fob_modules_overview.md).

**NOTE**: Use this prop only to [configure custom FOB Modules][creation_of_custom_fob_module]. Do not assign this props to common standalone zones. If you do it, this might cause a crash.

This prop is a wrapper over the [*ZonePropertyInventoryStorage*](./../inventory_storage_zones.md) prop that allows you to configure a storage for fuel, repair parts, spare wheels and various inventory items.

However, the *ZonePropertyDroneDelivery* zone typically uses only the following settings from its parent:

-   **fuelSlotSettings** – for the *ZonePropertyDroneDelivery*, they specify the amount of Fuel that will be available in the *Cargo drone* FOB module initially, straight after building it. The setup parameters are the same as in [*ZonePropertyInventoryStorage*](./../inventory_storage_zones.md).

-   **expandedConsumablesCapacity** – for the *ZonePropertyDroneDelivery*, they specify the upper limit of Fuel in the *Cargo drone* FOB module. The calculations here are also the same as in [*ZonePropertyInventoryStorage*](./../inventory_storage_zones.md).  

**NOTE**: However, if necessary, you can use all other *ZonePropertyInventoryStorage* fields, e.g. the ones for inventory, they will work as usual.

Along with regular *ZonePropertyInventoryStorage* fields, there are two additional fields in this zone:

-   **fuelLevel** – *not used.* You should use **fuelSlotSettings** instead.

-   **deliveryCost** – the cost of one *Cargo drone* delivery, in Fuel units.   

[creation_of_custom_fob_module]: ./../../../../../custom_gameplay_entities/fob_modules/creation_of_custom_fob_module.md