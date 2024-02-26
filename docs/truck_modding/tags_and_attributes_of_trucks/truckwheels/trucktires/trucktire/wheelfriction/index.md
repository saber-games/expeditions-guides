# WheelFriction

The `<WheelFriction>` tag within `<TruckTire>` desribes the friction parameters of this tire.

**NOTE**: The *meaning* of some attributes of this tag has changed in Expeditions, see [Wheel Friction Changes](./../../../../../new_features/wheel_friction_changes.md) for details.

Attributes:

-   `BodyFriction="1.3"`  
    *In SnowRunner:*  
    (Mandatory.) Friction with the ground, clean terrain without mud, and other collision objects. Default value: `1`, Value range: `[0.1; 10]`.  
    *In Expeditions (NEW):*  
    *(Mandatory.)* Friction with *map* models that have the `FrictionPreset` attribute of the `<Body>` tag configured in their XML class of the model. Typically, this preset is configured for models of rocks, stones, and other similar objects. Default value: `1`, Value range: `[0.1; 10]`.

    **NOTE**: In Expeditions, the value of this coefficient can be changed by the `OnModelFriction` attribute in the [decreased pessure modes](./../tiresinflationsystemsettings/low_reduced/index.md) of the [`<TiresInflationSystem>`](./../tiresinflationsystemsettings/index.md).

-   `BodyFrictionAsphalt="1.5"`  
    *In SnowRunner:*  
    Friction with the road. Default value: `BodyFriction`, Value range: `[0.1; 10]`.  
    *In Expeditions (NEW):*  
    Friction of tires with the ground, clean terrain without mud, and other collision objects. Default value: `1`. Value range: `[0.1; 10]`.

    **NOTE**: In Expeditions, the value of this coefficient can be changed by the `BodyFrictionAsphalt` attribute in the [decreased pessure modes](./../tiresinflationsystemsettings/low_reduced/index.md) of the [`<TiresInflationSystem>`](./../tiresinflationsystemsettings/index.md).

-   `SubstanceFriction="1.2"`  
    *(Mandatory.)* Friction with mud.  
    Default value: `1`. Value range: `[0; 10]`.

    **NOTE**: In Expeditions, the value of this coefficient can be changed by the `SubstanceFriction` attribute in the [decreased pessure modes](./../tiresinflationsystemsettings/low_reduced/index.md) of the [`<TiresInflationSystem>`](./../tiresinflationsystemsettings/index.md).

-   `IsIgnoreIce="true"`  
    Whether or not the ice surfaces should be ignored. For example, this parameter is used for tires with chains. 

-   `UiName="UI_TIRE_TYPE_OFFROAD_NAME"`  
    Name of the ***type*** of tires in the UI. This field links this tire to one of the tire categories in the UI (in the Garage). The value of this field cannot be custom. It **must** be one of the following predefined values:

    -   `UI_TIRE_TYPE_HIGHWAY_NAME` – highway tires

    -   `UI_TIRE_TYPE_ALLTERRAIN_NAME` – all-terrain tires

    -   `UI_TIRE_TYPE_OFFROAD_NAME` – off-road tires

    -   `UI_TIRE_TYPE_CHAINS_NAME` – chained tires

    -   `UI_TIRE_TYPE_MUDTIRES_NAME` – mud tires

