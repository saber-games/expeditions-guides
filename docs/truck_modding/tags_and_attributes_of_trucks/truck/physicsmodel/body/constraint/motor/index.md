# Motor

Motor ("movement muscle").

If the [`<Body>`](./../../index.md) is a bone, the [`<Constraint>`](./../index.md) is the joint between the bones, then the `<Motor>` will be the muscle. If `<Motor>` is not described, then the bone will hang loose under the influence of gravity and inertia according to the limitations of the [`<Constraint>`](./../index.md).  

**NOTE**: `<Motor>` is not used with the constraints of the following types: `Ragdoll`, `UnlimitedHinge`, and `Rigid`.

Attributes:

-   `Type="Spring"`  
    Type of the motor.  
    Values:

    -   `Spring` - a spring.  
    -   `Position` - a position that can be controlled by pressing certain buttons when this constraint is a Powered Constraint or Controlled Constraint.  
        For details on Powered Constraints, see [Powered Constraints: Overview](./../../../../../../additional_info_on_trucks/powered_constraints/powered_constraints_overview.md) and [`<PoweredConstraints>`](./../../../../poweredconstraints/index.md).  
        For details on Controlled Constraints, see [`<ControlledConstraints>`](./../../../../controlledconstraints/index.md) and [Controls for Controlled Constraints of an Addon](./../../../../../../additional_info_on_trucks/addons_selected_info/17_1_2___controls_for__controlled__constraints_of_an__addon.md).

-   `Spring="0.5"`
    This attribute is used for the `Spring` type of the motor. Its value is the stiffness of the spring.   
    Default value: `0`, limits: `[0, 1000000000]`.

-   `Damping="0.02"`  
    Damping.  
    Value:

    -   `Spring`: by default: `0`, limits: `[0, 1000000000]`.
    -   `Position`: by default: `1`, limits: `[0, 1]`.

-   `Tau="0.9"`  
    This attribute is used for motors of the `Position` type that are controlled. A coefficient that determines the effect of the Havok physics on the constraint when it is trying to reach a given position. If `Tau` equals to `0`, then the physical object will move according to the surrounding physics, without the influence of the controlling at all. If `Tau` equals to `1`, then the surrounding physics will not affect the controlling at all.  
    Default value: `0.8`, Limits: `[0, 1]`.

-   `Force="0.9"`  
    This attribute is used for motors of the `Position` type that are controlled. The force applied to the body that allows it to reach a given position. Default value: `0`, Limits: `[0, 1000000000]`.



