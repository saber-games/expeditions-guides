# Reference Properties

To edit reference properties, select it in the **References** list in the **Scene View** panel. After doing this, you can edit the properties of the selected reference in the lower part of the **Scene View** panel.

The properties are the following:

-   **Position** - the coordinates of the reference on your map.

-   **HeightOffset** - the shift in the height that can be set for the terrain of the reference. Using this field, you can increase or decrease all terrain of the reference (as a whole).

-   **Angle** - the angle of rotation of the reference on your map.

-   **Layer** - the layer of the reference on the map that can be used in the case of the intersection of the references to determine what reference should be on top and what reference settings should have more priority. The higher the number of the layer is, the more priority the reference will have.

-   **Flatten** - whether or not the reference should flatten the terrain below it. If this parameter is **True**, the initial terrain of your map below the reference will be flattened, then the terrain of the reference will be applied above it, and the terrain on the edges of the reference will be normalized to fit into the terrain of the other part of your map. If this parameter is **False**, then the terrain of the reference (its height) is simply added to the terrain (height) of the initial map in this place.

-   **ApplyMaterials** - whether or not the reference should substitute the initial materials of the map below it with its own materials. Please note that if this parameter is **True**, the materials will be substituted for all terrain blocks the reference lies on, even if it does not cover them fully (see the screenshot of Step **6** in [Adding References](./adding_references.md) above). If set to **False**, the reference will use the materials of the map underneath (see the screenshot of Step **7**). The Materials used by the reference can be also substituted with other materials using [Mutators](./usage_of_mutators.md).

-   **ApplyMergeMap** - whether or not the reference should use the **RefMergeMask** map (the **\_ref_merge.tga** texture) for merging the reference with the map. For details, see [RefMergeMask brush][refmergemask_brush].

-   **MergeMaterialMasks** - whether or not the reference should blend the materials of the reference and the map using the **RefMergeMask** mask. For details, see [RefMergeMask brush][refmergemask_brush].

-   **ApplyDistributionMergeMap** - whether the distributions specified in the reference should be added to the map as is (in the case of the `False` value of the option) or added to the map using the RefMergeMask mask specified within the reference (in the case of the `True` value of the option). For details on the RefMergeMask mask, see [RefMergeMask brush][refmergemask_brush].

-   **WetnessBlendMode** - specifies what should be done with the wetness of the reference (see [Wetness](./../terrain/geometry_brushes_for_terrain/wetness.md). Possible values:

    -   **Replace** - the wetness mask of the reference should replace the wetness mask of the map below it.

    -   **Add** - wetness values of the reference should be added to the wetness values of the map below it.

-   **Snow** - specifies what should be done with the depth of the snow of the reference (see [Snow](./../terrain/geometry_brushes_for_terrain/snow.md) above). Possible values:

    -   **Replace** - the depth of the snow of the reference should replace the depth of the snow of the map below it.

    -   **Add** - the depth of the snow of the reference should be added to the depth of the snow of the map below it.

    -   **Ignore** - the depth of the snow of the reference should be ignored. In this case, the depth of the snow of the map below the reference will remain the same.

-   **STG** - displays the name of the reference (it cannot be modified).

**NOTE**: After changing the properties of the reference, you need to perform the **Rebuild Terrain** operation to apply your changes. You can do it by right-clicking the terrain and selecting **Rebuild Terrain** from the context menu.

For recommendations on the setup of these properties, see [Recommendations for References](./recommendations.md).


[refmergemask_brush]: ./ref_merge_mask_brush.md
