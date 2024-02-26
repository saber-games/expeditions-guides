# Tow Truck zones

*(NEW) This feature is valid for Expeditions only.*

The *ZonePropertyTowTruck* prop is used for setting up the *Tow truck* (TOW_TRUCK) [FOB module zone](./zones_of_fob_modules_overview.md). 

Settings:

-   **priority** – *(currently not used, will be removed)* In Expedtions, the player manually selects the zone that they want to recover to, so this field is not used.

-   **fullyRepairTruck** – whether or not the truck should be fully repaired during recovery.

-   **refuelTruck** – whether or not the truck should be fully refueled during recovery.

-   **restoreAddonRepairAndFuel** – whether or not the *Repair parts* and *Fuel* should be fully restored in addons of the truck after recovery. This includes aready spent *Repair parts* and *Fuel* consumables that were attached to truck as addons (but *not* as sideboard items) at the beginning of the Expedition.

-   **repairAmount** – the additional amount of repairing that will be applied after recovery of the truck.

-   **refuelAmount** – the additional amount of refueling that will be applied after recovery of the truck. 

    **NOTE**: If a player has both *Tow truck* and *Expanded parking* FOB modules, the final additional repairing/refueling amounts will be the sum of their values. 

-   **moduleId** – links this zone to the custom FOB module. In this field, you need to specify the [*identifier*][fob_module_identifier] of this custom FOB module. I.e., in the **moduleId** field you need to specify exactely the same value as you have specified in the **name** field in the general properties of this custom FOB module.

-   **recoveryDiscount** – the discount on the price of recovery of the truck. Possible values: from `0` to `1`. For example, `0.2` corrsponds to `20%` discount.

-   **zoneDiscoverability** – *(Optional)* settings related to the zone discovery. See [Discoverability of Zones](./../discoverability_of_zones.md). Typically not specified, since it is a FOB module.


[fob_module_identifier]: ./../../../../../custom_gameplay_entities/fob_modules/general_properties_of_fob_modules.md
