
# Step 3: Creating Textures
In general, all textures created for the mod should follow the requirements listed in the sections below.

However, when we are creating a non-professional mod, we can keep textures as simple as possible, see the last section for details.  

## Format of Textures
All texture files must be in the `.tga` format.

## Naming Scheme for Textures
All textures must be named according to the correct naming scheme. The naming of textures is strictly defined, since postfixes in their file names indicate the type of data inside them. 

The name of the file is formed according to the following pattern:

```text
name__postfix.tga
```
Where:
-   `name` – any appropriate name that does not include two underscores in a row (no `__` inside it).
-   `postfix` – defines the type of data within a texture according to the table below.

| `__postfix`   |    Type of Texture      |      Parameter in XML      |
|---------------|-------------------------|----------------------------|
|`__d`          |    Albedo Map           |       AlbedoMap            | 
|`__d_a`        |    Albedo Map + Alpha   |       AlbedoMap            |
|`__n_d`        |    Normal Map           |       NormalMap            |
|`__sh_d`       |    Shading Map          |       ShadingMap           |
|`__em_d`       |    Emissive Map         |       EmissiveMap          |

**WARNING**: The naming scheme for textures described above is mandatory. This naming scheme is necessary to enable streaming for textures of the mod, which may be essential. Particularly, mods with the wrong naming of textures result in memory leaks on consoles and will not receive approval for them.

## Size of Texures
Suggested sizes of textures used for truck mods are the following:

-   **External part of the truck** and its **low-poly cabin**
    -   For a regular truck – `1` texture, `2048х2048`.
    -   For a large truck – `2` textures, each of `2048х2048` size: one for the front part of the truck (cabin and its surroundings) and one for the rest of the model (chassis, and so on).
-   **Glass** (all glass part of the truck) – `1024х1024` or `2048х1024` (depends on the format of the glass).
-  **High-Res Cabin** – `2K`.
-   **Gauges** – `1024х1024` or `2048х1024` (depends on the number of elements).
-  **Glass of the Gauges** – `512x512`.
-   **Tire** – `1024х512`.
-   **Rim** – `512x512`.
-   **Addons** – may vary (depends on size/complexity), texel is `~230`.

## Location of Textures
Truck mod textures should be put to the `textures` folder within the [folder of the truck mod][truck_mod_folder]. Or, to the subfolder there, e.g. to `textures\trucks`. 

In the latter case you will need to mention this subfolder in the values of the corresponding attrubutes of `<Material>` tag. For example:
```xml
...
	<Material
		AlbedoMap="trucks/mod_scout__d.tga"
		...
	/>
...
```

## Textures for Our Simple Mod
Since we are creating an illustrative mod and are using simple color fills instead of professional textures that require working with UV, we will create very simple textures and only the diffuse ones.

Previously, we have created two materials (`middle_part` and `lower_part_and_roof`), so we will create two diffuse textures with `128x128` dimensions:

-   `middle_part_texture__d.tga` (shown below as `.png`, requires hovering to find it :)

    ![preview of the texture 1](./media/middle_part_texture__d.png)

-   `lower_part_and_roof_texture__d.tga` (shown below as `.png`)

    ![preview of the texture 2](./media/lower_part_and_roof_texture__d.png)

**WARNING**: _Previews_ of these textures shown above are in the PNG format, but the _original textures_ must be in the TGA format.

So, we will create the `textures\trucks` folders in the folder of the truck mod and put the `middle_part_texture__d.tga` and `lower_part_and_roof_texture__d.tga` files there.

After that, we can proceed to the next step – [the creation of the XML file of the truck mesh](./step_4_creating_xml_file_of_truck_mesh.md).


[truck_mod_folder]: ./step_0_prerequisites.md#mod-folder
