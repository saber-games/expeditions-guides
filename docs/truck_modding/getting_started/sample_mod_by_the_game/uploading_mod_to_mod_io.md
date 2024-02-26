# Uploading Mod to mod.io

## Overview
After [packing][step_5], you can make the mod available in the main game (not only on the "Proving Ground" map). 

To do this, will you need to:

1.  [Upload](#uploading-process) these `.zip `archives to mod.io, by this creating a new mod there.
    
    **NOTE**: Depending on the **Visibility** of your mod at mod.io, your mod can be made available to the public (`Public` mods) or remain hidden (`Hidden` mods).

2.  **Subscribe** to the resulting mod.io mod and **Enable** it in the game – see [Enabling Mod in the Game][step_7] for details.


## Uploading Process
The set of `.zip` files generated during [packing][step_5], can be uploaded mod to mod.io.

In short, the uploading process is the following:

1.  Open the site of the game at mod.io:

    -   For *Expeditions*: [https://mod.io/g/expeditions](https://mod.io/g/expeditions).
    -   For *SnowRunner*: [https://mod.io/g/snowrunner](https://mod.io/g/snowrunner).

    **NOTE**: To login to [mod.io][mod_io] you can use authentication by the e-mail. And, during sign-in, use the *same e-mail address* that you have used during the activation of the **MOD BROWSER** in the Main Menu. See [Registration and Authentication][registration_and_authentication] for details. 

2.  After sign-in, at the site of the game (see above), click the **Add mod** button, located at the upper right corner of the page.

3.  Pass the **Add your Mod wizard**. You will need the `.zip` files that you have [generated][zip_files] during packing at its 3rd step ("File manager").

    Please note that to upload a mod to mod.io correctly – you need to upload every *.zip file* of every platform as a *separate file* at the **File manager** step.

    Particularly, at the **File manager** step, for every `.zip` file from the set, you will need to:

    -   Click **Select zip file** button.
    -   Select single `.zip` file corresponding to a particular platform.  
        For example, `my_sample_mod_01_pc.zip`. Or, `my_sample_mod_01_nx64.zip`
    -   On the same page, select the platform of the file by the check mark.  
        For example, **Windows** (for `..._pc.zip` file). Or, **Nintendo Switch** (for `...__nx64.zip` file).
    -   Specify other fields on this page.
    -   Click **Upload & next** to finish with the file for the particular platform.
    -   Then, come back to the same **File manager** step (by clicking its number at the top of the page) and repeat the same operations for the next `.zip` file of the platform. 
    
    **NOTE**: Depending on the **Visibility** of your mod at mod.io, your mod can be made available to the public (`Public` mods) or remain hidden (`Hidden` mods).

For details, see the corresponding pages at the [Uploading Mods][uploading_mods] section of the portal.

After successful creation of the new mod.io mod, you can **Subscribe** to it and **Enable** it in the game – see [Enabling Mod in the Game][step_7] for details.


[step_5]: ./packing_vehicle_mod.md
[zip_files]: ./packing_vehicle_mod.md#generated-files
[step_7]: ./enabling_mod_in_the_game.md
[registration_and_authentication]: ./../../../usage_and_uploading_of_mods/2___registration_and__authentication.md
[uploading_mods]: ./../../../usage_and_uploading_of_mods/4_1___initial__step.md