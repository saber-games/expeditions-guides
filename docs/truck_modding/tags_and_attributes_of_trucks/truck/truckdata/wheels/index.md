# Wheels

Section that describes wheels of the truck.

Attributes of this tag may contain information about the default tire and rim. All wheels of the truck are described in the form of child tags of this tag.

**NOTE**: Particular types of wheels that are compatible with the truck are set by the [`<CompatibleWheels>`] tags.

Attributes:

*In case of wheels as "sets of tires and rims":*

-   `DefaultRim="rim_1"`  
    The name of the default rim specified in the file referenced by `DefaultWheelType`.

-   `DefaultTire="highway_1"`  
    The name of the default tire specified in the file referenced by `DefaultWheelType`.

-   `DefaultWheelType="wheels_example"`  
    The name of the default XML class of the wheels in the `/classes/wheels/` folder, without extension.  
    E.g. `wheels_example` for `.../classes/wheels/wheels_example.xml`.

*In case of wheels as "single entities":*

-   N/A



[compatiblewheels]: ./../compatiblewheels/index.md