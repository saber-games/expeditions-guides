# Distributions for Farming Area

*This topic is valid for SnowRunner only.*  

Now, you need to create a group of distributions for your farming area.

Particularly, you will need to *plan* the process of farming on your field done by the player and create a separate distribution *for every state* of your farming area, including the default one and even the stages that will require no actions from the player (but require changing the texture of the field).

For example, if you want to plant potatoes on your farming area, you can have `6` distributions (states from `0` to `5`), as shown in the table below.

**WARNING**: Regardless of the fact that the `Empty Distribution` distribution will be empty, you still need to assign a **Map** (`.tga`) to them and paint your field on this map in a regular way (however, without selecting **Brushes**). Otherwise, the **State** specified for these distributions will *not* be saved and farming field will not work correctly.

|**State**| **Description of Farming Stage**       | **Description of Distribution**      | **Distribution Name**    |
|---------|----------------------------------------|--------------------------------------|--------------------------|
| `0`     | Initially, your area can be filled with canes. | The default state of the field that corresponds to the `CanesDry` distribution with some dry canes all over the field.                                                        | `CanesDry`               |
| `1`     | Then, the player will be cultivating the field with the Cultivator and the field will become plowed: first – in the areas passed by the Cultivator, and, at the end, entirely.                     | This state corresponds to the plowed ground without any plants, i.e., you can create an `Empty Distribution` (i.e. a distribution without selecting any **Brushes**) for this state.  | `Empty Distribution` |
| `2`     | After that, the player will be planting potatoes on the field, with the help of the Planter. | This state corresponds to small sprouts of potatoes appearing on the field in the areas passed by Planter. I.e., for this stage, you need to create the `PotatoSmall` distribution where the entire field is covered with small sprouts of potatoes.                                       | `PotatoSmall`       |
| `3`     | However, at the end of the planting stage, when the player successfully finishes planting small potatoes, the planted sprouts will grow into the large ones, on the entire field. This stage will require no action from the player. I.e., it will be "hidden" in the UI (will not be displayed as a subtask) and will be passed automatically when the player finishes the previous stage. However, the plants on the field will do change. | For this state you need to create the `PotatoBig` distribution where the entire field is covered with large sprouts of potatoes. | `PotatoBig` |
| `4`     | Now, when the potatoes have grown, the player will be harvesting them with the help of the Harvester, and, in the areas passed by the Harvester, potato tubers will appear.    | This state corresponds to the `PotatoCore` distribution representing the potato tubers left on the field after Harvester.  | `PotatoCore`   |
| `5`     | Finally, after the stage of harvesting of potatoes is finished, the potato tubers will disappear from the field and it will be empty again. This stage again will require no action from the player (will be automatically passed and "hidden" stage), but the field will do change again.  | This state corresponds to the ground without any plants. I.e., you can create an `Empty Distribution` (i.e. a distribution without selecting any **Brushes**) again for this state.    | `Empty Distribution` |

As you can see, all these distributions will appear one after the other. Every next distribution will appear:

-   either gradually, only in sections of the field passed by farming equipment (e.g. when the player is cultivating with the Cultivator, or planting with the Planter, or harvesting with the Harvester),

-   or, on the entire field at once (e.g. when small potato sprouts "grow" automatically into the big ones),

-   or, in both of these ways (e.g. after the player successfully finishes cultivating to the specified percentage, the entire field will appear plowed, even in sections that were not passed, and so on).

However, regardless of the manner of appearance, the *order* of appearance of these distributions is always fixed.

To define this order, in the **State** field within the properties of every distribution you will need to specify its number, starting with zero and without omissions.

![](./media/image366.png)

**WARNING**: There is an important nuance for `Empty Distributions`, if you want to include them in your farming cycle. Regardless of the fact that these distributions will be empty, for every such distribution, you need to assign a Map (`.tga`) to it and paint your field on this map in a regular way (however, without selecting **Brushes**). Otherwise, the **State** specified for the distribution will *not* be saved and farming field will not work.

However, all these distributions are created for the same farming area and the game should be able to identify that. So, along with specifying **State** numbers, you also need to group them and link the resulting group of distributions to the zone created at Step 1.

To do this:

1.  Create a *group* of distributions. This can done by right-clicking the **Distributions** section in the **Scene View** panel and selecting **Distributions – Add Group**. See [Groups](./../../getting_started/ui_overview/groups.md) for details.
    
    **NOTE**: Initially, the created group will have a number as a name. You can specify the proper name of the group by selecting the created group in the **Scene View** panel and changing the **Name** field in its properties.

2.  Assign all distributions created for the farming area to this group. This can be done by selecting a Distribution and changing the value of the **Group** field in its properties, see [Groups](./../../getting_started/ui_overview/groups.md) for details. Or, alternatively, after creating a group, you can create new distributions directly in it, by right-clicking the group and selecting **\<name_of_the\_ group\> -- Add Distribution**.

3.  *Importantly*, specify the name of this group of distributions in the **Distributions group name** field of the zone that you have created for your farming area (see [Step 1](./zone_for_farming_area.md) on the farming zone for details). This will link the zone to the distributions group.
    
    **NOTE**: The value specified in the **Distributions group name** field must be *exactly* the same as the name of the distributions group, otherwise the game will not find these distributions and the farming area will not work.
    
    ![](./media/image367.png)

Except nuances described above, every distribution from the set is added in a standard way, see [Adding Multiple Objects via Distribution](./../distributions/adding_multiple_objects_via_distribution.md) for details. The borders of the distribution area typically match the borders of the created farming area zone.

![](./media/image368.png)

**NOTE**: For obvious reasons, if you change the location or borders of the farming area zone, you need to repaint all distributions related to this farming area.


