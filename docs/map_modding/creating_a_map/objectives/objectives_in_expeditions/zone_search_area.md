# Zone Search Area

*(NEW) This feature is valid for Expeditions only.*

## Overview
When you create a [substage][stages_and_substages] of a certain type, you are typically setting up a target zone for it. And, typically, this zone is explicitly displayed on the map. 

However, if necessary, you can avoid giving explicit location of this zone to the player. Instead, you can give them only the area that they will need to explore to locate the target zone.

This can be done using the **radiusSett** section of the substage. This section is available for all [substages][stages_and_substages], except **scoutingInfo** and **freeRoamInfo**.


## Setup 
The setup of this feature is simple:

1.  In the **radiusSett** section of the necessary [substage][stages_and_substages], you select *ZoneRadiusSettings*.
2.  In the **zoneRadius** field within these settings, you specify the radius of the search area, in meters.

**NOTE 1**: The search area will have the specified radius, but the target zone will be *not necessarily* in its center, since it will be generated in a random way.

**NOTE 2**: If you have configured [Fake Zones](./fake_zones.md) for the same [substage][stages_and_substages], they will be automatically displayed as search areas with the same **radiusSett** settings.


[stages_and_substages]: ./stages/stages_in_expeditions.md