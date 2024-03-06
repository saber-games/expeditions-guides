# Goods Delivery 

*This topic is valid for SnowRunner only.*  

The group of fields in the **actions** section corresponds to the "delivery of goods" assignment.

For each zone that you need to deliver the goods to, add a separate entry to the **zoneToFill** list.

The ID of this zone is specified in the **globalZoneId** field. If you want to specify some additional zones where the player may deliver the goods, specify their IDs in the **additionalUnloadZones** list.

The cargo that needs to be delivered is specified in the **cargo** list (ID of cargo + its amount).

For example, the assignment of delivering two cargo units of barrels to one of two zones (**delivery_zone**, **delivery_zone_2**) will look like the following:

![](./media/image305.png)

**NOTE**: To create a zone for *loading* cargo, you can use the zone of the **\...CargoLoading** type (see [[5.15.1.1]](#loading-cargo-...cargoloading-and-...manualloading-zones) above). To create a zone where the physical objects of goods will be spawned for manual loading, you can use the **spawnCargoOnStageActive** stage (see [[5.16.1.7]](#spawning-cargo-on-a-map-spawncargoonstageactive-section) below).

If necessary - you can specify the ID of the truck that is required to perform this delivery in the **Truck need to visit Uid** field.\
For a description of Model Building Settings - see [[5.16.3]](#model-building-settings) below.

Moreover, using the **Manual Unloading Settings** and an additional zone, you can set up manual unloading of necessary cargo -- see [[5.16.1.1.2]](#manual-unloading-of-cargo) below.

