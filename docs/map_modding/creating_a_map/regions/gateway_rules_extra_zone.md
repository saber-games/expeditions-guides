# Rules for a target zone of a Gateway. Extra zone

*Currently, this topic is valid for SnowRunner only.*  
*In Expeditions, custom Regions with multiple interconnected maps are currently not supported. However, they are planned to be supported in the next versions of the game.*  

To avoid issues during the transition of a player via the created gateway, the zone locator of the gateway's target zone should met the following requirements:

-   This zone locator should ***not*** have models of any kind inside it (e.g. no rocks, no lampposts, no fences, and so on). Otherwise, the truck or a trailer of the player can inappropriately collide with these models during the transition.

-   This zone locator should ***not*** contain any plants with enabled collisions (e.g. no trees, no bushes, and so on). The reason for that is the same -- the vehicle can collide with them and this may result in inappropriate behavior.

-   The size of a zone locator (i.e. **Length\...** and **Width** in Zone Locator properties) should be typically larger than the size of regular zone locators.

![](./media/image353.png)

![](./media/image354.png)

Moreover, to avoid issues with large trucks and trailers you can specify an extra zone that will be used for gateway transitions if the dimensions of the initial zone of the gateway are insufficient.

This zone should be selected in the **extraZoneToPlaceTrucks** and **extraZoneToPlaceWinch** fields of the gateway settings.

> **NOTE**: Previously, we used *two* extra zones (i.e. a separate zones for **extraZoneToPlaceTrucks** and **extraZoneToPlaceWinch**) and recommended to do the same for map mods. However, now we use the one and the same zone for **extraZoneToPlaceTrucks** and **extraZoneToPlaceWinch** to save space necessary for the gateway setup.

The recommended size of this extra zone is 40x9 at least (this should be sufficient for any truck and trailer pair in the game).

![](./media/image355.png)

**IMPORTANT**: As opposed to the zone selected in the **levelZoneLink**, this zone should be ***located on the same map as the gateway entrance***, since it will be used when the player ***returns*** to this gateway (during the backward transition).

For example, if we have **gateway_1** on **level_map_1** and **gateway_2** on **level_map_2**, and these gateways are linked to each other, then their extra zone settings will look like the following:

![](./media/image356.png)

As you can see, extra zone of the **gateway_1** is located on **level_map_1** and extra zone of **gateway_2** is located on **level_map_2**. When the player will travel from **gateway_1** to **gateway_2**, the player will be transferred to either **gateway_2** or **gw2_extra_zone_1** -- depending on the size of the player's vehicle. When the player will travel back, from **gateway_2** to **gateway_1**, they will be transferred to either **gateway_1** or **gw1_extra_zone_1**.

Extra zones will be visible only in the Editor; they will not be visible to the player in the game.

**WARNING**: The zone specified in the **extraZoneToPlaceTrucks** and **extraZoneToPlaceWinch** fields must have empty **props** sections in its settings, both on the level of region and the level of the particular map. I.e. this zone should be used by the gateway only and should ***not*** be used in any other way. Otherwise, the gateway may stop working correctly.

In gateway settings, this extra zone should be selected in the following fileds:

-   **extraZoneToPlaceTrucks** -- the zone that will be used if dimensions of the initial zone of the gateway are insufficient for the transitioned vehicles.

-   **extraZoneToPlaceWinch** -- the zone that will be used for both the main truck and trucks or trailers that are connected to it by the winch, if dimensions of the initial zone of the gateway are insufficient.
    
    **NOTE**:The current behavior of passing gateways with a truck or trailer on a winch is the following:

    1.  During gateway transition, the game detaches anything that was connected by the winch.

    2.  If there is a sufficient space in the initial gateway zone, the game will put both the main truck and the truck/trailer that was on the winch in the initial gateway zone. They will spawned there in the \"ghost mode\" and will not interfere with each other.

    3.  If the space in the initial gateway zone is insufficient, the game will put both the main truck and the truck/trailer that was on the winch in the **extraZoneToPlaceWinch** zone. They also will spawned there in the \"ghost mode\" there.

Usage of this extra zone is optional. Even if you did not use it, the game will try to deliver the player's vehicles to the gateway zone.

**NOTE**: If the size of the player's vehicles exceeds dimensions of the target zone, the system will display the corresponding warning to the player. However, the player can ignore this warning and proceed to the gateway anyway.

