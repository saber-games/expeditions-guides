# Ability-Specific Properties of Inventory Items

Ability-specific properties appear only for those inventory items that use the particular ability.

**NOTE 1**: The list of possible abilities is predefined and fixed, since all of them correspond to the particular game logic.

**NOTE 2**: To create such an item, along with the selection of the correct **type** and **Requested Ability type**, you need also to create instance of the correct *class* when creating an Item with Ability. See [Creation of Custom Inventory Item](./creation_of_custom_inventory_item.md) for details.

The fields related to all possible abilities can be found below.

**WARNING**: The creation of custom *Drone*, *Echo Sounder*, and *Binoculars* items is currently not supported. Please do not create the mods of these items since currently they lead to errors. This issue is known and these items will be supported for sure in the future releases of the game.(`TBD`) 


## Drone

**WARNING**: The creation of custom *Drone*, *Echo Sounder*, and *Binoculars* items is currently not supported. Please do not create the mods of these items since currently they lead to errors. This issue is known and these items will be supported for sure in the future releases of the game. 

-   **previewDroneModel** – The name of the XML class of the model that will be used by the Drone. To use the existing original in-game model of the Drone, you can specify `drone_us07` in this field. If you want to use custom model of an Drone, it should be put (as the FBX file) in the `\meshes\models` subfolder of the folder of the mod, along with the corresponding XML file of the mesh. The XML file of the class of this model should be put in the `\classes\models` subfolder of the folder of the mod, similarly to [how it is done for FOB modules][models_of_fob_modules].  
   
    **NOTE**: The XML classes of models for a custom *Drone*, *FOB Module* or *Anchor* should contain the special `NeedPreload` attribute in the `<ModelBrand>` tag and this attribute should be equal to `true`. This is necessary for the system to be able to preload these models before starting the level.

-   **maxDistance** – The maximum *horizontal* distance from the truck, in meters. This distance does *not* take into account the drone's height.
-   **maxHeight** – The maximum height of the drone, in meters. 
-   **maxSpeed** – The maximum speed of the drone, in meters per second.
-   **heightLimitEnterZone** – In Expeditions, you are able to "visit" zones using the drone. The **heightLimitEnterZone** parameter is the maximum height of the drone above a zone that is required for this zone to be considered "vizited" by the drone. E.g., if **heightLimitEnterZone** is 2 meters, then the drone should fly in 2 meters (or lower) above the zone to "visit" it.   
-   **minAngleCamera** – The minimum angle of the dron's inclination, in degrees 
-   **maxAngleCamera** – The maximum angle of the dron's inclination, in degrees
-   **mass** – The mass of the drone, in kilograms. This parameter affects the speed and manoeuvrability of the drone.
-   **acceleration** – The coefficient of the *horizontal* acceleration of the drone. If this parameter is increased, the drone gains speed faster and moves faster.
-   **coefResistanceForce** – The coefficient of *horizontal* resistance that is applied to the drone and pulls it to the side that is opposite to the direction of its horizontal movement. If this parameter is increased, the drone loses speed faster and its maximum speed decreases.
-   **accelerationHeight** – The coefficient of the *vertical* acceleration of the drone. If this parameter is increased, the drone gains height faster.
-   **coefResistanceForceHeight** – The coefficient of *vertical* resistance that is applied to the drone and pulls it to the side that is opposite to the direction of its vertical movement. If this parameter is increased, the drone loses *vertical* speed faster.
-   **forceRotation** – The coefficient of the *angular* horizontal acceleration of the drone. If this parameter is increased, the drone gains *angular* horizontal speed faster and rotates faster.
-   **coefResistanceForceRotation** – The coefficient of *angular* horizontal resistance that is applied to the drone and pulls it to the side that is opposite to the direction of its rotation. If this parameter is increased, the drone loses *angular* horizontal speed faster.
-   **startHeightAboveTruck** – The height of the drone above the truck when it starts.
-   **distanceThirdPersonCamera** – *(Does not work and should not be used now)* The distance between the camera and the model of the drone if the third person view is enabled (see **isThirdPerson** below).  
-   **angleSpeed** – The speed of the inclination of the drone. 
-   **angleCameraSpeed** – The coefficient for the speed of camera movement when it follows the cursor. Possible values: from `0` to `1`.
-   **coeffForceTorque** – The torque coefficient that affects skidding of the drone. Can be overriden by the **droneTorqueCoefOverride** in the **MinigameProcessPoints** settings of the particular Drone minigame.
-   **isThirdPerson** – *(Does not work and should not be used now)* If this option is enabled, the camera of the drone is switched from first person view to third person view. By default, this option is disabled. 
-   **isTruckMode** – *(Should not be used during manual configuration of the Drone, will be removed)* Internal field that is used during Drone mini-games, should not be used.
-   **isNeedNoiseByDistance** – *(Does not work and should not be used now)* This option used to enable the noise effect at the certain distance from the truck (see **startNoiseEffect** below). However, in the current version of the game, the noise effect appears only when the drone is flying towards the edge of the map, see **noFlyZone** and **distanceStartNoiseEffectNearNoFlyZone** below.   
-   **startNoiseEffect** – *(Does not work and should not be used now)* This option used to specify the percentage of the maximum horizontal distance from the truck (see **maxDistance** above) at which the noise effect would appear. However, in the current version of the game, the noise effect appears only when the drone is flying towards the edge of the map, see **noFlyZone** and **distanceStartNoiseEffectNearNoFlyZone** below.
-   **distanceStartNoiseEffectNearNoFlyZone** – Specifies the distance from the edge of the no flight zone at which the noise effect will appear. The value is specified in meters. 
-   **noFlyZone** – The distance from the edge of the map that will set the no flight zone near the edges of the map. The value is specified in meters. 
-   **unlockFogOfWarRadius** – The radius of the full uncovering of the fog of war, in meters.
-   **unlockFogOfWarGrayRadius** – The radius of the partial uncovering of the fog of war ("gray" fog of war on the map), in meters.
-   ***Required zone discovery settings: UnlockSettings***:
    -   **Partial unlock radius (?)** – The radius of partial exploration. Partial exploration locates new POI, but does not identify them (shows them as "question" marks). 
    -   **Full unlock radius** – The radius of full exploration. New POI are fully identified.

