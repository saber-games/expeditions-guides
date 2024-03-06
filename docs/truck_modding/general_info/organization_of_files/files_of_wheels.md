# Files of Wheels

Wheels of a truck include tires and rims and must contain both of these entities.
Wheels of trailers and semi-trailers may be created using the old scheme where a wheel is a single entity (similarly to the first Mudrunner).

The old scheme is the following:

1.  FBX file of the wheel, `/meshes/wheels/wheel_example.fbx`.

2.  XML file of a mesh, `/meshes/wheels/wheel_example.xml`, which contains information on textures and radius of the non-deformable part of the wheel (RubberRadius, wheel rim radius).

3.  XML file of a class, `/classes/wheels/wheel_example.xml`, which contains a description of the physical properties of the wheel (radius, width, friction, rigidity, etc.)

The new scheme describes not a wheel, but the particular *type* of the wheel. Wheels of this type may have different tires and rims. I.e., after selection of any rim from a wheel type, any tire from the same wheel type will fit with it well (and there will be no gaps or intersections of geometry):

1.  Set of FBX files for tires and rims in `/meshes/wheels/`:  
    `example_rim1.fbx`, `example_rim2.fbx`, ...  
    `example_tire1.fbx`, `example_tire2.fbx`, ...  

2.  Set of XML files for meshes of tires and rims that contain information on textures in
    `/meshes/wheels/`:  
    `example_rim1.xml`, `example_rim2.xml`, ...  
    `example_tire1.xml`, `example_tire2.xml`,...  

3.  XML file of a class, `/classes/wheels/wheel_example.xml`,  
    which contains the description of the physical properties of this type of wheels.   This file describes all tires and rims of this type and their properties.
