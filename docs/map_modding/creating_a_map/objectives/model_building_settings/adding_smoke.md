# Adding Smoke

*This topic is valid for SnowRunner only.*  

In *SnowRunner*, Starting with the *DLC 9* ("*Season 9: Renew & Rebuild*"), you can add smoke to your custom maps. This feature was used in the *DLC 9* and it is also available in the Editor.

Objects that initiate the smoke are small cubes that are available as regular `_objective` models:

-   `cube_objective_09`

-   `cube_objective_big_09`

-   `cube_objective_big_09_01`

-   `cube_objective_small_09_01`

-   `cube_objective_small_09_02`

Setup of the start and stop of smoke follows the general Model Building Settings pipeline, see [5.16.3. Model Building Settings](#model-building-settings) above.

However, there are few nuances:

-   Values of the `Name` attribute of the `<Subset>` tags – and, correspondingly, the names of states in **stagesProgress** – for smoke cubes are specific:

    -   `stage_visible` – corresponds to smoke on.

    -   `stage_hidden` – corresponds to smoke off.

-   The sources of the smoke – models of cubes themselves – are visible on map as white cubes and have collision. So, they should be placed below the terrain.

-   You can enable and disable multiple smokes at once by specifying the same **Tag** for them in the properties of their cubes.

**NOTE**: Currently, there is also a known issue with smokes: even if you have accomplished the related objective/stage and, by this, have disabled the smoke cube – this smoke cube will start to emit smoke again when you reload the level (e.g. by loading a saved game).

