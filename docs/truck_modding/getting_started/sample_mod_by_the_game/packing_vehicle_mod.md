# Packing Vehicle Mod

**WARNING**: In the current version of *Expeditions*, there is an issue in packing. If your `Media\Mods` folder with local truck mods contains *multiple* truck mods of the same type (e.g `SCOUT`), the game will *not* be able to pack any of them – these mods will be trying to use addons of each other and will fail in that. This is a known issue that will be fixed. Currently, please pack mods one by one – with only one mod of the particular type existing in the mods folder during packing.

## Overview
After you have created your vehicle as a new mod and converted it, you can pack it.

When you pack the mod, the system will generate a set of `.zip` archives corresponding to versions of your mod for different platforms (PC and various consoles).

These archives you will need when you will be [uploading][step_6] your mod to mod.io.

**NOTE**: In *SnowRunner*, packing is necessary to test your mod in the game (not only on the "Proving Ground" map). I.e., in *SnowRunner*, to make the mod available in the main game, you will need to [upload][step_6] these `.zip `archives to mod.io, by this creating a new mod there, and, then, [enable][step_7] this mod in the game. In *Expeditions*, this is not necessary, and you can [test in the game][step_4a] even *unpacked* mods.


## Packing
To pack your mod to these `.zip` archives:

1.  Open **Mod Manager** from the **TOOLS** menu.

2.  In the appearing window, select your mod in the **Available trucks** list and click **Pack**.

3.  After doing this, the system will check and validate your mod, pack it, and create the set of `.zip` archives for all supported platforms.

**NOTE**: If errors occur during packing, you can view log records of these errors. See [Viewing Error Log][error_log] for details.


## Generated Files
Generated `.zip` files will be located *in the folder of your mod* within the **Mods** folder:

-   For *Expeditions*: in `...\Documents\My Games\Expeditions\Media\Mods\<name_of_the_mod>`
-   For *SnowRunner*: in `...\Documents\My Games\SnowRunner\Media\Mods\<name_of_the_mod>`

Names of all archives will be the same as the name of your mod, with the addition of the platform suffix.

For example, if the name of the mod is `my_sample_mod_01`, then, in the `...\Mods\my_sample_mod_01` folder, we will have such archives as:

-   `my_sample_mod_01.zip` – the .zip package for **PC** platform

-   `my_sample_mod_01_playstation_4.zip` – the .zip package for **PlayStation 4** platform

-   `my_sample_mod_01_playstation_5.zip` – the .zip package for **PlayStation 5** platform

-   `my_sample_mod_01_xbox_one.zip` – the .zip package for **Xbox One** platform

-   `my_sample_mod_01_xbox_series.zip` – the .zip package for **Xbox Series X\|S** platform

-   `my_sample_mod_01_nx64.zip` – the .zip package for **Nintendo Switch** platform

**TIP**: Every generated `.zip` file corresponds to a separate version of the mod that is optimized for the particular platform. Particularly, textures for every platform are different.


[error_log]: ./viewing_error_log.md
[step_6]: ./uploading_mod_to_mod_io.md
[step_7]: ./enabling_mod_in_the_game.md
[step_4a]: ./testing_unpacked_mod_in_the_game.md