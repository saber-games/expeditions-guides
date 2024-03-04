# DROP Water Stations

*This topic is valid for SnowRunner only.*  

## Overview
`DROP` Water Station zones allow the player to "drop" water, i.e. to *fill the water reservoir of the zone from their truck tank.*

**NOTE**: For these zones, water cannot go in the reverse direction, i.e. the player *cannot* fill the truck tank from the zone reservoir.

## Setting Up
Setting up this zone is a simple process:

1.  In the **stationUIName** field of **ZonePropertyWaterStation**, you set up the name of the zone (e.g. `Water Storage Tank`) or leave the default one.

2.  In **stationType** – select `DROP`.

3.  In **Water** – specify the amount of water, in liters, that is initially available in the reservoir of this zone. The player will be able to add water to this amount, but will not be able to take water from it. To specify an infinite initial amount (e.g. in case of the river), you can specify the `-1` value, but this case is non-typical for the `DROP` zones. The amount of water for `DROP` zones that are used in objectives should be set to `0` (it is reset on the activation of the objective, see [Water Delivery Objectives](./water_delivery_objectives.md)).

4.  In **Capacity** – specify the maximum capacity of the water reservoir of this zone. The player will be able to add water to the zone reservoir until it will be totally full. Specified **Capacity** must be greater than current amount (**Water**). The `-1` value will set the capacity of this water reservoir to infinity, but this case is non-typical for the `DROP` zones.

5.  For the **Is water delivery objective zone** option:

    -   If this `DROP` zone is used as a target zone in a water delivery objective – *enable* the **Is water delivery objective zone** option. This will hide this zone before the activation of the objective and when the currect Stage of the objective is not using it as the target zone. For details, see [Water Delivery Objectives](./water_delivery_objectives.md).

    -   If this `DROP` zone is not used in any objective – leave the **Is water delivery objective zone** option disabled.

6.  Leave the blank list of **Shared Water Zones** (this list is necessary for `TRANSIT` zones only).

**NOTE**: You can set up objectives that will require the player to deliver the particular amount of water to the Water Station zone of the `DROP` type. See [Water Delivery Objectives](./water_delivery_objectives.md) for details.

