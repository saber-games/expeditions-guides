# Step 6: Creating XML Files of Truck Components

## Oveview
Now, we can focus on the XML classes of Suspensions, Engines, Gearboxes, and Winches that we haved touched [earlier][step_5_component_sockets].

Let's do it step by step. The summary and motivation of these activities will be as follows. 

Before this step, our mod was *not* [packable][packable], due to validation that is performed during packing. 

Particularly, *some* classes in the *original* XML files of components have the `UnlockByExploration` and `AddonUnlockByObjective` attributes set to `true`, since they are locked by default and will be unlocked either by exploring some map in the original game or by accomplishing some in-game objective.

However, if you are creating a truck mod that is not linked to any map, you will not be able to unlock them that way. I.e., these components will remain locked.

So, during packing, the validator identifies the `true` values in these attributes and cancels packing due to them – to avoid "forever locked" components in the mod.

And, we will also remove references to [Truck Replacements][truck_replacements] from the Suspension classes, since they are not covered by this guide.

I.e., we will need to:

1.  Create copies of the XML files of these components.
2.  Rename these files themselves and identifiers of variants of components within them.
3.  Set `UnlockByExploration` and `AddonUnlockByObjective` to `false` for all variants of these components.
4.  Remove references to [Truck Replacements][truck_replacements].


## Process

### Create Copies of XML files of Truck's Components

#### Creating Subfolders
Let's begin with creating subfolders for the XML files of the components' classes. 

Paricularly, in the `classes` subfolder of the [folder of your mod][mod_folder], you will need to create four subfolders:

-   `engines`
-   `gearboxes`
-   `suspensions`
-   `winches`

Totally, you will have 5 subfolders in `classes`, since you already created `trucks` there.

#### Extracting files from initial.pak
Now, you need to extract the original files of truck's compontents that are used for *International Loadstar 1700* from the `initial.pak` archive.

This archive is located in the *folder of the installed game*, within its `\preload\paks\client\` subfolder. For details, see [File Paths][file_paths] in the **Map Modding** section.

To extract files from this archive, you will need some file archiver that works correctly with `.pak` files, e.g. **WinRAR**. You will need only to extract files, you will not need to modify the archive.

**WARNING**: Incorrect *modifying* of the `initial.pak` archive may lead to a crash of the game or the game not working. Always make the backup of it. 

In the `initial.pak`, the necessary files are located at the following paths:

-   `[media]\classes\engines\e_us_truck_old_international_loadstar_1700.xml`
-   `[media]\classes\gearboxes\gearboxes_trucks_international_loadstar_1700.xml`
-   `[media]\classes\suspensions\s_international_loadstar_1700.xml`
-   `[media]\classes\winches\winches_scouts.xml`

You will need to extract these files and put them into [subfolders](#create-subfolders) you have created.

**NOTE**: All XML classes of suspensions, engines, gearboxes, and winches can be found in the subfolders of the `initial.pak` archive mentioned above.

### Rename Files and Idnentifiers of Components
Now, you need to rename these files and identifiers of component variants within them.

These identifiers are specified as the value of the `Name` attribute for every class of the component within the XML file.

For example, the identifier of *one variant* of an engine from all compatible engines listed in `e_us_truck_old_international_loadstar_1700.xml` is `us_truck_loadstar_1700_engine_0`:

```xml
	<Engine
		CriticalDamageThreshold="0.55"
		DamageCapacity="160"
		DamagedConsumptionModifier="1.5"
		FuelConsumption="4.6"
		Name="us_truck_loadstar_1700_engine_0"
		Torque="100000"
		BrakesDelay="0.47"
		EngineResponsiveness="0.018"
		MaxDeltaAngVel="0.015"
		DamagedMinTorqueMultiplier="1.0"
		DamagedMaxTorqueMultiplier="0.65"
	>
		<GameData
			Price="1000"
			UnlockByExploration="false"
			AddonUnlockByObjective="false"
			UnlockByRank="1"
		>
			<UiDesc
				UiDesc="UI_ENGINE_US_TRUCK_OLD_0_DESC"
				UiIcon30x30=""
				UiIcon40x40=""
				UiName="UI_ENGINE_US_TRUCK_OLD_0_NAME"
			/>
		</GameData>
	</Engine>
