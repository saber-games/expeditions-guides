# PhysicsModel

Physics model of the addon. Similar to [`<PhysicsModel>`](./../../truck/physicsmodel/index.md) specified for the truck, but has some additional attributes.

**NOTE**: The child tags of `<PhysicsModel>` for addon are similar to child tags of `<PhysicsModel>` for the truck. For their descriptions please refer to the subsections of the [`<PhysicsModel>`](./../../truck/physicsmodel/index.md) for the truck.

Attributes:

-   `Mesh="trucks/tuning/mytruck_tuning"`  
    *(Mandatory.)* Path to the FBX file of the addon from the `.../meshes/` folder. In Expeditions, this FBX can also contain meshes of other addons, see [Addon Changes](./../../../new_features/addon_changes.md) for details.

-   `MeshFrame="viz_mytruck_roofrack"`  (NEW)  
    The name of the particular visual mesh from the specified FBX file that is related to this particular addon. See [Addon Changes](./../../../new_features/addon_changes.md) for details.

    **WARNING**: The name of the separate *visual mesh* of the particular addon in the FBX must be different from the name of the *XML class of this addon*. If these two names are the same, the addon will not work. Due to this, we recommend using the `viz_` prefixes in names of visual meshes of addons in the FBX. See [Addon Changes](./../../../new_features/addon_changes.md) for details.  

-   `AcceptVisualDamage="false"`  (NEW)  
    Enables (`true`) or disables (`false`) visual damage to the mesh of the addon. Typically disabled for [Consumables](./../../../new_features/consumables.md).



