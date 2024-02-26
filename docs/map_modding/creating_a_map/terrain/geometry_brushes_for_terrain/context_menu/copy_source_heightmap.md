#### 5.2.0.1. Copy Source Heightmap: Creation of Terrain by Third-Party Tool

The **Copy Source Heightmap** command is useful if you want to use the heightmap from some third-party tool and want to generate terrain for your map based on it.\
Particularly:\
When you create a new terrain in the Editor, it creates the **\_height_source.png** texture in the source folder of the level (**Media\\prebuild\\\<level_name\>**). This texture has 1 channel and it must be 16-bit. If necessary, you can generate the heightmap for your map using a third-party tool and save the resulting heightmap to this texture. To add heightmap from this texture to your map in the Editor, you can use the **Copy Source Heightmap** command.

