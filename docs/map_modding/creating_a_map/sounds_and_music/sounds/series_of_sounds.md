# Series of Sounds

When configuring a [sound actor](./adding_sounds.md) or a [sound domain](./../sound_domains/adding_sound_domains.md), you can specify not a single specific sound file to be played, but a random alternation of the sounds from a specific set. 

For example, the barking of a dog can be played as a series of barking sounds, where each successive sound will be different from the previous one.

If you browse the `shared_sound.pak` archive, you will see that nany series of the files in its `[sound]` directory have been designed that way.

**NOTE**: The `shared_sound.pak` archive is located in the folder with [`initial.pak`][initial_pak].

Let's illustrate the "Series of Sounds" mechanics on the set of sounds for a night owl, created for *SnowRunner*. 

In *SnowRunner*'s `shared_sound.pak`, you can find it in the `[sound]\amb\amb_us_autumn\amb_us_autumn_night_forest_owl\` directory. 

This directory consists of `5` sounds. Each of these sound files has the `__<N>` suffix (the double underscore with a number) in the file name:

-   `amb_us_autumn_night_owl_rnd__1.pcm`

-   `amb_us_autumn_night_owl_rnd__2.pcm`

-   `amb_us_autumn_night_owl_rnd__3.pcm`

-   `amb_us_autumn_night_owl_rnd__4.pcm`

-   `amb_us_autumn_night_owl_rnd__5.pcm`

To configure the sound actor to play a series of these sounds, rather than a particular sound, you need to specify the name of one of these files without its `__<N>` suffix in the **Sound file** field of this [actor](./adding_sounds.md).

In this case, the whole series of these sounds will be played.

For example, to play in the sound actor all the files above, you can specify the following value of the **Sound file** parameter in the actor's properties:
`amb/amb_us_autumn/amb_us_autumn_night_forest_owl/amb_us_autumn_night_owl_rnd`

Series of sounds in *Expeditions* work the same way.




[initial_pak]: ./../../../getting_started/file_paths_and_naming/file_paths.md#source-of-info-initialpak-archive