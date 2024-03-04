# Snorkel

Snorkel of the truck. Similarly to [`<Intake>`](./../truckdata/intake/index.md) defines the air intake point of the truck with a snorkel.

Please note that the `<Snorkel>` tag can be also used within the `<TruckAddon>` tag of the truck addon, when a snorkel is installed as an addon to the truck.

**NOTE**: The `<Snorkel>` tag can be used multiple times, to specify multiple "drowning points" in case of multiple snorkels.
For example:

```xml
<TruckAddon>
	<Snorkel Origin="(2.651; 2.709; 0.780)" />
	<Snorkel Origin="(2.651; 2.709; -0.780)" />
	<PhysicsModel Mesh="trucks/tuning/tatra_force_t815_7_tuning" MeshFrame="tatra_force_t815_7_snorkel_02">
		<Body ImpactType="Truck" Mass="12" ModelFrame="BoneSnorkel02_cdt">
			<Constraint Type="Rigid" />
		</Body>
	</PhysicsModel>
	<GameData
		CameraPreset="side_l"
		Category="snorkel"
		Price="3700"
		UnlockByExploration="false"
		UnlockByRank="14"
	>
		<UiDesc
			UiDesc="UI_TUNING_KRS_58_SNORKEL_02_DESC"
			UiIcon30x30=""
			UiIcon40x40=""
			UiName="UI_TUNING_KRS_58_SNORKEL_02_NAME"
		/>
		<InstallSocket Type="TatraForceT8157Snorkel" />
	</GameData>
</TruckAddon>
```

Attributes:

-   `Origin="(2.365; 0.953; 0)"`  
    The position of the point that is used for the mechanism of receiving damage from drowning. The truck will start to receive such damage if the water is above this point.

