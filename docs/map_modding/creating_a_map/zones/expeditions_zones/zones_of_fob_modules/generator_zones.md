# Generator zones

The *ZonePropertyGenerator* prop:

- contains a supply of electricity,
- allows converting fuel into electricity,
- generates a signal zone for drones,
- enables drones to evacuate to points where this module is installed.

This property is used in the *Generator* (GENERATOR) [FOB module zone](./zones_of_fob_modules_overview.md).

The *ZonePropertyGenerator* prop is a wrapper over the [*ZonePropertyInventoryStorage*](./../inventory_storage_zones.md) prop that allows you to configure a storage for fuel, repair parts, spare wheels and various inventory items.

The generator's **radius** (signal range) is set in the module model's XML file. See the `<GameData SignalRadius="100.0"/>` line — in this case `100.0` is the radius, in meters. Refer to the `fob_module_generator_big` file in the project for sample settings.

Settings of the `ZonePropertyGenerator` prop:

- **Exchange rate of a unit of fuel to a unit of electricity** — the number of liters of fuel required to convert into one unit of electricity.
- **How much fuel/electricity pours in one click** — the amount of fuel or electricity that is transferred per click.
- **How much fuel converts in one click** — the amount of fuel that is converted to electricity per click.
- **Fuel amount to convert in one time** — *not used; this setting will be removed soon.* 
- **Initial amount of fuel in module** — the starting amount of fuel in the module during its construction and upcoming deployments.
- **Initial amount of electricity in module** — the starting amount of electricity in the module during its construction and upcoming deployments.