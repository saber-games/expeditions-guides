# Rewards

*(NEW) This topic is valid for Expeditions only.*  
*For Rewards in SnowRunner, see [Rewards](./../objectives_in_snowrunner/rewards.md).*  

## Reward Description
The decription of the reward for the [objective][objectives_overview] is specified in the **Reward Description** field in its properties.

This field is a [common field][common_fields_of_objectives] that is available in all types of objectives.

## Main Rewards
Main rewards for the [objective][objectives_overview] are added to the **rewards** list in its properties.

This list is a [common field][common_fields_of_objectives] that is available in all types of objectives.

Types of rewards that can be added to this list are the following:

-   **ObjectveRewardAddItemsToZone** – *(Not used in Expeditions; To be deleted)* Should not be used in *Expeditions*, will be removed. In *SnowRunner*, as a reward, adds some Cargo to the particular zone. (`TBD`)

-   **ObjectiveRewardOpenZonePropertes** <a id="open_zone"></a> – As a reward, opens the particular zone to the player, allowing you to specify the properties of this new zone. The zone locator for this zone needs to be created for this zone beforehand.  
    This reward has the following settings: 
    
    -   **ZoneSettings** – The list of zone records that will be opened as a reward. Every record in this list corresponds to the particular zone and contains settings of the **ZonePropertiesSettingsObjectiveReward** type. If multiple records are added to this list, multiple zones will be opened as a reward. For every zone record, you need to specify:

        -   **zoneId** – The identifier of the zone, in the short form, without the name of the map and without `||` as a delimiter. This identifier should be the same as the corresponding identifier of the zone locator that is created and placed on the map in the Editor (beforehand). For example, `my_zone_01`.

        -   **mapId** – The identifier of the map. I.e., the name of the XML file of your map, without the `.xml` extension.

        -   **props** – Properties of this zone. I.e., *props* that will be assigned to the opened zone, with all settings within these props specified in a usual way. See [Zone Types Overview][zone_types_overview] and [Zone Types in Expeditions][zone_types_in_expeditions] for details.

            **NOTE**: You need to create a *zone locator* with the specified identifier (**zoneId**) for this zone in the Editor beforehand.

-   **ObjectiveRewardUpdateZoneProperties** – As a reward, dynamically changes the properties of the particular zone(s). 

    -   **ZoneSettings** – The list of zone records where the props will be *added*. Every record in this list corresponds to the particular zone and contains settings of the **ZonePropertiesSettingsObjectiveReward** type. If multiple records are added to this list, props will be added to multiple zones.  
    For every zone record, you need to specify:

        -   **zoneId** – The identifier of the existing zone, in the short form, without the name of the map and without `||` as a delimiter. For example, `my_zone_01`.

        -   **mapId** – The identifier of the map. I.e., the name of the XML file of your map, without the `.xml` extension.

        -   **props** – Properties that will be *added* to this zone. I.e., *props* that will be added to the specified zone, with all settings within these props specified in a usual way. See [Zone Types Overview][zone_types_overview] and [Zone Types in Expeditions][zone_types_in_expeditions] for details.

            **NOTE**: The zone with the specified identifier (**zoneId**) should exist on the map.

    -   **zoneSettingsToRemove** <a id="remove_props"></a>– The list of zone records where the props will be *removed*. Every record in this list corresponds to the particular zone and contains settings of the **ZonePropertiesSettingsObjectiveReward** type. If multiple records are added to this list, props will be removed from multiple zones.  
    For every zone record, you need to specify:

        -   **zoneId** – The identifier of the existing zone, in the short form, without the name of the map and without `||` as a delimiter. For example, `my_zone_01`.

        -   **mapId** – The identifier of the map. I.e., the name of the XML file of your map, without the `.xml` extension.

        -   **props** – Properties that will be *removed* from this zone. I.e., *props* that will be removed from the specified zone, with all settings within these props specified in a usual way. See [Zone Types Overview][zone_types_overview] and [Zone Types in Expeditions][zone_types_in_expeditions] for details.

            **NOTE**: The zone with the specified identifier (**zoneId**) should exist on the map.

-   **ObjectiveRewardsUpgradeGarage** – *(Not used in Expeditions; To be deleted)* Should not be used in *Expeditions*, will be removed. In *SnowRunner*, allows you to activate a certain functionality area of an upgradeable Garage as a reward. Not valid for Expeditions. (`TBD`)

-   **ObjectiveRewardMoney** – Money that will be granted as a reward.  
    Has only one setting:

    -   **amount** – The amount of money to be given.

-   **ContestResultRewards** – *(Not used in Expeditions; To be deleted)*. Should not be used in *Expeditions*, will be removed. (`TBD`)

-   **ObjectiveRewardUnlock** – The particular truck or truck upgrade that will unlocked for the player as a reward.    
    Has only one setting:

    -   **itemToUnlock** – The identifier of the item to be unlocked.

        **NOTE**: Identifiers of trucks can be seen in XML classes of the trucks in the `initial.pak` and while adding truck in the Editor. Identifiers of truck upgrades can be seen in the XML classes of the trucks and components in the `initial.pak` and after the debug **Garage** UI is opened from the **TOOLS** menu of the "Proving Ground" map. See [How to Identify IDs of Truck Parts][truck_parts] for details.

-   **ObjectiveSingleRewardUnlockOnce** – *(Technical class; Should not be used; Should be hidden)* This a technical internal class of reward used a parent of other classes. It should not be used and should be hidden. (`TBD`)  
    Has only one setting:

    -   **Unlockable stuff Id** – The identifier of the item to be unlocked. 

