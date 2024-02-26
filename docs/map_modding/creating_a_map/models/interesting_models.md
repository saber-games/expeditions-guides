# Interesting Models

You can add various interesting models to your map to enhance its atmosphere or give a point of interest to the player.

## For Expeditions
In *Expeditions*:

-   Some animal models have the `animal` suffix.
-   Some models of totems have the `totem` suffix.
-   Some UFO-related objects have the `ufo` in their names.   

There are [overlays][overlays] with the `animal_tracks` suffix.

As in *SnowRunner*:

-   Animated models have `_objective` suffix
-   Far plane models have `farplane` suffix.


## For SnowRunner
In *SnowRunner*, The current list of such models is the following:

-   **air_balloon1**, **air_balloon2**, **air_balloon3**, **air_balloon4**, **air_balloon5** – air baloons

-   **anim_rus_garage_07** – an old garage with an animated figure of man within.

-   **bear_01** – a static figure of a white bear.

-   **bird_crow**, **bird_crow_notshy** – a static figure of a crow.

-   **birds_flying_01** – an animated group of flying birds.

-   **birds_sea_01** – an animated group of flying birds (sea birds).

-   **cat_01**, **cat_01_notshy** – a static figure of a cat.

-   **fireflies_animated_01** – an animated group of fireflies.

-   **fish_01_animated**, **fish_animated_us09, fish_static_us09** – animated and static fishes that can be placed within a River.

-   **fish_man_notshy** – a boat with a figure of a fisherman.

-   **hunter_01_notshy** – a figure of a hunter.

-   **mushroomer_01_notshy** – a figure of a mushroom hunter.

-   **ufo_01** – a UFO.

-   **us_boat_09_us06_animated** – a small fishing boat rocking on the waves.

-   **wolf**, **wolf_close**, **wolf_notshy** – a static wolf figure.

-   **wolf2** – shiny eyes of a wolf in the darkness (eyes are active at night).

-   **yeti_snow_man** – a static figure of Yeti (the Snowman).

You can add these creatures to the map as regular models. They require no additional setup. However, there are some important nuances in their visibility to the player:

-   Some models are visible to the player *only at the particular distance*. For example, some creatures are visible only when the distance to them is between `50` and `150` meters. I.e., if a distance to such a model is less than 50 meters or greater than 150 meters, the model becomes invisible.

-   The **...\_notshy** models do *not* become invisible at close distances.

-   The \"**wolf2**\" model (which displays eyes in the darkness) is visible only at night.


[overlays]:./../overlays/adding_overlays.md
