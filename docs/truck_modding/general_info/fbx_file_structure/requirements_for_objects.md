# Requirements for Objects

Requirements for Objects in the FBX file are as follows.

**All objects and meshes** must have identity scale. For example:

-   in Blender - it corresponds to the `(1, 1, 1)` scale.

-   in Maya - to the `(1, 1, 1)` scale,

-   in 3ds Max - to the `(100, 100, 100)` scale.

Ensure that the **root bone** and **all truck meshes** have **identity rotation** of `(0, 0, 0)`.

A truck, addon, and (in *SnowRunner*) a semi-trailer can have **only one root bone**. All other bones must be lower in the hierarchy.

A truck or semi-trailer must have **at least one physical bone**. 

The physical bone must have a **collision mesh**. All bones and meshes of trucks and semi-trailers must have **skin modifiers**.

Addons may have no bones at all (e.g., small addons such as lamps, posters, and other addons that do not need a collision). If an addon has bones, then these bones must have skin modifiers and there must be at least one physical bone.

Wheels have no bones or collision objects. Wheel collision is defined in XML.

