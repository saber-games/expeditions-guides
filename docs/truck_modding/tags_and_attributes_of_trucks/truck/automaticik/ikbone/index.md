# IKBone

Inverse kinematics bone.  

See [Non-Physical Bones](./../../../../general_info/fbx_file_structure/non_physical_bones.md#automaticik) for details.


Attributes:

-   `ModelFrame="BoneTieRodHinge2"`  
    *(Mandatory)* Name of the bone.

-   `ParentFrame="BoneTieRod_cdt"`  
    *(Mandatory)*  The name of the bone of the physical model, to which the root of the IK-chain is attached. It is used only for root and required for it.

-   `AttachToFrame="BoneTieRod_cdt"`  
    *(Mandatory)* The name of the bone of the physical model, to which the last bone of the IK-chain is attached. It is used only for the last bone of the IK-chain and required for it.

-   `AttachOffset="(0; 0; 0)"`  
    The shift of the "joint". By default: `(0; 0; 0)`.

