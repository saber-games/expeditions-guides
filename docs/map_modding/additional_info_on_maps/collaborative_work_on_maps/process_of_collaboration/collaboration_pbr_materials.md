# Collaboration: PBR Materials

In both games, we have *fixed maximum* amount of [PBR Materials][materials] and *fixed maximum* amount of their layers: maximum `4` materials, with maximum `4` layers each.

*Piece of tech info*: Every material has `4` layers. Every layer corresponds to a RGBA channel in the `mtrl_base_blends.tga` texture. The data on the particular material the terrain is painted with is stored within the `mtrl_layout.tga` texture (and this data is used based on the RGBA channels too). Thus, when a modder modifies the properties of the particular PBR material (without modifying the texture), in fact, they change only the brush assigned to one of these textures, i.e. to one of the RGBA channels.

Thus, when simultaneously working with PBR materials, there may be three scenarios:

1.  **The modder does *not* modify the properties of the Material and layers specified for it, but modifies the painting of the terrain (i.e. the texture) within this modder's own map pieces**.  
    In this case, all that this modder have to send to other team members is the `mtrl_base_blends.tga` and `mtrl_layout.tga` textures *from the modified map pieces* (i.e. from the corresponding `data\0_0` ... `data\3_3` folders).

2.  **The modder modifies the properties of the Material and layers specified for it, but does *not* modify the painting of the terrain (i.e. the texture).**  
    In this case, all that this modder has to send to other team members is the piece of XML code containing info on the brush of this PBR Material from the `<level_name>.xml` that is stored in `Media\prebuild` – for this to be added to the copies of this XML file on the side of the other modders.  
    For example:  
    ![](./media/image383.png)

3.  **The modder modifies both the material properties and the texture within this modder's own map pieces.**  
    In this case, the modder has to send both the `mtrl_base_blends.tga` and `mtrl_layout.tga` textures from the modified map pieces and this XML piece.


[materials]: ./../../../creating_a_map/pbr_materials/assigning_pbr_materials_to_terrain.md
