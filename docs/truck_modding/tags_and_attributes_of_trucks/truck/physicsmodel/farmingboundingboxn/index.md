# FarmingBoundingBoxN

*This tag is valid for SnowRunner only.* 

The `<FarmingBoundingBox1>` ... `<FarmingBoundingBoxN>` tags are used only for farming trailers.

There can be multiple `<FarmingBoundingBox..>` tags within the parent [`<PhysicsModel>`][physicsmodel] tag: `<FarmingBoundingBox1>`, `<FarmingBoundingBox2>`, `<FarmingBoundingBox3>`, and so on.

**WARNING**: You cannot omit numbers in the names of these tags. E.g., only `<FarmingBoundingBox3>` should go after `<FarmingBoundingBox2>`, not `<FarmingBoundingBox4>` or `<FarmingBoundingBox5>`. Otherwise, the `<FarmingBoundingBox..>` tags that go after this omission will be ignored by the system.

Every such tag allows you to set up the part of the trailer that will be interacting with the farming field. 

This part of the trailer is set up as a bounding box of the particular size that is attached to one of the bones the trailer's model. While passing over the farming field, this bounding box will transform one farming distribution of this field into another farming distribution.

**NOTE**: For details of farming distributions and the general setup of the farming field, see [Farming][farming] in **Map Modding**.

For example, in the original in-game `trailer_cultivator.xml`, this configuration looks like this:

```xml
	<PhysicsModel Mesh="trucks/trailers/trailer_cultivator">
		...
		<FarmingBoundingBox1 BaseBone="BoneTrailer_cdt" Min="(-5.23; -0.6; -2.81)" Max="(-1.97; 0.6; -0.14)" />
		<FarmingBoundingBox2 BaseBone="BoneTrailer_cdt" Min="(-5.23; -0.6; 0.14)" Max="(-1.97; 0.6; 2.81)" />
		<FarmingBoundingBox3 BaseBone="BoneTrailer_cdt" Min="(-9.15; -0.6; 0.14)" Max="(-5.66; 0.6; 2.81)" />
		<FarmingBoundingBox4 BaseBone="BoneTrailer_cdt" Min="(-9.15; -0.6; -2.81)" Max="(-5.66; 0.6; -0.14)" />
		...
	</PhysicsModel>
```

Attributes:

-   `BaseBone="BoneTrailer_cdt"`  
    The name of the bone of the trailer's model that the bounding box is attached to.

-   `Min="(-5.23; -0.6; -2.81)"`  
    The vector that specifies the coordinates of the "minimum" (lower, by X, Y, Z) corner of the bounding box. The size of the bounding box is determined by the `Min` and `Max` vectors.

-   `Max="(-1.97; 0.6; -0.14)"`  
    The vector that specifies the coordinates of the "maximum" (upper, by X, Y, Z) corner of the bounding box. The size of the bounding box is determined by the Min and Max vectors.

**NOTE**: Along with a set of the `<FarmingBoundingBox..>` tags, you will also need to specify the `FarmingTrailerType` in the [`<Truck>`][truck] tag for your farming trailer. For more details, see [Farming Trailers][farming_trailers].


[physicsmodel]: ./../index.md
[farming]: ./../../../../../map_modding/creating_a_map/farming/farming_overview.md
[truck]: ./../../index.md
[farming_trailers]: ./../../../../additional_info_on_trucks/farming_trailers/farming_trailers.md