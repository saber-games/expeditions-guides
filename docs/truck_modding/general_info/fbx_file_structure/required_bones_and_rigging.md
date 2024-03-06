# Required Bones and Rigging

## Required Bones
Both in *Expeditions* and *SnowRunner*, there is a required set of bones that is necessary for the truck mod to operate. 

This set contains both [physical][physical] and [non-physical][non-physical] bones.

Particularly, this minimum set is the following:

-   `BoneChassis_cdt` – Physical bone of the Chassis.
-   `BoneAxleRear` – Non-physical bone of the rear Axle.
-   `BoneCabin_cdt` – Physical bone of the Cabin/Body. *(Optional, see NOTE below.)*
-   `BoneAxleFront` – Non-physical bone of the front Axle.
-   `BoneRack` – Non-physical bone of the Steering Rack.
-   `BoneRackLeft` – Non-physical bone of Left Hub that will be attached to the left wheel.     
-   `BoneRackRight` – Non-physical bone of Right Hub that will be attached to the right wheel.    

**NOTE**: Actually, only `1` physical bone is absolutely required for the truck. However, we have added `2` such bones (`BoneChassis_cdt` and `BoneCabin_cdt`) to this list, since the typical physics behavior of the truck in the game will be better in this case. 

The *names* of the bones listed above may vary.

Only the *role* they play in the FBX of the truck is important. And, this role is defined not only by this bone itself and its rigging, but also by its XML description. For example, the game will *not* identify the `BoneAxleFront` bone above as the bone of the Axle until you specify the name of this bone in the attribute of the [`<Axle>`][axle] tag, in the XML class of the truck.

**TIP**: For an illustration of the process of creating a minimum set of bones for the truck and forming their sample hierarchy, see [Step 1: Creating 3D Model][step_1] of the [Simple Truck Mod from Scratch][tutorial] tutorial.

However, the number of bones is not limited by the bones listed above. You can create as many additional bones as necessary.

## Rigging
There is an important difference in rigging between the [Collision Meshes][collision_meshes] that participate in physics and [Visual Meshes][visual_meshes] that are only rendered.

Particularly: 

-   Collision Meshes need to be *parented* to Physical Bones. I.e., they need to be parented to physical bones *as a whole*, without skinning.
-   Visual Meshes need to be *skinned* to bones. I.e., they need to be parented to the bones of the truck with *weights* of the mesh vertices.

**TIP**: For an illustration of the process of attaching collision meshes and visual meshes to bones, see [Step 1: Creating 3D Model][step_1] of the [Simple Truck Mod from Scratch][tutorial] tutorial.

All bones from the minimum set (see above) must be rigged. 

[Physical][physical] bones must have collision meshes that are parented to them, by their definition. 

But, all [non-physical][non-physical] bones must be skinned too. 

For example, if we create a `BoneRack`, configure it in the [`<SteeringRack>`][steeringrack] tag in the XML description, but forget to skin at least one mesh vertex to it, our truck will be crashing the game if you try to spawn it on the Proving Grounds and the Editor will output the corresponding error if you try to open this truck in it.

[physical]: ./physical_bones_and_collision_meshes.md
[non-physical]: ./non_physical_bones.md
[step_1]: ./../../getting_started/simple_truck_mod_from_scratch/step_1_creating_3d_model.md
[step_5]: ./../../getting_started/simple_truck_mod_from_scratch/step_5_creating_xml_file_of_truck_class.md
[tutorial]: ./../../getting_started/simple_truck_mod_from_scratch/overview.md 
[collision_meshes]: ./physical_bones_and_collision_meshes.md
[visual_meshes]: ./truck_meshes.md
[axle]: ./../../tags_and_attributes_of_trucks/truck/truckdata/axles/axle/index.md
[steeringrack]: ./../../tags_and_attributes_of_trucks/truck/truckdata/steeringrack/index.md