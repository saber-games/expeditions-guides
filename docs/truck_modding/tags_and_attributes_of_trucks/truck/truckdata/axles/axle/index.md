# Axle

The `<Axle>` tag describes the axle of the truck.

This tag contains a link to the bone that is *not* from the physical model. See [Non-Physical Bones][non_physical_bones_axles] for details.

The operation logic here is the following:

1.  The system automatically locates two nearest opposite wheels (or just one wheel, if the `IsIndependent` attribute is set to `true`).

2.  The bone orientates on them and takes the middle position between them (or is attached to the nearest one).

The position of this bone must necessarily coincide by the `X` and `Y` axes with the position of the bones that it must interact with. Otherwise, the bone will simply occupy the middle, possibly unexpected, position when the simulation starts.

Attributes:

-   `Frame="BoneAxle"`  
    *(Mandatory.)* The bone that the axle is attached to during skinning.

-   `IsIndependent="true"`  
    Whether the suspension is independent or not.

[non_physical_bones_axles]: ./../../../../../general_info/fbx_file_structure/non_physical_bones.md#axles

