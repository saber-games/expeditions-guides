# Limitations and Recommendations for Rivers

You can add multiple rivers to the map. However, **two rivers should have the same settings, if they are within the same terrain block**.

You cannot merge rivers with and without the defined **Flow**. The river colors (**Clean Type** and **Muddy Type**) of the merged rivers should also match. Otherwise, one of the rivers within a terrain block will use river colors of another river and there will be a sharp border in the color of the river on the edge of the terrain block:

![](./media/image125.png)

Moreover, on the banks of the river, the surface of the water and the surface of the terrain should ***not*** have the same height. (The height of the terrain should be a little bit more.) Otherwise, the border between the water and the terrain will look unpleasant:

![](./media/image126.png)

To fix this issue, you typically need to increase the height of the terrain a little bit.

