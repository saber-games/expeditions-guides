# Deploy zones

*(NEW) This feature is valid for Expeditions only.*


## Main Function: Deployment of Trucks
The *ZonePropertyDeploy* prop is used for the creation of Deploy zones.

Every map created for *Expeditions* requires at least one Deploy zone, since this zone is the point where the player starts on the map.

There can be multiple such zones on the map – e.g., the primary one and the secondary ones. Moreover, if you want to use one map for multiple Expeditions, you can make some of them intially unexplored in [**zoneDiscoverability**](./discoverability_of_zones.md) settings and allow the player to open them gradually. Or, open them as rewards for objectives using the **ObjectiveRewardOpenZoneProperties** reward type. The secondary deploy zones are typically called *Outposts*.

If there are multiple Deploy zones on the map, the player is able to select several of them for the deployment of trucks.

**NOTE**: The deployment zones should be located a little bit above the underlying terrain to avoid collisions of deployed trucks with ground.


## Base module and Store
If necessary, you can allow the player to use the *Base module* and *Store* FOB modules at the Deploy zone.

To allow the player to use the *Base module* you will need to:

1.  Add the [*ZonePropertyInventoryStorage*](./inventory_storage_zones.md) prop to the Deploy zone props list and configure it.

2.  Within this *ZonePropertyInventoryStorage* prop of the Deploy zone:

    -   You need to enable the **isAtDeployZone** option – to provide the correct "saving items between expeditions" behavior of the *Base module* and display its correct header in the Trade screen.
    -   You need to enable the **alwaysSpawn** option – for it to be spawned always.
    -   You are able to configure all contents of the *Base module* that will be available to the player, the same way as you do for the regular [*ZonePropertyInventoryStorage*](./inventory_storage_zones.md) zone.

3.  Back in the properties of the *ZonePropertyDeploy* prop of the Deploy zone, in the **mainBaseModuleInteractionZone** field of it, you need select the *deploy zone itself*. The interaction zone for *Base module* will be always the Deploy zone itself. 

To allow the player to use the *Store* at the Deploy zone, you need to specify the link to the Deploy zone itself in the **supplyShopModuleInteractionZone** field of *ZonePropertyDeploy* prop of the Deploy zone.


## FOB Modules
If you want to allow the player to build FOB modules within your base, you will need to create separate zones for them.

**NOTE**: You can add only *potential* FOB modules to the map. I.e., you can only set up zones where these FOB modules *may* be built by the player. You are not able to add an already built and operational FOB module of the particular type to the map. 

Particularly, for every potential FOB module, you will need to create two zones:

-   *Placement Zone* – the zone where the visual model of this FOB module will be built when the player decides to build it.

-   *Interaction Zone* – the zone where the player will be able to interact with this FOB module.

The *Placement Zone* that you will create does not require any properties – i.e., it can have empty **props**.

On the contrary, after its creation, the *Interaction Zone* needs to be linked to the *Placement Zone* in its properties. Particularly, you will need to assign the [*ZonePropertyBaseBuilding*](./base_building_zones.md) prop to the *Interaction Zone* and, in its **modelPlacementZone** field, specify the link to the *Placement Zone*.

In the properties of Deploy zone, for every potential FOB Module, you will need to add a corresponding record to the **fobModulesZones** list and, in the properties of this record, specify links to the *Placement Zone* and *Interaction Zone* of this FOB module, within the **modulePlacementZone** and **moduleInteractionZone** fields.

The Main Base usually has more space for "building" FOB modules than secondary Outposts. Due to this, FOB modules have two visual models corresponding to them: the medium-sized model and the small model. 

The former one is "built" when the **defaultDeployPoint** option (see below) is enabled in the prop of the Deploy zone. The latter one appears when this option is disabled. 

Typical dimensions of the regular *Placement Zone* for FOB modules do vary also:

-   For *Main Base*, they are `10 х 10` meters.
-   For *secondary Outposts*, they are `7 х 7` meters.


## Recovery
The Recovery feature of the base is *not* provided by default.

If you want to add it, you need to add the [*ZonePropertyRecovery*](./recovery_zones.md) prop to the Deploy zone and configure it.

I.e., in this case, the Deploy zone will have both *ZonePropertyDeploy* and *ZonePropertyRecovery* props. Or, if you have [Base module](#base-module-and-store) configured, even three props: *ZonePropertyDeploy*, [*ZonePropertyInventoryStorage*](./inventory_storage_zones.md), and *ZonePropertyRecovery*.


## ZonePropertyDeploy Prop Settings
Settings of the *ZonePropertyDeploy* prop are the following:

-   **Deploy cost multiplier** – *(this feature is currently not used)* the multiplier for the cost of the truck deployment to this Deploy zone.

-   **defaultDeployPoint** – whether or not this zone is selected by default when the player selects the deployment zones for trucks in the beginning of the Expedition. If FOB modules are configured for this deploy point, the state of this option also defines what model – the medium-sized one or the small one – will be "built" in the *Placement Zone* of this FOB module, see [above](#fob-modules).

-   **maxTrucksNum** – the maximum number of trucks that can be simultaneously deployed to this Deploy zone.

-   **fogOfWarUnlockRadius** – the radius of the *fully* explored area around the zone after the deployment to it.

-   **fogOfWarUnlockRadiusTransparent** – the radius of the *partially* explored area around the zone after the deployment to it.

-   **warningRadius** – the radius from the deploy zone after exceeding of which the warning about insufficient equipment is shown (if it is required by the Expedition settings).

-   **zoneDiscoverability** – settings related to the zone discovery. See [Discoverability of Zones](./discoverability_of_zones.md). 

-   **model** – *(Optional)* the model that will change its visual state depending on whether or not this zone is spawned. For example, if you open this Deploy zone as a reward, via **ObjectiveRewardOpenZoneProperties**, the specified model will be "built" when the player recieves this reward and the zone is spawned. See [Model Building Settings](./../../objectives/model_building_settings/model_building_settings.md) for details.

-   **mainBaseModuleInteractionZone** – *(Optional)* if you want to allow the player to use the *Base Module* on this Deploy zone, you need to specify here the link to the Deploy zone itself. And, you need to add the [*ZonePropertyInventoryStorage*](./inventory_storage_zones.md) prop to the Deploy zone props list and configure it. See [Base module and Store](#base-module-and-store) above.

-   **supplyShopModulelnteractionZone** – *(Optional)* if you want to allow the player to use the *Store* on this Deploy zone, you need to specify here the link to the Deploy zone itself. See [Base module and Store](#base-module-and-store) above.

-   **fobModulesZones** – *(Optional)* the list of the potential FOB modules that can be built by the player.

    -   *\[number of FOB Module\]* – a record of a potential FOB module.

        -   **modulePlacementZone** – the link to the *Placement Zone* of this module where the visual model of the module will appear after building. This zone itself does not require any properties – i.e., it can have empty **props**. See [FOB Modules](#fob-modules) above.

        -   **modulelnteractionZone** – the link to the *Interaction Zone* of this module zone where the player will be able to interact with it. This zone requires the [*ZonePropertyBaseBuilding*](./base_building_zones.md) prop to be assigned and, in the **modelPlacementZone** field of this prop, should link to the *Placement Zone* of this module. See [FOB Modules](#fob-modules) above.
