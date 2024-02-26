# Suspension

Suspension. Determines the interaction of the wheel with the truck.

Attributes:

-   `WheelType="rear"`  
    *(Mandatory).* Type of the wheel. Allowed values: `front` аnd `rear`. In the XML file of the truck, it is described by the `Location` attribute of the [`<Wheel>`](./../../../truck/truckdata/wheels/wheel/index.md) tag.

-   `Height="0.15"`  
    *(Mandatory).* Suspension height. Wheel shift along the -OY axis relative to the position defined by the `Pos` attribute of the [`<Wheel>`](./../../../truck/truckdata/wheels/wheel/index.md) tag in the truck description.  
    Value range: `[-1000;1000]`.  

-   `Strength="0.15"`  
    *(Mandatory).* Suspension stiffness. Value range: `[0; 1000]`.

-   `Damping="0.3"`  
    Damping.

-   `SuspensionMin="0.3"`
    *(Mandatory).* Minimum suspension travel. I.e., the position that the wheel can take in the case of the full lowering of suspension.  
    Value range: `[-1000; 1000]`.  

-   `SuspensionMax="0.3"`  
    Maximum suspension travel. I.e., the position that the wheel can take if the suspension is in the operating condition and its stiffness is a zero when the wheel hangs in the air.  
    Default value: `1`.  
    Value range: `[-1000; 1000]`.  

-   `BrokenSuspensionMax="0.25"`  
    *(Mandatory).* Maximum suspension travel for a broken suspension.  
    Value range: `[-1000; 1000]`.  
    
