# Creation of Maps: Overview

For both games, the process of creating a map is similar:

1.  Create a new [terrain](./terrain/creation_of_terrain.md).

2.  Modify the terrain and add objects to it:

    -   Create the necessary [height differences](./terrain/geometry_brushes_for_terrain/overview_main_geometry_brush.md) on it, smooth it in the right places, and so on.

    -   Assign the necessary [PBR materials](./pbr_materials/assigning_pbr_materials_to_terrain.md) and use their layers to paint the terrain.

    -   Add [mud](./terrain/geometry_brushes_for_terrain/mud.md) and/or [snow](./terrain/geometry_brushes_for_terrain/snow.md) areas.

    -   Add [rivers and water objects](./rivers_and_water_objects/adding_rivers_and_water_objects.md).

    -   Add plants:
        -   as single [standalone plants](./plants/adding_plants.md)
        -   or massively via [Distributions](./distributions/adding_multiple_objects_via_distribution.md)

    -   Add various [models](./models/adding_models.md): buildings, light poles, etc.

    -   If necessary, add various [overlays](./overlays/adding_overlays.md): roads, wires, etc.

    -   Add [zones](./zones/zones_overview.md) that the player will interact with and that will be used in objectives.

        **WARNING**: In *Expeditions*, you need to add at least one [Deploy zone](./zones/expeditions_zones/deploy_zones.md) to the map. This is necessary for spawning the player's trucks on the map.

    -   Add [objectives](./objectives/objectives_overview.md) related to some of these zones.

        **WARNING**: In *Expeditions*, you need to add at least one [Expedition](./objectives/objectives_in_expeditions/expeditions_and_contracts.md) to the map's objectives. This Expedition is necessary for the player to be able to load the map.

    -   Add [trucks](./trucks/adding_trucks.md) to your map. (In *Expeditions*, this is optional.)

        **WARNING**: In *SnowRunner*, you need to add at least one [truck](./trucks/adding_trucks.md) to the map and select this truck as **Active**. This is necessary for correct spawning on the map.

    -   If necessary, use external maps built for some objects and/or small typical areas of the map as [references](./references/adding_references.md) on the main map.

    -   Add [sounds](./sounds_and_music/sounds/), [sound domains](./sounds_and_music/sound_domains/adding_sound_domains.md), and [ambient sounds](./sounds_and_music/ambient_sounds/adding_ambient_sounds.md).

    -   If necessary, add some [music](./sounds_and_music/music/adding_music.md) to the map.

    -   If necessary, add some special features to the map: [minigames](./minigames/minigames_overview.md) in *Expeditions* or [farmning](./farming/farming_overview.md) and [water delivery](./water_as_resource/water_as_resource.md) in *SnowRunner*.

3.  [Pack](./../packing_and_publishing_maps/packing_maps.md) your map to `.pak` and `.zip` files.

4.  [Test](./../packing_and_publishing_maps/testing_maps.md) your map locally in the game.

5.  [Publish](./../packing_and_publishing_maps/publishing_maps.md) your map to mod.io.


In *SnowRunner*, you can also combine multiple custom maps into a [Region](./regions/regions_with_multiple_maps.md).  
In *Expeditions*, this is currently not supported.  

