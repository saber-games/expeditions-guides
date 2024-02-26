# Ambient Preset XML file

Let's review the typical contents of the XML file of the Ambient Preset.

## Sample Ambient Preset File
```xml
<AmbientSounds>
	<Volume Min="0.6" Max="0.6" FadeTime="3.0"/>
	<Interval Min="1.0" Max="1.0" />
	<DayForest Sound="amb/aspen/day_forest_loop">
		<RandomSet
			Sound="amb/aspen/day_forest_birds1/day_forest_birds1_rnd"
			MinRadius = "10"
			MaxRadius = "35"
			MinInterval = "30"
			MaxInterval = "50"
			MinVolume = "0.5"
			MaxVolume = "0.7"
		/>
		<RandomSet
			Sound="amb/aspen/day_forest_birds2/day_forest_birds2_rnd"
			MinRadius = "10"
			MaxRadius = "35"
			MinInterval = "25"
			MaxInterval = "45"
			MinVolume = "0.5"
			MaxVolume = "0.7"
		/>
	</DayForest>ло	<DayWind Sound="amb/aspen/day_wind_loop">
		<RandomSet
			Sound="amb/aspen/day_wind_birds1/day_wind_birds1_rnd"
			MinRadius = "10"
			MaxRadius = "35"
			MinInterval = "25"
			MaxInterval = "50"
			MinVolume = "0.5"
			MaxVolume = "0.7"
		/>
		<RandomSet
			Sound="amb/aspen/day_wind_birds2/day_wind_birds2_rnd"
			MinRadius = "10"
			MaxRadius = "35"
			MinInterval = "30"
			MaxInterval = "50"
			MinVolume = "0.5"
			MaxVolume = "0.7"
		/>
	</DayWind>
	<NightForest Sound="amb/aspen/night_forest_loop">
		<RandomSet
			Sound="amb/aspen/night_forest_elves/elf_music"
			MinRadius = "18"
			MaxRadius = "55"
			MinInterval = "15"
			MaxInterval = "40"
			MinVolume = "0.5"
			MaxVolume = "1.0"
		/>
		<RandomSet
			Sound="amb/aspen/night_forest_owl/night_owl_rnd"
			MinRadius = "10"
			MaxRadius = "40"
			MinInterval = "25"
			MaxInterval = "50"
			MinVolume = "0.7"
			MaxVolume = "1.0"
		/>
	</NightForest>
	<NightWind Sound="amb/aspen/night_wind_loop">
		<RandomSet
			Sound="amb/aspen/night_wind_wolf/night_wind_wolf_rnd"
			MinRadius = "10"
			MaxRadius = "40"
			MinInterval = "25"
			MaxInterval = "55"
			MinVolume = "0.9"
			MaxVolume = "1.0"
		/>
	</NightWind>
	<WaterFlow
		Sound2D="amb/amb_river_flow_near_loop"
		Sound3D="amb/amb_river_flow_far_loop"
		MaxDist="150"
		Dist2D="0"
		Dist3D="30"
	/>
</AmbientSounds>
```
  

## `<Volume>` and `<Interval>` tags
The content of these tags does not change, typically. We recommend the following values for it:

```xml
	<Volume Min="0.6" Max="0.6" FadeTime="3.0"/>
	<Interval Min="1.0" Max="1.0" />
```

In previous versions of the game, the volume of ambient sounds was changing from `Min` to `Max`. However, typically, we do not want it to change, so we set equal values for `Min` and `Max` here. `FadeTime` - is the time interval between the adjacent ambient sounds, in seconds. It is also typically set to 3.0 seconds, which is a recommended value.

