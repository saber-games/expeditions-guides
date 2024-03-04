# WheelSoftness

The `<WheelSoftness>` tag within `<TruckWheel>` describes softness of wheel tires when a wheel is a single entity.

**NOTE**: If you a creating a wheel as a set of tires and rims, this tag should be used for *tires* (within `<TruckTire>`). See [WheelSoftness](./../../truckwheels/trucktires/trucktire/wheelsoftness/index.md). 

Attributes:

-   `RadiusOffset="0.02"`  
    *(Mandatory.)* The radius of the collision object of the wheel equals to the difference between the radius of the wheel (the `Radius` parameter specified in the `<TruckWheel>` tag) and this offset (`RadiusOffset`).   
    Default value: `0`. Value range: `[0; 0.25]`.

-   `SoftForceScale="0.32"`  
    *(Mandatory.)* The multiplier of the body momentum in case of collisions with other collision objects.  
    Default value: `1`. Value range: `[0.1; 1]`.

