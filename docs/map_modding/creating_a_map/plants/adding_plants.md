# Adding Plants

The list of models does not include plants. They are added to the scene separately.

The way you add plants to the map depends on how many plants you want to add:

-   If you want to add a single plant, it can be done as described in this section.

-   If you want to add *multiple plants at once*, it can be done with the help of the appropriate [**Distribution**][distribution].

Single plants are added to the map similarly to the models. You right-click the scene (or the **Plants** section in the **Scene View**) and select **Add Plant** from the context menu. After doing this, the window with the list of the plants will open. You can search the list and double-click the necessary plant to add it to the map.

**NOTE**: Every plant in this window has its type displayed next to it: "**STATIC**", "**DYN**", "**DESTR**", "**DESTR+CHUNKS**". For information on these types, see [Types of Models.Collisions](./../models/types_of_models_collisions.md). These types for plants work similarly to similar model types.

Moving, rotating, and scaling the plants are also performed similarly to [models][models].

There are practically no differences. However, in the settings of the plant itself, there are several additional parameters:

-   **Do Land** - If this option is set to **True**, the plant will always be attached to the terrain. This allows you to avoid situations when a tree is hanging in the air.

-   **Perpendicularity** - Perpendicularity to the coordinate grid. This is a useful setting for trees growing on steep hills and mountains. The value of this parameter is specified by the slider that appears to the right of the value when you click it.

**NOTE**: For information on the **Collision Type** and **Freeze Physics** properties of a plant, see [Types of Models.Collisions](./../models/types_of_models_collisions.md). These settings work for plants the same way they work for models.


[distribution]: ./../distributions/adding_multiple_objects_via_distribution.md
[models]: ./../models/adding_models.md