# Minigames: Overview

*(NEW) This feature is valid for Expeditions only.*

## Overview
In Expeditions, the player is able to play various minigames: Visual Inspection, Scanning with a Drone, and so on.

These minigames can be both:

-   provided as a special stage of an Objective (the recommended scenario)
-   always enabled for the particular zone, without an objective

The high-level setup required for these scenarios is described below.

However, the particular settings of minigames do vary depending on their type. They are described in the corresponding topics of the same section:

-   [Visual Inspection](./visual_inspection.md)
-   [Taking Photos](./taking_photos.md)
-   [Echo Sounder](./echo_sounder.md)
-   [Scanning with Drone](./scanning_with_drone.md) 

## Minigame as a Stage of the Objective

The general process of setting up a minigame as a part of an objective is the following:

### Step 1: Create a Zone for the Minigame

1.  Create a new zone.
2.  Add the *ZonePropertyMinigame* prop to **props** of this zone.
3.  Configure its general properties:

    -   **alwaysAvailable** – whether or not the minigame should be always avialable for the player in this zone. Typically, for minigames within objectives, this is set to `false`. In this case, the zone locator and ability to play the minigame will be available only until the player passes the minigame.

    -   **zoneDiscoverability** – Settings related to the zone discovery. See [Discoverability of Zones](./../zones/expeditions_zones/discoverability_of_zones.md).

    -   **setting** – the type of the minigame that will be available within this zone. Particularly, it can be one of the following:

        -   **MinigameCamera** – [Taking Photos](./taking_photos.md) minigame.
        -   **MinigameEcholot** – [Echo Sounder](./echo_sounder.md) minigame.
        -   **MinigameProcessPoints** – [Scanning with Drone](./scanning_with_drone.md) minigame.
        -   **MinigameVisuallnspection** – [Visual Inspection](./visual_inspection.md) minigame.

4.  Within the **setting** section, specify the **name** of the minigame. This name will be the *identifier* of this minigame within this zone and you will need it later.

    **NOTE**: Since the **name** is an identifier, it must not contain spaces.

5.  Within the **setting** section, configure all other type-specific properties of the minigame.

6.  Save your changes.


### Step 2: Create a Stage for the Minigame

1.  Open the necessary [Stage][stages_and_substages] of the [Objective][objectives_overview].
2.  In this Stage, in the [**minigameInfo**][minigameinfo_substage] section, select **MinigameSettings**.
3.  Within the **minigameInfo** section, in the **minigames** list, add the new record by clicking the plus button. If you want to make multiple minigames available in the same zone, add the corresponding amount of records. One record of the list (e.g. `[0]`) corresponds to one minigame.
3.  Within the record of the minigame, specify the following minigame-specific properties:

    -   **name** – the identifier of the particular minigame within the minigame zone selected in **zoneGloballd**. Should be exactly the same as the value specified in the settings of the corresponding zone (*ZonePropertyMinigame* \> **setting** \> [**name**](#step-1-create-a-zone-for-the-minigame)). 
    -   **zoneGloballd** – the link to the zone with the *ZonePropertyMinigame* prop. 

4.  Specify **uiDesc** and other properties of the Stage, if necessary.
5.  Save your changes.


## Minigame without an Objective
If you want to configure a minigame to be always enabled within the particular zone, without an objective, you should perform only [Step 1](#step-1-create-a-zone-for-the-minigame) above.

However, in this case, you should set *ZonePropertyMinigame* \> **alwaysAvailable** option to `true`.

And, in this case, the *ZonePropertyMinigame* \> **setting** \> **name** is optional, since you do not need to link your objective to the minigame.



[stages_and_substages]: ./../objectives/objectives_in_expeditions/stages/stages_in_expeditions.md
[objectives_overview]: ./../objectives/objectives_overview.md
[minigameinfo_substage]: ./../objectives/objectives_in_expeditions/stages/minigameinfo.md

