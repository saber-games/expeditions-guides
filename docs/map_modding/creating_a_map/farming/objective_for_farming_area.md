# Objective for Farming Area

*This topic is valid for SnowRunner only.*  

## Overview
After you have created the [zone][farming_zone] and the [group of distributions][farming_distibutions] for your farming area, you can finally create an objective for it.

In general, your farming objective is created in the absolutely regular way, see [Objectives](./../objectives/objectives_overview.md) section for the general info on that. You can create it in the form you like: Contract, Task, or even Contest. All these types of objectives support farming assignments within them (e.g. cultivate the particular farming area, plant a certain vegetation, harvest the grown plants).

Similarly to other assignments, farming assignments are described as [Stages](./../objectives/objectives_overview.md#stages-and-substages).

Particularly, every farming assignment needs to be described within the separate **farmingInfo** section in the **Stages** list. Below comes the description of all fields of this section.


## Mechanics
However, before proceeding to these particular properties, let's highlight some general important things related to farming assignments:

-   Typically, there are multiple farming Stages within a Contract, Task, or Contest. The player needs to cultivate the field, then they need to seed it, then – to gather the harvest – all these assignments are described by separate Stages that go in the certain order, but, if necessary, with some other non-farming assignments (Stages) in between.

-   Farming stages are tied not only to a particular zone, but also to the group of distibutions (states of the field) that also must have a defined order. So, before or in parallel with creating these Stages within an objective, you need to create the [zone][farming_zone] and the [group of distributions][farming_distibutions] for the farming area.

-   Particulary, every farming Stage is using two distributions (states of the field) and defines the rules of transforming one of them into another:

    -   *The first one* – is the state of the field that the player has at the start of Stage. Looking ahead, we can say that this state (distribution) of the field that is displayed *at the beginning* of the Stage must have a the state that is less than the **neededState**. I.e., its state should be one of the states thar are *previous* to **neededState**. However, you do *not* need to directly specify this state in the properties of this Stage, and the only requirement for this state is that its less than **neededState**. So, it can be *any* state that goes before it.

    -   *The second one* – the state (distribution) that will be appearing in the areas of the field where the player is performing the defined farming action (with the defined farming trailer). This distribution/state is the **neededState** defined for the Stage.

-   If you are wondering how the game will define that the player can interact with the field with one of farming trailers, here is the list of these criteria. The farming field will interact with the player's trailer if the active Stage of the current objective contains the **farmingInfo** section where:

    -   the **farmingZone** (see below) of this Stage corresponds to this farming field.

    -   the player is using the **requiredTrailer** (see below) of this Stage.

    -   the current state of the faming field is less than the **neededState** of this Stage.

-   When necessary, for some Stages, this transition of one distribution into another can be done at once and without any actions from the player, see **hideStageFromUi** below.


## Properties of farmingInfo section
The properties of **farmingInfo** section are the following:

![](./media/image369.png)

The main properties of the farmingInfo section are the following:

-   **requiredTrailer** – the farming trailer required for the assignment. Possible values:

    -   `Cultivator` – the trailer of this type is typically used for cultivating the farming area, to make the ground plowed.  
        *For example, `trailer_cultivator` that can be found in the Editor.*

    -   `Planter` – the trailer of this type is typically used for planting the vegetation on the farming field.  
        *For example, `trailer_planter` in the Editor.*

    -   `Harvester` – the trailer of this type is typically used for harvesting the farming field.  
        *For example, `trailer_harvester` in the Editor.*
        
        **NOTE**: The farming area will be interacting *only* with the specified trailer and the zone will iteract with it *only* when the current state of this field is goes before the **neededState** (i.e. when the fields in any of the previous states), see below.

-   **neededState** – The state of the farming field *that this field will be switched to* after the player will pass the required percentage of it (defined by **tolerance**, see below) with the **requiredTrailer**. There are `6` possible values of **neededState** and every such state is linked to the distribution with the corsponding **State** number. See the mapping table below and [Distributions for Farming Area](./distributions_for_farming_area.md).
 
    |**neededState** value         | Sequence number of Distribution        | Typical value of the **State** field of the Distribution  |
    |------------------------------|----------------------------------------|-----------------------------------------------------------|
    |`FIELD_STATE_DEFAULT`         |  The first (initial) distribution that is visible before any farming activities. | `0`             |
    |`FIELD_STATE_PLOWED`          |  The second distribution.                                                        | `1`             |
    |`FIELD_STATE_SOWN`            |  The third distribution.                                                         | `2`             |
    |`FIELD_STATE_SOWN_GROWN`      |  The forth distribution.                                                         | `3`             |
    |`FIELD_STATE_COMPLETE`        |  The fifth distribution.                                                         | `4`             |
    |`FIELD_STATE_COMPLETE_GROWN`  |  The sixth distribution.                                                         | `5`             |


    **NOTE 1**: The **neededState** field of the Stage corresponds *not* to the state of the farming field when the player *starts* this Stage, but to the final state of the filed when the player *finishes* this Stage. However, when the player *is performing* the Stage, the sections of the field that are passed by the player with a necessary farming tailer (**requiredTrailer**) are also converted to the distribution corresponding to the specified **neededState**.
    
    **NOTE 2**: The state (distribution) of the field that will be displayed *at the beginning* of the Stage must have a the state that is less than the **neededState**. I.e., its state should be one of the states thar are *previous* to **neededState**.  
    For example, for sample farming process described in [Distributions for Farming Area](./distributions_for_farming_area.md), for the Stage when the player will be planting potatoes on the field with the help of the Planter, the **neededState** will be equal to `FIELD_STATE_SOWN`, but the field, at the beginning of this process, will display the distribution corresponding to the previous state – `FIELD_STATE_PLOWED`. So, during the stage, the field will go from state `1` (second distribution) to state `2` (third distribution). If necessary, you can skip some states, and go not from `1` to `2`, but from `0` to `2`. But the state of the **neededState** must be greater than the current state of the field at the moment (e.g. `2 > 1` and `2 > 0`). Since you may have such transitions (e.g. from `0` to `4` or from `0` to `5`), the *current* state of the field is not specified in the Stage, only the **neededState**.

    **NOTE 3**: There are only a few requirements for a farming field to interact with the player's trailer during the Stage. Particularly, the farming field will interact with the player's trailer if the active Stage of the objective contains the **farmingInfo** section where:

    -   the **farmingZone** (see below) of this Stage corresponds to this farming field.
    -   the player is using the **requiredTrailer** (see above) of this Stage.
    -   the current state of the faming field is less than the **neededState** of this Stage.

-   **tolerance** – this coefficient, with possible values from `0` to `1`, defines the percentage of the farming field area that can be *omitted* by the player when they perform the stage. Indirectly, this value defines the *required* percentage of the farming field that the player needs to pass with the **requiredTrailer** to accomplish the Stage. The formula for the *required* percentage is the following:  
    `req_percentage = (1 – tolerance) * 100%`  
    For example, if you want the player to harvest the field with the Harvester and set tolerance for this Stage to `0.3`, then the player needs to perform this harvesting on the `(1 – 0.3) * 100% = 70%` percents of the field and this will be enough for the player to accomplish the Stage.
    
    **NOTE 1**: However, the percentage that the player will see in the UI can be higher than `(1 – tolerance) * 100%`, since this percentage corresponds to the progress of this particular farming assignment. E.g., even when **tolerance** equals to `0.3` (and `req_percentage` is `70%`), the player will see `95%` in the UI when they have completed `95%` *of the required 70% of the field*.
    
    **NOTE 2**: The precise process of calculating sections of the field worked by the player with the farming trailer (and transforming the current distribution into the next one in these areas) is not so simple as it seems to be. Particularly, the game tracks not the area passed by the trailer as a whole, but the area passed by specific (invisible) boxes that are set up in the trailer properties. See [Custom Trailers for Farming](./custom_trailers_for_farming.md) for details.

-   **hideStageFromUi** – Enabling this option will mark that this stage requires no actions from the player and should be hidden in the UI of the game. I.e., if you enable this option, no **UiDesc** will be displayed for this Stage and it will be passed automatically *when the player finishes the previous stage*. However, the game will do perform actions defined by this Stage, i.e. it will switch the field to the next distribution (corresponding to the state specified in **neededState**, see above), so, plants on the field *will do change*. By default, farming Stages do require actions from the player, so this option is initially disabled.
    
    **WARNING**: For Stages with enabled **hideStageFromUi** option, the value of **tolerance** (see above) *must* be equal to `1`. This will allow the game to perform the Stage automatically.

    **NOTE**: For example, in sample stages shown in the [Appendix](./appendix_sample_stages_of_farming_contract.md), there are two of these "hidden" Stages that do not require actions from the player. One of these Stages is placed after the planting stage and switches the field from the distribution with small sprouts of potato to the distribution with large potato sprouts at once, when the player has successfully finished planting of small potatoes. I.e., due to this "hidden" Stage, the planted small sprouts "grow" into the large ones on the entire field and there are no objectives displayed to the player at this moment.

-   **Ui** **Desc** – the description of the Stage assignment. For example: "Cultivate the field". Or, the UI_IDENTIFIER of this text if you want to provide your map [in multiple languages](./../../additional_info_on_maps/localization/localization.md).

-   **farmingZone** – the ID of the zone that you have created for this farming area. See [Zone for Farming Area](./zone_for_farming_area.md) for details on creating it.
    
    **NOTE**: If you have a Region with multiple maps, this zone must be located on the same map as the objective (on the map the objective is assigned to).

**TIP**: In the [Appendix: Sample Stages of Farming Contract](./appendix_sample_stages_of_farming_contract.md), you will find fully functional stages of a sample Contract for the farming area we have been creating used in [Zone for Farming Area](./zone_for_farming_area.md) and [Distributions for Farming Area](./distributions_for_farming_area.md).

## Model Building Settings
However, along with the main properties listed above, you can also specify [Model Building Settings](./../objectives/model_building_settings/model_building_settings.md) for the farming stage (see below).

![](./media/image370.png)

![](./media/image371.png)

As you can see, the fields in this **Model Building Settings** section are the same as in other sections of this kind. The mechanics is also the same – you can play a certain animation at the end (the successful completion) of the certain farming Stage.

The only difference of setting up this for farming stages is that you will probably want to play an animation related to farming, not to building or repairing.

However, to be able to do this, you will need an `_objective` model with this animation added to your map. Particularly, you will need to do the following:

1.  Add an animation source to your map, in the form of the `_objective` model, as with building/repairing animations.

2.  Tag this model in its properties and specify the same tag value in **modelTag** in the **Model Building Settings** section.

3.  In XML class of this `_objective` model model, look up the values of its states (values of the `Name` attributes of the `<Subset>` tags), and add them to **stagesProgress** list in **Model Building Settings**, specifying correct order for them.

After that, the specified animation will be shown to the player at the end of the Stage.

If necessary, you can use two `_objective` models from *DLC 8* that contain animations providing a look on your farming field: `field_animation_objective` and `field_animation_2_objective`.

They can be found in Editor. Their XMLs are at `[media]\_dlc\ru_08\classes\models\` of *SnowRunner*'s [`initial.pak`][initial_pak].



[farming_zone]: ./zone_for_farming_area.md
[farming_distibutions]: ./distributions_for_farming_area.md
[initial_pak]: ./../../getting_started/file_paths_and_naming/file_paths.md#source-of-info-initialpak-archive