The `<Interval>` tag also has the `Min` and `Max` values. If these values are different, the system takes the random value from the `[Min, Max]` interval, and this value defines the interval of time (in seconds), within which the volume level will be defined by the value from `<Volume>` tag (also the random value from the `Volume`'s `[Min, Max]` interval). The system also remembers the current volume level, so, after the new volume level for the next interval is selected, the current volume level is changed smoothly to the new value.

After the time defined by `Interval`'s value passes, the system starts this algorithm from the beginning, i.e., selects a new `Interval` value, etc.

This algorithm is used to make ambient sounds more diverse. In the original game, we do not need it (and we set equal values for `Min` and `Max` of `Interval` ), since we solved this problem by a large number of various ambient sounds. However, it may be helpful for mods, since for mods the number of ambient sounds is typically less.


## `<DayForest>`, `<DayWind>`, `<NightForest>`, and `<NightWind>` tags
The particular set of sounds from the preset that will be selected for playback to the player depends on:

-   the in-game time, i.e. whether it is a day (`DAY`) or night (`NIGHT`).

-   the *type* of the area the player is in, i.e. whether it is open space (`WIND`) or not an open space ("forest", `FOREST`). The game automatically defines this type based on the predefined conditions and the position of the player on the map.

**NOTE**: When the player changes their position and, for example, moves from `DAY_FOREST` to `DAY_WIND`, the corresponding presets of ambient sounds are changed smoothly (they are blended).

I.e., we will have four different loops in one preset for different conditions: `DAY_FOREST`, `DAY_WIND`, `NIGHT_FOREST`, and `NIGHT_WIND`.

These four "condition subpresets" are defined in the main ambient preset using the `<DayForest>`, `<DayWind>`, `<NightForest>`, and `<NightWind>` tags.

**NOTE**: When you are specifying the value of the **Conditions** field for your sounds, you also use these conditions, see [Adding Sounds](./../sounds/adding_sounds.md).


## Main sound loops of "condition subpresets" and `<RandomSet>` tags
For each of these condition subpresets (`<DayForest>`, `<DayWind>`, etc.) you can specify two types of sounds:

1.  *Main sound loop*, which will be played constantly. It is specified in the `Sound` attribute of the corresponding subpreset. Typically, from the point of view of the file structure, it is *not* a series of sounds, but a single sound file (long loop). However, if necessary, you can use here a [series of sounds](./../sounds/series_of_sounds.md) too.  
    For example:
    
    ```xml
    <DayWind Sound="amb/my_level_1/day_wind_loop">
	...
	</DayWind>
	```
	Where `Sound` sets the sound or the series of sounds this condition subpreset will play on repeat. You need to specify the path to the file of the sound here, relative to the `Media\sounds\`** folder and without the file extension.  
    For example: E.g., `amb/my_level_1/day_wind_loop` for `Media\sounds\amb\my_level_1\day_wind_loop.wav`.  
    For more info on the properties of sound files and their location, see [Custom Ambient Sounds][custom_ambient_sounds] in this section.
    
    **NOTE**: If you are using a [series of sounds](./../sounds/series_of_sounds.md), the name of the file should be specified without the `__<N>`" suffix.

2.  *Random set*, which is played with specified time intervals *in addition to the main sound loop (over it)*. It is similar to the [**OneShotSoundDomain**](./../sound_domains/one_shot_sound_domain_properties.md), which covers all the map, i.e. the sound will also be played within a certain ring around the player, etc. The properties that define how the sound will be played here are identical to properties of **OneShotSoundDomain**.  
    There can be multiple random sets in one subpreset. Parameters of random sets are set within the `<RandomSet>` tags, which are children of the condition subpreset tags. There can be multiple `<RandomSet>` tags within a condition subpreset tag. Typically, the sound file(s) used in a random set is a [series of sounds](./../sounds/series_of_sounds.md).  
    For example:

    ```xml
    <DayWind Sound="amb/my_level_1/day_wind_loop">
	    <RandomSet
            Sound="amb/my_level_1/birds/birds_rnd"
	    	MinRadius = "10"
	    	MaxRadius = "35"
	    	MinInterval = "25"
	    	MaxInterval = "50"
	    	MinVolume = "0.5"
	    	MaxVolume = "0.7"
	    />
    </DayWind>
	```
    Where:
    
    -   `Sound` - the sound or the series of sounds this random set will play. ***You should use Mono sounds here.*** You need to specify the path to the file of the sound here, relative to the `Media\\sounds` folder and without the file extension. If you are using a series of sounds, the name of the file should be specified without the `__<N>` suffix.  
    For more info on the properties of sound files and their location, see [Custom Ambient Sounds][custom_ambient_sounds] in this section.

    -   `MinRadius` and `MaxRadius` - these fields set a ring around the player, with the inner radius of the ring equal to the Min value and its outer radius equal to the Max value. Both Min and Max values are specified in meters. The sound will be played at a random point inside this ring.

    -   `MinInterval` and `MaxInterval` - these fields set the minimum and maximum time intervals between sounds (in seconds). Each successive sound will be played after the previous one with a delay, and the value of this delay will be each time taken randomly from the `[Min, Max]` range.

    -   `MinVolume` and `MaxVolume` - the volume range of the played sounds. Each new sound will be played with a new random value of the volume from this range.


## `<Waterflow>` tag
This tag contains attributes that define the playback of the sounds of the river.

```xml
	<WaterFlow
		Sound2D="amb/amb_river_flow_near_loop"
		Sound3D="amb/amb_river_flow_far_loop"
		MaxDist="150"
		Dist2D="0"
		Dist3D="30"
	/>
```

**NOTE**: For these sounds to be played, the "sound riverbed" should be set up for the river, see [Adding River Sounds via "RiverMarkup][rivermarkup] for more details.

The parameters of this tag are the following:

-   `Sound2D` - the 2D sound that will be played *inside* the "sound riverbed" defined by the [RiverMarkup][rivermarkup]. I.e., the sound which is played when the player is *close* to the river. ***This must be a Mono sound and it must be looped.***  
    As with other sound fields in the preset, you need to specify the path to the file of the sound here, relative to the `Media\sounds` folder and without the file extension.

-   `Sound3D` - the 3D sound that will be played *outside* the "sound riverbed" defined by the [RiverMarkup][rivermarkup]. I.e., the sound which is played when the player is *far* from the river. ***This must be a Mono sound and it must be looped.***  
    As with other sound fields in the preset, you need to specify the path to the file of the sound here, relative to the `Media\sounds` folder and without the file extension.

-   `MaxDist` - the maximum distance, at which the sound of the river can be heard by the player (in meters). See `Dist3D` below.

-   `Dist2D` - the distance from the "sound riverbed", at which only the 2D sound of the river is played. See `Dist3D` below.

-   `Dist3D` - the distance from the "sound riverbed", at which the 2D sound of the river starts to be blended with its 3D sound.  
    I.e., the following rules are used:

    -   when the player is farther than `MaxDist` from the "sound riverbed" - no sound of the river is played

    -   when the distance is less than `MaxDist` but greater than `Dist3D` - the 3D sound will be played

    -   when the distance is less than `Dist3D` but greater than `Dist2D` - the 3D sound will be blended with 2D sound

    -   when the distance is less than `Dist2D` - only the 2D sound will be played


[rivermarkup]: ./../../rivers_and_water_objects/adding_river_sounds_via_river_markup.md
[custom_ambient_sounds]: ./custom_ambient_sounds.md