# Shaker

The `<Shaker>` tag describes the behavior of the particular [non-physical "shaker" bone][shaker_def].

I.e., this tag describes non-physical (independent of Havok physics) rattling of the bone that depends on the current engine power. 

The bone rattles according to the noise that has the amplitude and the frequency.


Attributes:

-   `Frame="BoneExhaust"`  
    *(Mandatory.)* The name of the shaker bone.


-   `MinAngle="(0; 0.5; 1)"`  
    The maximum angles of rotation of the bone when the engine is running, but the vehicle is standing (not moving).


-   `MaxAngle="(0; 2; 4)"`  
    The maximum angles of rotation of the bone when the engine is working at the limit of its power.


-   `MaxOffset="(0.1; 0.1; 0.01)"`  
    Maximum linear bone shifts when the engine is working at the limit of its power.


-   `MaxFrequency="0.2"`  
    Maximum frequency of rattling. Values: `[0; 1000]`, by default: `1`.


-   `LimitDirectionX="Positive"`  
    Used to stop negative or positive rotation in the direction of the `X` axis. Values: `Positive`, `Negative`. Particularly, it was used to ensure the correct behavior of the exhaust pipe cap (it should be closed, when the engine is off; when the engine is running, the cap should move only in one direction; the cap should not intersect with the exhaust pipe itself).


-   `LimitDirectionY="Positive"`  
    Similarly to `LimitDirectionX`.


-   `LimitDirectionZ="Positive"`  
    Similarly to `LimitDirectionX`.


[shaker_def]: ./../../../../../general_info/fbx_file_structure/non_physical_bones.md#shakers