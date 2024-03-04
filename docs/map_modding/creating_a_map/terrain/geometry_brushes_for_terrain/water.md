# Water

The **Geometry** \> **Water** [brush][brush] does *not* create water objects. It allows you to change the properties for *already created* water objects. 

**NOTE**: The water objects themselves are created by the **River** tool. See [Adding Rivers and Water Objects][river].

Properties that can be changed with this brush:

-   **Foam** - adds foam to the water surface.

-   **Speed** - sets the speed of the water, separately from its direction (flow). By default, the flow direction goes from the `0` point of the [**River**][river] object to the next points (`1`, `2`, etc.).

-   **Flow** - Overrides the direction of the water flow, when the [**River**][river] object has the **UseFlowMap** parameter set to `True`. See [Adding Rivers and Water Objects][river] for details.

**WARNING**: When painting the direction of the water flow using the **Flow** mode, the **Autofade** option of the brush should be ***disabled***. The enabled **Autofade** option will result in the automatic correction of brushstrokes, which may result in the incorrect map of flow directions.

**TIP**: Firstly, set the main direction of the flow for the whole river using a brush with a huge **Size**. Then, using the brush of a smaller size, add the details of the river flow in the necessary areas: the water flow near obstacles and reflection of water from the banks of the river (at `45` degrees from the direction of the main flow). Finally, to achieve the best result and to avoid sharp borders between parts of the flow, you can open the map of flow (the `_water_flow.tga` texture) and blur the necessary parts of it in the image editor of your choice.

The mask for the foam is stored in the green channel of the `_water.tga` texture (in the map mod folder). The mask for the speed of water is stored in the blue channel of the same texture. The result of painting the flow of the river is stored in the `_water_flow.tga` texture. 

**NOTE**: The `_water_flow.tga` texture is generated as *multiple files*, see [Map Pieces. Their Subfolders](./../../../additional_info_on_maps/collaborative_work_on_maps/map_pieces_their_subfolders.md). 

Along with manual painting of the flow of the river, you can generate a default flow map and then tune it with a third-party tool. See [Create Default Flowmap](./context_menu/create_default_flowmap.md) for details.


[river]: ./../../rivers_and_water_objects/adding_rivers_and_water_objects.md
[brush]: ./overview_main_geometry_brush.md