# Tire Inflation System
*(NEW) This feature is valid for Expeditions only.*

Tire Inflation System is a completely new feature of Expeditions that allows the player to modify the tire pressure of the wheel, enhancing its off-road capabilities at the cost of the increased damage to wheels and high fuel consumption.

This feature is configured in the XML file of the wheels, for tires (`<TruckTire>`), using the [`<TiresInflationSystemSettings>`](./../tags_and_attributes_of_trucks/truckwheels/trucktires/trucktire/tiresinflationsystemsettings/index.md) tag that stores descriptions of parameters for different *decreased pressure* modes ([`<Low>`](./../tags_and_attributes_of_trucks/truckwheels/trucktires/trucktire/tiresinflationsystemsettings/low_reduced/index.md) and [`<Reduced>`](./../tags_and_attributes_of_trucks/truckwheels/trucktires/trucktire/tiresinflationsystemsettings/low_reduced/index.md)). Every such mode can also have a [`<TickDamageParams>`](./../tags_and_attributes_of_trucks/truckwheels/trucktires/trucktire/tiresinflationsystemsettings/low_reduced/tickdamageparams/index.md) child tag that describes wheel damage model used for this mode.

**NOTE**: The *normal pressure* mode corresponds to default settings of the wheels and is *not* set up within Tire Inflation System. 

See descriptions of these tags in the **[Tags and Attributes of Trucks](./../tags_and_attributes_of_trucks/index.md)** section for more details.

**NOTE**: You can only use a Tire Inflation System when wheels of your truck are created according to the "wheel as a set of tires and rims" concept. It does not work with the "wheel as a single entity" wheels.

