# Wheel Friction Changes

*(NEW) Changes described in this topic are valid for Expeditions only.*

The names of attributes of [`<WheelFriction>`](./../tags_and_attributes_of_trucks/truckwheels/trucktires/trucktire/wheelfriction/index.md) tag are the same in *Expeditions* and *SnowRunner*. 

However, the *meaning* of one of them have been changed.  

The following table will help you to avoid mishmash:

| Attribute            | Meaning in SnowRunner      | Meaning in Expeditions       |
|----------------------|----------------------------|-----------------------------------------|
|`BodyFriction`        | Friction with the ground, clean terrain without mud, and other collision objects. | Friction with the ground, clean terrain without mud, and other collision objects. |
|`BodyFrictionAsphalt` | Friction with the road.    | Friction with rocks. I.e., friction with *map* models that have the `FrictionPreset` attribute of the `<Body>` tag configured in their XML class of the model: rocks, stones, and so on. |
|`SubstanceFriction`   | Friction with mud. | Friction with mud. |

See [`<WheelFriction>`](./../tags_and_attributes_of_trucks/truckwheels/trucktires/trucktire/wheelfriction/index.md) tag for details.

Another change is that you can now change these parameters in the particular pressure mode of the [Tire Inflation System](./tire_inflation_system.md).






