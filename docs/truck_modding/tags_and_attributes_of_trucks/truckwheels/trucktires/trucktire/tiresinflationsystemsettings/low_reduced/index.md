# Low and Reduced
*(NEW) These tags are valid for Expeditions only.*

The `<Low>` and `<Reduced>` child-tags of [`<TiresInflationSystemSettings>`](./../index.md) correspond to different *decreased pressure* modes that the player can select within the Tire Inflation System in the UI of the game. After selection by the player, every such mode changes characteristics of the truck and truck wheels. 

Tire Inflation System works with only **two** pressure modes: `<Low>` and `<Reduced>`. The **third** one – the normal pressure mode – corresponds to default settings of the wheels and is *not* set up within Tire Inflation System. All child tags of `<TiresInflationSystemSettings>` except `<Low>` and `<Reduced>` are ignored by the system.

**NOTE**: Along with attributes, every `<Low>` and `<Reduced>` tag can contain the [`<TickDamageParams>`](./tickdamageparams/index.md) child-tag that describes the model of the wheel damage used for the corresponding mode.

Attributes:

-   `OnModelFriction="3.0"`  
    *(Mandatory.)* The friction multiplier for friction with *map* models that have the `FrictionPreset` attribute of the `<Body>` tag configured in their XML class of the model. Typically, this preset is configured for models of rocks, stones, and other similar objects.  
    Value range: `[0.1; 10]`.

-   `BodyFrictionAsphalt="1.3"`  
    *(Mandatory.)* The multiplier for friction of tires with the ground, clean terrain without mud, and other collision objects.  
    Default value: `1`. Value range: `[0.1; 10]`.

-   `SubstanceFriction="1.3"`  
    *(Mandatory.)* The multiplier for friction of tires with mud.  
    Default value: `1`. Value range: `[0.1; 10]`.

-   `FuelConsumptionModifier="1.5"`  
    *(Mandatory.)* The multiplier for the fuel consumption. It works similarly to `DamagedConsumptionModifier` from [Engine](./../../../../../enginevariants/engine/index.md).  
    Value range: `[0.1; 10]`.

-   `SteeringSpeedModifier="0.7"`  
    *(Mandatory.)* The multiplier for the steering speed. It works as `SteerSpeed * SteeringSpeedModifier`.  
    Value range: `[0.1; 10]`.

-   `AdditionalRadiusOffset="0.1"`  
    The additional offset for the radius of the collision object of the wheel. This parameter also affects visual flattening of the tire that is caused by the low pressure. The larger is the value of this parameter, the more flattened is the tire.  
    Value range: `[0; 0.25]`.

-   `DamageMult = "1.0"`  
    The multiplier for the wheel damage that will be used when this pressure mode is selected. See also: [TickDamageParams](./tickdamageparams/index.md).
    Default value: `1`. Value range: `[0.1; 10]`.
