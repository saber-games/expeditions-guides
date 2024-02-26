# GarageEntrance and GarageExit zones

*This topic is valid for SnowRunner only.*  

Typically, to add a Garage to the map, you need to add two zones:

-   **Garage entrance** – the zone with the **ZonePropertyGarageEntrance** property in the **props** section.

-   **Garage exit** – the zone with the **ZonePropertyGarageExit** property in the **props** section.

However, you can add only the Garage entrance zone – in this case, it will be automatically used as the Garage exit.

**WARNING**: The size of the zone locator for the Garage exit zone should be sufficient for spawning large trucks without issues. Otherwise, if the size of the zone is small and there is an adjacent building of the Garage, a spawned truck may collide with the wall of the building or the player may experience issues with the camera. If the amount of free space for the zone is low, try to locate the exit zone along the Garage building.

The Garage entrance zone, along with the **...GarageEntrance** property itself, has also the **Upgradeable Garage State** section. If you want a regular Garage that will be fully functional from the start, leave "**null***"* as the value of this section. If you want to set up the Garage where some parts of functionality are disabled at the start, but will become active upon accomplishment of some objectives by the player, you will need to fill in the **Upgradeable Garage State** section and *enable a specific option in **Terrain** properties*, see [Upgradeable Garage](upgradeable_garage.md) for detals.

![](./media/image190.png)

The Garage exit zone has no additional properties, except the **...GarageExit** property itself.

![](./media/image191.png)

A map can contain *only one* **ZonePropertyGarageEntrance** zone and *only one* **ZonePropertyGarageExit** zone.

