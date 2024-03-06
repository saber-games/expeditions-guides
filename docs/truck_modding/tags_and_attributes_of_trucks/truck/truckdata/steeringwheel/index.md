### 8.1.4. \<SteeringWheel\>

Steering wheel.

The only attribute here is the bone that the steering wheel is bound to during skinning. This bone is not part of the physical model and its behavior is different from the behavior of the other bones. The mesh of the steering wheel is always skinned to the single bone; however, cab may be skinned to multiple bones. The influence of the other bones on the steering wheel bone is determined by the weights of the nearest vertex of the mesh that is skinned onto other bones.

Attribute:

-   Frame=\"BoneSteering\"\
    **\*** The name of the bone on which the steering wheel is skinned.

