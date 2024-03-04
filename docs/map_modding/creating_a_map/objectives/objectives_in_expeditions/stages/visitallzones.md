# visitAllZones

*(NEW) This feature is valid for Expeditions only.*  
*For the **visitAllZones** substage in SnowRunner, see [Visiting Zones][visit_zones_snowrunner].*

## Overview
The **visitAllZones** [substage][stages_and_substages] corresponds to an assignment where the player needs to visit the particular zone(s).

If necessary, the **visitAllZones** assignment can be set up so that the player will be able to visit the target zone with the *Drone* – as one of the possible variants of visiting (the **mayVisitZoneWithDrone** option). Or, you can even set up that visiting the zone by the drone is the only choice for the player (the **visitWithDroneOnly** option).

If you are creating zones that can be visited only with the Drone, you need to locate them *not* in the *No Flight Zone* that is automatically created near the edges of the map. For default *Drone*, the distance of *No Flight Zone* from the edge of the map is `170` meters. To measure distance in the Editor, you can user **Ruler** tool, see [Toolbar Buttons][toolbar_buttons] for details. And, you should also take into account that, for default *Drone*, the maximum height (from the truck) is `30` meters. 

**TIP**: If you have created your own Drone as a [custom Inventory Item][custom_inventory_item] and want to use it for visiting zones, you can modify this *No Flight Zone* distance by tuning the [**noFlyZone**][ability_specific_properties_of_inv_items] parameter in the custom drone settings. And, in this case, you can also tune the [**heightLimitEnterZone**][ability_specific_properties_of_inv_items] parameter in the drone properties that sets the maximum height of the drone above the target zone for it to be considered "visited".

If you are configuring these Drone-only zones, ensure that you have enabled *both* **visitWithDroneOnly** and **mayVisitZoneWithDrone** options. If you enable only **visitWithDroneOnly** and leave **mayVisitZoneWithDrone** disabled, the player will *not* be able to visit this zone by any means, since visiting by the truck will be prohibited by enabled **visitWithDroneOnly** and visting by the drone will *not* be allowed since **mayVisitZoneWithDrone** is disabled. 

**NOTE**: This substage may have [multiple target zones][zone_related_assignments] that the player will need to visit. These zones correspond to records in the **zones** list: `[0]`, `[1]`, etc. Target zones and visiting options are set up on the per zone basis (within these records).


## Setup
After selecting the appropriate settings type, the **visitAllZones** section will contain the following settings:

-   **notification** section – *(Optional; Currently does not work.)* Settings of the notification displayed to the player upon accomplishing the whole substage. See [Notifications][notifications] for details.

-   **zones** list – The list of [zone-related assignments][zone_related_assignments] correspoding to zones that need to be visited. At least one record in this list is required. If you add multiple records to this list, the player will need to visit *all* of these zones, in any order, with the particular visiting settings specified on the per zone basis.

    -   `[0]`, `[1]`, `[2]`, etc. – The record of the particular [zone-related assignment][zone_related_assignments] correspoding to the zone that needs to be visited.

        -   **OptionalToPerform** – *(Optional)* Enabling this option will mark this substage as optional. By default, this option is disabled and the substage is required. See [Optional Substages][optional_substages] for details.

        -   **uiDesc** – The name of the substage that will be displayed in the UI of the game.

        -   **Truck need to visit Uid** – *(Cannot be appropriately used in Expeditions.)* In SnowRunner, this field allows to specify the identifier of the truck that the player needs to use to visit the target zone, where this truck is initially located on the map and has the same **Id** in its properties. However, in Expeditions, trucks are selected by the player and deployed to Deploy zones and there is no ability to sit into the truck that was *initially* (before deploying) located on the map. That's why this field cannot be used in Expeditions and there is no need to use it.

        -   **mayVisitZoneWithDrone** – *(Optional)* By default, disabled. Enabling this field *allows* the player to visit the target zone using the *Drone*. However, the player is able to visit it by truck instead, if they want to. Both types of "visiting" will accomplish the corresponding assignment.

        -   **visitWithDroneOnly** – *(Optional)* By default, disabled. Enabling this field *requires* the player to visit the target zone using the *Drone*. In this case, visiting of the target zone using the truck will *not* accomplish the assignment. If you enable the **visitWithDroneOnly** option, you need to enable the **mayVisitZoneWithDrone** option too – otherwise, the player will *not* be able to accomplish the assignment, see [above](#overview).

            **WARNING**: If you are creating zones that can be visited *only* with the Drone, you need to locate them *not* in the *No Flight Zone*, see [above](#overview).

        -   **notification** – *(Optional)* The notification to be displayed after completion of this [zone-related assignment][zone_related_assignments] of the substage. See [Notifications][notifications] for details.

        -   **Fake Zones** – *(Optional)* The list of initially possible, but, after exploration, *unsuitable* zones for the execution of this assignment. See [Fake Zones][fake_zones] for details.

        -   **globalZoneId** – The target zone that needs to be visited by the player.

        -   **radiusSett** – *(Optional)* The radius of the [Zone Search Area][zone_search_area] where you want the player to search for the target zone, if you do *not* want to give the player its explicit location. See [Zone Search Area][zone_search_area] for details.


[visit_zones_snowrunner]: ./../../objectives_in_snowrunner/stages/visiting_zones.md
[stages_and_substages]: ./stages_in_expeditions.md
[zone_related_assignments]: ./stages_in_expeditions.md#multiple-zone-related-assignments-within-substage
[notifications]: ./../notifications.md
[optional_substages]: ./../optional_substages.md
[fake_zones]: ./../fake_zones.md
[zone_search_area]: ./../zone_search_area.md
[custom_inventory_item]: ./../../../../../custom_gameplay_entities/inventory_items/custom_inventory_items_overview.md
[ability_specific_properties_of_inv_items]: ./../../../../../custom_gameplay_entities/inventory_items/ability_specific_properties_of_inventory_items.md
[toolbar_buttons]: ./../../../../getting_started/ui_overview/toolbar_buttons.md

