# scoutingInfo

*(NEW) This feature is valid for Expeditions only.*  

## Overview
The **scoutingInfo** [substage][stages_and_substages] corresponds to an assignment where the player needs to explore the particular area(s) of the map. Every such area is defined by the particular hidden zone, a certain radius around it, and a required percentage of area exploration.

This assignment requires *full* exploration (of the specified percentage) of target areas. *Full* exploration fully removes the fog of war and displays the explored area *in full color* on the map. On the contrary, *partial* exploration partially removes the fog of war and displays the explored area in the *shades of gray* on the map. 

However, target areas need to be *fully* explored only to required percent to accomplish the assignment, see **winCondition** below.

**NOTE 1**: This substage may have [multiple target areas][zone_related_assignments] that the player will need to explore. These areas correspond to records in the **scoutingsProp** list: `[0]`, `[1]`, etc. Radiuses of the target areas and their exploration options are set up on the per area basis (within these records).

**NOTE 2**: Every area to be explored is defined by a certain target zone and a certain radius around it. Previously, to make this target zone hidden, you were required to add the *ZonePropertyHiddenHint* prop with the completely disabled [**zoneDiscoverability**][zonediscoverability] settings to the **props** of this target zone. However, in the current version of the game, this is not required. The target zone will be hidden automatically, but you will need to ensure that it is not used in other objectives that may make it visible.


## Setup
After selecting the appropriate settings type, the **scoutingInfo** section will contain the following settings:

-   **scoutingsProp** list – The list of [zone-related assignments][zone_related_assignments] correspoding to areas that need to be explored. At least one record in this list is required. If you add multiple records to this list, the player will need to explore *all* of these areas, in any order.

    -   `[0]`, `[1]`, `[2]`, etc. – The record of the particular [zone-related assignment][zone_related_assignments] correspoding to the area that needs to be explored.

        -   **OptionalToPerform** – *(Optional)* Enabling this option will mark this substage as optional. By default, this option is disabled and the substage is required. See [Optional Substages][optional_substages] for details.

        -   **uiDesc** – The name of the substage that will be displayed in the UI of the game.

        -   **radius** – The radius of the area to be explored around the specified target zone (selected in the **zoneGlobalId** field).

        -   **winCondition** – The required percentage of target area exploration. Possible values: from `0` to `1`, where `0` corresponds to `0%`, and `1` corresponds to `100%`. For example, the value of `0.75` will require exploration of `75%` of the target area to accomplish the assignment.
            
            **NOTE**: Values displayed to the player in the UI will always be from `0%` to `100%`, but the specified **winCondition** value will be taken into account during calculations of the progress of this scale. I.e., the percentage required in **winCondition** will correspond to `100%` in the UI. However, the player will not actually see `100%` in the UI, since at `100%` the assignment will be considered accomplished.

        -   **notification** – *(Optional)* The notification to be displayed after completion of this [zone-related assignment][zone_related_assignments] of the substage. See [Notifications][notifications] for details.

        -   **Fake Zones** – *(Optional)* The list of initially possible, but, after exploration, *unsuitable* zones for the execution of this assignment. See [Fake Zones][fake_zones] for details.

        -   **zoneGlobalId** – The target zone that, along with the **radius** (see above), defines the target area to be explored by the player. By default, the zone selected in the **zoneGlobalId** field will be located in the center of the area to be explored and **radius** will define the radius of the exploration area around it. If necessary, the center of the exploration area may be moved from the target zone, see **localOffsetScoutingAreaRelativeZone** below.

        -   **localOffsetScoutingAreaRelativeZone** – The offset of the center of the exploration area from the center of the **zoneGlobalId** zone. Currently, there are two classes of settings available in this section: 
            -   `Vector2d`:
                -   **x** – the offset of the center of the exploration area by the X axis in the Editor.
                -   **y** – the offset of the center of the exploration area by the Z axis in the Editor.
                
                **NOTE**: For example, if coordinates of the center of the **zoneGlobalId** zone locator in the Editor are `(160, -50)` and you are specifying `10` as the value for both **x** and **y**, the coordinates of the center of the exploration area in the Editor will be `(170, -40)`. Please note that in the Editor, this will be its `(X, Z)` coordinates.
                
            -   `Vector2dRnd` – This type of settings should not be selected. It will be removed.        
       
            **WARNING**: Please note that even when you need no **localOffsetScoutingAreaRelativeZone** offset, one of the not-`null` setting types *must* be selected in this field. After selecting, you can leave it with the zero values. If you do not select one of the setting types (`Vector2d` or `Vector2dRnd`) in this field, this will result in an error (crash).

[stages_and_substages]: ./stages_in_expeditions.md
[zone_related_assignments]: ./stages_in_expeditions.md#multiple-zone-related-assignments-within-substage
[zonediscoverability]: ./../../../zones/expeditions_zones/discoverability_of_zones.md
[notifications]: ./../notifications.md
[optional_substages]: ./../optional_substages.md
[fake_zones]: ./../fake_zones.md


