# Spawning Cargo 

*This topic is valid for SnowRunner only.*  

The **spawnCargoOnStageActive** section does *not* correspond to an assignment.

It allows you to create a zone where the system will be spawning cargo as a physical object. After manual loading with the crane, the spawned cargo can be used for the "delivery of the goods" assignment.

The ID of the target zone here is specified in the **zone \> globalZoneId** field. The spawned cargo items must be added to the **cargos** list (similarly to the "delivery of goods" assignment).

**NOTE**: Cargo spawned by the **spawnCargoOnStageActive** feature can be loaded to the truck only manually, by the crane. For automatic loading of the cargo, use the **\...CargoLoading** zone (see [[5.15.1.1]](#loading-cargo-...cargoloading-and-...manualloading-zones) above).

**WARNING**: The **spawnCargoOnStageActive** section must be added to the Stage where other assignments (delivery, visit all zones, living area, etc.) do exist. If there is only the **spawnCargoOnStageActive** section within the Stage and there are no other assignments within the same Stage, this Stage will be skipped and no cargo will be spawned.

There are additional limitations for spawning cargo using **spawnCargoOnStageActive** in the case of Regional Contracts, see **WARNING** in the [[5.17.4]](#locking-objectives-based-on-exploration) below.

Along with other properties, the **spawnCargoOnStageActive** section also includes the **Should be discovered by metallodetector** option, which is necessary when creating objectives for Metal Detector, see below.

