# PICK_UP Water Stations

*This topic is valid for SnowRunner only.*  

## Overview
`PICK_UP` Water Station zones allow the player to "pick up" water, i.e. to *fill the water tanks of their truck from the zone reservoir*.

**NOTE**: For these zones, water cannot go in the reverse direction, i.e. the player *cannot* fill the zone reservoir from the truck tank.

## Setting Up
Setting up this zone is rather simple:

1.  In the **stationUIName** field of **ZonePropertyWaterStation**, you set up the name of the zone (e.g. `River Water`) or leave the default one.

2.  In **stationType** – select `PICK_UP`.

3.  In **Water** – specify the amount of water, in liters, that the player can take from this zone. I.e., this will be the current amount of water in the water reservoir of this zone. To specify an infinite amount (e.g. in case of the river), you can specify the `-1` value.

4.  In **Capacity** – specify the maximum capacity of the water reservoir of this zone. Specified **Capacity** must be greater than current amount (**Water**). The `-1` value will set the capacity of this water reservoir to infinity, and, if you specified infinite current amount (**Water**), then the **Capacity** must be infite too.

5.  Leave the **Is water delivery objective zone** option disabled. (This option should be enabled for `DROP` zones that are target zones of some objectives only).

6.  Leave the blank list of **Shared Water Zones** (this list is necessary for `TRANSIT` zones only).

