## 11.2. Viewing XML file of the Mesh

If you open the XML file of the mesh of the truck, you will see the contents of the Fbx file with applied textures.

![](./media/image396.png)

Here you can quickly check the opened model for correctness.

In the **Scene View** panel, you can see the whole hierarchy of the truck skeleton with the CDT objects. If you select an object there, it will be displayed in the main panel and its properties (coordinates, etc.) will be displayed at the lower part of the panel.

Next to the name of the collision object, you can see how the form of this collision object is interpreted by the game engine:

![](./media/image397.png)

The best such form is the "box"; however, "convex" is also suitable; the "mopp" value here means memory optimized partial polytope ([[Havok]](https://cgl.ethz.ch/teaching/former/seminar02/papers/Havok_Overview.pdf) term), which seems to be better than "convex"; if the object is marked as "non-convex", it may cause some issues. For details, see "*2.6.1.1. Collision meshes*" of the **Integration of Trucks and Addons** guide (it is available as **Integration_of_Trucks_and_Addons.pdf** in the same documentation package).

