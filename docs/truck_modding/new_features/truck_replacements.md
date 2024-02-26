# Truck Replacements
*(NEW) This feature is valid for Expeditions only.*

## Overview
*Truck Replacement* – is a substitution of some data of the truck (properties, visuals, physical model, and so on) that is tied to the selection of the particular Suspension. 

**NOTE**: The scope of this substitution may vary greately: from changing few parameters to a completely separate version of the truck.

This modding feature was not available in SnowRunner and has been implemented specifically for Expeditions. Its intention was to give modders additional control over the change of suspension of the truck. Particularly – give them the ability to modify the visuals of the truck in the realistic manner after the change of the suspension.

So, the Truck Replacement feature allows you to create a substitution of the truck data that will correspond to (and will be selected along with) the different Suspension Set. It can contain the completely new setup of the wheels, wich points, different engine sockets, gearbox sockets, textures, bones, and different FBX file of the truck model. Actually, it can be a completely new truck since most of its properties can be replaced by the Truck Replacement.

## Setup
The setup of a Truck Replacement consists mainly of the following:

1.  We create a new FBX file of the truck (replacement) in the `/meshes/trucks/`. E.g. `truck_example_repl_01.fbx`

2.  We create a new XML file of the mesh of the truck (replacement) in the `/meshes/trucks/`. E.g. `truck_example_repl_01.xml`

3.  We create a new XML file of the class of the truck replacement in `/classes/truck_replacements/`. E.g. `truck_example_repl_01.xml`
   
    **NOTE**: To create an XML class of a truck replacement, you can copy-paste data from the XML class of the truck and modify only the parameters you need, keeping all other data as is.

    **WARNING**: However, after copy-pasting data from the XML class of the truck, you need to delete all information on `<AddonSockets>` from the XML class of Truck Replacement. Data in `<AddonSockets>` needs to be specified in the XML class of the Truck, not in the XML class of Truck Replacement. If you want to set up what addons will be compatible with this new Truck Replacement, you need to do this in XML classes of these Addons, by the `<RequiredSuspension>` tag, see [Note on Addons](#note-on-addons) below.

4.  In the XML class of the Suspension (e.g. `/classes/suspensions/s_truck_example.xml`), we link the particular `<SuspensionSet>` to the XML class of the truck replacement. This can be done with the help of the `TruckReplacement` attribute, where you need to specify the name of the XML class of the paticular Truck Replacement, without file extension (e.g. `"truck_example_repl_01"` for `truck_example_repl_01.xml`).

    For example:

    ```xml
    <SuspensionSet
        _template="High"
        CriticalDamageThreshold="0.6"
        DamageCapacity="140"
        BrokenWheelDamageMultiplier="1.5"
        Name="truck_example_suspension_high"
        TruckReplacement="truck_example_repl_01"
    >
    ...
    </SuspensionSet>
    ```

After that, when the player selects this Suspension Set in the game for this truck, its data will be substituted with the truck replacement.

## Limitations
You cannot use [inheritance](./../general_info/xml_structure/inheritance.md) (i.e. the `<_parent/>` tag) in the XML class of the truck replacement. 

And, along with that, a particular set of fields cannot be changed in the Truck Replacement.

Particularly, the XML data related to the following subjects should be the same and should be copied as is from the original XML file of the class of the truck (e.g. from `truck_example.xml`):

 -  Type of the Truck (`TruckType` in `<TruckData>`)
 -  Icon of the Truck in the Garage (`TruckImage` in `<TruckData>`)
 -  UIDs (`<UiDesc>` in `<TruckData>`)
 -  Price data (`Price` in `<GameData>`)
 -  Available suspensions (`Type` in the `<SuspensionSocket>`)
 -  Available gearboxes (`Type` in the `<GearboxSocket>`)

 And, you should also remove all information on `<AddonSockets>` from the XML class of Truck Replacement. This data should be specified in the original XML class of the Truck only.
 
 The `<CustomizationCameras>` section should also be removed from the XML class of Truck Replacement, since these camera presets are also specified in the XML class of the Truck only (changing them in the XML class of the Truck Replacement will have no effect at all).


## Note on Addons
We can also add limitations to the setup of the [Addons](./addon_changes.md), requiring the particular suspension (and, by this, the particular Truck Replacement) for them.

This can be done in the XML class of the Addon, by the `<RequiredSuspension>` tag with the `Types` attribute. In this attribute, we need to specify the `Name` of the `<SuspensionSet>` (which we have linked to the particular Truck Replacement).

For example:
```xml
<RequiredSuspension Types="truck_example_suspension_high" />
```