## 18.2. Powered Constraints used for Farming Trailers 

Powered Constraints that are related to farming are a little bit simplier than regular Powered Constraints, since they require no Actions (that are similar to the ones specified by the Action attribute of the \<Constraint\> tag, see [17.1.2](#controls-for-controlled-constraints-of-an-addon) above) and, instead of being controlled by the player, are automatically controlled by the game when the player enters or leaves the farming field (which should be in the appropriate state).

**NOTE**: The full description of regular Powered Constraints that are controlled by Actions is out of the scope of this guide at this moment.\
\
Steps of creation of *this type* of Powered Constraint are rather simple:

**Step 1: Define a Contraint itself and don't forget about Type=\"Position\" for its Motor.**

First of all, you need to define a \<Constraint\> itself (see [8.4.2.1. \<Constraint\>](#constraint)) and specify, in its \<Motor\> child tag (see [8.4.2.1.1. \<Motor\>](#motor)), that this will be a Controlled/Powered constraint, by setting \"Position\" as the value of its Type attribute.

For example:

\<Truck Type=\"Trailer\" FarmingTrailerType=\"Cultivator\"\>\
\...\
\<PhysicsModel Mesh=\"trucks/trailers/trailer_cultivator\"\>\
\<Body \...\>\
\<Body \...\>\
\...\
\<Body\
CenterOfMassOffset=\"(-0.5; 0; 0)\"\
Mass=\"1000\"\
ModelFrame=\"BoneSuspension_cdt\"\
\>\
\<Constraint\
AxisLocal=\"(0; 0; 1)\"\
Name=\"LiftSuspension\"\
Type=\"Hinge\"\
MinLimit=\"0\"\
MaxLimit=\"29.38\"\
\>\
\<Motor\
Force=\"350000\"\
Tau=\"0.8\"\
Type=\"Position\"\
/\>\
\</Constraint\>\
\</Body\>\
\</Body\>\
\</Body\>\
\</PhysicsModel\>\
\...

\</Truck\>

**Step 2**: **Add it to the auto-controlled Group of Powered Constraints.**

Then, you need to add the entry about this constraint (with the same Name value) to the \<Group\> of Powered Constraints within the \<PoweredConstraints\> tag. And, the value of the Id of this \<Group\> should be either \"trailer_lift\" or \"side_lift\", to allow the game to control this constraint automatically. The added \<Group\> that will be controlled by the game may have multiple child \<Constraint\> tags within it, i.e. you are able to provide control over multiple constraints (sumultaneosly) to the game.\
\
**NOTE**: The attributes of the \<Constraint\> tag within the \<Group\> of \<PoweredConstraints\> are different from the description of the \<Constraint\> itself, given in **Step 1**. See the description of these attributes below.

For example:

\<Truck Type=\"Trailer\" FarmingTrailerType=\"Cultivator\"\>\
\...\
\<PoweredConstraints\>\
\...\
\<Group Id=\"side_lift\" LocaleUid=\"UI_SIDE_LIFT\"\>\
\<Constraint\
InitialFix=\"true\"\
Name=\"LiftSuspension\"\
SpeedMult=\".35\"\
TerminalFix=\"true\"\
Position=\"30\"\
/\>\
\...\
\</Group\>\
\</PoweredConstraints\>\
\...\
\</Truck\>

Attributes of the \<Constraint\> tag within the \<Group\> of \<PoweredConstraints\> are the following:

-   InitialFix=\"true\"\
    If enabled, then, prior to being activated (for regular Powered Constraints -- by the player pressing a button, for "farming" Powered Constraints -- automatically, by the game), a constraint behaves like a fixed constraint. That is, if the force of the constraint is small, then, for example, the constraint will spring when the player is driving on bumps. See also the TerminalFix below.

-   Name=\"LiftSuspension\"\
    This attribute is **required**. It sets the name of the constraint from the \<PhysicsModel\> of the farming trailer (see Step 1 above), which is controlled by this Powered constraint. I.e., the value of the Name attribute of \<PhysicsModel\> → \<Constraint\> must be equal to the Name of some \<PoweredConstraints\> → \<Constraint\>.\
    \
    **NOTE**: The Name attribute is also used for linking sounds. I.e., if you want to add sound effects to your constraint, then the ConstraintName attribute of the \<ConstraintSounds\> → \<SoundIK...\> tags must be equal to this Name for each sound that corresponds to this constraint.

-   SpeedMult=\".35\"\
    The multiplier for the control over (the movement of) the constraint.

-   TerminalFix=\"true\"\
    Enables the following behavior: if the constraint hits an obstacle before reaching the end point of its movement (initiated by the player pressing a button -- for regular Powered Constraints, or initiated automatically, by the game -- for "farming" Powered Constraints) and cannot push it through, then it will stop pushing and will become fixed constraint. See also the IntialFix above.

-   Position=\"30\"\
    This is the end point, to which the bone moves due to this constraint (its motor). It will move from zero to Position.\
    \
    **NOTE**: In the description of the constraint, you can set the minimum and maximum values ​​for it. And, the Powered Constraint can only move from zero to the specified Position. For regular Powered Constraints: the constraint goes to the specified Position when the player presses the particular button; when they press it again, the constraint goes back to 0. For Powered Constraints of the "farming" type -- the same process is done automatically. Therefore, typically we set up 0 as the minimum value of constraint and Position as its maximum value.

Powered Constraints related to farming that are set up according to the Steps above will be automatically activated by the game and will "expand" or "collapse" your farming trailer upon entering or leaving the farming field (when it is in the appropriate state).

