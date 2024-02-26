# Foot

*This tag is used for SnowRunner only.*

The `<Foot>` tag corrsponds to a single leg from the pair of legs (landing gear) of the trailer/semi-trailer.

**NOTE**: This tag is used for trailers and semi-trailers only. It is *not* used for trucks.

The main purpose of this tag is to tell the system the position of the lower end of the "leg" of the trailer or semitrailer. This information is typically necessary for the correct placement of this trailer on the ground.

The number of such tags corresponds to the number legs of the trailer. For example, for a single pair of legs:

```xml
	</TruckData>
		…
		<Foot Origin="(3.2; -0.25; 0.9)" />
		<Foot Origin="(3.2; -0.25; -0.9)" />
	</TruckData>
```

Attributes:

-   `Origin="(3.2; -0.25; 0.9)"`  
    The position of the lower end of the "leg" of the trailer or semitrailer. This position is used for the correct placement of the trailer/semitrailer on the ground during spawning.

