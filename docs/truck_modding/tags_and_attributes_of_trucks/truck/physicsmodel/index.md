# PhysicsModel

Physics model of the truck.

Inside this section, within its children tags, we should describe the properties of bones that are included in Havok simulation and their interactions with themselves and the environment. I.e., we need to describe here the bones that must react to gravity, collide with each other, have friction, and so on.

All bones of the physical model must have collision objects. For convenience, we use naming with the `NameOfBone_cdt` pattern, which means that this bone has a collision mesh.

Attributes:

-   `Mesh="trucks/cat_ct680"`  
    *(Mandatory.)* Path to the FBX file of the truck from the `.../meshes/` folder.

**NOTE 1**: The `<PhysicsModel>` tag configured for an addon (in the XML class of the addon) has some addtional attributes, see for [PhysicsModel](./../../truckaddon/physicsmodel/index.md) details. 

**NOTE 2**: The child tags of `<PhysicsModel>` for addon are similar to child tags of `<PhysicsModel>` for the truck. For their descriptions please refer to the subsections of the current section.

