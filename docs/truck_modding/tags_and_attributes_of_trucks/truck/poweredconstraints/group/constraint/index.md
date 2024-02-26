# Constraint

Description of a Powered Constraint.

**NOTE**: The `<Constraint>` tag within the [`<Group>`][group] tag has a meaning different from the *regular* [`<Constraint>`][physicsmodel_constraint] described within the [`<PhysicsModel>`][physicsmodel] and also has different attributes. The [`<PhysicsModel>`][physicsmodel] → [`<Constraint>`][physicsmodel_constraint] describes the constraint *itself*, the [`<PoweredConstraints>`][poweredconstraints] → `<Constraint>` describes the *"powered" nature of this constraint*.

The [`<PoweredConstraints>`][poweredconstraints] → `<Constraint>` tags must be tied to the corresponding *regular* [`<PhysicsModel>`][physicsmodel] → [`<Constraint>`][physicsmodel_constraint] tags by thier `Name`. I.e., they must have the same value of the `Name` attribute.

**NOTE**: The [`<Motor>`][motor] tag within a [`<PhysicsModel>`][physicsmodel] → [`<Constraint>`][physicsmodel_constraint] tag must have `Type` attribute equal to `Position`, if this constraint is tied to a [`<PoweredConstraints>`][poweredconstraints] → `<Constraint>` tag as described above.

For details, see [Powered Constraints: Overview](./../../../../../additional_info_on_trucks/powered_constraints/powered_constraints_overview.md) in the **Additional Info on Trucks**.

Attributes:

-   `InitialFix="true"`  
    If enabled, then, prior to being activated (either by the player pressing a button, or by internal code of the game), a constraint behaves like a fixed constraint. That is, if the force of the constraint is small, then, for example, the constraint will spring when the player is driving on bumps. See also: `TerminalFix` below.

-   `Name="Leg"`  
    This attribute sets the name of the *regular* constraint from the [`<PhysicsModel>`][physicsmodel] that is controlled by this Powered Constraint. I.e., the value of the `Name` attribute of the [`<PoweredConstraints>`][poweredconstraints] → `<Constraint>` must be equal to the `Name` of some [`<PhysicsModel>`][physicsmodel] → [`<Constraint>`][physicsmodel_constraint].

-   `SpeedMult=".4"`  
    The multiplier for the speed of the Powered Constraint when it moves to target position and back.

-   `TerminalFix="true"`  
    Enables the following behavior: if the constraint hits an obstacle before reaching the end point of its movement (initiated by the player pressing a button, or by internal code of the game) and cannot push it through, then it will stop pushing and will become fixed constraint. See also the `IntialFix` above.

-   `Position="0.467"`  
    This is the end point, to which the bone moves due to this constraint (its [motor][motor]). It will move from zero to `Position`. The value can be in either meters or degrees – this depends on the type of the *regular* [constraint][physicsmodel_constraint] tied to this Powered Constraint. Minimum and maximum values for movement are also specified within the description of the *regular* [constraint][physicsmodel_constraint] and particular attributes for them there depend on the type of this constraint. Moreover, if specified `Position` is greater than the maximum value specified for the *regular* [constraint][physicsmodel_constraint], the Powered Constraint will *not* be able to reach this `Position`. 

    **NOTE**: In the description of the *regular* [constraint][physicsmodel_constraint], you can set the minimum and maximum values for it. And, the Powered Constraint can only move from zero to the specified `Position`. For player-controlled Powered Constraints: the constraint goes to the specified `Position` when the player presses the particular button; when they press it again, the constraint goes back to `0`. For code-controlled Powered Constraints – the same processes are initiated from the code. Therefore, typically we set up `0` as the minimum value of constraint and `Position` as its maximum value.

[group]: ./../index.md
[physicsmodel]: ./../../../physicsmodel/index.md
[physicsmodel_constraint]: ./../../../physicsmodel/body/constraint/index.md
[motor]: ./../../../physicsmodel/body/constraint/motor/index.md
[poweredconstraints]: ./../../index.md