-   **ObjectiveRewardBaseUpgrade** – The particular *FOB Module* that will unlocked for the player as a reward. Has only one setting:

    -   **Unlockable stuff Id** – The identifier of the FOB Module to be unlocked. 
    
        **NOTE**: See [Zones of FOB Modules: Overview][zones_of_fob_modules_overview] for the full list of identifiers of FOB Modules. Or, for details on custom FOB Modules, see [Custom FOB Modules: Overview][custom_fob_modules_overview]

-   **ObjectiveRewardItem** – The particular upgrade of the truck or the truck itself that will be given as a reward.  
    Has only one setting:

    -   **Unlockable stuff Id** – The identifier of the upgrade of the truck or the truck.  
        
        **NOTE**: Identifiers of trucks can be seen in the XML classes of the trucks in the `initial.pak` and while adding truck in the Editor. Identifiers of truck upgrades can be seen in the XML classes of the trucks in the `initial.pak` and after the debug **Garage** UI is opened from the **TOOLS** menu of the "Proving Ground" map. See [How to Identify IDs of Truck Parts][truck_parts] for details.

-   **ObjectiveRewardSticker** – The particular sticker for the truck that will be given as a reward. Has only one setting:

    -   **Unlockable stuff Id** – The identifier of the sticker. 
        
        **NOTE**: The full list of identifiers of original stickers is available (along with other localization strings) in the `strings_english.str` file, located in the `initial.pak` archive within the `[strings]` subfolder.  

-   **ObjectiveRewardSpecialist** – The particular *Specialist* who will become available for the player as a reward. Has only one setting:

    -   **Unlockable stuff Id** – The identifier of the Specialist. For example, `Mechanic_01`. Or, `Jaeger_02`. Or, `Hydrologist_03`.


## Bonus Rewards
Along with [Main Rewards](#main-rewards), you can also give some additional money to the player as bonus reward if the particular condition has been fulfilled during the execution of an [Expedition][expeditions_and_contracts]. 

**NOTE**: Bonus Rewards are valid for [Expeditions][expeditions_and_contracts] only. They are *not* valid for [Contacts][expeditions_and_contracts] and [Tasks][tasks].

These rewards can be added to the **bonusRewards** list in the properties of an [Expedition][expeditions_and_contracts].

All types of these rewards use the same **info** section in their settings. This section contain two fields:

-   **uiDesc** – Text that will be displayed in the UI when this bonus reward is granted.
-   **rewardMoney** – The amount of money that will be given when this bonus reward is granted.

The types of bonus rewards themselves are the following:

-   **BonusConditionBase** – *(Technical class; Should not be used; Should be hidden)* This is a technical class on bonus reward used as a parent for other classes. It should not be used and should be hidden, (`TBD`)

-   **BonusConditionWithLimit** – *(Technical class; Should not be used; Should be hidden)* This is a technical class on bonus reward used as a parent for other classes. It should not be used and should be hidden, (`TBD`)

-   **BonusConditionDamageTaken** – This reward is given when the player takes less damage than the specified **limit**.

-   **BonusConditionDetectResource** – This reward is given when the number of previously unknown Points Of Interest (POIs) on the map found by the player is greater than the specified **limit**.

-   **BonusConditionDoNotUseItem** – This reward is given when the number of times the player uses the particular item is less than the specified **limit**. The type of this item used in this reward is specifed using the **abilityType** drop-down. In the original game, this condition is mainly used to check the `JACKSCREW` usage. Such values as `TOOLKIT`, `PORTABLE_METEOSTATION`, `FUEL_CANISTER`, `INSPECTION`, `NONE` should *not* be used as the value of this field. (`TBD`)

-   **BonusConditionEngineStall** – This reward is given when the number of times the engine of the player's truck gets stalled (due to the particular reason) is less than the specified **limit**. The particular reason of the stall is selected in the **stallReason** drop-down. In the original game, this condition is mainly used to check the number of times the player's truck has rolled over (the `ROLL_OVER` option in **stallReason**).

-   **BonusConditionItemConsumed** – This reward is given when the number of completely consumed *items with "charges"* (*Anchor* and *Jackscrew*) from the player's Inventory is less than the specified **limit**.

-   **BonusConditionMinigameTryLimit** – This reward is given when the number of times the player fails when playing the particular [minigame][minigames] is less than the specified **limit**. The name of the particular [minigame][minigames] is specified in the **minigameName** field and the Expedition of this bonus reward must contain the Stage with the minigame of the specified name.

-   **BonusConditionNoRecovery** – This reward is given when the number of times the player recovers their truck is less than the specified **limit**.

-   **BonusConditionTireInflation** – This reward is given when the *amount of damage* taken due to the usage of [*Tire Inflation System*][tire_inflation_system] is less than the specified **limit**.

## Stage Rewards

You can **open** the particular zone to the player **as a reward**. It is possible to specify the properties of this new zone, see the details [above](#open_zone).

Also you can **remove** properties from the particular zone, with all the settings within these properties. See the details [above](#remove_props).


[objectives_overview]: ./../objectives_overview.md
[common_fields_of_objectives]: ./common_fields_of_objectives.md
[zone_types_overview]: ./../../zones/zone_types_overview.md
[zone_types_in_expeditions]: ./../../zones/expeditions_zones/zone_types_in_expeditions.md
[zones_of_fob_modules_overview]: ./../../zones/expeditions_zones/zones_of_fob_modules/zones_of_fob_modules_overview.md
[minigames]: ./../../minigames/minigames_overview.md
[tire_inflation_system]: ./../../../../truck_modding/new_features/tire_inflation_system.md
[expeditions_and_contracts]: ./expeditions_and_contracts.md
[tasks]: ./tasks.md
[custom_fob_modules_overview]: ./../../../../custom_gameplay_entities/fob_modules/custom_fob_modules_overview.md
[truck_parts]: ./../../trucks/how_to_identify_ids_of_truck_parts.md
        