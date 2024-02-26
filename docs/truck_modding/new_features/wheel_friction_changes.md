# Wheel Friction Changes
*(NEW) Changes described in this topic are valid for Expeditions only.*

The *meaning* of some attributes of [`<WheelFriction>`](./../tags_and_attributes_of_trucks/truckwheels/trucktires/trucktire/wheelfriction/index.md) tag has changed in Expeditions. However, their *names* have not changed, so you need to be accurate with ther usage.  

The following table will help you to avoid mishmash:

| Attribute          | Meaning in SnowRunner      | Meaning in Expeditions       |
|----------------------|----------------------------|-----------------------------------------|
|`BodyFriction`        | Friction with the ground, clean terrain without mud, and other collision objects. | Friction with *map* models that have the `FrictionPreset` attribute of the `<Body>` tag configured in their XML class of the model: rocks, stones, and so on. | 
|`BodyFrictionAsphalt` | Friction with the road.    | Friction of tires with the ground, clean terrain without mud, and other collision objects. |
|`SubstanceFriction`   | Friction with mud. | Friction with mud. |

As you can see, mud is always mud, other things are changing. See [`<WheelFriction>`](./../tags_and_attributes_of_trucks/truckwheels/trucktires/trucktire/wheelfriction/index.md) tag for details.

Another change is that you can now change these parameters in the particular pressure mode of the [Tire Inflation System](./tire_inflation_system.md).






