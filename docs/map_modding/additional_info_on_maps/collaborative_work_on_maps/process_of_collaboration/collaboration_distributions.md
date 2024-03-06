# Collaboration: Distributions

When you add a new [Distribution][distribution] to your level, the Editor automatically:

1.  Adds the information about this distribution (its brushes, etc.) to the level:

    -   *If this Distribution does not belong to any group of objects* – this info will be added to the main XML file of the level, the `<level_name>.xml` one that is stored in `Media\prebuild`.

    -   *If this Distribution belongs to a [group][group] of objects* – this info will be added to the XML file of this group, which will be located in the `Media\prebuild\<level_name >\subgroups` folder.

2.  Adds the texture of this distribution in the `.tga` format to data of the level. Particularly, since the map is always splitted into the conventional map pieces, the appropriate texture pieces (`.tga` files with the same name) are added to the corresponding `data\0_0` ... `data\3_3` subfolders.

Thus, if a modder from modding team wants to add a distribution to one of their map pieces, then this modder needs to send to other members of the team the following info:

1.  The piece of XML code containing info on this distribution – to be added to the corresponding XML file of the level or subgroup on the side of other modders.
    For example, the following piece from the XML file of the level:
    
    ![](./media/image380.png)

    Or, from the XML file of the subgroup:

    ![](./media/image381.png)

2.  Textures (maps) of this distribution that were created for it in *all* `data\0_0` ... `data\3_3` subfolders:
    
    ![](./media/image382.png)

    **NOTE**: If a distribution is already created on all modders' copies of the level, and the modder modifying it has modified only its *`.tga` texture* (map) within *this modder's own map pieces* and has not modified the other properties of this distribution, this moder can send only the modified map pieces, as described in the general [process][process].



[distribution]: ./../../../creating_a_map/distributions/adding_multiple_objects_via_distribution.md
[group]: ./../../../getting_started/ui_overview/groups.md
[process]: ./process_of_collaboration_overview.md