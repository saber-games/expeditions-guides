# TruckWheel

The `<TruckWheel>` tag acts as the root tag of the wheel class file, when a wheel is described as a single entity. See [Wheels Overview](./../../general_info/wheels_description/wheels_overview.md) and subsequent topics for details.

**NOTE**: This tag is used only for wheels, where a tire and a rim are a single entity. For similar tag in the case when a wheel is described as a set of tires and rims, see [TruckWheels](./../truckwheels/index.md).

Attributes:

-   `Mesh="wheels/trailer_sideboard_2"`  
    Path to the FBX file of a wheel.

-   `Mass="100"`  
    Mass of the wheel.

-   `Radius="0.594"`  
    The radius of the wheel, which is used to create the collision cylinder in Havok. The wheel described in such a way cannot be scaled. Therefore, this radius must match the outer radius of the tire in the FBX file.

-   `Width="0.44"`  
    Width. This parameter is used to create a collision cylinder in Havok, to determine the area where the mud is sticking to the tread of the tire and to identify the width of the track. The specified width should match the width of the tread in the FBX file.

-   `DamageCapacity="50"`  
    Amount of the allowed damage. Value range: `[0; 64000]`.

