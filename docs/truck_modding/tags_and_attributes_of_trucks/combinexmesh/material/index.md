# Material

The `<Material>` tag describes a Material.

**How the materials in SnowRunner and Expeditions are different from MudRunner ones**

-   Unlike MudRunner, this tag describes exactly the material assigned in the FBX file and not the material assigned to a specific MeshPart. Therefore, the material that was specified in the tag will be applied to *all the meshes* to which it was assigned in the Fbx file.

-   The shading has changed. Previously, the "diffuse-specular" shading of models was used. Now, PBR materials are used.

-   The snow cover effects of the surfaces were added.

**Material Maps**

All files of the maps must be in the `tga` format. The naming of map files is strictly defined, postfixes in their file names indicate the type of data inside them.
The name of the file is formed according to the following pattern: `name__postfix.tga`.  
where:

-   `name` – any name that does not include two underscores in a row (no `__` inside it).

-   `postfix` – defines the type of the data.


| `__postfix`   |    Type of Texture      |      Parameter in XML      |
|---------------|-------------------------|----------------------------|
|`__d`          |    Albedo Map           |       AlbedoMap            | 
|`__d_a`        |    Albedo Map + Alpha   |       AlbedoMap            |
|`__n_d`        |    Normal Map           |       NormalMap            |
|`__sh_d`       |    Shading Map          |       ShadingMap           |
|`__em_d`       |    Emissive Map         |       EmissiveMap          |


**WARNING**: The naming scheme for textures described above is mandatory. This naming scheme is necessary to enable streaming for textures of the mod, which may be essential. Particularly, mods with wrong naming of textures result in memory leaks on consoles and will not receive approval for them.

**NOTE**: In most cases, the Alpha channel of the Albedo Map is used for transparency or "hard transparency" (using `AlphaKill="true"`, see description of the attributes below). However, for wheels of the truck, the Alpha channel of the Albedo Map is related to the behavior of the mud or snow chunks that can stick to wheels. In this case, low values (e.g. black color) in the Alpha channel result in the behavior when the snow or dirt chunks stick to the wheel surface.

**Note on the parameters of snow cover effect in SnowRunner and Expeditions**:

In SnowRunner and Expeditions, the snow cover effect actually consists of two independent effects:

-   ***snow layer*** - this effect corresponds to the white layer of snow on top of the surface (i.e. accumulated falling snow). Parameters of this effect have the `SnowUp...` prefix (see in the list of attributes below).

-   ***snow powder*** - this effect corresponds to snowflakes that cling to the surface on many sides: e.g., on the sides, under the bottom, etc. Parameters of this effect have the `Snowify...` prefix (see the list of attributes below).

**Attributes:**

-   `Name="mod_scout_mat"`  
    Name corresponding to the name of the material in the FBX file.

-   `AlbedoMap="trucks/mod_scout__d.tga"`  
    Texture with basic surface color (RGB). Optional alpha (A) can be used either as a hard opacity mask for the alpha test (see `AlphaKill` below) or as a transparency mask (see `Blending` below).

-   `AlphaKill="true"`  
    Hard transparency mode that uses the black and white mask from the alpha channel of the AlbedoMap texture. Default value: `false`. For example, this parameter is needed to make a protective grid of the radiator.

-   `Blending="alpha"`  
    The mode of blending for surface materials when they are rendered. Possible values: `none`, `alpha`, and `additive`. The `alpha` value enables the regular transparency of the material. The `additive` value is not used for trucks. By default, the `none` value is used.

-   `NormalMap="trucks/mod_scout__n_d.tga"`
    The normal map in the tangent space (RGB). The green color corresponds to the bottoms of the embossments.

-   `NormalScale="1"`  
    Coefficient of influence for the NormalMap texture. Default value: `1.0`

-   `ShadingMap="trucks/mod_scout__sh_d.tga"`  
    Specifies map for the PBR shading data:

    -   R – metalness: metalness of the surface (0 = dielectric, 1 = metal).
    -   G – roughness: the roughness of the surface (0 = perfectly smooth surface, 1 = extremely rough surface).
    -   B – ambient occlusion mask: shading mask for the ambient light (0 = completely occluded, 1 = not occluded at all).

-   `MetalnessScale="1"`  
    А multiplier for the metalness value from the ShadingMap texture.
    I.e., `metalness = metalness * MetalnessScale`.
    Value range: `[0.0 - 1.0]`.  
    Default value : `1.0`.

-   `MetalnessВias="0"`  
    Shift for the metalness value from the ShadingMap texture.
    I.e., `metalness = metalness + MetalnessBias`.
    Value range: `[0.0 - 1.0]`.  
    Default value : `0.0`.

-   `RoughnessScale="1"`  
    Multiplier for the roughness value from the ShadingMap texture.
    I.e., `roughness = roughness * RoughnessScale`.
    Value range: `[0.0 - 1.0]`.  
    Default value : `1.0`

-   `RoughnessВias="0"`
    Shift for the roughness value from the ShadingMap texture.
    I.e., `roughness = roughness + RoughnessBias`.
    Value range: `[0.0 - 1.0]`
    Default value : 0.0

-   `AmbientOcclusionIntensity="1"`  
    Coefficient of influence for the ambient light shading mask from the ShadingMap texture. Default value: `1.0`

-   `ReflectivityMultiplier="1"`  
    Multiplier that increases the intensity of reflections on the material.
    Default value: `1.0`

-   `EmissiveMap="trucks/mod_scout__em_d.tga"`  
    Emissive color of the surface (RGB). If the texture is absent, the surface will not be emissive. This effect is not supported for transparent PBR materials (glass, etc.).
    The emissive effect is enabled when the ignition is turned on.

-   `SnowUpIntensity="10"`  
    Intensity of the snow cover on the surface.
    Default value: `10.0`

-   `SnowUpNormalsSpace="object"`  
    The snow overlay mode. For moving, dynamic objects, use the `object` mode. Possible values: `world`, `object`, `foliage`. Default value: `world`.

-   `SnowUpNoiseIntensity="0"`  
    Intensity of the noise pattern used during the creation of the snow layer.
    Default value: `0.0`

-   `SnowUpNoiseScale="0.5"`  
    Noise frequency of the snow layer.
    Default value: `0.5`

-   `SnowUpAngleRange="45"`
    The maximum angle of deviation of the surface normal from the upwards vector, at which a snow layer will be applied.
    Default value: `45`.

-   `SnowUpFlatten="0"`
    The leveling coefficient for the original normal map (in the area of ​​the surface where the snow layer was applied).  
    Value range: `[0.0 - 1.0]`  
    Default value: `0.0`

-   `SnowifyNoiseIntensity="40"`
    The intensity of the effect of snow powder on the surface.
    Default value: `0.0`

-   `SnowifyNoiseIntensityShift="40"`
    The coefficient that increases the influence of the shading mask for the ambient light on the intensity of snow powder.
    Default value: `0.0`

-   `SnowifyNoiseTilingMult="1"`
    The tiling effect multiplier for snow powder.
    Default value: `1.0`

-   `ForceSnowUnderwater="true"`
    If enabled, this parameter forces snow overlay even after the surface is submerged in water. By default, the snow overlay is cleaned in these cases.

-   `DOFOrder="DistanceBased"`
    Currently not used in the game.

