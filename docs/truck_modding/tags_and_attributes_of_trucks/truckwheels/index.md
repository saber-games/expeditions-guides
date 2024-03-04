# TruckWheels

The `<TruckWheels>` acts as a root tag of the wheel type class file, when a wheel is described as a set of tires and rims. See [Wheels Overview](./../../general_info/wheels_description/wheels_overview.md) and subsequent topics for details.

This tag describes a type of a wheel that contains several interchangeable tires and rims.

Attributes:

-   `DamageCapacity="50"`  
    *(Mandatory.)* Amount of allowed damage. Value range: `[0; 64000]`.

-   `Radius="1"`  
    *(Mandatory.)* Wheel radius. It should match the outer radius of the tire in the FBX file. This is the radius of the collision object of the wheel in Havok. We recommend making wheels with a radius of `1` meter. In this case, when the wheel is installed on the truck, the value of the `Scale` parameter from the `<CompatibleWheels>` tag will correspond to the desired wheel radius for a particular truck. See [CompatibleWheels](./../truck/truckdata/compatiblewheels/index.md).

-   `Width="0.58"`  
    *(Mandatory.)* Wheel width. The specified width should match the width of the tread in the FBX file. This is the height of the collision cylinder of the wheel in Havok. It is used to determine the area where the mud is sticking to the tread of the tire and to identify the width of the track.

-   `RadiusRear="1.2"`  
    The radius of the rear wheel. It must match the radius of the mesh of the rear wheel that has the `tire_back` name. By default is the same as `Radius`.

-   `WidthRear="1.2"`  
    The width of the rear wheel. It must match the width of the mesh of the rear wheel that has the `tire_back` name. By default is the same as `Width`.

