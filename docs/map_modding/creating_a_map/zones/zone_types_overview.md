# Zone Types Overview

## Overview
Zone properties that depend on the *type* of the zone are specified in the [**props**][props_section] section.

The [Expeditions Zones][expeditions_zones] and [SnowRunner Zones][snowRunner_zones] subsections below describe these type-specific properties for every type of the zone.

## Multiple Props
All type-specific zone properties can be combined.

I.e., a single zone can have multiple zone types in the [**props**][props_section] section. 

For example, in Expeditions, a typical [Deploy zone][deploy_zones] has 3 props in its settings:

-   [*ZonePropertyDeploy*][deploy_zones] – to support the deployment of player's trucks.
-   [*ZonePropertyInventoryStorage*][inventory_storage_zones] – to support the *Base module* of this Deploy zone.
-   [*ZonePropertyRecovery*][recovery_zones] – to support Recovery to this Deploy zone.

Or, in SnowRunner, you can make the zone that will be the fuel station (and correspondingly will have the *ZonePropertyFuelStation* prop and, in the same time, will automatically repair player's vehicle (the *ZonePropertyAutoRepairAndRestore* prop).

## Using Rewards to Change Props
You can use rewards given to the player for the accomplishment of an objective to:

-   Open the particular zone(s) to the player, with particular **props** assigned to them. This can be done with the help of the **ObjectiveRewardOpenZoneProperties** reward. 

-   Dynamically change the **props** of the zone to expand its functionality or, on the contrary, to remove some of its functions. This can be done with the help of the **ObjectiveRewardUpdateZoneProperties** reward.

For details on rewards in *Expeditions*, see [Rewards][rewards].

For details on rewards in *SnowRunner*, see [Common Fields of Objectives][common_fields_of_objectives].


[props_section]: ./zones_overview.md#props
[expeditions_zones]: ./expeditions_zones/zone_types_in_expeditions.md
[snowRunner_zones]: ./snowrunner_zones/zone_types_in_snowrunner.md
[deploy_zones]: ./expeditions_zones/deploy_zones.md
[inventory_storage_zones]: ./expeditions_zones/inventory_storage_zones.md
[recovery_zones]: ./expeditions_zones/recovery_zones.md
[rewards]: ./../objectives/objectives_in_expeditions/rewards.md
[common_fields_of_objectives]: ./../objectives/objectives_in_snowrunner/common_fields_of_objectives.md

