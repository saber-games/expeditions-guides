# Recovery zones

*(NEW) This feature is valid for Expeditions only.*

## Main Function: Recovery of the Truck
The *ZonePropertyRecovery* prop is used for the creation of target zones for the Recovery of the truck.

**NOTE**: However, in Expeditions, *ZonePropertyRecovery* props are used for [Deploy zones](./deploy_zones.md) *only*. They should not be used for other zones.

If you want to enable Recovery for a Deploy zone, you need to add the *ZonePropertyRecovery* prop to the list of props of this Deploy zone. See [Deploy zones](./deploy_zones.md) for details.


## ZonePropertyRecovery Prop Settings
Settings of the *ZonePropertyRecovery* prop are the following:

-   **priority** – *(currently not used, will be removed)* In Expedtions, the player manually selects the zone that they want to recover to, so this field is not used.

-   **fullyRepairTruck** – whether or not the truck should be fully repaired after recovering to this zone. 

-   **refuelTruck** – whether or not the truck should be fully refueled after recovering to this zone.  

-   **restoreAddonRepairAndFuel** – whether or not the *Repair parts* and *Fuel* should be fully restored in addons of the truck after recovery. This includes aready spent *Repair parts* and *Fuel* consumables that were attached to truck as addons (but *not* as sideboard items) at the beginning of the Expedition.

-   **repairAmount** – the amount of repairing, in percents, that will be applied to all parts of the truck after recovery.

-   **refuelAmount** – the amount of refueling, in percents, that will be applied to the truck after recovery.

-   **zoneDiscoverability** – settings related to the zone discovery. See [Discoverability of Zones](./discoverability_of_zones.md). 
