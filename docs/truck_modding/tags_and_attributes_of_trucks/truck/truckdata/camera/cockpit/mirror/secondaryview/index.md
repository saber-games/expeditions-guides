# SecondaryView

The `<SecondaryView>` tag within [`<Mirror>`][mirror] describes the *dependent mirror*.

The image on this dependent mirror is taken from the camera described in the [`<Mirror>`][mirror] parent tag.

I.e., this tag does not create the new camera but takes the image from the existing main mirror.

Attributes:

-   `MeshFrame="mirror_left"`  
    *(Mandatory.)* Name of the mesh, defined in the FBX file.


-   `Pos="(1; -0.05; 0)"`  
    *(Mandatory.)* Position of the center of the mirror. For convex mirrors, we recommend to specify the position of the center using the coordinates that lie within the plane of the base of the mirror. Usage of the coordinates that lie within the plane touching the "top" of the mirror is not recommended. See the illustration shown for the `Pos` attribute of [`<Mirror>`][mirror].


-   `ClipDir="(-0.94; 0; -0.342)"`  
    *(Mandatory.)* Normal vector of the plane of the mirror, from the driver's side of this plane.


-   `FOVScale="1"`  
    Scale of the field of view. The value of the `FOVScale(secondary_mirror)/FOVScale(primary_mirror)` ratio defines the part of the texture of the main mirror that will be visible in the dependent mirror. If `FOVScale (secondary) = FOVScale (primary)` then the image will be duplicated. If `FOVScale (secondary)` \< `FOVScale (primary)` then only part of the image from the main mirror will be displayed in the dependent mirror. `FOVScale` of the dependent mirror cannot be more than the `FOVScale` of the main mirror.


-   `CurveAngle="10"`  
    Curvature of the texture, in degrees. This parameter allows you to visualize that objects in mirrors look farther than they are. Please, do not set a very high value of this parameter (about `60` degrees is a recommended value). Otherwise, the artifacts near the edges will be visible. Default value: `60`.


-   `UnskinnedCoordinates="false"`  
    The coordinate system in which the mirror parameters are specified. The `false` value means that the coordinates are calculated taking into account the initial transformations of the bones of the skeleton of the truck. The `true` value means that the coordinates are calculated from the positions of the vertices of the mirror. These values correspond to two independent algorithms for calculation of coordinates that are most often indistinguishable.  
    The default value is `false`.

[mirror]: ./../index.md