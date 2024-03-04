# Body

The `<Body>` tag corresponds to a physical body (or a physical bone).

A physical body is the combination of the attachment point and the collision mesh that participates in Havok physics. The physical body can collide with other physical bodies. The physical body can be attached to its parent by various means: move linearly relative to its parent within some limits, or swing along one or several axes, or be fixed tightly, etc. The physical body has some physical characteristics: mass, friction, and so on.

The hierarchy of bones in the FBX file must be the same as the hierarchy of the bodies in the description of the physics model. This hierarchy must have only one root physical body.

Attributes:

-   `NetSync="pv"`  
    Network synchronization of the `p`osition and `v`elocity of the physical body.
    Values: `p`, `v`, `pv`.

-   `ModelFrame="BoneCabin_cdt"`  
    *(Mandatory.)* Name of the bone from the Fbx file.

-   `Mass="1700"`  
    *(Mandatory.)* Mass of the physical body. By default: `0`. Limits: `[0;1000000]`.

-   `CenterOfMassOffset="(0.2; -0.2; 0)"`  
    The shift of the center of mass of the body relative to the center of mass calculated by Havok. Havok calculates this value based on the shape of the collision mesh.

-   `GravityFactor="0.7"`  
    Coefficient of the gravity influence. Default value: `1`, Limits: `[0;1000]`.

-   `AngularDamping="0.7"`  
    Viscosity of the environment for angular movements. Default value: `0.05`. Limits: `[0;1000000]`.

-   `LinearDamping="0.7"`  
    Viscosity of the environment for linear movements. Default value: `0`. Limits: `[0;1000000]`.

-   `Friction="0.7"`  
    Friction when interacting with other physical bodies. Default value: `0.5`, Limits: `[0;1000]`.

-   `ImpactType="Truck"`  
    This parameter is responsible for special effects. The `Truck` value means that a collision will result in the appearance of sparks and the playing of the appropriate collision sounds.

-   `Collisions="None"`  
    Type of the collision. Values:

    -   `Default` – default value. Bones of the truck and its add-ons collide with all collision objects, but not with each other.

    -   `None` – the bone does not collide with anything.

    -   `All` – the bone collides both with external objects and with bones of the truck and addons.

    -   `Internal` – the bone collides with bones of the parent truck and with bones of its addons.

    -   `OnlyWithAll` – the bone collides only with bones that have the `All` type of collision specified.

-   `ForceBodyParams="true"`  
    Only \"large\" bodies of the truck interact with mud and water. But small ones do not. Which are large and which are small is determined automatically. However, you can force this interaction by enabling this parameter.

-   `NoFoliageCollisions="true"`  
    Disables collision with grass and foliage.