## Binocular

**WARNING**: The creation of custom *Drone*, *Echo Sounder*, and *Binoculars* items is currently not supported. Please do not create the mods of these items since currently they lead to errors. This issue is known and these items will be supported for sure in the future releases of the game. 

-   **unlockFogOfWarRadius** – The radius of the full uncovering of the fog of war, in meters.
-   **unlockFogOfWarGrayRadius** – The radius of the partial uncovering of the fog of war ("gray" fog of war on the map), in meters.
-   **coeffSensitiveMouse** – The coefficient of mouse sensitivity when controlling the binoculars with the mouse.
-   **coeffSensitiveKeyboard** – The coefficient of the rotation speed when controlling the binoculars with the keyboard.
-   **coeffSensitiveGamepad** – The coefficient of the rotation speed when controlling the binoculars with the gamepad.
-   **coeffHoverFrictionMax** – The coefficient that affects "friction" of camera movement when the binoculars point at some POI.
-   ***Required zone discovery settings***:
    -   **Partial unlock radius (?)** – The radius of partial exploration. Partial exploration locates new POI, but does not identify them (shows them as "question" marks). 
    -   **Full unlock radius** – The radius of full exploration. New POI are fully identified.
-   **coeffSensitivePower** – The spline that set the dependence of the accelaration of the binocular from the player's control input, typically to ease the camera movement and allow more precise movements of the binocular.

## Anchor

-   **setupRadius** – The radius of the setup of the anchor, in meters. 

