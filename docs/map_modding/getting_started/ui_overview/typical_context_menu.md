# Typical Context Menu

Right-clicking the main window of the scene or right-clicking the section/object in the **Scene View** panel will open the context menu.

**NOTE 1**: However, when a brush is selected, the right-click behavior is different, see [Typical Brush dialog](./typical_brush_dialog.md).

**NOTE 2**: The list of commands within a context menu depends on where particularly you have performed a right-click. 


The list of most frequently used commands is shown below:

|**Command**                   | **Description**                     | 
|------------------------------|-------------------------------------|
| **Do Land**                  |  Place the object on the terrain surface. | 
|  **Replace**                 |   Replaces the right-clicked object with another object.|
|  **Fly To**                  |   Moves the camera to the right-clicked object, zooms it, and selects it.|
|  **Delete**                  |   Deletes the right-clicked object from the map. You cannot undelete it after that.|
|  **Duplicate**               |   Duplicates the selected object.|
|  **Reload**                  |   Reloads the terrain. Any unsaved changes will be lost.|
|  **Rebuild Terrain**         |   Rebuilds all terrain of the map, applies all changes that you have done to its properties (heights, references, etc.), and refreshes the appearance of the level in the Editor. |
|  **Rebuild Selection**       |   Similar to **Rebuild Terrain**, but rebuilds only selected terrain blocks, which is faster. You can select multiple terrain blocks by holding CTRL and left-clicking the terrain in the main window of the scene. |
|  **Rebuild Visible**         |   Similar to **Rebuild Terrain**, but rebuilds only terrain blocks currently visible in the main window of the scene, which is faster.  |
|  **Combine chunks in directory**    |   Creates full-sized textures from small textures corresponding to all map pieces of the map. See [Collaborative Work on Maps](./../../additional_info_on_maps/collaborative_work_on_maps/collaborative_work_on_maps_overview.md) for details. |
|  **Separate chunks from directory** |  Divides full-sized textures into smaller ones that correspond to map pieces. See [Collaborative Work on Maps](./../../additional_info_on_maps/collaborative_work_on_maps/collaborative_work_on_maps_overview.md) for details. |
|  **Add Pbr Material**         |  Adds a new PBR Material, see [Assigning PBR Materials to Terrain](./../../creating_a_map/pbr_materials/assigning_pbr_materials_to_terrain.md).|
|  **Add Zone**                 |  Adds a new zone locator, see [Zones: Overview](./../../creating_a_map/zones/zones_overview.md).|
|   **Add Model**               |  Adds a new Model, see [Adding Models](./../../creating_a_map/models/adding_models.md).|
|  **Add Plant**                |  Adds a new standalone Plant, see [Adding Plants](./../../creating_a_map/plants/adding_plants.md).|
|  **Add Distribution**         |  Adds a new Distribution (e.g. massively planted trees, rocks, etc.),  see [Adding Multiple Objects via Distribution](./../../creating_a_map/distributions/adding_multiple_objects_via_distribution.md).|
|  **Add Overlay**              |  Adds a new Overlay (e.g. a road, wires, etc.), see [Adding Overlays](./../../creating_a_map/overlays/adding_overlays.md).|
|  **Add River**                |  Adds a new River object, see [Adding Rivers and Water Objects](./../../creating_a_map/rivers_and_water_objects/adding_rivers_and_water_objects.md).|
|  **Add River Markup**         |  Add a new River Markup object (a sound area for the river), see [Adding River Sounds via RiverMarkup](./../../creating_a_map/rivers_and_water_objects/adding_river_sounds_via_river_markup.md).|
|  **Add Reference**            |  Adds a new Reference, see [Adding References](./../../creating_a_map/references/adding_references.md).|
|  **Add Truck**                |  Adds a new Truck, see [Adding Trucks](./../../creating_a_map/trucks/adding_trucks.md).|
|  **Add Sound**                |  Adds a new Sound, see [Adding Sounds](./../../creating_a_map/sounds_and_music/sounds/adding_sounds.md). |
|  **Add ... Sound Domain**     |  Adds a new Sound Domain of the particular type, see [Adding Sound Domains](./../../creating_a_map/sounds_and_music/sound_domains/adding_sound_domains.md). |
|  **Play ambient ...**   (NEW) |  Allow you to play particular sets of sounds (that correspond to different conditions) from the **Ambient Preset** configured for the map. See [Adding Ambient Sounds](./../../creating_a_map/sounds_and_music/ambient_sounds/adding_ambient_sounds.md). |
|  **Stop  play ambient** (NEW) |  Stops playing ambient sounds that were turned on by the **Play ambient ...** commands |
