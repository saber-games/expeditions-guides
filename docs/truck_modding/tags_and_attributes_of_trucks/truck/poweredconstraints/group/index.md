# Group

Group of Powered Constraints. So-called *Powered Group*. Contains a group of powered constraints that are activated simultaneously.

Powered constraints within this group are described using *special* [`<Constraint>`][group_constraint] tags that are *different* from the *regular* [`<Constraint>`][physicsmodel_constraint] tags described in the [`<PhysicsModel>`](./../../physicsmodel/index.md).

These *special* `<Group>` → [`<Constraint>`][group_constraint] tags must be tied to the corresponding *regular* [`<PhysicsModel>`][physicsmodel] → [`<Constraint>`][physicsmodel_constraint] tags by `Name`. I.e., they must have the same value of the `Name` attribute.

The [`<Motor>`][motor] tag within a [`<PhysicsModel>`][physicsmodel] → [`<Constraint>`][physicsmodel_constraint] tag must have `Type` attribute equal to `Position`, if this constraint is tied to a `<Group>` → [`<Constraint>`][group_constraint] tag as described above.

If such group is *not* within a [`<Chain>`][chain], the powered constraints within this group can be activated by a certain `Action`, i.e., when a player is pressing a particular button, see `Action` below. Or, such groups can be activated by the game logic.

For details on Powered Constraints, Groups, and Actions, see [Powered Constraints: Overview](./../../../../additional_info_on_trucks/powered_constraints/powered_constraints_overview.md) and [Actions. Their Mapping to Buttons](./../../../../additional_info_on_trucks/powered_constraints/actions_and_their_mapping_to_buttons.md) in the **Additional Info on Trucks**.

Attributes:

-   `Action="1"`  
    This number defines the button that can used by the player for the activation or deactivation of this Powered Group and will be displayed in the UI (see `ExternalUi` below). Regardless of their setup (via [`<Chain>`][chain] tag, or via `<Group>` tag), Powered Constaints are activated and deactivated by the single and same button, so possible values here are from `1` to `8`. Particular buttons that correspond to these `Action` values are defined by the player in the game settings. However, their default values are listed in [Actions. Their Mapping to Buttons](./../../../../additional_info_on_trucks/powered_constraints/actions_and_their_mapping_to_buttons.md) in the **Additional Info on Trucks**.

-   `ExternalUi="false"`  
    *For Expeditions:*  
    Only `false` values are possible. In Expeditions, Actions that activate or deactivate the Powered Group (defined by `Action` attributes) are displayed to the player after the selection of the **USE ...** command in the Radial menu. See [Powered Constraints: Overview](./../../../../additional_info_on_trucks/powered_constraints/powered_constraints_overview.md) in the **Additional Info on Trucks** for details. *Currently, this functionality is in the process of development.*  
    Values: `false`.  
    *For SnowRunner:*  
    If this option is set to `false`, then Actions that activate or deactivate the Powered Group will be displayed to the player after the selection of the **Use ...** command in the Functions menu when the truck engine is working.  
    If this option is set to `true`, then Actions will not work and the player will be activating Powered Groups directly by corresponding commands from the Functions menu (when the truck engine is working). The name of every command there will be defined by the `LocaleUid` value of the corresponding Powered Group. See [Powered Constraints: Overview](./../../../../additional_info_on_trucks/powered_constraints/powered_constraints_overview.md) in the **Additional Info on Trucks** for details.    
    Values: `false`, `true`.

-   `Id="_trailer_foot"`  
    The identifier of this Powered Group. Some particular values of `Id` attribute are required for Powered Groups that are activated not by Actions, but by internal game code.

-   `LocaleUid="UI_HUD_INTEGRATION_PANEL_ACTIVATE_ADDON"`  
    The text that will be displayed in the UI for the activation and deactivation of this Powered Group. 

-   `UnfoldingDelay="2.5"`  
    The delay before the constraints of this Powered Group move to their *target* positions, in seconds.

-   `FoldingDelay="1.5"`  
    The delay before the constraints of this Powered Group return to their *initial* positions, in seconds.



[group_constraint]: ./constraint/index.md
[physicsmodel]: ./../../physicsmodel/index.md
[physicsmodel_constraint]: ./../../physicsmodel/body/constraint/index.md
[motor]: ./../../physicsmodel/body/constraint/motor/index.md
[chain]: ./../chain/index.md


