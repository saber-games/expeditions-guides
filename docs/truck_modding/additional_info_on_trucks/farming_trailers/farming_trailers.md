# Farming Trailers

*This feature is valid for SnowRunner only.*

## Overview
In *SnowRunner*, starting with the *DLC 8* (*"Season 8: Grand Harvest"*) you are able to create farming fields on your custom maps. For details, see [Farming][farming] in **Map Modding**.

To interact with these farming fields, you can use regular farming trailers that are provided with Editor, such as: `trailer_cultivator`, `trailer_harvester`, and `trailer_planter`.

**TIP**: The XML files of classes of these trailers are available in the [`initial.pak`][initial_pak], in the following folder of this archive: `[media]\_dlc\dlc_8\classes\trucks\trailers`.

However, you can also create your own custom farming trailers. The process of their creation is very much similar to the process of creating a regular trailer, there are only a few differences, listed below as "Steps" of adding a farming feature to a regular trailer.

## Step 1: Type of Trailer
First of all, you need to specify the type of the farming trailer (`FarmingTrailerType`).

This farming type of a trailer will define the farming assignments where the player will be able to use it.

Particularly, you can choose one from `3` predefined types here: `Cultivator`, `Planter`, and `Harvester`.

You need to specify this farming subtype in the `FarmingTrailerType` attribute of the `<Truck>` tag of XML of class of a trailer.

For example:

```xml
<Truck Type="Trailer" FarmingTrailerType="Cultivator">
...
</Truck>
```

## Step 2: "Interacting" Parts

After that, you need to set up "interacting" parts of the trailer (`FarmingBoundingBox1`, `FarmingBoundingBox2`, ...).

I.e., you need to identify parts of your trailer model that will be interacting with the ground of the farming field and specify the location of these parts in the set of "farming" bounding boxes.

**NOTE**: When the game processes a farming assignment being done by the player, it tracks *not* the area passed by the farming trailer as a whole, but the area passed by these bounding boxes.

These bounding boxes needs to be described as the `<FarmingBoundingBox..>` tags within the `<PhysicsModel>` tag. 

You can create `<FarmingBoundingBox1>`, `<FarmingBoundingBox2>`, and so on, as many of these tags as needed. Every such tag defines a bounding box of the particular size that is attached to one of the bones the trailer's model.

For example:

```xml
<PhysicsModel Mesh="trucks/trailers/trailer_cultivator">
    ...
    <FarmingBoundingBox1 BaseBone="BoneTrailer_cdt" Min="(-5.23; -0.6; -2.81)" Max="(-1.97; 0.6; -0.14)" />
    <FarmingBoundingBox2 BaseBone="BoneTrailer_cdt" Min="(-5.23; -0.6; 0.14)" Max="(-1.97; 0.6; 2.81)" />
    <FarmingBoundingBox3 BaseBone="BoneTrailer_cdt" Min="(-9.15; -0.6; 0.14)" Max="(-5.66; 0.6; 2.81)" />
    <FarmingBoundingBox4 BaseBone="BoneTrailer_cdt" Min="(-9.15; -0.6; -2.81)" Max="(-5.66; 0.6; -0.14)" />
    ...
</PhysicsModel>

```

**NOTE**: That's it for simple farming trailers. However, there are a lit bit more complex cases, when a farming trailer uses some constraints and some of them need to be automatically "activated" to obtain a final form of the trailer that is suitable for farming. For example, original farming trailers (`trailer_cultivator`, `trailer_harvester`, and `trailer_planter`) do expand when they reach a target farming field during the appropriate farming stage. If this is your case, please refer to [Auto-Activation of Constraints of a Farming Trailer][auto_activation_of_constraints_farming_trailer] for some additional nuances related to these constraints.

After adding these properties, you can repack your trailer and test it on one of the custom farming maps. For details on creating your own farming map, see [Farming][farming] in **Map Modding**.


[farming]: ./../../../map_modding/creating_a_map/farming/farming_overview.md
[initial_pak]: ./../../../map_modding/getting_started/file_paths_and_naming/file_paths.md#source-of-info-initialpak-archive
[auto_activation_of_constraints_farming_trailer]: ./auto_activation_of_constraints_of_farming_trailer.md