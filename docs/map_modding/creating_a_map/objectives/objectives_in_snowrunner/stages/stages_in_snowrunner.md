# Stages in SnowRunner

*This topic is valid for SnowRunner.*
*For a similar Expeditions topic, see [Stages in Expeditions](./../../objectives_in_expeditions/stages/stages_in_expeditions.md).*


## General Info
All objectives in Expeditions and SnowRunner consist of *Stages*. 

Every *Stage* corresponds to a group of assignments of particular types that the player needs to accomplish as a paticular stage of this objective. These assignments are called *Substages*.

Stages are created in the **Stages** list within the properties of the objective. For example, you can create Stage `[0]`, `[1]`, `[2]`, etc.

To create a Substage within a Stage, you need to fill in a certain section of settings within this Stage.  
For example, you can expand the `[0]` stage within the **Stages** list of a Task and fill in the **visitAllZones** section within this `[0]` stage – to tell the player to visit a particular zone at Stage `[0]`. By this, you will create the **visitAllZones** substage of the Stage `[0]`.

**NOTE**: For more general info on Stages and Substages, see [Objectives: Overview](./../../objectives_overview.md#stages-and-substages).


## Possible Types of Substages in SnowRunner
In SnowRunner, the list of possible substage types is the following:

-   **actions > zoneToFill** section – substage that corresponds to a delivery of goods, water, etc.
-   **truckDelivery** section – substage that corresponds to a delivery of the truck.
-   **truckRepair** section – substage that corresponds to repairing of the truck.
-   **changeTruck** section – substage where the player needs to sit in the particular truck.
-   **vizitAllZones** section – substage where the player needs to visit particular zones.
-   **Seismograph Settings** section – substage where the player needs to perform a seismic vibration in the particular non-displayed zones.
-   **spawnCargoOnStageActive** section – substage that can be used in two different ways:
    -   as a substage where the spawning of cargo is performed.
    -   as a substage where the player needs to locate certain cargo with the metal detector. 
-   **livingAreaInfo** section – substage that corresponds to a delivery of some cargo (typically *Cabins*) to the Living Area zone.
-   **farmingInfo** section – substage where the player needs to perform a farming assignment.


## Fields That Are Common For All Stages

Along with particular Substage sections mentioned above, every Stage also have a set of properties, displayed at the beginning of the Stage record within the **Stages** list. 

These properties are common for all Stages regardless of their type. They are the following:

-   **needToStartTimer** – This option allows you to start timer for Contracts and Contests that have specific time limit. I.e., for Contracts or Constests that have a configured **TimeFailReason** as one of the **failReasons**, see [Contacts](./../contracts.md) and [Contests](./../contests.md).  
See also: the **needToStartTimerInGiverZone** option in [Contests](./../contests.md). 
    
    **NOTE**: By default the **needToStartTimer** option is enabled for every Stage. However, if you disable it for some initial Stages of the time-limited Contract or Contest, the timer for them will start from the first Stage where it is enabled. For example, using this option, you can configure the behaviour when, at first, the player needs to reach some starting zone (Stage `[0]`, **needToStartTimer** = `false`) and, after it, needs to do something with a time limit (Stages `[1]`, `[2]`, ..., **needToStartTimer** = `true`).
 
-   **Don't display target cargo on map** – this option tells the game to *not* display markers for target cargo (e.g. that needs to be delivered to some zone) for the player *within the particular Stage*. This allows you to force the player to search for this cargo without markers in the UI. By default, this option is *disabled* and the target cargo markers are *shown*.
    
    **NOTE**: Regardless of its state, this option works as if it is enabled for objectives where the usage of metal detector is required, see [Metal Detector](./metal_detector.md).

-   **Ui Desc \[DEPRECATED\]** – *Deprecated field, please do not use it.* Instead of it, please use **uiDesc** fields in Stage sections related to the Stage type.

