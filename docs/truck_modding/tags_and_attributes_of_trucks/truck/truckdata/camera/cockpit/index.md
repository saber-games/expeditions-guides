# Cockpit

Internal camera and windshield.

Attributes:

-   `WindshieldDetailDensity="0.6"`  
    Tiling of the detailed texture (one common texture for all trucks, chips on the windshield). By default: `0.4`.


-   `WindshieldDiffuseTexture="trucks/tuz_16_actaeon_glass__d_a.tga"`  
    Diffuse map of the windshield texture (same as on the outside window of the truck). Located in the `.../textures/` folder.


-   `WindshieldShadingTexture="trucks/tuz_16_actaeon_glass__sh_d.tga"`  
    Shading map of the windshield texture (same as on the outside window of the truck). Located in the `.../textures/` folder.


-   `WindshieldDiffuseCleanAlpha="0.5"`  
    Transparency of the alpha channel. By default: `0`.


-   `WindshieldDiffuseAlphaContrast="0.5"`  
    Contrast of the alpha channel. By default: `1`.


-   `ViewPos="(1.148; 2.6; 0.488)"`  
    *(Mandatory.)* Default position of the internal camera.


-   `ViewDir="(1; -0.05; 0)"`  
    *(Mandatory.)* Default direction vector of the internal camera.


-   `LimitsHor="(-2.8; 2.4)"`  
    *(Mandatory.)* Limits for the horizontal rotation of the camera. Value in radians.


-   `LimitsVer="(-0.32; 0.2)"`  
    *(Mandatory.)* Limits for the vertical rotation of the camera. Value in radians.


-   `ZoomViewDirOffset="(0; -0.05; 0)"`  
    *(Mandatory.)* Shift of the direction vector in case of the camera zoom.


-   `ZoomViewPosOffset="(0.2; 0; 0)"`  
    *(Mandatory.)* Shift of the camera in case of the zoom.