-   ***Required controller desc:*** – Settings of the controller of an anchor. You need to select the *AnchorSetupControllerDesc* here, it is required.

    -   **anchorBrand** – The name of the *XML class* of the model that will be used by the anchor. To use the existing original in-game model of the Anchor, you can specify `test_anchor` in this field. If you want to use custom model of an Anchor, it should be put (as the FBX file) in the `\meshes\models` subfolder of the folder of the mod, along with the corresponding XML file of the mesh. The XML file of the class of this model should be put in the `\classes\models` subfolder of the folder of the mod, similarly to [how it is done for FOB modules][models_of_fob_modules]. However, don't forget about the `NeedPreload` and `<WinchSocket>` in the XML class of your model (see notes below).  

        **NOTE 1**: The XML classes of models for a custom *Drone*, *FOB Module* or *Anchor* should contain the special `NeedPreload` attribute in the `<ModelBrand>` tag and this attribute should be equal to `true`. This is necessary for the system to be able to preload these models before starting the level.

        **NOTE 2**: You should specify the location of the winch attachment point on the model of the anchor in its XML class file. Particularly, in this file, this should be done using the `Pos` attribute of the `<WinchSocket>` tag within `<GameData>`. For example:

        ```xml
        <ModelBrand
            ...
            NeedPreload="true"
        >
            ...
            <GameData>
                <WinchSocket Pos="(0.0; 0.1; 0.0)" Color="(1.0f; 1.0f; 0.0f; 1.0f)" />
            </GameData>
        </ModelBrand>        
        ```

    -   **previewAnchorModel** – The name of *the model* of the anchor that will be used for its preview during anchor usage (before the anchor is placed). To use the existing model from the the game, you can specify `models_test_anchor` in this field. To highlight that this is the name of *the model* and *not* the name of its XML class, it is specified with the `models_` prefix, i.e. – `models_<name_of_model>`. This field can be used if you want to use one model for the preview of the anchor and another one – for its actual placement (see **anchorBrand** above). However, the original game uses the same model for that. 

        **WARNING**: Cutom models of Anchors are currently *not* supported, but will be for sure supported in the future.

    -   **upDirOffset** – The offset upwards from the pivot of the model. Should be specified if the anchor should be placed on the ground *not* at the position of its pivot.

        **WARNING**: The incorrect value of this offset can result in the situation when the placed anchor is hanging in the air.   

    -   **scale** – The scale of the model of the Anchor.
    -   **isRemovableByWinch** – If this option is enabled, the anchor can be removed using the winch after its usage. In the original game, the *Removable Anchor* has this option enabled and the regular *Anchor* has it disabled.   
    -   ***Required controller desc:*** – Settings of the controller. You need to select the *ModelSetupPreviewControllerDesc* here, it is required. 
        -   **doPaintModel** – *(Enabled by default and this value is recommended)* This option specifies whether or not the model of the anchor should be tinted with the **Required allow setup color** or **Required forbid setup color** colors to highlight that the anchor can or can not be placed at the selected point. By default enabled and this value is recommended. The disabled state removes the tint from the model and switches it to the different behavior: in this case, the model itself will be *shown* in the "allowed" points and *hidden* in the "forbidden" points.
        -   **allowSetupUnderWater** – Whether or not the anchor can be set up by the player under the water.
        -   **allowedWaterLevel** – The maximum depth of the water for placing the anchor.
        -   **height** – The maximum height of the terrain, relative to the truck, for placing the anchor.
        -   **maxUserDefinedHeight** – the maximum height which the player is able lift the model to if changing of the height is available to them. Not used for anchors. 
        -   **rotation Speed Modifier** – *(Not used for anchors)* 
        -   **Required allow setup color** – The color of the *point* where the anchor *can be placed*. The same color is used for the tint of the anchor model displayed at this point, if **doPaintModel** is enabled.
        -   **Required forbid setup color** – The color of the *point* where the anchor *can not be placed*. The same color is used for the tint of the anchor model displayed at this point, if **doPaintModel** is enabled.
        -   ***Required set JackScrew.GamepadMove*** – *(Not customizable during modding)*.
        -   ***Required set JackScrew-SetupModel*** – *(Not customizable during modding)*.
        -   ***Input Rotation*** – *(Not customizable during modding)*.
        -   ***Input Move*** – *(Not customizable during modding)*.
        -   ***Required settup effect info:*** – Settings of the visual effect. You need to select the *SetupEffectDesc* here, it is required.
            -   **innerIntensityHelpCircle** – The color intensity for the *main* helper circle (colored with **Required color main allow circle** and **Required color main forbidden circle**).
            -   **helpCircleRadius** – TBD
            -   **countAnchorHelpCircles** – The amount of circles for the visual effect of highlighting the anchor while its placement.
            -   **Required color main allow circle** – The color of the *areas* where the placement of the anchor is recommended.
            -   **Required color main forbidden circle** – The color of the *areas* where the placement of the anchor is not recommended or prohibited.

## Jackscrew (Jack-Screw)

