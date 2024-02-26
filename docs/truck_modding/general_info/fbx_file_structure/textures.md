# Textures

## Overview
In the FBX file, any textures can be assigned to the truck mesh. 

Textures must have correct names. Their names can contain only Latin characters, digits, and underscore characters (`_`). Their names must not contain spaces (` `).

The system takes only the name of a texture from the FBX file. All properties of a texture are described in the XML file of the mesh.

The fewer textures are assigned to the truck, the better the performance is.


## Correct Naming
All textures of materials of the mod must adhere to the specific naming scheme, see [<Material>](./../../tags_and_attributes_of_trucks/combinexmesh/material/index.md) for details. 

This naming scheme is necessary to enable streaming for textures of the mod, which may be essential. 

Particularly, mods with wrong naming of textures result in memory leaks on consoles and will not receive approval for them.


## Configuration Perspective
You may use the same texture maps on different shapes. But, you should look at textures from the perspective of configuring them.

For example, if one shape is inside the cab and the other is outside the cab, then you should take this into account at the stage of creating the FBX file. Particularly, in this case, you should create two materials with *different names* in the FBX file, since their parameters will be different in XML. E.g., their parameters responsible for the snow cover will be different. 

You can use one texture for all truck meshes, but the FBX file should have as many materials as the number of different sets of parameters in the XML description.

For example, you can have one `.tga` file of texture. And, if you assign one material to the truck in Maya, everything will be looking OK there. However, in the XML file, there may be a necessity to define different parameters for different parts of the truck. Е.g., enable or disable the snow cover. And, you will not be able to do this if you have assigned one material for all parts of the truck. 
So, you will need to duplicate the material in Maya, rename the second copy of the material there, and assign this second material to the necessary parts of the truck. In this case, you will be able to define different values of parameters in the XML for it.
