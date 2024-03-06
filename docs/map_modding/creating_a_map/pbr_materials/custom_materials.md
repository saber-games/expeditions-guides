# Custom Materials

Along with creating all sorts of various PBR materials with layers based on pre-defined textures (provided with the Editor), you can create so-called "Custom PBR Materials",

I.e., you can base layers of your PBR material on custom textures created by yourself.

To do this, you will need to create textures and XML class of your material, and place them in correct subfolders of the `Media` folder.

**NOTE**: For details on how to create the files of a custom material, please refer to the *"4. Custom PbrMaterials"* chapter of the "*Custom Level Entities: Models, Overlays, and PbrMaterials*" guide. It is currently available as [Custom_Level_Entities_Models_Overlays_and_PbrMaterials.pdf][pdf].

After that, you can restart Editor, and, if you have created the files of the material correctly, your material will be integrated with it. Particularly, you will be able to find this material in the regular **Asset** window displayed when you are selecting **File** of the material (texture) for the Layer of your PBR Material. 

It will be displayed there with the name you have specified for it and the `\Media` postfix.

After that, you can use this material (texture) in a regular way, select it as one of the Layers of your PBR Material, and paint the necessary areas of terrain with it.

[pdf]: ./../../../custom_level_entities/Custom_Level_Entities_Models_Overlays_and_PbrMaterials.pdf