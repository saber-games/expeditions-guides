#### 5.2.0.2. Create Water Heightmap: Useful Map of Water Surfaces

The **Create Water Heightmap** command creates the texture with a heightmap of water surfaces that were created as River objects on the map (see [[5.9. Adding Rivers and Water Objects]](#adding-rivers-and-water-objects)). This texture is called **\_water_height.png**, it has one channel, 16 bit. This texture is ***not*** used by the Editor for the generation of the level. However, this texture can be used, if masks for layers and distributions are generated in third-party applications (e.g. Substance Designer or Houdini). Using this texture and a heightmap of the level, one can easily see where the map contains water and what is its depth.

For example, according to the data on this mask, one can generate the distribution of canes on the banks of water objects and a wetness mask near them.

