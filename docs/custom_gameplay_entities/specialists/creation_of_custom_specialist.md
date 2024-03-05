# Creation of Custom Specialist

**NOTE**: In the current version of Expeditions, there is an issue that saving a custom specialist may not work when this specialist is created *for the first time*. As the result of this issue, you will see the "*Can’t open file: ...*" message. This issue occurs because the `Media\Mods` folder is not created automatically. The temporary solution for this is to create this folder manually. Or, as an alternative, create and *pack* any map. This issue is known and will be fixed in the next versions of the Editor.

## Overview
Custom Specialists are created similarly to custom Inventory Items and FOB Modules.

This process is initiated in by clicking the **EXP MODs creation** (![](./../../map_modding/creating_a_map/media/exp_mods_creation_button.png)) button on the toolbar of the Editor.

At first, after selecting in the main menu that you want to create a Specialist, you will need to specify the *identifier* of the custom Specialist in the game. It is specified in the **name** field.

After that, in this dialog, you specify the [general properties][general_properties] of the Specialist at first.

And, then, add and configure the necessary [modifiers][modifiers] of this Specialist.


## Pipelines

### Creation

To create a new custom Specialist, do the following:

1.  Open the Editor. 

2.  Click **EXP MODs creation** (![](./../../map_modding/creating_a_map/media/exp_mods_creation_button.png)) on the toolbar.

3.  In the main menu of the appearing dialog, select **File** \> **New Mod** \> **Specialist**.

4.  In the **name** field – specify the identifier of the new Specialist. The specified value should contain only Latin characters, digits, and underscores (`_`). It must not contain spaces (` `).

5.  At the top of the dialog, specify [general properties][general_properties] of this Specialist.

6.  In the **modifiers** list, add and configure necessary [modifiers][modifiers] of this Specialist.

7.  To save your changes, select **File** \> **Save** from the main menu.

**NOTE**: In the current version of Expeditions, there is an issue that saving a custom specialist may not work when this specialist is created *for the first time*. As the result of this issue, you will see the "*Can’t open file: ...*" message. This issue occurs because the `Media\Mods` folder is not created automatically. The temporary solution for this is to create this folder manually. Or, as an alternative, create and *pack* any map. This issue is known and will be fixed in the next versions of the Editor.

After the creation, you can pack this Specialist to make it available in the game and to be able to upload it to mod.io later on.

#### Source Files
After saving, saved properties of the specialist can be found in the *folder of this specialist* within `Documents\My Games\Expeditions\Media\Mods\`. 

The name of this folder is formed based on the `SpecialistDesc_<identifier_of_specialist>` pattern.

For example:  
`\Documents\My Games\Expeditions\Media\Mods\SpecialistDesc_roald_amundsen\`

The properties themselves are saved in the `SpecialistDesc` file in this folder, in the JSON format.


### Opening
To open an existing custom specialist:

1.  Open the Editor. 

2.  Click **EXP MODs creation** (![](./../../map_modding/creating_a_map/media/exp_mods_creation_button.png)) on the toolbar.

3.  In the main menu of the appearing dialog, select **File** \> **Open**.

4.  In the appearing dialog, expand the section named as the class of specialists (`SpecialistDesc`).

5.  Select the necessary specialist in the list and click **OK**.


### Packing

To pack a custom specialist:

1.  Create or open the custom specialist.
2.  Select **File** \> **Pack** from the main menu of the dialog.
3.  The message box displays the path to the location of `.zip` files that will be generated for the specialist. Click **OK** to generate them.

#### Generated Files
During packing, the system generates:

-   The set of `.pak` files – for local testing of the mod.
-   The set of `.zip` files – for uploading to mod.io.

The `.zip` files can be found in the [*folder of this specialist*](#source-files) within `Documents\My Games\Expeditions\Media\Mods\`.

The `.pak` files are stored in the root of the `Documents\My Games\Expeditions\Media\Mods\`. 

### Local Testing
After packing, your specialist will be available in the game. 

The game will use the `.pak` files generated during packing to identify the mod (locally).

However, you will need to restart the game for this identification.


### Uploading to mod.io 
Uploading to mod.io is performed similarly to uploading of the truck mods. See [Uploading Mod to mod.io][uploading].


### Subscription and Enabling  
Subscription to the mod and its activation are performed the same way as for truck mods. See [Enabling Mod in the Game][enabling].



[general_properties]: ./general_properties_of_specialists.md
[modifiers]: ./modifiers_of_specialists.md
[uploading]: ./../../truck_modding/getting_started/sample_mod_by_the_game/uploading_mod_to_mod_io.md
[enabling]: ./../../truck_modding/getting_started/sample_mod_by_the_game/enabling_mod_in_the_game.md