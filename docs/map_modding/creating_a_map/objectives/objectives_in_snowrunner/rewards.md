# Rewards

*(NEW) This topic is valid for SnowRunner only.*  
*For Rewards in Expeditions, see [Rewards](./../objectives_in_expeditions/rewards.md).*


## Reward Description
The decription of the reward for the [objective][objectives_overview] is specified in the **Reward Description** field in its properties.

This field is a [common field][common_fields_of_objectives] that is available in all types of objectives.


## List of Possible Rewards
Main rewards for the [objective][objectives_overview] are added to the **rewards** list in its properties.

This list is a [common field][common_fields_of_objectives] that is available in all types of objectives.

Types of rewards that can be added to this list are the following:

-   **ObjectiveRewardExperience** – the amount of XP granted as a reward.

-   **ObjectiveRewardMoney** – the amount of money granted as a reward.

-   **ObjectiveRewardItem** – here you need to specify the ID of the type of the necessary upgrade (for details, see [How to Identify IDs of Truck parts](./../../trucks/how_to_identify_ids_of_truck_parts.md)).  
    Alternatively, you can specify here the ID of the ***type*** of the truck if you want to give it as a reward (e.g. `chevrolet_kodiakc70`).  
    
    ![](./media/image296.png)

    After the player accepts the reward, the truck of the specified type will become available in the Garage.

    **NOTE**: Alternatively, you can give the truck involved in the assignment as a reward after the completion of the objective. For details, see [Truck Delivery](./stages/truck_delivery.md).

-   **ObjectiveRewardOpenZoneProperties** – we can open the particular zone to the player as a reward. You need to specify:

    -   **zoneId** – the ID of the zone (in the short form, without the name of the map and `||`).

    -   **mapId** – the ID of the map (the name of the XML file of your map, *without* the extension).

    -   **props** – properties of this zone, see [Zone Types in SnowRunner][zone_types_in_snowrunner] for details.

        **NOTE**: You do *not* need to create a duplicate of this zone in the **TERRAIN LOCATORS LIST** of the zone settings plugin. However, you need to create a *zone locator* with the specified ID for this zone in the Editor (see [Zones: Overview][zones_overview] for details).

-   **ObjectiveRewardAddItemsToZone** – as a reward, we can add some cargo to the particular zone. You need to specify:

    -   **zoneId** – the ID of the zone (in the short form, without the name of the map and `||`).

    -   **mapId** – the ID of the map (the name of the XML file of your map, *without* the extension).

    -   **cargosSettings** – standard settings of cargo that will appear in the zone:

        -   **name** – the type of the cargo to be added.

        -   **Count If Finite** – the amount of cargo to be added.

-   **ObjectiveRewardUpdateZoneProperties** – as a reward, we can dynamically change the properties of a zone. Particularly, you will need to specify:

    -   **zoneSettings** – the properties that will be *added* to the particular zone. Particularly, you will need to specify:

        -   **zoneId** – the ID of the zone (in the short form, without the name of the map and `||`).

        -   **mapId** – the ID of the map (the name of the XML file of your map, *without* the extension).

        -   **props** – properties of this zone that will be *added*, see [Zone Types in SnowRunner][zone_types_in_snowrunner] for details.

    -   **zoneSettingsToRemove** – the properties that will be *removed* from the particular zone. Particularly, you will need to specify:

        -   **zoneId** – the ID of the zone (in the short form, without the name of the map and `||`).

        -   **mapId** – the ID of the map (the name of the XML file of your map, *without* the extension).

        -   **props** – properties of this zone that will be removed, see [Zone Types in SnowRunner][zone_types_in_snowrunner] for details.
                
            **WARNING**: For **zoneSettings** / **zoneSettingsToRemove**, you do ***not*** need to create a duplicate of this zone in the **TERRAIN LOCATORS LIST** of the zone settings plugin. However, you need to create a *zone locator* with the specified ID for this zone in the Editor (see [Zones: Overview][zones_overview] for details).

-   **ObjectiveRewardsUpgradeGarage** – allows you to activate a certain functionality area of an upgradeable Garage as a reward. See [Upgradeable Garage][upgradeable_Garage] for details.

-   **ObjectiveRewardUnlock** – allows you to *unlock* a certain item for the player as a reward. The identifier of this item needs to be specified in the **itemToUnlock** field. Similarly to **ObjectiveRewardItem** (see above), you can specify here the ID of the upgrade or the *type* of the truck, if it was previously locked (see [Locking and Unlocking Trucks and Upgrades](#locking-and-unlocking-trucks-and-upgrades)) and you want to *unlock* it as a reward.  
    For example, you can lock and then unlock `chevrolet_kodiakc70`.


## Contests-Specific Rewards
For *Contests*, the following additional type of rewards can be used:

-   **ObjectiveRewardsByTime** – here you can set 3 types of rewards (Bronze, Silver, and Gold) given to the player based on the time of the accomplishment of the objective.  
    For each type, you specify:

    -   **Time limit** – time limit for this type of reward, in seconds.

    -   **Experience** – the amount of granted XP.

    -   **Money** – the amount of given money.

    -   **Possible Item reward** – the ID of the type of the necessary upgrade. Or, the ID of the ***type*** of the truck if you want to give it as a reward (see **...Item** above).





[objectives_overview]: ./../objectives_overview.md
[common_fields_of_objectives]: ./common_fields_of_objectives.md
[zones_overview]: ./../../zones/zones_overview.md
[zone_types_in_snowrunner]: ./../../zones/snowrunner_zones/zone_types_in_snowrunner.md
[upgradeable_Garage]: ./../../zones/snowrunner_zones/garageentrance_and_garageexit_zones/upgradeable_garage.md 
[locking_and_unlocking_trucks_and_upgrades]: ./../../other_map_settings/content_settings/locking_and_unlocking_trucks_and_upgrades.md