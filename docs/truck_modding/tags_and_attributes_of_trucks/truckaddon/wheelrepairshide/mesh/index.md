### 14.1.1. \<Mesh\>

There may be several of these tags.

Attributes:

-   Frame=\"wheel1\"\
    The mesh name that is defined in the Fbx file.


-   HideThreshold=\"0.4\"\
    Threshold for hiding. In percent.\
    **Usage**: Consider that the number of spare wheels in the TruckData tag is two (WheelRepairsCapacity = \"2\"). In this case, to hide two wheels as they are spent, you will need:\
    \-- for one Mesh tag, specify any HideThreshold value in the half-interval of \[0.5; 1).\
    \-- for the second Mesh tag, specify the value in the half-interval of \[0; 0.5).\
    If you specify a value of 0.4 in this example, then the wheel1 mesh will be hidden when both spare wheels are used up.\
    ![https://image.mod.io/members/28d1/2079993/profile/image_51.png](./media/image65.png)

