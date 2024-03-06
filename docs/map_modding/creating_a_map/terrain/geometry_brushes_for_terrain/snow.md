# Snow

*Currently, this feature is used in SnowRunner only.*

The **Geometry \> Snow** brush allows you to control the depth of snow.

This brush can only be used on the snow terrain layer, after painting it with the **snow_layer** layer of the corresponding PBR material (see [Assigning PBR Materials to Terrain](./../../pbr_materials/assigning_pbr_materials_to_terrain.md)). 

You can paint using this brush if there is at least a little layer of snow terrain in the painted area. For example, if `0` amount of the snow is painted on the layer, then there will be no deep snow; however, if the weight of the snow on the snow layer is `50%`, then deep snow can be painted. This is done so to avoid sharp "steps" of the deep snow (since on the map of the deep snow `1` pixel equals to `50` cm).

As with [mud](./mud.md), after painting with the depth of the snow, a region with vertical lines with horizontal marks will appear on the terrain. The more horizontal marks are displayed on the vertical line, the deeper the snow is.

![](./media/image75.png)

**IMPORTANT**: If there is solid ground under the snow and there is no mud, the car will not sink in the snow for more than half of a wheel. If the snow is deeper than 1 horizontal mark (see screenshot above) and there is a hidden mud (mud of the "**Extrudes**" type) under the snow, the car will sink deeper in the snow and will bury itself in the snow below the level of the wheels.

Properties:

-   **Depth** - sets the depth of snow (similarly to Mud).

-   **Flatten** - flattens snow depth.

-   **Smooth** - smooths transitions between sections of snow with different depths.

By enabling the **Update material** option in the **Brush** window, you can add both the depth of the snow and the **snow_layer** itself, simultaneously.

**NOTE**: If you are creating a large level and are working with snow (painting depth or working with a material with the **snow_layer**), then we recommend you to disable the auto rebuild of the terrain. Otherwise, the auto rebuild and/or any operation with the material will take a long time.

To view the final result of the performed changes, you need to rebuild the scene. To do this, right-click the scene window and select **Rebuild Terrain** or **Rebuild Visible / Selection** (to rebuild only visible or selected areas).

After painting with the depth of snow - the system will mark this level as snowy. And, only after that, the **soft_snow** and **crust_snow** layers can be applied (see [Material Properties](./../../pbr_materials/material_properties.md) for details). They will be available only after performing **Rebuild Terrain** also. The **Procedural snow coverage** parameter of the Terrain (see [Terrain Properties](./../terrain_properties.md)) also works only for snowy levels.

