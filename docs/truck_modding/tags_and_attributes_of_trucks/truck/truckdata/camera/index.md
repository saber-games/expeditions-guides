# Camera

The `<Camera>` tag in [`<TruckData>`][truckdata] describes the external camera.

-   `Center="(-1.7; 0; 0)"`  
    *(Mandatory.)* Point that the external camera is directed to.


-   `RadiusMultiplier="0.8"`  
    Scale of the distance to the Center. By default: `1`. For large trucks, it is typically equal to `1.1`, For scouts – to `0.8`.


-   `ParentFrame="BoneCabin_cdt"`  
    The bone from the physical model hierarchy, which the camera is attached to. If the parameter is not specified, then it will be the root bone of the physical model.


[truckdata]: ./../index.md