# Stages in Expeditions

*(NEW) This topic is valid for Expeditions.*
*For a similar SnowRunner topic, see [Stages in SnowRunner](./../../objectives_in_snowrunner/stages/stages_in_snowrunner.md).*


## General Info
All objectives in Expeditions and SnowRunner consist of *Stages*. 

Every *Stage* corresponds to a group of assignments of particular types that the player needs to accomplish as a paticular stage of this objective. These assignments within a *Stage* are called *Substages*.

Stages are created in the **Stages** list within the properties of the objective. For example, you can create Stage `[0]`, `[1]`, `[2]`, etc.

To create a Substage within a Stage, you need to fill in a certain section of settings within this Stage.

For example, you can expand the `[0]` stage within the **Stages** list of a Task and fill in the **visitAllZones** section within this `[0]` stage – to tell the player to visit a particular zone as a Substage of Stage `[0]`. By this, you will create the **visitAllZones** substage of the Stage `[0]`.

**NOTE**: For more general info on Stages and Substages, see [Objectives: Overview](./../../objectives_overview.md#stages-and-substages).


## Possible Types of Substages in Expeditions
In Expeditions, the list of possible substage types is the following:

-   [**objectConstruction**][objectconstruction] section – delivery of certain [Inventory Items][inventory_items] to the particular zone, with "building" objects, if necessary. 
-   [**takeInventory**][takeinventory] section – the player needs to *take* certain [Inventory Items][inventory_items] from the particular zone.
-   [**truckDelivery**][truckdelivery] section – delivery of a certain truck located on the map to the particular zone.
-   [**visitAllZones**][visitallzones] section – the player needs to visit particular zones.
-   [**minigameInfo**][minigameinfo] section – the player needs to play a [minigame][minigame] of the particular type. 
-   [**scoutingInfo**][scoutinginfo] section – the player needs to explore the particular areas of the map. Every such area is defined by the particular hidden zone, a certain radius around it, and a required percentage of area exploration.
-   [**Seismograph Settings**][seismograph_settings] section – the player needs to perform a seismic vibration in the particular zones. These zones themselves are not displayed on the map and the player needs to locate them.
-   [**freeRoamInfo**][freeroaminfo] section – this substage is used for the *Free Roam* mechanics only. If you want the player to be able to *Free Roam* on the map, you need to create the separate Expedition for this map and make only 1 Stage only in this Expedition, with the **freeRoamInfo** substage inside it.  


## Common Fields

### Fields Common for All Stages
Unlike SnowRunner, Expeditions does not have properties that are common for all Stages (e.g. *no* **needToStartTimer**, etc.). 

However, Substages in Expeditions do have some common fields, see below.


### Fields Common for All Substages
Regardless of the fact that all substages listed [above](#possible-types-of-substages-in-expeditions) have some specific fields, there are ields that are available in most of substage types:

-   **OptionalToPerform** option – *(Optional field; for all substages, except **truckDelivery** and **freeRoamInfo**)* Disabled by default. When enabled, marks this substage as an optional one that can be skipped by the player. See [Optional Substages](./../optional_substages.md) for details.

-   **notification** section – *(Optional settings; for all substages, except **freeRoamInfo**)* settings of the notification displayed to the player upon accomplishing this substage and/or the particular [zone-related assignment](#multiple-zone-related-assignments-within-substage) of this substage. See [Notifications][notifications] for details.

-   **Fake Zones** list – *(Optional settings; for all substages, except **truckDelivery** and **freeRoamInfo**)* The list of [Fake Zones][fake_zones] that the player may visit when trying to accomplish the substage, but that will be *not* suitable for the accomplishing the substage. See [Fake Zones][fake_zones] for details.

-   **radiusSett** section – *(Optional field; or all substages, except **scoutingInfo** and **freeRoamInfo**)* Allows you to hide the target zone of the substage from the map, but show the approximate area where it is located, of a certain radius. I.e., instead of giving explicit target location to the player, you give them area that they need to explore to locate the target zone. See [Zone Search Area][radiussett] for details. 

-   **Model Building Settings** section – *(Optional settings; for **objectConstruction** and **takeInventory** substages)* These optional sections allows you to link the process of "building" some object on the map to delivering/taking some object by the player. The model referenced in this section will chnage its state once this substage is accomplished. See [Model Building Settings][model_building_settings] for details.  


## Multiple Zone-Related Assignments within Substage
Some types of substages allow you to configure multiple zone-related assignments within a substage.

For example, when configuring **visitAllZones** substage, you can add multiple records to the **zones** list in its properties. And, in this case, the player will need to visit *all* zones mentioned in these records, in any order. 

Or, when configuring **objectConstruction** substage, you can add multiple records to the **zoneToFill** list in its properties. And, correspondigly, the player will need to deliver items to *all* of these zones, also in any order, with the particular items to be delivered specified on the per zone basis.

Particularly, the following substage types support these multiple zone-related assignments:

-   [**objectConstruction**][objectconstruction]
-   [**takeInventory**][takeinventory]
-   [**truckDelivery**][truckdelivery]
-   [**visitAllZones**][visitallzones]
-   [**minigameInfo**][minigameinfo]
-   [**scoutingInfo**][scoutinginfo]
-   [**Seismograph Settings**][seismograph_settings]


[inventory_items]: ./../../../../../custom_gameplay_entities/inventory_items/custom_inventory_items_overview.md
[minigame]: ./../../../minigames/minigames_overview.md
[fake_zones]: ./../fake_zones.md
[radiussett]: ./../zone_search_area.md
[model_building_settings]: ./../../model_building_settings/model_building_settings.md
[notifications]: ./../notifications.md 

[objectconstruction]: ./objectconstruction.md 
[takeinventory]: ./takeinventory.md
[truckdelivery]: ./truckdelivery.md
[visitallzones]: ./visitallzones.md
[minigameinfo]: ./minigameinfo.md
[scoutinginfo]: ./scoutinginfo.md
[seismograph_settings]: ./seismograph_settings.md
[freeroaminfo]: ./freeroaminfo.md
