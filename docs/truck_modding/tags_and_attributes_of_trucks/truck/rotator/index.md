# Rotator

The `<Rotator>` tag describes the bone that rotates when the engine of the truck is turned on.

Attributes:

-   `Frame="BoneRotator"`  
    The non-physical bone, which is rotated.

-   `EngineTorqueFactor="0"`  
    *(Mandatory.)* The effect of the engine speed on the rotation speed. If the value equals `0`, then the bone will be rotating with `RotationSpeed` when the engine is started and will not accelerate with the increase of the engine speed. If the engine is turned off, the rotator will not rotate.

-   `RotationSpeed="3"`  
    *(Mandatory.)* Speed of rotation. By default: `0`.

-   `RotationAxis="(0; 1; 0)"`  
    *(Mandatory.)* The rotation axis. By default: `(0; 1; 0)`.

-   `Name="Lightbar"`  
    The name of the rotator.
