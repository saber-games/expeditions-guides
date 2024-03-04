# General Properties of FOB Modules

## Main Properties 
When creating a FOB module, you always begin with specifying the following main properties:

-   **name** – the *identifier* of the FOB module. The specified value should contain only Latin characters, digits, and underscores (`_`). It must not contain spaces (` `).

-   **BaseUpgradeDesc** – The [class][class] of the settings of the FOB module. Currently, two classes are avialable:

    -   `BaseUpgradeDesc` – for most modules (whose functionality depends on the zone selected for FOB Module).
    -   `AntennaUpgradeDesc` – for modules with `Antenna` ability. This class has an additional field in properties, see [below](#for-antennaupgradedesc-class).

    See [Custom FOB Modules: Overview][class] for details.


## General Properties
General properties are specified for all [FOB Modules](./custom_fob_modules_overview.md). 

They are the following:

-   **modelId** – The name of the XML class of the *medium-sized* static model of the FOB module, without the `.xml` extension. This model will be displayed after this module is built in a *medium-sized* zone. See [3D Models of FOB Modules][3d_models_of_fob_modules] and [Deploy zones][deploy_zones_fob_modules] for details. 

-   **modelYRotation** – The rotation of the *medium-sized* (**modelId**) model around its axis, in degrees.

-   **modelIdAdditional** – The name of the XML class of the *small* static model of the FOB module, without the `.xml` extension. This model will be displayed after this module is built in a *small* zone. See [3D Models of FOB Modules][3d_models_of_fob_modules] and [Deploy zones][deploy_zones_fob_modules] for details.

-   **modelAdditionalYRotation** – The rotation of the *small* (**modelIdAdditional**) model around its axis, in degrees.

-   **modelAnimated** – *(Optional)* The name the XML class of the *medium-sized* animated (`_objective`) model, without the `.xml` extension. This model will be used as the source of animation for the appearance of the module in a *medium-sized* zone. See [3D Models of FOB Modules][3d_models_of_fob_modules] and [Deploy zones][deploy_zones_fob_modules] for details.  
    See also: **animationStagesProgress** below. 

-   **modelAdditionalAnimated** – *(Optional)* The name the XML class of the *small* animated (`_objective`) model, without the `.xml` extension. This model will be used as the source of animation for the appearance of the module in a *small* zone. See [3D Models of FOB Modules][3d_models_of_fob_modules] and [Deploy zones][deploy_zones_fob_modules] for details.  
    See also: **animationAdditionalStagesProgress** below.

-   **cost** – The cost of the building of this FOB module for the player. Integer and positive value.

-   **sellPrice** – The selling price of this FOB module. Integer and positive value.

-   **isLockedByDefault** – Whether or not this FOB module is initally locked for the player, see [Custom FOB Modules: Overview][locked] for details. By default, disabled.

-   **isOnlyOneAvailableAtDeployZone** – By default, disabled. If this option is enabled, the player will be able to build only one such FOB module at the Deploy zone. If there are multiple Deploy zones, the player is able to build one instance of this module on every Deploy zone.

-   **isInteractive** – Whether or not this FOB module allows the player to directly interact with it, see [Custom FOB Modules: Overview][isinteractive] for details.

-   **uiName** – The name of the FOB module in the UI. If localization is necessary, you can use UI_IDENTIFIERS for localization strings within this text field. See [Localization][localization] for details. The name of the FOB module should not exceed `20` characters, including spaces.

-   **icon20** – The name of the small icon of the FOB module that is displayed in the pop-ups and rewards. Format: `PNG`, Dimensions: `20 x 20`. 

-   **icon40** – The name of the small (orange and black) icon of the FOB module that is used to identify this module during gameplay. Format: `PNG`, Dimensions: `40 x 40`.

-   **iconMap40** – The name of the small (grey) icon of the FOB module that is displayed on the map. Format: `PNG`, Dimensions: `40 x 40`.

-   **iconTrade** – The name of the icon of the FOB module that is used in the Trade screen (at the left side of it, before the header). Format: `PNG`, Dimensions: `48 x 48`.

-   **tradeArrowsSpecialIcon** – The name of the small icon that is displayed between the "to module" and "from module" arrows when the player is performing "Trade" wtih the module. For example, in the case *Workshop*, it is the small icon of *Repair parts* (`repairPartsImg30`). Format: `PNG`, Dimensions: `30 x 30`.

-   **iconModuleBg** – The name of the large icon that is displayed in the dialog of the FOB module when it is used not for "Trade" or similar activities, but only shows information on the module. This icon is used only for "passive" modules that are similar to *Intelligence center*, *Service station* , *Expanded parking*, and *Tow truck*. For all other modules it is not used.

    **NOTE**: Currently, custom icons (**icon20**, **icon40**, **iconMap40**, **iconTrade**, etc.) of the FOB modules are not supported. However, you *can* use custom images for pictures of FOB modules in the **bg**, **bgSmall**, and **bgRight** fields, see below.

-   **bageIcon** – *(Should not be used. Will be removed.)* This field corresponds to the deprecated image of the FOB module. It should not be used and will be removed (`TBD`).  

-   **bg** – The name of the image of the module that is displayed in the list of modules available for building. Format: `PNG`, Dimensions: `380 x 92`. Typically, this image has the transparent background and the image of this particular module at the left side of it. Location of the image: This image should be put to the [folder of this FOB module][folder_of_fob_module] within `Documents\My Games\Expeditions\Media\Mods\`, into the `ui\textures` subfolder there. 

-   **bgSmall** – The name of the small image that will be displayed in the upper list of modules. Format: `PNG`, Dimensions: `124 x 52`. Typically, this image has the transparent background and the image of this particular module at the center of it. Location of the image: This image should be put to the [folder of this FOB module][folder_of_fob_module] within `Documents\My Games\Expeditions\Media\Mods\`, into the `ui\textures` subfolder there. 

-   **bgRight** – The name of the image of the module displayed at the header of the Trade screen and at the header of the Details screen (when this module is selected in the list of modules available for building). Format: `PNG`, Dimensions: `760 x 90`. Typically, this image has the transparent background and the image of this particular module at the right side of it. Location of the image: This image should be put to the [folder of this FOB module][folder_of_fob_module] within `Documents\My Games\Expeditions\Media\Mods\`, into the `ui\textures` subfolder there. 

-   **uiDesc** – The description of the FOB module in the UI. If localization is necessary, you can use UI_IDENTIFIERS for localization strings within this text field. See [Localization][localization] for details. The description of the FOB module should not exceed `240` characters, including spaces.

-   **uiDescTradeHeader** – The text that will be displayed at the header of the Trade screen, at the left side of it, below the name of the module.

-   **uiDescTradeHeaderIcon** – The small icon that is displayed next to the text of **uiDescTradeHeader**, at the right side of it.

-   **uiTradeDefaultDescText** – The text that is displayed at the bottom of the Details screen (when this module is selected in the list of modules available for building).

-   **availableViaDroneDelivery** – Whether or not the player will be able to "Trade" with this FOB module using the *Cargo drone* mechanics.

-   **dbg_locked** – *(Optional. Will be removed.)* Enabling this option will hide this FOB module in the list of modules available for building. This field will be removed (`TBD`).

-   **modelOffset** – The offset of the *medium-sized* static model of the FOB module from the center of its *medium-sized* zone, as a vector.

-   **modelAdditionalOffset** – The offset of the *small* static model of the FOB module from the center of its *small* zone, as a vector.

-   **animationStagesProgress** – *(Optional)* The section that defines the animation states of the *medium-sized* animated model of the FOB module and their order. See [3D Models of FOB Modules][3d_models_of_fob_modules] for details.

    **NOTE**: The animation states in the **animationStagesProgress** section need to be filled only if you have specified the animated model in the **modelAnimated** field.

-   **animationAdditionalStagesProgress** – *(Optional)* The section that defines the animation states of the *small* animated model of the FOB module and their order. See [3D Models of FOB Modules][3d_models_of_fob_modules] for details.

    **NOTE**: The animation states in the **animationAdditionalStagesProgress** section need to be filled only if you have specified the animated model in the **modelAdditionalAnimated** field.    

-   **zoneProperty** – The zone of the FOB module that will provide its functionality. For details on particular zone types that are possible in this field, see the [Zones of FOB Modules: Overview][fob_module_zones] topic in **Map Modding** and topics related to particular zone types in the same section. 
    
    **NOTE**: For modules of `AntennaUpgradeDesc` [class][class] the **zoneProperty** field may be left with `null` values.


## Additonal Fields

### For AntennaUpgradeDesc Class
If you have selected the `AntennaUpgradeDesc` [class][class] in the **BaseUpgradeDesc** field, your module will have the `Antenna` ability. 

This ability requires no interaction from the player and opens all [*Air Drops*][inventory_storage_zones] that are located within the specified radius from the module.

In this case, the properties of your module will have an additional field:

-   **radiusDiscoverInventoryStorageZone** – The radius from the module within which all [*Air Drops*][inventory_storage_zones] will be opened for the player.



[class]: ./custom_fob_modules_overview.md#classes
[locked]: ./custom_fob_modules_overview.md#locking-and-unlocking
[isinteractive]: ./custom_fob_modules_overview.md#interaction-with-player
[rewards]: ./../../map_modding/creating_a_map/objectives/objectives_in_expeditions/rewards.md
[localization]: ./../../map_modding/additional_info_on_maps/localization/localization.md
[folder_of_fob_module]: ./creation_of_custom_fob_module.md#source-files
[inventory_storage_zones]: ./../../map_modding/creating_a_map/zones/expeditions_zones/inventory_storage_zones.md
[3d_models_of_fob_modules]: ./3d_models_of_fob_modules.md
[deploy_zones_fob_modules]: ./../../map_modding/creating_a_map/zones/expeditions_zones/deploy_zones.md#fob-modules
[fob_module_zones]: ./../../map_modding/creating_a_map/zones/expeditions_zones/zones_of_fob_modules/zones_of_fob_modules_overview.md
[folder_of_fob_module]: ./creation_of_custom_fob_module.md#source-files