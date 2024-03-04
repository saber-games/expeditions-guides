# Base Building zones

*(NEW) This feature is valid for Expeditions only.*

## Main Function: Interaction Zone for FOB Module
For every potential FOB module, you need to create two zones:

-   *Placement Zone* – the zone where the *visual model* of this FOB module will be built when the player decides to build it.

-   *Interaction Zone* – the zone where the player will be able to *interact* with this FOB module.

The *ZonePropertyBaseBuilding* prop of the zone marks this zone as an *Interaction Zone* of the FOB module. And, in the **modelPlacementZone** field of this prop, links the *Interaction Zone* to the *Placement Zone*. 

I.e., *Interaction Zones* of FOB modules must have the *ZonePropertyBaseBuilding* prop and the **modelPlacementZone** field of this prop must link to the *Placement Zone* of the same module.

The corresponding *Placement Zone* can have empty **props**.

**NOTE**: Along with that, every potential FOB module must be mentioned in the properties of the corresponding [Deploy zone](./deploy_zones.md) this module relates to. Particularly, for every such module, you need to create a new record in the **fobModulesZones** list of the [Deploy zone](./deploy_zones.md), and, in the properties of this record, specify links to the *Placement Zone* and *Interaction Zone* of this FOB module. See [*FOB Modules*](./deploy_zones.md#fob-modules) in [Deploy zones](./deploy_zones.md) for details.


## ZonePropertyBaseBuilding Prop Settings
Settings of the *ZonePropertyBaseBuilding* prop are the following:

-   **zoneDiscoverability** – settings related to the zone discovery. See [Discoverability of Zones](./discoverability_of_zones.md).

-   **modelPlacementZone** – link to the *Placement Zone* of this FOB module. See [*FOB Modules*](./deploy_zones.md#fob-modules) in [Deploy zones](./deploy_zones.md) for details.