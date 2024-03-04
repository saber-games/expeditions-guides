# Creation of Custom FOB Module

## Overview
Custom FOB Modules are created similarly to custom Inventory Items and Specialists.

This process is initiated in by clicking the **EXP MODs creation** (![](./../../map_modding/creating_a_map/media/exp_mods_creation_button.png)) button on the toolbar of the Editor.

In the appearing dialog, after selecting in the main menu that you want to create a FOB module, you will need to specify the *identifier* of the custom FOB Module in the game. It is specified in the **name** field.

Then – you need to select the [*class*][class] of the FOB Module in the **BaseUpgradeDesc** field. 

After that, you need to specify the [properties][properties] of the FOB module. 

**NOTE**: During the creation of the FOB module, you will need to either use existing 3d models of FOB modules provided with the game, or create your own custom 3d models for it. See [3D Models of FOB Modules][3d_models_of_fob_modules] for details.   


## Pipelines

### Creation

To create a new custom FOB Module, do the following:

1.  Open the Editor. 

2.  Click **EXP MODs creation** (![](./../../map_modding/creating_a_map/media/exp_mods_creation_button.png)) on the toolbar.

3.  In the main menu of the appearing dialog, select **File** \> **New Mod** \> **Base Module**.

4.  In the **name** field – specify the identifier of the new FOB Module. The specified value should contain only Latin characters, digits, and underscores (`_`). It must not contain spaces (` `).

5.  In the **BaseUpgradeDesc** field – select the [*class*][class] of the FOB Module. Currently, two classes are avialable:

    -   `BaseUpgradeDesc` – for most modules (whose functionality depends on the zone selected for FOB Module).
    -   `AntennaUpgradeDesc` – for modules with `Antenna` ability.

    See [Custom FOB Modules: Overview][class] for details.

6.  Specify [properties][properties] of this FOB Module.

7.  To save your changes, select **File** \> **Save** from the main menu.

After the creation, you can pack this FOB module to make it available in the game and to be able to upload it to mod.io later on.

#### Source Files
After saving, saved properties of the FOB module can be found in the *folder of this FOB module* within `Documents\My Games\Expeditions\Media\Mods\`. 

The name of this folder is formed based on the `BaseUpgradeDesc_<identifier_of_fob_module>` pattern.

For example:  
`\Documents\My Games\Expeditions\Media\Mods\BaseUpgradeDesc_my_fuel_station\`

The properties themselves are saved in the `BaseUpgradeDesc` file in this folder, in the JSON format.

### Opening
To open an existing custom FOB module:

1.  Open the Editor. 

2.  Click **EXP MODs creation** (![](./../../map_modding/creating_a_map/media/exp_mods_creation_button.png)) on the toolbar.

3.  In the main menu of the appearing dialog, select **File** \> **Open**.

4.  In the appearing dialog, expand the section named as the class of FOB modules (`BaseUpgradeDesc`).

5.  Select the necessary FOB module in the list and click **OK**.


### Packing

To pack a custom FOB module:

1.  Create or open the custom FOB module.
2.  Select **File** \> **Pack** from the main menu of the dialog.
3.  The message box displays the path to the location of `.zip` files that will be generated for the FOB module. Click **OK** to generate them.

#### Generated Files
During packing, the system generates:

-   The set of `.pak` files – for local testing of the mod.
-   The set of `.zip` files – for uploading to mod.io.

The `.zip` files can be found in the [*folder of this FOB module*](#source-files) within `Documents\My Games\Expeditions\Media\Mods\`.

The `.pak` files are stored in the root of the `Documents\My Games\Expeditions\Media\Mods\`. 


### Local Testing
After packing, your FOB module will be available in the game.

The game will use the `.pak` files generated during packing to identify the mod (locally).

However, you will need to restart the game for this identification.

Your FOB module will be available in the game in the same zones as the original FOB modules.


### Uploading to mod.io 
Uploading to mod.io is performed similarly to uploading of the truck mods. See [Uploading Mod to mod.io][uploading].


### Subscription and Enabling  
Subscription to the mod and its activation are performed the same way as for truck mods. See [Enabling Mod in the Game][enabling].



[class]: ./custom_fob_modules_overview.md#classes
[properties]: ./general_properties_of_fob_modules.md
[3d_models_of_fob_modules]: ./3d_models_of_fob_modules.md
[uploading]: ./../../truck_modding/getting_started/sample_mod_by_the_game/uploading_mod_to_mod_io.md
[enabling]: ./../../truck_modding/getting_started/sample_mod_by_the_game/enabling_mod_in_the_game.md