# Gateway zones

**WARNING**: In *Expeditions*, custom Regions with multiple interconnected maps are currently not supported. However, they will be for sure supported later, in the next versions of the game. Currently, only mods of standalone maps are supported in *Expeditions*. (`TBD`)

*(NEW) This feature is valid for Expeditions only.*  
*For SnowRunner, see [Settings of the Gateway zone](./../../regions/settings_of_gateway_zone.md).*

## Main Function: Gateways between Maps
Zones with *ZonePropertyGateway* prop allow you to create portals that transfer the player from one map to another map. The main principle here is simple: you create a Gateway zone on the first map and link it to the zone on the second map in the properties of the Gateway zone.

**NOTE**: Both maps of the gateway must be within the same [*Region*](./../../regions/regions_with_multiple_maps.md).

The main field in the *ZonePropertyGateway* prop is **levelZoneLink** that links a gateway to a target zone the player will be transfered to. For a gateway, you need to create at least two zones: one on one map and another one on the different map of the same region. Both zones need to have *ZonePropertyGateway* props linking to each other in the **levelZoneLink** field.

**WARNING**: If one of the two gateway zones does not have a *ZonePropertyGateway* prop, there will be a crash during the transfer of the truck through this gateway. For [locked](#locked-and-unlocked-gateways) gateways, this *ZonePropertyGateway* prop can be added as reward. I.e., this prop should be either added straight away to the zone properties, or (planned to be) added later – as reward for one of the objectives. 

However, that's not all to make the gateway working. Along with these zones and correct **levelZoneLink** values, you also need to provide images for a gateway popup, non-zero values of **cameraDir**, and, if necessary, other settings.


## Images for Gateway Pop-up
In Expeditions, when the player activates the gateway, they see the special pop-up that provides some details on the destination map this gateway leads to. 

Particularly, this pop-up displays:

-   The description of the target map – It is specified in the **uiDesc** field of the level properties (in `level_<name_of_level>.sso` TBD).
-   The name of the parent Region of the target map.
-   The image of the target map – The particular image here depends on the state of the Gateway:
    -   *If the gateway is active,* the image is taken from: level properties (`TBD`) > **uiImages** > **Size_800x520**. 
    -   *If the gateway is [locked](#locked-and-unlocked-gateways),* system uses another image: level properties (`TBD`) > **uiImages** > **Size_800x520_Gray**. 

**NOTE**: Currently, both **Size_800x520** and **Size_800x520_Gray** images must be specified for the correct work of the gateway. `(TBD)`.


## Main Rules for Gateway zones
The zone locator of a target gateway zone:

-   should not have models of any kind inside it.

-   should not contain any plants with enabled collisions.

Dimensions of this zone locator in the Editor (its **Length...** and **Width**) are made typically larger than the size of regular zone locators.


## Extra Zones 
*SnowRunner* was about long trucks and trailers, that's why gateways there typically required extra zones: **Extra Zone Nearby** and **Extra Zone 40x9**. The main function of these zones was to have large zone locators to provide necessary space for large trucks and trailers during gateway transition. If these zones were created and set up, they would be used *only if the transferred truck does not fit the main gateway zone*.

*Expeditions* works with much smaller trucks, so these zones are more or less optional. But, if necessary, you can configure them, or just one of them – **Extra Zone Nearby** – and make its zone locator larger than the zone locator of the gateway itself to fit large trucks. 

However, please note that, as opposed to the zone selected in the **levelZoneLink**, these extra zones should be located on the *same map as the gateway entrance*, since they will be used when the player *returns* to this gateway (during the backward transition). 

For example, if you are configuring the *ZonePropertyGateway* prop for the `gateway_on_map_01` zone, which is located at `level_my_map_01` and leads to the `gateway_on_map_02` zone of `level_my_map_02`, your configuration of `gateway_on_map_01` zone will be the following:

-   **levelZoneLink** – `level_my_map_02 || gateway_on_map_02`
-   **Extra Zone Nearby** – `level_my_map_01 || gateway_on_map_01_larger_zone`

Where the `gateway_on_map_01_larger_zone` extra zone is located at `level_my_map_01`, as the `gateway_on_map_01` zone itself.

**NOTE**: Extra zones do not require any props in their properties.

For details, see [Gateway Rules. Extra zone](./../../regions/gateway_rules_extra_zone.md).


## Locked and Unlocked Gateways
Locking and unlocking gateways is performed automatically, based on rewards configured for level objectives.

Particularly, if you want to create a gateway that will be unlocked and ready-to-use when the player finds it, you simply configure all required zones with *ZonePropertyGateway* props right away.

However, you can also configure a locked gateway that will become opened for the player after the accomplishment of the particular objective. To do this, add the *ZonePropertyGateway* prop with the same properties to the gateway zone using the **ObjectiveRewardOpenZoneProperties** reward type for the necessary objective.

In this case, the system will detect that the *ZonePropertyGateway* prop will be added to this zone as the reward and will initially display the gateway as locked to the player. 


## "Same Map" Gateways
If really necessary, you can configure a gateway that leads not to a different map, but to the same map.

The setup of gateway properties will not change, you will just create both gateway zones on the same map.

However, in this case, the pop-up of the gateway will be showing the information about the *current* map, which will not look very good.


## Gateways and Objectives
If an object (e.g. a zone) mentioned in the configuration of an Objective is located *not* on the current map, the game will automatically move the focus to *the gateway to the map that contains this object* when the player selects this object in the map mode.

**NOTE**: In the current version of the game, all objects mentioned in an Objective must be located within one map. However, the player will be able to proceed to this map through the gateway, if necessary.


## ZonePropertyGateway Prop Settings
Settings of the *ZonePropertyGateway* prop are the following:

-   **Duration of transition** – The duration of the gateway animation sequence, in milliseconds.

-   **Delay at start** – The delay before the playback of the gateway animation, in milliseconds.

-   **Delay at end** – The delay after the playback of the gateway animation, in milliseconds.

-   **levelZoneLink** – The target zone on another map to which the player will be transferred.

-   **Extra Zone Nearby** – *(Optional)* See [Extra Zones](#extra-zones) above.

-   **Extra Zone 40x9** – *(Optional)* See [Extra Zones](#extra-zones) above.

-   **zoneDiscoverability** – Settings related to the zone discovery. See [Discoverability of Zones](./discoverability_of_zones.md). 

-   **cameraPos** – The position of the camera at the start of the gateway animation. From this position the camera will fly to the starting point of the truck on the gateway zone.

-   **cameraDir** – The direction vector for the camera at the start of the gateway animation. You should specify the direction vector here. For example: `(1, 0, 0)`. See [Tip on cameraPos and cameraDir values](./../../../additional_info_on_maps/camera_values/tip_on_camera_pos_and_camera_dir_values.md) for a hint on specifying this value.

    **WARNING**: If you leave the **cameraDir** field with `0` values, the gateway will not work (the player will see the black screen).




