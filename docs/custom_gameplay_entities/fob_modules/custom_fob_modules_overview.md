# Custom FOB Modules: Overview

*(NEW) This feature is valid for Expeditions only.*

## Overview
*FOB Modules* (or *Base Modules*) are buildings that can be built in the specifically configured zones near the Main Base or Outposts.

**NOTE**: You can add only *potential* FOB modules to the map. I.e., you can only set up zones where these FOB modules may be built by the player. You are not able to add an already built and operational FOB module of the particular type to the map. For details on the necessary configuration of zones and their props that will allow the player to build FOB modules, see [Deploy zones][deploy_zones_fob_modules].

In addition to original FOB Modules, you can create custom FOB modules that will be available in the game in the same zones as the original ones.

The functionality that the custom FOB module will provide to the player is based on:

-   Its [Class](#classes) (Currently, there are only two classes).
-   Its [FOB Module zone](#fob-module-zones) and its settings.

**NOTE**: Lists of classes and FOB module zones are predefined. 

All built FOB modules appear as some visual models in the game. So, when creating a custom module, you will need to either use one of the predefined models of FOB modules, or create your own custom 3d models for that. For details on these models and their setup, see [3D Models of FOB Modules][3d_models_of_fob_modules]. 


## Classes
Similarly to custom [inventory items][inventory_items_overview], FOB Modules may have different classes: 

-   `BaseUpgradeDesc` – The regular class of the FOB module. Funtionality provided by the FOB module of this class is solely defined by the [FOB Module zone](#fob-module-zones) selected for it.
-   `AntennaUpgradeDesc` – The special class of the FOB module that provides the `Antenna` ability. This ability requires no interaction from the player and opens all [*Air Drops*][inventory_storage_zones] that are located within the specified radius. This radius is defined by the value of the additional **radiusDiscoverInventoryStorageZone** field in the proprties of the FOB module of this class. 

**NOTE**: For modules of `AntennaUpgradeDesc` class, the [FOB Module zone](#fob-module-zones) may be not defined. Thus, the functionality of the module is typically defined by either the `BaseUpgradeDesc` class with some [FOB Module zone](#fob-module-zones), or by the `AntennaUpgradeDesc` class without it.


## FOB Module Zones
For every module, in the **zonePropery** field, you are able to select one [FOB Module zone][fob_module_zones] that will define the functionality provided by this module. 

For details on particular zone types that are possible in this field, see the [Zones of FOB Modules: Overview][fob_module_zones] topic in **Map Modding** and topics related to particular zone types in the same section.

**NOTE**: Some zones of FOB modules have an addittional field – **moduleId**. In this field, you need to specify the [*identifier*][fob_module_identifier] of this custom FOB module – to link the zone to this module. For every custom FOB module, the identifier is defined during its [creation][creation_of_custom_fob_module]. 


## 3D Models
Every FOB module should use 2 static models of the "built" module and may use 2 animated models that will visualize the appearance of the module.

See [3D Models of FOB Modules][3d_models_of_fob_modules] for details.


## Interaction with Player
The **isInteractive** option in the properties of the FOB module allows you to specify whether or not the player will be able to interact with this module.

If the module is interactive, the player will be able to interact with it the same way as with regular in-game modules of the same type. For example, initiate this process in the interaction zone of the module, which will open the Trade dialog or Workshop dialog, and so on.

However, some types of the modules are not interactive. E.g., the built *Tow truck* module reduces the cost of evacuation, but the player does *not* directly interact with this module itself.

The values of the **isInteractive** option for different types of modules – defined by the [zone](#fob-module-zones) selected for them or by their non-regular [class](#classes) – are below.

| **Type of FOB Module**     | **isInteractive** | **zoneProperty** / **class**                                 | 
|----------------------------|-------------------|--------------------------------------------------------------|
| similar to *Base module*   | `True`            | [ZonePropertyFobModuleStorage][zonepropertyfobmodulestorage] |
| similar to *Store*         | `True`            | [ZonePropertySupplyShop][zonepropertysupplyshop]             |
| similar to *Gas station*   | `True`            | [ZonePropertyFobModuleStorage][zonepropertyfobmodulestorage] |
| similar to *Warehouse*     | `True`            | [ZonePropertyFobModuleStorage][zonepropertyfobmodulestorage] | 
| similar to *Repair station*| `True`            | [ZonePropertyFobModuleStorage][zonepropertyfobmodulestorage] |
| similar to *Tow truck*     | `False`           | [ZonePropertyTowTruck][zonepropertytowtruck]                 |
| similar to *Essentials storage* | `True`       | [ZonePropertyFobModuleStorage][zonepropertyfobmodulestorage] |
| similar to *Expanded parking*   | `True`       | [ZonePropertyParking][zonepropertyparking]                   |
| similar to *Workshop*      | `True`            | [ZonePropertyWorkshop][zonepropertyworkshop]                 |
| similar to *Service station*    | `False`      | [ZonePropertyServiceStation][zonepropertyservicestation]     |
| similar to *Cargo drone*   | `True`            | [ZonePropertyDroneDelivery][zonepropertydronedelivery]       |
| similar to *Intelligence center*| `False`      | [`AntennaUpgradeDesc`](#classes) class             |

## Locking and Unlocking
By default, custom FOB Modules are unlocked and available from the start. 

However, by enabling the **isLockedByDefault** option in the [properties][properties] of the FOB Module, you can lock it.

Locked FOB modules may be unlocked using a special reward granted after accomplishing the particular objective. See [Rewards][rewards] for details.

However, this locking should be used only if you provide this FOB module as a [linked mod][linked_mods].


[zonepropertyfobmodulestorage]: ./../../map_modding/creating_a_map/zones/expeditions_zones/zones_of_fob_modules/fob_module_storage_zones.md
[zonepropertysupplyshop]: ./../../map_modding/creating_a_map/zones/expeditions_zones/zones_of_fob_modules/supply_shop_zones.md
[zonepropertytowtruck]: ./../../map_modding/creating_a_map/zones/expeditions_zones/zones_of_fob_modules/tow_truck_zones.md
[zonepropertyparking]: ./../../map_modding/creating_a_map/zones/expeditions_zones/zones_of_fob_modules/parking_zones.md
[zonepropertyworkshop]: ./../../map_modding/creating_a_map/zones/expeditions_zones/zones_of_fob_modules/workshop_zones.md
[zonepropertyservicestation]: ./../../map_modding/creating_a_map/zones/expeditions_zones/zones_of_fob_modules/service_station_zones.md
[zonepropertydronedelivery]: ./../../map_modding/creating_a_map/zones/expeditions_zones/zones_of_fob_modules/drone_delivery_zones.md

[deploy_zones_fob_modules]: ./../../map_modding/creating_a_map/zones/expeditions_zones/deploy_zones.md#fob-modules
[fob_module_zones]: ./../../map_modding/creating_a_map/zones/expeditions_zones/zones_of_fob_modules/zones_of_fob_modules_overview.md
[initial_pak]: ./../../map_modding/getting_started/file_paths.md#source-of-info-initialpak-archive
[rewards]: ./../../map_modding/creating_a_map/objectives/objectives_in_expeditions/rewards.md
[properties]: ./general_properties_of_fob_modules.md
[inventory_items_overview]: ./../inventory_items/custom_inventory_items_overview.md
[inventory_storage_zones]: ./../../map_modding/creating_a_map/zones/expeditions_zones/inventory_storage_zones.md
[fob_module_identifier]: ./general_properties_of_fob_modules.md
[creation_of_custom_fob_module]: ./creation_of_custom_fob_module.md
[3d_models_of_fob_modules]: ./3d_models_of_fob_modules.md

[linked_mods]: ./../../usage_and_uploading_of_mods/linking_mods.md