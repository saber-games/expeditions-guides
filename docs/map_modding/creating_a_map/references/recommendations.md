# Recommendations for References

If you do not plan to use [Mutators][mutators] and plan to use materials of the reference (i.e. **ApplyMaterials** is `True` in [Reference Properties][reference_properties]), then the ***base layer*** of the [PBR materials][pbr_materials] of the reference and the map should be the same. 

Generally, there are two types of references:

-   *Type 1* – "natural" references, where there is no water or objects.

-   *Type 2* – references that contain water or objects.

There are two sets of typical values of reference properties for these types.

For *Type 1*, you can use the ability to completely adjust the reference to the map. I.e., you can set up the reference so that it modifies the level for itself only slightly. In this case, typical settings of the reference are the following:

-   **Flatten** = `False`

-   **ApplyMaterials** = `False` (`True` is also possible)

-   **ApplyMergeMap** = `True` (so, typically you need to specify the RefMergeMask, see [RefMergeMask brush][refmergemask_brush]).

-   **MergeMaterialMasks** = `True`

-   **ApplyDistributionMergeMap** = `True`

-   **WetnessBlendMode** = `Add` (`Replace` is also possible)

-   **Snow** = `Replace`

*Type #2* is the most common and universal. We recommend you to make the terrain below it rather flat to avoid sharp differences in height at the reference border. For this type, the typical settings of the reference are the following:

-   **Flatten** = `True`

-   **ApplyMaterials** = `True`

-   **ApplyMergeMap**= `True` (so, typically you need to specify the RefMergeMask, see [RefMergeMask brush][refmergemask_brush]).

-   **MergeMaterialMasks** = `True`

-   **ApplyDistributionMergeMap** = `True`

-   **WetnessBlendMode** = `Replace`

-   **Snow** = `Replace`

On the map, at the location of the reference, we recommend you to remove all plants. However, if necessary, you can leave some plants on the map at the edges of the reference area.

If your reference contains a river, the river colors from the reference may override the river colors of another river on the map near it. The usage of river colors from the reference is the default behavior in this case. However, if you set the **AboveReferences** field of your river on the map to `True`, you will protect its river colors from overriding.


[mutators]: ./usage_of_mutators.md
[reference_properties]: ./reference_properties.md
[pbr_materials]: ./../pbr_materials/assigning_pbr_materials_to_terrain.md
[refmergemask_brush]: ./ref_merge_mask_brush.md