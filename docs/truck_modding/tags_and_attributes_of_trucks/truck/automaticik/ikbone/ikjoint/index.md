# IKJoint

The joint of the IK bone.

An analogue of the `<Constraint>` tag in the physical model.

See [Non-Physical Bones](./../../../../../general_info/fbx_file_structure/non_physical_bones.md#automaticik) for details.

Attributes:

-   `AxisLocal="(1; 0; 0)"`    
    *(Mandatory)*  Direction vector.

-   `Type="Hinge"`  
    *(Mandatory)* Type of the joint.
    Values:

    -   `Hinge` - rotation around the AxisLocal axis.

    -   `Slider`- linear movement along the AxisLocal axis.

    -   `Hinge2` - rotation around axes perpendicular to the `AxisLocal` axis.

