# Rear

The `<Rear>` tag contains settings for the "leaning out of the window" mechanics. It is used when the player starts looking back in the Cockpit view.

Attributes:

-   `HorTransitionStart="-1.2"`  
    The angle in radians at which the camera shift begins.


-   `HorTransitionEnd="-1.5"`  
    The angle in radians at which the camera shift ends.


-   `LimitsVer="(-1.2; 0.2)"`  
    *(Mandatory.)* Maximum limits for the vertical rotation of the camera after its shift. Value in radians.


-   `RollAngle="-15"`  
    *(Mandatory.)* Maximum rotation angle by `OX` (twist rotation, inclination of the head to left or right). The value of this angle is `0` when the camera is turned by `HorTransitionStart`, and `RollAngle` when the camera is turned by `HorTransitionEnd`. The value of this parameter is in degrees.


-   `ViewDir="(1; -0.05; 0)"`  
    *(Mandatory.)* Direction vector of the camera when looking back.


-   `ViewPosOffset="(0.25; -0.1; 0.7)"`  
    *(Mandatory.)* Shift of the camera when looking back.

