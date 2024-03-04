# Controls for Controlled Constraints of an Addon

*This section is not refactored yet. It will be checked and refactored later. Sorry for inconvenience. (`TBD`)*

Controlled constraints (\<ControlledConstraints\>) of an addon work similarly to the controlled constraints of a truck (see [8.9. \<ControlledConstraints\>](#controlledconstraints)).

Particularly, the controlled constraint is a constraint (see [8.4.2.1. \<Constraint\>](#constraint)) that can be controlled by the player, using the keyboard or controller. It is controlled by **two** buttons. When you press and hold one of the control buttons, the constraint starts to approach its minimum value, when you press and hold another button of the pair, the constraint starts to approach its maximum value.

For example, by default, on a PC, you will press W to extend the towing platform from the screenshot above; and you will press S to shorten it.

Let's configure the controlled constraints of the addon and enable the FastMode for them on the example of the "Articulated Towing Platform" addon:\
\
**NOTE**: The pieces of the XML code below are taken from the XML class of this addon -- which is available in the **\[media\]\\\_dlc\\dlc_5\\classes\\trucks\\addons\\frame_addon_tow.xml** file within the **initial.pak** archive.

1.  In the XML class of the Addon, in the \<PhysicsModel\> of the addon, set up the constraint in a regular way. Do not forget to specify the Name attribute of the constraint (e.g. Name=\"ramp_extend\"), you will need it at the later steps.\
    For details on constraint configuration, see [8.4.2.1. \<Constraint\>](#constraint).

> \<Body\
> \...\
> Mass=\"300\"\
> ModelFrame=\"BoneRampPrismatic_cdt\"\
> \...\
> \>\
> \<Constraint\
> AxisLocal=\"(1; 0; 0)\"\
> Name=\"ramp_extend\"\
> Type=\"Prismatic\"\
> MinLimit=\"0\"\
> MaxLimit=\"4\"\
> \>\
> \<Motor Force=\"300000\" Type=\"Position\" /\>\
> \</Constraint\>\
> \...\
> \</Body\>

2.  As a child of the \<TruckAddon\> tag, create an \<ActionCategories\> tag.

> Within this tag, add a single or multiple \<ActionCategory\> tags. (Most addons have a limited set of operations, so in most cases, one \<ActionCategory\> tag is enough).\
> \
> **NOTE**: If you want to enable FastMode for your controls, then at least one \<ActionCategory\> tag is required (this mode is enabled in the AvailableForFastMode attribute of this tag). If you do not need FastMode and do not want to group Actions displayed for your controlled constraints, then you can skip this step and do not create \<ActionCategories\> and \<ActionCategory\> tags at all. In this case, after selecting the main command corresponding to the addon usage (\"CONTROL {name of the addon}\") from the Functions menu, the player will proceed directly to a panel with buttons corresponding to all controlled constraints.
>
> In general, an action category is used for grouping actions assigned to your controlled constraints into multiple categories. For example, you can create two \<ActionCategory\> tags that will correspond to two groups of actions that the player may use with your addon, which will result in the fact that the player will select each group of these actions separately in the UI. And, along with that, this will allow you to use the same buttons for different controlled constraints if they are assigned to different action categories.\
> \
> **NOTE**: ActionCategories define the grouping of controls in general, they can be used not only for the controlled constraints.
>
> The \<ActionCategory\> tag and its attributes define the properties of the action category itself and the common properties of the constraints that are assigned to this category. Particularly, they define what will be the name of the UI button shown for this category, by what Action (button) it will be activated, whether the FastMode will be enabled or disabled for the constraints assigned to this category, and so on.
>
> **IMPORTANT**: The particular behavior of the action category and its attributes depend on the number of action categories used for this addon and whether or not are they working in FastMode. Please refer to [17.1.4](#different-scenarios-of-usage-for-the-actioncategory-fields) below for details.
>
> However, the code sample below will correspond to a single most typical scenario -- one action category that works in FastMode. This is also a piece from **frame_addon_tow.xml**:
>
> \<ActionCategories\>\
> \<ActionCategory\
> Action=\"1\"\
> Id=\"tow_control\"\
> LocaleUid=\"UI_TOW_CONTROL\"\
> AvailableForFastMode=\"true\"\
> RemoveChildActionsFromCustomPanelShowCounter = \"true\"\
> /\>\
> \</ActionCategories\>
>
> The attributes of the \<ActionCategory\> tag are the following:

-   Action=\"1\"\
    Required attribute. Defines the action (button) that will select this category in the UI. You need to use Actions that correspond to a single button here (see Actions 1-8 in [17.1.3](#actions.-buttons-for-controlled-constraints) below). However, the particular behavior of this attribute depends on the scenario applied to this \<ActionCategory\>, see [17.1.4](#different-scenarios-of-usage-for-the-actioncategory-fields) below for details. Particularly:

    -   If there is at least one non-FastMode category, this Action will define the button used for the selection of this category.

    -   If there are only FastMode categories, this attribute will not affect anything and the specified button will not be used. However, even in this case this attribute and its value are **required** due to internal reasons.

-   Id=\"tow_control\"\
    The identifier of the action category. You will need to specify the same identifier in the BelongToCategorie attribute of the \<Constraint\> tag for each controlled constraint that belongs to this group.

-   LocaleUid=\"UI_TOW_CONTROL\"\
    The name of this category in the UI. However, the particular behavior of this attribute depends on the scenario applied to this \<ActionCategory\>, see [17.1.4](#different-scenarios-of-usage-for-the-actioncategory-fields) below for details. Particularly:

    -   If all categories are non-FastMode ones, this value will define the name of the UI button displayed for this category at the bottom of the screen after the player selects the command corresponding to the addon ("Control \<name_of_addon\>") in the OPERATE subsection of the Functions menu.

    -   If all categories are FastMode ones, this value will define the name of the command corresponding to this category in the OPERATE subsection of the Functions menu.

    -   If there are FastMode and non-FastMode categories, this value will define *both*:

        -   The name of the UI button displayed for this category after the player selects the "Control \<name_of_addon\>" command in the OPERATE subsection of the Functions menu.

        -   The name of the additional command corresponding to this category in the OPERATE subsection of the Functions menu (if this value is specified for the FastMode category)

    **NOTE**: You can [localize the value of this field to different languages](./../../../map_modding/additional_info_on_maps/localization/localization.md).

-   AvailableForFastMode=\"true\"\
    Defines whether the FastMode is enabled (\"true\") or disabled (\"false\") for this \<ActionCategory\>. I.e., if \"true\", then the controls of the controlled constraints from this category are available in FastMode. If \"false\", then these controls will be available only separately (e.g. the Crane mode for operations with crane).

-   RemoveChildActionsFromCustomPanelShowCounter = \"true\"\
    This parameter with the \"true\" value is required for all categories with FastMode controls. However, it is required for internal reasons and, possibly, will be removed later on. For categories without FastMode controls, it can be omitted or set to \"false\".

    1.  As a child of the \<TruckAddon\> tag, create an \<ControlledConstraints\> tag. Within this tag, add the necessary number of \<Constraint\> tags.

> Every \<Constraint\> tag from this set will define the properties of the particular controlled constraint. Particularly, the pair of buttons this constraint is assigned to, the name of the corresponding action in the UI, and so on.
>
> \<ControlledConstraints\>\
> \...\
> \<Constraint\
> Action=\"10\"\
>   Id=\"ramp_extend\"\
> LocaleUid=\"UI_RAMP_EXTEND\"\
> Name=\"ramp_extend\"\
> SpeedMult=\"1.5\"\
> BelongToCategorie=\"tow_control\"\
> /\>\
> \...\
> \</ControlledConstraints\>
>
> The attributes of the \<Constraint\> tag here are the following:

-   Action=\"10\"\
    This number defines the button or a pair of buttons that are used by the player for controlling the constraint. Every number in Action corresponds to the particular button/predefined pair of buttons, see [17.1.3](#actions.-buttons-for-controlled-constraints) below for details. For controlled constraints (that require a pair of buttons) possible values here are from \"9\" to \"14\".

-   Id=\"ramp_extend\"\
    The identifier of the controlled constraint. This attribute is **required**. However, for addons, it does not affect anything. (For trucks, the value Id=\"chassis_steer\" is necessary to link the control over constraint to steering).\
    \
    **NOTE**: Assignment of the controlled constraint to \<Constraint\> described in the \<PhysicsModel\> of the addon is performed by the value of the Name attribute, see below. Sounds are also assigned using the value of the Name attribute.

-   LocaleUid=\"UI_RAMP_EXTEND\"\
    The name of the command (action) corresponding to this controlled constraint in the UI, e.g. \"Extend\" in the FastMode panel.\
    \

    **NOTE**: You can [localize the value of this field to different languages](./../../../map_modding/additional_info_on_maps/localization/localization.md).

-   Name=\"ramp_extend\"\
    This attribute is **required**. It sets the name of the constraint from the \<PhysicsModel\> of the addon (see Step 1 above), which is controlled by this controlled constraint. I.e., the value of the Name attribute of \<PhysicsModel\> → \<Constraint\> must be equal to the Name of some \<ControlledConstraints\> → \<Constraint\>.\
    The Name attribute is also used for linking sounds. I.e., if you want to add sound effects to your constraint, then the ConstraintName attribute of the \<ConstraintSounds\> → \<SoundIK...\> tags must be equal to this Name for each sound that corresponds to this constraint.

-   SpeedMult=\"1.5\"\
    The multiplier for the player's control over (the movement of) the constraint.

-   BelongToCategorie=\"tow_control\"\
    The identifier of the action category this constraint belongs to.\
    I.e., the value of the Id attribute of the target \<ActionCategory\> tag.

    1.  If you want to add sounds that will be activated when the player uses your controlled constraint, add the \<ConstraintSounds\> tag as a child of \<GameData\> and create a set of \<SoundIK..\> tags within it, see below.

> \<ConstraintSounds\>\
> \...\
> \<SoundIKStop\
>   Name=\"addons/addon_tow/addon_tow_ramp_extend_stop\"
>
>  Range=\"20\" Volume=\"1\" ConstraintName=\"ramp_extend\"\
> /\>\
> \
> \<SoundIKStart\
>   Name=\"addons/addon_tow/addon_tow_ramp_extend_start\"\
>  Range=\"20\" Volume=\"1\" ConstraintName=\"ramp_extend\"\
> /\>\
> \
> \<SoundIKLoop\
>   Name=\"addons/addon_tow/addon_tow_ramp_extend_loop\"\
>   Range=\"20\" Volume=\"1\" ConstraintName=\"ramp_extend\"\
> /\>\
> \...\
> \</ConstraintSounds\>
>
> The \<SoundIK..\> tags to be used there are the following:

-   \<SoundIKStart\> -- this sound will be played when the player *starts* to control the constraint.

-   \<SoundIKStop\> -- this sound will be played when the player *stops* to control the constraint.

-   \<SoundIKLoop\> -- this sound will be played when the player *is in the process of controlling* the constraint.

> The **Format** of these sounds needs to be the following:

-   **44 kHz** (or less), **Mono**, **16 bit**, stored as **.wav** files.\
    \
    **NOTE**: These sounds need to be in **Mono** since they will be played as 3D sounds and will have the position in the scene (the position of the addon). Otherwise, the sounds will work as "flat" sounds (with the same volume in both channels) and the player will not be able to identify the direction of the sound.

> All \<SoundIK..\> tags have the same attributes:

-   Name=\"addons/addon_tow/addon_tow_ramp_extend_stop\"\
    The path to the corresponding sound file, relative to the **sounds** folder in the folder of the mod and without the file extension.\
    E.g., \"addons/my_addon_1/my_sound\" for the ...**\\Media\\Mods\\\<mod_name\>\\sounds\\addons\\my_addon_1\\my_sound.wav**\
    For the format of the sound file, see the **NOTE** above.

-   Range=\"20\"\
    The distance (in meters), within which the sound is played at its maximum volume. If we are moving away from the position of the sound and the distance has exceeded the Range value, the sound volume will start to fade.

-   Volume=\"1\"\
    The multiplier of the sound volume. \"1\" corresponds to the original volume of the sound file.

-   ConstraintName=\"ramp_extend\"\
    The name of the controlled constraint this sound is assigned to (i.e. the value of the Name attribute of this constraint).

**NOTE**: For a list of possible buttons ("Actions") that can be assigned to controlled constraints, see [17.1.3](#actions.-buttons-for-controlled-constraints) below.

**NOTE**: For different scenarios of usage of the ActionCategory attributes, please refer to [17.1.4](#different-scenarios-of-usage-for-the-actioncategory-fields).

