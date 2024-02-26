# WheelFriction

The `<WheelFriction>` tag within `<TruckWheel>` describes parameters of the friction of the wheel when it is a single entity.

**NOTE 1**: If you a creating a wheel as a set of tires and rims, this tag should be used for *tires* (within `<TruckTire>`) and will contain additional attributes. See [WheelFriction](./../../truckwheels/trucktires/trucktire/wheelfriction/index.md) for details.

**NOTE 2**: The *meaning* of some attributes of this tag has changed in Expeditions, see [Wheel Friction Changes](./../../../new_features/wheel_friction_changes.md) for details.

Attributes:

-   `BodyFriction="1.3"`  
    *In SnowRunner:*  
    (Mandatory.) Friction with the ground, clean terrain without mud, and other collision objects. Default value: `1`, Value range: `[0.1; 10]`.  
    *In Expeditions (NEW):*  
    *(Mandatory.)* Friction with *map* models that have the `FrictionPreset` attribute of the `<Body>` tag configured in their XML class of the model. Typically, this preset is configured for models of rocks, stones, and other similar objects. Default value: `1`, Value range: `[0.1; 10]`.

-   `BodyFrictionAsphalt="1.5"`  
    *In SnowRunner:*  
    Friction with the road. Default value: `BodyFriction`, Value range: `[0.1; 10]`.  
    *In Expeditions (NEW):*  
    Friction of tires with the ground, clean terrain without mud, and other collision objects. Default value: `1`. Value range: `[0.1; 10]`.

-   `SubstanceFriction="1.2"`  
    *(Mandatory.)* Friction with mud.  
    Default value: `1`. Value range: `[0;10]`.

-   `IsIgnoreIce="true"`  
    Whether or not the ice surfaces should be ignored. For example, this parameter is used for tires with chains.

