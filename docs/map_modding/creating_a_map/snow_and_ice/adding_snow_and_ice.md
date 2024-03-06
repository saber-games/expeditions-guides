# Adding Snow and Ice

*Currently, this feature is used in SnowRunner only.*

This section is a summary of snow and ice creation. It links to other sections for details.

## Snow and Ice Coverage
To create snow/ice coverage on the map:

1.  Create a **PBR Material** that contains the **snow_layer**. The **snow_layer** texture must be selected as **Layer 3** of this material. Other layers are up to you, but probably you will want to select textures in a winter setting for them. See [Assigning PBR Materials to Terrain][assigning_pbr_materials_to_terrain] and [[5.3.1. Material properties]](#material-properties) for details.

2.  Paint with **Layer 3 (snow_layer)** the areas of the map you want to cover with snow. See [Assigning PBR Materials to Terrain][assigning_pbr_materials_to_terrain] and [Material Properties][material_properties] for details.

3.  Using the **Geometry \> Snow** brush, add the depth to the snow in the areas painted with the **snow_layer**. For more details, see [Snow][snow_brush].  
    After using this brush, perform **Rebuild Terrain**.

4.  Since you have painted snow depth in some areas, the Editor will consider that your map is snowy and will automatically display additional layers within the Brush available *for your PBR Material*. Particularly, you will see the **soft_snow** and **crust_snow** layers there (see [Material Properties][material_properties] for details). Usage of these layers is the following:

    -   **soft_snow** - soft snow, it is typically painted mainly in the areas that contain a forest, bushes, and a lot of plants.

    -   **crust_snow** - compressed snow with hard lumps, it is typically painted along the edges of the road.

    **NOTE**: These layers change only the normal map of the **snow_layer** only. This is necessary to vary the snow appearance as described above. The results of painting with these layers cannot be seen in the Editor itself, but are visible in the game.

5.  Paint the necessary areas with the **soft_snow** and **crust_snow** layers.

6.  Now, if your map contains some hard surfaces (e.g. the winter asphalt, winter stone, ice) as layers of your **PBR Material**, you can make them icy by painting them with the **Geometry \> Wetness** brush, see [Wetness][wetness_brush].

7.  When your level is considered snowy, you can also change the amount of procedural snow on the surfaces of models and terrain layers (except the snow layer itself). This is done with the help of the **Procedural snow coverage** parameter of the Terrain, see [Terrain Properties][terrain_properties].

8.  If you enable the **Settings \>** **Show Snow By Up Vector** option in the main menu, you will view the snow cover effect for models and plants on the scene, according to their texture settings.

## Frozen River and Lakes
Frozen rivers, lakes, and other ice surfaces are created as a *terrain* with the material containing either `ice_01` or `ice_02` texture as a layer. They are *not* created as regular River objects.

## Falling Snow
Falling snow and other weather conditions are specified in the **Daytime Presets**, see [Terrain Properties][terrain_properties].


[assigning_pbr_materials_to_terrain]: ./../pbr_materials/assigning_pbr_materials_to_terrain.md
[material_properties]: ./../pbr_materials/material_properties.md
[snow_brush]: ./../terrain/geometry_brushes_for_terrain/snow.md
[wetness_brush]: ./../terrain/geometry_brushes_for_terrain/wetness.md
[terrain_properties]: ./../terrain/terrain_properties.md 