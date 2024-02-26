## 18.1. Auto-Activation of Constraints of a Farming Trailer

If your farming trailer uses constraints (see [8.4.2.1. \<Constraint\>](#constraint)) to obtain a final form of a farming trailer (like the original **trailer_cultivator**, **trailer_harvester**, and **trailer_planter**), you need to take into account some nuances about the setup of constraints for farming trailers.

Particularly, all farming trailers must:

1.  Interact with the farming field only in their "expanded" form.

2.  Be able to expand on the farming field that is in the appropriate state.\
    \
    **NOTE**: The appropriate state is identifined according to the corresponding farming Stage of the objective, see "***5.23. Farming***" in the "**SnowRunner™ Editor Guide**" available as **SnowRunner_Editor_Guide.pdf** in the same documentation package.

3.  Automatically "expand" or "collapse" upon entering or leaving the farming field that is in the appropriate state.

Moreover, the game will help you to automatically expand or collapse your trailer in the appropriate conditions if it set up correctly.

Particularly, to automatically expand and collsapse your farming trailer, you can use such identifiers of Groups of Powered Constraints as \"trailer_lift\" and \"side_lift\". These identifiers will be automatically found by the system in the XML class of the trailer and the corresponding powered constraints will be activated automatically when entering or leaving the farming field (when it is in the appropriate state).

For example, these \"trailer_lift\" and \"side_lift\" Groups of powered constraints do exist in the original **trailer_cultivator.xml**:

\<PoweredConstraints\>\
    \<Group Id=\"\_trailer_foot\"\>\
        \<Constraint\
            InitialFix=\"true\"\
            Name=\"Leg\"\
            Tau=\"0.04\"\
            TerminalFix=\"true\"\
            Position=\"0.4\"\
        /\>\
    \</Group\>\
    \<Group Id=\"trailer_lift\" LocaleUid=\"UI_TRAILER_LIFT\"\>\
        \<Constraint\
            InitialFix=\"true\"

            Name=\"LiftCoupler\"

            SpeedMult=\".1\"

            TerminalFix=\"true\"

            Position=\"7.8\"

        /\>\
    \</Group\>\
    \<Group Id=\"side_lift\" LocaleUid=\"UI_SIDE_LIFT\"\>\
        \<Constraint

            InitialFix=\"true\"

            Name=\"LiftSuspension\"

            SpeedMult=\".35\"

            TerminalFix=\"true\"

            Position=\"30\"

        /\>\
        \<Constraint

            InitialFix=\"true\"

            Name=\"SideRotate\"

            SpeedMult=\".35\"

            TerminalFix=\"true\"

            Position=\"90\"

        /\>\
    \</Group\>       \
\</PoweredConstraints\>

Apart from predefined names of these Groups, the setup of these powered constraint is regular. However, since we have not described it before, let's provide some details on it, describing only Powered Constraints that are used in farming (see [18.2](#powered-constraints-used-for-farming-trailers) below).

