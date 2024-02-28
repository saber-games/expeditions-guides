# Uploading Mods to mod.io

## Packing
When you create a mod, one the steps you pass is *packing*.

It should be done for all types of mods that you want to publish: maps, trucks, etc.

Particular instructions to initiate packing of the mod vary depending on the mod type. For details, see the corresponding section of the portal that is related to the type of the modding entity you want to pack.

However, for all modding entities, as a result of packing, the game or the Editor will generate fhe set of `.zip` files. The location of these .zip files is also different for different mod types. See the corresponding section of the portal for details.

To create a new mod at mod.io, you will need to upload these `.zip` fles there.


## Uploading Process
In short, the uploading process is the following:

1.  Open the site of the game at mod.io:

    -   For *Expeditions*: [https://mod.io/g/expeditions](https://mod.io/g/expeditions).
    -   For *SnowRunner*: [https://mod.io/g/snowrunner](https://mod.io/g/snowrunner).

    **NOTE**: To login to mod.io you can use authentication by the e-mail. And, during sign-in, use the *same e-mail address* that you have used during the activation of the **MOD BROWSER** in the Main Menu. See [Registration and Authentication][registration_and_authentication] for details. 

2.  After sign-in, at the site of the game (see above), click the **Add mod** button, located at the upper right corner of the page.

3.  Pass the **Add your Mod wizard**. You will need the `.zip` files that you have generated during packing at its 3rd step ("File manager").

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

After successful creation of the new mod.io mod, you can **Subscribe** to it and **Enable** it in the game – see [Usage of Mods from mod.io][usage_of_mods_from_mod_io] for details.

[registration_and_authentication]: ./registration_and_authentication.md
[usage_of_mods_from_mod_io]: ./usage_of_mods_from_mod_io.md