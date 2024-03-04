# OneShotSoundDomain Properties

**OneShotSoundDomain** domains are designed to play single 3D sounds inside a certain ring around a player when they enter the domain. Sounds will be generated at a random position within this ring. 

For example, you can configure a sound of the rockfall using this type of domain. When the player drives near a large rock and enters the domain located near it, the player will hear that the sounds of crumbling stones will be played around them at a random position with a certain frequency.

Properties of an **OneShotSoundDomain** are the following:

-   **Name** - the internal name of the sound domain in the Editor.

-   **Sound File** - sets a [sound][adding_sounds] or a [series of sounds][series_of_sounds] to be played. For domains, this field works the same way as for [regular sounds][adding_sounds]. Typically, **OneShotSoundDomain** is used to play a [series of sounds][series_of_sounds].

-   **Volume** (**Min**, **Max**) - the volume range of the played sounds. Each new sound will be played with a new random value of the volume from this range.

-   **Radius** (**Min**, **Max**) - these fields set a ring around the player, with the inner radius of the ring equal to the **Min** value and its outer radius equal to the **Max** value. Both **Min** and **Max** values are specified in meters. The sound will be played at a random point inside this ring.

-   **Interval** (**Min**, **Max**) - these fields set the minimum and maximum time intervals between sounds (in seconds). Each successive sound will be played after the previous one with a delay, and the value of this delay will be each time taken randomly from the `[Min, Max]` range.

-   **Weather Intensity threshold** - this field is currently not used. You should keep the default value of it, which is `-1`.

-   **Conditions** - if this parameter is not specified (the field is empty), the sound will play at any time, during day or night. However, you can limit the interval during which it can be played:

    -   If you want to play your sound only during the day, then you should set this parameter to `DAY_FOREST, DAY_WIND`  
        Please note that these two comma-separated IDs are the single value of this parameter, not the two values. They cannot be used separately.

    -   If you want to play your sound only during the night, then you should set this parameter to `NIGHT_FOREST, NIGHT_WIND`  
        These two comma-separated IDs are also the single value of this parameter and cannot be used separately.



[series_of_sounds]: ./../sounds/series_of_sounds.md
[adding_sounds]: ./../sounds/adding_sounds.md



