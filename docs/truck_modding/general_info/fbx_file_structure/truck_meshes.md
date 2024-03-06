# Truck Meshes

## Types of Meshes
Conventionally, there are two main types of meshes in the FBX:

-   *Visual meshes* (or simply "meshes") – They will be responsible for the visuals of your truck and will be rendered.

-   *Collision meshes* (or "cdt meshes") – They will be used for collisions in the physics engine. These meshes are attached to physical bones and, along with them, form physical bodies of the truck. See [Physical Bones and Collision Meshes](./physical_bones_and_collision_meshes.md) for details.

Since they participate in physics calculations, collision meshes typically have very simple forms for a better performance. On the contrary, visual meshes may have commplex shapes and many polygons.

**TIP**: For a simple illustration of creating visual meshes and collision meshes in the FBX of the truck, see [Step 1: Creating 3D Model](./../../getting_started/simple_truck_mod_from_scratch/step_1_creating_3d_model.md) of the [Simple Truck Mod from Scratch](./../../getting_started/simple_truck_mod_from_scratch/overview.md) tutorial.


## Number of Visual Meshes. Polycount
The number of visual meshes is not limited. 

However, every separate mesh causes a separate draw call, which reduces performance. 

On the other hand, the engine does not support too many triangles in the same mesh. The number of triangles is calculated during the export from FBX and is different for every mesh. 

So, we have to look for a balance.

The approximate values of polycount for different parts of the truck model are the following:

-   External part of the truck (without wheels) – up to `60К` triangles and not more.
-   High-res interior of the truck (for the cabin view) – up to `40К` triangles and not more.
-   Other elements (including wheels, visual customization, etc.) – up to `60К` triangles and not more.

**NOTE**: Wheels themselves are separate enities and are not included in the FBX of the truck.


## Low Poly and High Poly Versions of Cab
We recommend making the cab more detailed for a first-person camera, than for an external camera. 

If a mesh has the `lp_` prefix (lp = low poly), it will be visible only from an external camera. Meshes with the `hp_` prefix (hp = high poly) are visible only from a first-person camera. 

Thus, you are able to make two different versions of the cab: 

-   `hp_cab` - The high poly mesh of the cabin that will be used for the first-person camera.

-   `lp_cab` - The low poly mesh of the cabin that will be visible from the outside. 



