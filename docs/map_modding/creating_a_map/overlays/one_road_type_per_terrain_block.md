# One Road Type per Terrain Block

The engine of the game has a technical limitation: it can render only one *textural* overlay (an overlay that is rendered over terrain) within 1 terrain block.

So, you are not able to use different types of roads within 1 terrain block. The border of the terrain block is marked by the red cube that appears after clicking the terrain with the left mouse button.

If you add multiple types of roads to a single block, then the part of them may become invisible. However, you can add textural and non-textural overlays to one block (e.g. the road + wires).

However, there is a workaround for this. If you need to create an intersection of roads of different types within 1 terrain block, you can do the following:

1.  Place the main parts of different roads on different terrain blocks.

2.  In the intersection area, paint the terrain between roads using the PBR material where the similar texture is selected as one of the layers.

    ![](./media/image108.png)

As an alternative option, you can hide the intersection under the layer of snow, mud, etc.

