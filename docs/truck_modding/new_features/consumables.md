# Consumables
*(NEW) This feature is valid for Expeditions only.*

A *Consumable* item is an addon with specific characteristics that requires other addon(s) for the installation on the truck and is installed to the resource slot on the truck by the player.

For example, the spare wheel as a consumable may require a special bumper as a target addon and may be installed to the front resource slot that will become available after installation of this bumper.

**NOTE**: However, the spare wheel that is installed to a different addon (e.g., the rear bumper) or even to a different resource slot within the same addon – will be a *different* consumable with a *separate* XML class of the addon and a *separate* setup.

## Types of Consumables
There are three basic (predefined) types of consumables:

-   **Fuel** – addons with `FuelCapacity` within [`<TruckData>`](./../tags_and_attributes_of_trucks/truckaddon/truckdata/index.md) in the XML class of the addon.
-   **Repair parts** – addons with `RepairsCapacity` within [`<TruckData>`](./../tags_and_attributes_of_trucks/truckaddon/truckdata/index.md) in the XML class of the addon.
-   **Spare wheels** – addons with `WheelRepairsCapacity` within [`<TruckData>`](./../tags_and_attributes_of_trucks/truckaddon/truckdata/index.md) in the XML class of the addon.

However, you can create your own consumables if you want to. For example, you can add a some special lamp to the roof rack of the truck as a consumable.

## The `IsConsumable` attribute
Whether or not the addon is a consumbale is defined by the value of its `IsConsumable` attribute within [`<GameData>`](./../tags_and_attributes_of_trucks/truckaddon/gamedata/index.md) in the XML class of the addon.

Particularly, the value of `IsConsumable` must be `true` for all consumables. 

## Installation of Consumables
All consumables are installed to particular addons that can be made required by the [`<RequiredAddon>`](./../tags_and_attributes_of_trucks/truckaddon/gamedata/requiredaddon/index.md) tag of the consumable. This should be done in the XML class of this consumamble, or, speaking more precisely, in the XML class of the *addon that is defined as this consumable*, since every consumable is simply a special type of the addon from the point of view of the system.

 The name of the required addon is specified in the `Type` attribute of the [`<RequiredAddon>`](./../tags_and_attributes_of_trucks/truckaddon/gamedata/requiredaddon/index.md) tag. For example:

```xml
		<RequiredAddon Types="international_loadstar_1700_roofrack_01" />
```

The same XML class of the addon must contain the [`<InstallSocket>`](./../tags_and_attributes_of_trucks/truckaddon/gamedata/installsocket/index.md) tag with the name of the socket (on the *truck*) as the `Type` attribute. For example:

```xml
		<InstallSocket Type="InternationalLoadstar1700RoofrackSlot01" />
```

The XML class of the *truck* must also contain the socket with the same name via [`<AddonSockets>`](./../tags_and_attributes_of_trucks/truck/gamedata/addonsockets/index.md) and [`<Socket>`](./../tags_and_attributes_of_trucks/truck/gamedata/addonsockets/socket/index.md) tags:
```xml
		<AddonSockets >
			<Socket Names="InternationalLoadstar1700RoofrackSlot01" Offset="(0; 0; 0)" ParentFrame="BoneCabin_cdt"/>
		</AddonSockets>
```
Thus, the XML class of the truck will have:

-   The socket for the target addon to be installed for the consumables.
-   Sockets for consumables that will be available for this target addon.

If you want to configure that two (or more) different consumables are installed to the same resource slot in the UI, you can simply use the same socket for them. In this case, they will be both installed to this slot and will be mutually exclusive.

For example, such consumables for *International Loadstar 1700* as `international_loadstar_1700_roofrack_01_slot_01_fuel.xml` and `international_loadstar_1700_roofrack_01_slot_01_repair.xml` both require the `international_loadstar_1700_roofrack_01` roof rack as the target addon and are both installed to the `InternationalLoadstar1700RoofrackSlot01` slot, so these two lines are the same in the XML classes of these consumables:

```xml
        ...
		<RequiredAddon Types="international_loadstar_1700_roofrack_01" />
		<InstallSocket Type="InternationalLoadstar1700RoofrackSlot01" />
		...
```

**NOTE**: Resource slots available for the particular target addon and their quantity are determined automatically when the game locates all consumables requiring this addon and reads the configuration of sockets reserved for these consumables within the XML class of the truck.

