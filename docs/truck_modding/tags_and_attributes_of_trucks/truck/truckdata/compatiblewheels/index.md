# CompatibleWheels

`<CompatibleWheels>` tags within [`<TruckData>`][truckdata] describe wheels that are compatible with the truck and available for it.

This tag is used only for wheels that are "sets of tires and rims". It may be used multiple times, to install different types of wheels or the single type with different scaling.

**NOTE**: If the [`<Wheels>`][wheels] tag sets the default type of the wheel, then the `<CompatibleWheels>` tag should exist for the same type of the wheel.


Attributes:

-   `Type="wheels_medium_double"`  
    *(Mandatory.)* Type. Name of the XML class of the wheels, file from the `.../classes/wheels/` folder.


-   `Scale="0.55"`  
    *(Mandatory.)* The even scale of the wheel. We make wheels with the radius equal to `1` meter, so this `Scale` is equal to the actual size of the wheel on the truck.

-   `OffsetZ="0.1"`  
    Shift of the wheel along the `Z` axis relative to the position indicated in the `Pos` attribute of the [`<Wheel>`][wheel] tag. This parameter allows us to install wheels of different widths on the truck without intersections with it. If only the `OffsetZ` parameter is specified, all wheels will be shifted by the specified value, regardless of the `Location` of the [`<Wheel>`][wheel].

-   `RearOffsetZ="0.1"`  
    Shift of the rear wheel along the `Z` axis. If it is specified, wheels with `Location = "rear"` of the [`<Wheel>`][wheel] will be shifted by the specified value.


[truckdata]: ./../index.md
[wheels]: ./../wheels/index.md
[wheel]: ./../wheels/wheel/index.md