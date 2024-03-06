## Auto-Activation of Constraints of a Farming Trailer

*This feature is valid for SnowRunner only.*

If your farming trailer uses [constraints][constraints] to obtain a final form of a farming trailer (like the original `trailer_cultivator`, `trailer_harvester`, and `trailer_planter`), you need to take into account some nuances about the setup of constraints for farming trailers.

Particularly, all farming trailers must:

1.  Interact with the farming field only in their "expanded" form.

2.  Be able to expand on the farming field that is in the appropriate state.
    
    **NOTE**: The appropriate state is identifined according to the corresponding farming Stage of the objective, see [Farming][farming] in the **Map Modding** section for details.

3.  Automatically "expand" or "collapse" upon entering or leaving the farming field that is in the appropriate state.

Moreover, the game will help you to automatically expand or collapse your trailer in the appropriate conditions if it set up correctly.

Particularly, to automatically expand and collsapse your farming trailer, you can use such identifiers of Groups of Powered Constraints as `trailer_lift` and `side_lift`. 

These identifiers will be automatically found by the system in the XML class of the trailer and the corresponding powered constraints will be activated automatically when entering or leaving the farming field (when it is in the appropriate state).

For example, these `trailer_lift` and `side_lift` Groups of powered constraints do exist in the original `trailer_cultivator.xml`:

```xml
<PoweredConstraints>
    <Group Id="_trailer_foot">
        <Constraint
            InitialFix="true"
            Name="Leg"
            Tau="0.04"
            TerminalFix="true"
            Position="0.4"
        />
    </Group>
    <Group Id="trailer_lift" LocaleUid="UI_TRAILER_LIFT">
        <Constraint
            InitialFix="true"
            Name="LiftCoupler"
            SpeedMult=".1"
            TerminalFix="true"
            Position="7.8"
        />
    </Group>
    <Group Id="side_lift" LocaleUid="UI_SIDE_LIFT">
        <Constraint
            InitialFix="true"
            Name="LiftSuspension"
            SpeedMult=".35"
            TerminalFix="true"
            Position="30"
        />
        <Constraint
            InitialFix="true"
            Name="SideRotate"
            SpeedMult=".35"
            TerminalFix="true"
            Position="90"
        />
    </Group>        
</PoweredConstraints>
```

Apart from predefined names of these Groups, the setup of these powered constraints is regular.


[constraints]: ./../../tags_and_attributes_of_trucks/truck/physicsmodel/body/constraint/index.md
[farming]: ./../../../map_modding/creating_a_map/farming/farming_overview.md