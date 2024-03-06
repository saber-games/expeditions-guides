# Gauge

The `<Gauge>` tag describes the behavior of an arrow on the Dashboard.

A single unique arrow of the dashboard corresponds to a single FBX file.

In this file, the arrow is located in the zero coordinates, lies in the `OXZ` plane, and is directed along the `X` axis. 

There is no parent frame (bone) among the parameters of the arrow. It is attached to the nearest vertex of the truck.

Attributes:

-   `Mesh="trucks/arrows/mod_scout_arrow_01"`  
    *(Mandatory.)* Path to the Fbx file of an arrow `.../meshes/trucks/`. For example, `trucks/arrows/mod_scout_arrow_01` for `...\meshes\trucks\arrows\mod_scout_arrow_01.fbx`


-   `Org="(0.631; 3.501; -1.114)"`  
    *(Mandatory.)* Position of the arrow.


-   `Dir="(-0.944; 0.33; 0)"`  
    *(Mandatory.)* Direction vector, which is normal to the plane of the gauge dial and is directed inside the cab (in the coordinates of the FBX arrow it is `"(0; 1; 0)"`).


-   `OutputAngles="(-110; 30)"`  
    *(Mandatory.)* The range in which the arrow can rotate along the local `OY` axis.


-   `Scale=".9"`  
    The size of the arrow can be changed simultaneously by all axes (e.g. Scale=".9" equals to "(0.9; 0.9; 0.9)") or by particular axes only (e.g. "(1; 0.5; 1)").


-   `Damping="0.9993"`  
    *(Mandatory.)* Arrow response to the change of input value.


-   `InputRange="(0;1)"`  
    The range of input values. Depends on `InputType`. Most frequently, it is on/off (i.e. `(0;1)`), since after the start of the engine most arrows proceed to the particular value and remain there still. However, values similar to speed can be set up depending on what is written on the speedometer scale. Default value: `"(0; 1)"`.


-   `InputType="engineEnabled"`  
    *(Mandatory.)* Name of the input. Values: `"speed"`, `"rpm"`, `"fuel"`, `"none"`, `"handbrake"`, `"engineEnabled"`, `"headlight"`, `"difflock"`, `"difflockStress"`.

