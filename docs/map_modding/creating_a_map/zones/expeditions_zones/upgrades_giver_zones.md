# Upgrades Giver zones

*(NEW) This feature is valid for Expeditions only.*

*For SnowRunner, see [UpgradesGiver zones](./../snowrunner_zones/upgrades_giver_zones.md).*


## Main Function: Giving Upgrades to the Player
A *ZonePropertyUpgradesGiver* zone allows you to give the certain upgrade for the player. 

For example, you can give them a certain new engine, or a certain model of gear box, and so on.

This property has the **upgrades** list where you need to list IDs of all upgrades that will be given to the player by this zone.


## How I can identify the IDs of upgrades?
In short, you can:

-   Look up these IDs in the XML files of the truck that are available at the `initial.pak` archive. Particularly, the `[media]\classes\` folder of the `initial.pak` archive contains all XML classes of trucks, engines, gearboxes, and so on. DLC trucks are also available at the `initial.pak` archive, in the `[media]\_dlc` folder.
-   Load one of the "Testing Ground" maps, spawn the necessary truck there, and select **Garage** in the **TOOLS** menu. In the appearing menu, you can see all the necessary IDs.

See [How to Identify IDs of Truck Parts](./../../trucks/how_to_identify_ids_of_truck_parts.md) for details.


## ZonePropertyUpgradesGiver Prop Settings
Settings of the *ZonePropertyUpgradesGiver* prop are the following:

-   **zoneDiscoverability** – settings related to the zone discovery. See [Discoverability of Zones](./discoverability_of_zones.md). 

-   **upgrades** – the list with IDs of ugrades that will be given to the player by this zone.  
    For example, to open the *IMZ 425-M* engine of the *KHAN 39 Marshall*, you need to add the record with the `ru_scout_khan_39_engine_1` identifier to this list. 

    **NOTE**: Currently, only the 1-st item from the **upgrades** list is given to the player. All other items from this list are not given by the zone. This is a known issue that will be fixed.
