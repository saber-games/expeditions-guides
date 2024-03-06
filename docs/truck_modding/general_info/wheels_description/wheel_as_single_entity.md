# Wheel as Single Entity

If a wheel is set up as a single entity, then:

-   The FBX file of the wheel contains the whole geometry of the **left** wheel. 

-   Which part of the wheel is a tire (that can be deformed) and which part is the rim – is determined by the parameter in the XML file of the mesh of the wheel.

-   The XML of the class of the wheel contains all characteristics of the wheel, such as the following:
    -   friction
    -   tire stiffness
    -   wheel mark
    -   the mass of the wheel
    -   radius and width of the wheel in Havok

**NOTE**: If wheels of the truck are described in this way, then they cannot be changed. Moreover, in this case, there are no tire and wheel selection options in the menu of the Garage.




