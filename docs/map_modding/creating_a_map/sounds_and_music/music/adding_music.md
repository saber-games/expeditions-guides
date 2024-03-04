# Adding Music

Follow the steps below to add custom music to your map.


## Step 1: Prepare Music Files

First of all, prepare your music files.

### Format
`44.1 kHz`, `Stereo`, `16 bit`, stored as `.wav` files.

The recommended volume level for the music is `-7 db`.

### Amount of Files
Typically, we prepare a separate music track for each time of the day and a separate track for the Garage. We name these tracks using the name of the level as a suffix (see below). This seems to be a good convention.

|  **Name of the file**                    |   **Description**       |     **For example**      |
|------------------------------------------|-------------------------|--------------------------|
|  `<levelname>_day`                       | Track for the day.      |   **aspen_day.wav**      |
|  `<levelname>_evening`                   |  Track for the evening. |   **aspen_evening.wav**  |
|  `<levelname>_morning`                   |   Track for the morning.|  **aspen_morning.wav**   |
|  `<levelname>_night`                     |   Track for the night.  |  **aspen_night.wav**     |
|  *For SnowRunner:* `garage_<levelname>`  |  Track for the Garage   |   **garage_aspen.wav**   |

However, if you want, you can use only one or two tracks and name them as you like.

### Length
The length of every music track is up to you. 

Please note that each music track will be played on repeat.


## Step 2: Put Files in Folder

Put your music files into the `Media\sounds\music\<name_of_level>` folder.

For example, the subfolder in music can be names `aspen` if you are creating it for the `level_aspen.xml` map.

For example, for *SnowRunner*, the resulting files may look like the following:

![](./media/image166.png)

For *Expeditions*, it will be similar.


## Step 3: Create or Modify music_presets.xml

Now, create or modify the `Media\classes\sounds\music_presets.xml` file:

1.  Create the **Media\classes\sounds** folder (if you have not created it before).

2.  In this folder, create the `music_presets.xml` file (if you have not created it before).
    
    **NOTE**: If you have already created this file for another level, you need to append it with new values corresponding to your new level (see below).

3.  In this file, for every level where you want to use music, specify links to your level and its music files, using `<LevelMusic>`, `<Sound>`, and *(for SnowRunner)* `<GarageMusic>` tags and their attributes.

For example, for *SnowRunner*:
```xml
<MusicPresets>
	<LevelMusic LevelName="level_aspen">
		<Sound 
			Name="music/aspen/aspen_night"
			StartTime="24"
			EndTime="6"
			FadeInTime="30"
			FadeOutTime="10"
		/>
		<Sound
			Name="music/aspen/aspen_morning"
			StartTime="6"
			EndTime="13"
			FadeInTime="30"
			FadeOutTime="10"
		/>
		<Sound 
			Name="music/aspen/aspen_day"
			StartTime="13"
			EndTime="20.5"
			FadeInTime="30"
			FadeOutTime="10"
		/>
		<Sound
			Name="music/aspen/aspen_evening"
			StartTime="20.5"
			EndTime="24"
			FadeInTime="30"
			FadeOutTime="10"
		/>
		<GarageMusic
			SoundName="music/aspen/garage_aspen"
			FadeInTime="30"
			FadeOutTime="10"
			Volume="1"
		/>
	</LevelMusic>
</MusicPresets>
```

Where:

-   `LevelName` - must correspond to the ***exact*** name of your map without file extension (e.g. `level_aspen` for `level_aspen.xml`).

-   `Name` and `SoundName` - must contain the path to the corresponding music track, relative to the `Media\sounds` folder and without the file extension. E.g., `music/aspen/aspen_evening` for `Media\sounds\music\aspen\aspen_evening.wav`.

-   If you are using separate music tracks for different times of the day, as in the example above, you should keep the values of `StartTime`, `EndTime`, `FadeInTime`, and `FadeOutTime`. They are already set up for correct switching of the tracks according to the change of daytime.  
    However, if you want to change them:

    -   `StartTime` and `EndTime` - specify the time of the beginning and end of the track, in in-game hours.  
        E.g., the `13` value here will correspond to `1:00 P.M`.

    -   `FadeInTime` and `FadeOutTime` - specify the fade in and fade out duration, in seconds.

-   `Volume` - coefficient that corresponds to the volume of the music in the Garage (for *SnowRunner*).


## Step 4: Repack Your Level
Open your level in the Editor, and repack it.

Now, if you have specified all values correctly, your level will contain music and you can test it by loading the level in the game. 

To switch between different times of the day, you can use the **Skip Time** feature on the navigation map.


## Disabling Music in Particular Area
If necessary, you can remove the playback of the music within a certain area using [**NoMusicSoundDomain**](./../sound_domains/no_music_sound_domain_properties.md).

