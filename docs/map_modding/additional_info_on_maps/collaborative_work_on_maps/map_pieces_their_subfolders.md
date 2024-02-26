# Map pieces. Their Subfolders

**NOTE**: The name of a map must start with the `level_` prefix. E.g., `level_my_map_01`

*Regardless of its actual size*, every map is conventionally splitted at `16` map pieces that are numbered from `[0,0]` (as the top left piece) to `[3,3]` (as the bottom right piece), see the illustration below.

![](./media/image375.png)

**NOTE**: The actual size of every piece varies depending on the map size.

If you look into the folder of your map in [`Media\prebuild`][prebuild], and then proceed to `data` subfolder there, you will see that set of numbered subfolders, from `0_0` to `3_3`, see the screenshot below.

Every such subfolder contains (almost all) data of the corresponding piece of the map. However, there are exceptions to this, such as Rivers, Overlays, and some other entities that are shared between all pieces, see below.

![](./media/image376.png)


[prebuild]: ./../../getting_started/file_paths_and_naming/file_paths.md

