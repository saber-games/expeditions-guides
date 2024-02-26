# Damage

The `<Damage>` tag describes changes in damage parameters of the truck after installation of the addon.

It can contain multiple [`<Multiplier>`](./multiplier/index.md) tags. For example:

```xml
<TruckAddon>
	<TruckData>
		<Damage>
			<Multiplier Multiplier="0.85" Type="Engine" />
			<Multiplier Multiplier="0.85" Type="Gearbox" />
			<Multiplier Multiplier="0.9" Type="FuelTank" />
			<Multiplier Multiplier="0.9" Type="Suspension" />
		</Damage>
	</TruckData>
	...
</TruckAddon>

```


