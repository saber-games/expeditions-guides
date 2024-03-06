#### 5.2.0.3. Create Default Flowmap: Default Map of the Flow for River Objects

The **Create Default Flowmap** command creates the default map of the flow of water for River objects on the map (see [[5.9. Adding Rivers and Water Objects]](#adding-rivers-and-water-objects)). This texture is called **\_default_water_flow.tga**, it has 3 channels (RGB), 8 bit for each channel.

The R and G channels contain components of the speed vector (for U and V axes of the terrain correspondingly).

The default direction of the flow of the water is automatically calculated by the Editor based on the height differences along the river spline and its curvature.

The **\_default_water_flow.tga** texture is ***not*** used by the Editor for the generation of the level. However, it could be used to generate a more accurate flow map in third-party applications, using it together with the terrain heightmap and the water heightmap textures.

After tuning, this water flow texture can be renamed to the water flow texture used for the generation of the level - **\_water_flow.tga**. If you enable the **UseFlowMap** option (set **UseFlowMap = True**) in the properties of the River object after doing this, the Editor will use the created **\_water_flow.tga** texture when generating the level. Or, you can manually paint the River object with the **Water** brush in the Editor to specify the flow (see [[5.9. Adding Rivers and Water Objects]](#adding-rivers-and-water-objects)).

