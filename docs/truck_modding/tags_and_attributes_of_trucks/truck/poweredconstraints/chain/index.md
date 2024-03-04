# Chain

The chain of Powered Groups with Powered Constraints.

I.e., the `<Chain>` tag can contain muliple [`<Group>`](./../group/index.md) tags that, in their turn, will contain [`<Constraint>`](./../group/constraint/index.md) tags of their Powered Constaints.

Groups within a chain that are activated one after another, in the order of their appearance within the chain.

If a certain `Action` is specified, the whole chain will be activated by this `Action`, i.e., when a player is pressing a particular button. Or, a chain can be activated by the game logic.

For details on Powered Constraints, Chains, Groups, and Actions, see [Powered Constraints: Overview](./../../../../additional_info_on_trucks/powered_constraints/powered_constraints_overview.md) and [Actions. Their Mapping to Buttons](./../../../../additional_info_on_trucks/powered_constraints/actions_and_their_mapping_to_buttons.md) in the **Additional Info on Trucks**.

Attributes:

-   `Action="1"`  
    This number defines the button that can used by the player for the activation or deactivation of this Chain and will be displayed in the UI. Regardless of their setup (via `<Chain>` tag, or via [`<Group>`](./../group/index.md) tag), Powered Constraints are activated and deactivated by the single and same button, so possible values here are from `1` to `8`. Particular buttons that correspond to these `Action` values are defined by the player in the game settings. However, their default values are listed in [Actions. Their Mapping to Buttons](./../../../../additional_info_on_trucks/powered_constraints/actions_and_their_mapping_to_buttons.md) in the **Additional Info on Trucks**.

-   `LocaleUid="UI_SCAN_WATCHPOINT"`  
    Localization string that will be displayed in the UI, if the Chain is player-activated.

-   `Name="DetectorAddon"`  
    The chain's name that works as its identifier. Some particular values of `Name` attribute are required for chains that are activated not by Actions, but by internal game code.

-   `ParentBodies="BoneArmHinge1_FR_cdt,BoneArmHinge1_FL_cdt,BoneArmHinge1_RR_cdt,BoneArmHinge1_RL_cdt"`  
    Physical bones that are participating in the chain of powered groups that will be reset to their default states at the reset of powered groups.  
    *For SnowRunner:*  
    This reset of powered groups occures after the detachment of the trailer, removal of the addon, and after other trailer/addon-specific operations that are initiated from code (e.g. **Restore Crane** for cranes).  
    *For Expeditions:*  
    TBD    

-   `ResetOnLoad="true"`  
    By default, the save files of the game store data on the current state of the chain and all its powered groups at the moment when the save file is created. And, this saved state of the chain is restored when you load the game from the corresponding save file. This is the mechanics corresponding the `false` value of the `ResetOnLoad` (or when it is omitted). However, if you set this attribute to `true`, the saved state of the chain will be ignored and the chain and its powered groups will be restored to their default initial states when the game is loaded from the save file.  