```

As you have probably noticed, [earlier][step_5_component_sockets], in the XML class of the Truck, we have referenced the same particular values: the name of the XML file, without extension – in the `Type` attribute of the `<...Socket>` tag, the identifier of the *default variant* of the component – in its `Default` attribute.

Thus, we need to change the following:

-   *In XML classes of the components*:
    -   The names of their XML files themselves.
    -   The values in their `Name` attributes.
-   *In the XML class of Truck*:
    -   Corresponding values of the `Type` attribute in the `<...Socket>` tags
    -   Corresponding values of the `Default` attribute in the `<...Socket>` tags.

At first sight, this looks like a massive change, but it's well worth it.

However, if you are OK with reducing the number of customization variants for your mod, you can leave only a *single variant* of a component and specify the same variant as the default one. I.e., you can rename the files, and leave only a single `<Engine>`, `<Gearbox>`, `<SuspensionSet>`, and `<Winch>` tag (with its contents) in the `<...Variants>` parent tags within these files. And, then, reference only these variants as default ones in the XML class of the truck.

**NOTE**: Be sure to change names and identifiers in both *XML classes of the components* and *the XML class of Truck*.

In the end of this process, the corresponding piece of your XML class of the Truck may look similarly to the following:

```xml
<Truck>
	<TruckData
		...
	>
        ...
        <SuspensionSocket
			Default="mytruck_suspension_default"
			Type="s_mytruck"
			MaxWheelRadiusWithoutSuspension="0.5"
		/>

		<EngineSocket 
            Default="us_truck_mytruck_engine_0"
            Type="e_us_truck_old_mytruck"
        />

		<GearboxSocket 
            Default="g_truck_mytruck_default"
            Type="gearboxes_trucks_mytruck"
        />

        <WinchUpgradeSocket
            Default="w_mytruck_default"
            IsUpgradable="true"
            Type="winches_scouts_mytruck"
        />
        ...
	</TruckData>
    ...
</Truck>
```
And the XML classes of components will have the corresponding names and variants.


### Modify the UnlockByExploration and AddonUnlockByObjective attrubutes
But that's not all. We still need to set proper values of `UnlockByExploration` and `AddonUnlockByObjective` attributes.

Particularly, we need to set them to `false` if they are set to `true`.

To pass the validation during [packing][packable], they need to be `false` for *every variant* of the component that is described in the correspondign XML file.

*For example, for a single variant of the Engine:*
```xml
<_templates Include="trucks"/>
<EngineVariants>
	<Engine
		...
	>
		<GameData
			...
			UnlockByExploration="false"
			AddonUnlockByObjective="false"
			...
		>
			...
		</GameData>
	</Engine>
    ...
</EngineVariants>
```


### Remove References to Truck Replacement
Now we need to remove references to [Truck Replacements][truck_replacements] from the Suspension classes. They are a separate topic and are not covered by this simple tutorial.

Simply remove the following line:

```xml
	TruckReplacement="international_loadstar_1700_susp_1"
```

from the descriptions of the `..._high` and `_crawler` Suspensions in the corresponding XML file.

That's it. It seems we are done the XML classes of the components.


## Bonus
Working with this bunch of files may have the feeling of a mess, a little bit. 

But, creating and modifying these files gives you the power and control over components of your mod. 

In fact, similarly to the XML class of the truck itself, these files contain a lot of important properties in the form of tags and attributes.

*Do you want to make your engine more powerful?*  
Increase the value of the [`Torque`][torque] attribute of the necessary [`<Engine>`][engine] tag in the XML class of engines.

*Do you want the winch to be available only when the engine is working?*  
Set [`IsEngineIgnitionRequired`][winch] to `true` in the corresponding [`<Winch>`][winch] tag.

And so on.

However, our mod is now packable and we are almost ready to drive it.

Let's proceed to the next step – [Creating Truck Pictures][step_7].


[step_5_component_sockets]: ./step_5_creating_xml_file_of_truck_class.md#suspensionsocket-enginesocket-gearboxsocket-and-winchupgradesocket

[packable]: ./../sample_mod_by_the_game/packing_vehicle_mod.md
[truck_replacements]: ./../../new_features/truck_replacements.md
[mod_folder]: ./step_0_prerequisites.md#mod-folder
[step_7]: ./step_7_creating_truck_images.md
[file_paths]: ./../../../map_modding/getting_started/file_paths_and_naming/file_paths.md#source-of-info-initialpak-archive
[torque]: ./../../tags_and_attributes_of_trucks/enginevariants/engine/index.md
[engine]: ./../../tags_and_attributes_of_trucks/enginevariants/engine/index.md
[winch]: ./../../tags_and_attributes_of_trucks/winchvariants/winch/index.md