-   **radius** – The radius of the jackscrew usage, in meters. 
-   **uselfRolledOverOnly** – If enabled, the jackscrew can be used only if the car is rolled over. If disabled, this is not required for the jackscrew usage. By default, enabled. 
-   ***jackScrewControllerDesc:*** – Settings of the jack-screw controller. You need to select the *JackScrewControllerDesc* here, it is required. 
    -   ***modelSetupPreviewControllerDesc:*** – Settings of the controller. You need to select the *ModelSetupPreviewControllerDesc* here, it is required.
        -   **doPaintModel** – *(Enabled by default and this value is recommended)* This option specifies whether or not the model of the truck displayed during jack-screw usage should be tinted with the **Required allow setup color** or **Required forbid setup color** colors to highlight that the truck can or can not be placed at the selected point. By default enabled and this value is recommended. The disabled state removes the tint from the model of the truck and switches it to the different behavior: in this case, the model itself will be *shown* in the "allowed" points and *hidden* in the "forbidden" points.
        -   **allowSetupUnderWater** – Whether or not the truck can be placed under the water during jack-screw usage.
        -   **allowedWaterLevel** – The maximum depth of the water for placing the truck during jack-screw usage.
        -   **height** – The maximum height for placing the truck during jack-screw usage.
        -   **maxUserDefinedHeight** – the maximum height which the player is able lift the model to if changing of the height is available to them.
        -   **rotation Speed Modifier** – the multiplier for the rotation speed of the model of the truck during jack-screw usage.
        -   **Required allow setup color** – The color of the preview model of the truck in the *point* where the it *can be placed* using the jack-screw. The same color is used for the tint of the truck model displayed at this point, if **doPaintModel** is enabled.
        -   **Required forbid setup color** – The color of the preview model of the truck in the *point* where the it *cannot be placed* using the jack-screw. The same color is used for the tint of the truck model displayed at this point, if **doPaintModel** is enabled.
        -   ***Required set JackScrew.GamepadMove*** – *(Not customizable during modding)*.
        -   ***Required set JackScrew-SetupModel*** – *(Not customizable during modding)*.
        -   ***Input Rotation*** – *(Not customizable during modding)*.
        -   ***Input Move*** – *(Not customizable during modding)*.
        -   ***Required settup effect info:*** – Settings of the visual effect. You need to select the *SetupEffectDesc* here, it is required.
            -   **innerlntensityHelpCircle** – The color intensity for the *main* helper circle (colored with **Required color main allow circle** and **Required color main forbidden circle**).
            -   **helpCircleRadius** – TBD
            -   **countAnchorHelpCircles** – *(Not used for the Jack-screw).*
            -   **Required color main allow circle** – The color of the *areas* where the placement of the truck using the jack-screw is recommended. 
            -   **Required color main forbidden circle** – The color of the *areas* where the placement of the truck using the jack-screw is not recommended or prohibited.

## Echolot (Echo Sounder)

**WARNING**: The creation of custom *Drone*, *Echo Sounder*, and *Binoculars* items is currently not supported. Please do not create the mods of these items since currently they lead to errors. This issue is known and these items will be supported for sure in the future releases of the game. 

-   **radius** – The range of the echo sounder ability and the radius of the corresponding visual effect, in meters.
-   **viewAngleGrads** – The angle of the echo sounder pattern, in degrees. If you set this value to `45`, the echo sounder will work for the cone angle of 45 degrees in front of the truck only. Value of `360` degrees corresponds to the full circle around the truck.
-   **stepCount** – This parameter corresponds to the density of Echo Sounder visualization marks on the surface of water. The higher the value, the larger amount of these visual marks will appear.
-   **maxFxHeight** – The maximum depth to be visualized by the echo sounder, in meters.
-   **safeHeight** – The safe depth to be visualized by the echo sounder by green arrows, in meters.
-   **dangerousHeight** – The dangerous depth to be visualized by the echo sounder by red arrows, in meters.

    **NOTE**: The intermediate depths corresponding to yellow and orange arrows are determined automatically, using **safeHeight** as the upper limit and the **dangerousHeight** as the lower limit. 

-   **duration** – the duration of the visual effect of the echo sounder, in seconds. The echo sounder cannot be used again until the visual effect disappears. 


[models_of_fob_modules]: ./../fob_modules/3d_models_of_fob_modules.md#location-of-model-files