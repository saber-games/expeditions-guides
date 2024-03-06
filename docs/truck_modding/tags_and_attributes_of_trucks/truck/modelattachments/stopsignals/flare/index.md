# Flare

The `<Flare>` tag describes the "Flare" light. 

"Flare" light is a point source of light that creates a glow around the particular point. It is visually similar to the bright light of a bulb or the distant light from the headlights.

For example, in *SnowRunner*, it looks like this:
![](./media/flare_light.png)

In *Expeditions*, it looks the same way.

Attributes:

-   `Pos="(3.759; 1.169; 0.944)"`  
    Light source position.

-   `Dir="(1; -0.3; 0)"`  
    Direction vector.

-   `DirAngle="90"`  
    The angle of visibility of the flare, in degrees.

-   `AttenStart="10"`  
    The start of attenuation of the brightness of the flare, in meters.  
    By default: `60`.

-   `AttenEnd="50"`  
    Maximum length on which the flare is visible. By default: 120.

-   `ParentFrame="BoneCabin_cdt"`  
    A bone from the hierarchy of the physical model, which Flare is attached to. If the parameter is not specified, then this is a root bone.

-   `Color="g(255; 186; 112) x 2\"`  
    Light color and brightness multiplier.  
    Default value: `"(0; 0; 0)"`.

-   `ColorMultAtDay="0.5"`  
    A coefficient of the light brightness during daytime.  
    By default: `1`. Values: `[0; 1000]`.

-   `Size="0.2"`  
    Size of the flare.  
    By default: `1`, Values: `[0.0001; 1000000]`.

-   `AspectRatio="1.4"`
    Aspect ratio.  
    By default: `1`, Values: `[-1000000; 1000000]`.

-   `Texture="sfx/flare_simple__s_d.tga"`  
    Path to the texture file of the shape of the flare.  
    Default value: `"sfx/flare_simple__s_d.tga"`.

-   `Reflections="true"`  
    Reflections.

