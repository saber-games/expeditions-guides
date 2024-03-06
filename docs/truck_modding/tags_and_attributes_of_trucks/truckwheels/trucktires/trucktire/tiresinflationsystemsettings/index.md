# TiresInflationSystemSettings
*(NEW) This tag is valid for Expeditions only.*

The `<TiresInflationSystemSettings>` tag works as a container for the settings of the [Tire Inflation System](./../../../../../new_features/tire_inflation_system.md).

It contains descriptions of different *decreased pressure* modes as child tags: [`<Low>`](./low_reduced/index.md) and [`<Reduced>`](./low_reduced/index.md).

**NOTE**: Tire Inflation System works with only **two** pressure modes: `<Low>` and `<Reduced>`. The **third** one – the normal pressure mode – corresponds to default settings of the wheels and is *not* set up within Tire Inflation System. All child tags of `<TiresInflationSystemSettings>` except `<Low>` and `<Reduced>` are ignored by the system.


## Two Setup Scenarios
There are two scenarios for setting up `<TiresInflationSystemSettings>`:

-   They can be set up using [templates](./../../../../../general_info/xml_structure/templates/templates.md), by selection of a particular template for `<TiresInflationSystemSettings>`.
-   They can be set up explicitly, by specifying all hierarchy of child-tags within `<TiresInflationSystemSettings>`.

### Setup Using Templates
In the first scenario, you can use one of the predefined `<TiresInflationSystemSettings>` templates from `/_templates/trucks.xml` or create our own [template](./../../../../../general_info/xml_structure/templates/templates.md) for these settings in a similar way. And, then, we create a link to this template from the `<TiresInflationSystemSettings>` tag:

```xml
		<TruckTire Mass="75" Mesh="wheels/tire_scout_offroad_4" Name="offroad_1" SubstanceFriction="1.2" >
			...
			<TiresInflationSystemSettings _template="Test" />
			...
		</TruckTire>
```

This approach will allow us to avoid duplication of the settings and will keep them in a single place.

### Explicit Setup 
In the second scenario, you can add all hierarchy of child-tags to the `<TiresInflationSystemSettings>` tag explicitly. Particularly, you can add the [`<Low>`](./low_reduced/index.md) and [`<Reduced>`](./low_reduced/index.md) tags for these decreased pressure modes, and the [`<TickDamageParams>`](./low_reduced/tickdamageparams/index.md) tag inside some of them for the damage model of this mode.

For example:
```xml
		<TruckTire Mass="75" Mesh="wheels/tire_scout_offroad_4" Name="offroad_1" SubstanceFriction="1.2" >
			...
			<TiresInflationSystemSettings>
				<Low
					OnModelFriction="4.0"
					BodyFrictionAsphalt="2.0"
					SubstanceFriction="1.5"
					FuelConsumptionModifier="2.0"
					SteeringSpeedModifier="0.7"
					AdditionalRadiusOffset="0.1"
					>
					<TickDamageParams
						MinVel = "2.55"
						MaxVel = "5.0"
						MinDamage = "2"
						MaxDamage = "4"
						DamageTick = "5"
					/>
				</Low>
				<Reduced
					OnModelFriction="3.0"
					BodyFrictionAsphalt="1.3"
					SubstanceFriction="1.3"
					FuelConsumptionModifier="1.5"
					SteeringSpeedModifier="0.85"
					AdditionalRadiusOffset="0.05"
					>
					<TickDamageParams
						MinVel = "7.0"
						MaxVel = "10.0"
						MinDamage = "2"
						MaxDamage = "4"
						DamageTick = "5"
					/>
				</Reduced>		
			</TiresInflationSystemSettings>
			...
		</TruckTire>
```

**NOTE**: For details on the particular attributes, see description of child tags.

This approach will allow you to explicitly specify some specific settings directly in the description of the particular tire.