# Common Fields of Objectives

*This topic is valid for SnowRunner only.*  
*For common fields of objectives in Expeditions, see [Common Fields of Objectives](./../objectives_in_expeditions/common_fields_of_objectives.md).*

In *SnowRunner*, most fields of [Contracts](./contracts.md), [Tasks](./tasks.md), and [Contensts](./contests.md) are the same.

They are the following:

-   *Name* – The name of the objective is specified when you create a new Contract, Task, or Contest in the corresponding list. In the Zone Settings plugin, it is displayed not as the field, but as the name of the section (see screenshot below).

    **NOTE**: The names of the objectives must be unique, even objectives with different types must have different names! E.g., if a task and a contract have the same name, this can result in unpredicted behavior.

    ![](./media/image304.png)

-   **Ui Desc** – the description of the objective.

-   **Required rank** – the minimum rank of the player that is required for the objective.

-   **Blocked By Map** – allows you to lock/hide objective until the player opens the particular map (of the Region), see [Locking Objectives based on Exploration](./../../regions/locking_objectives_based_on_exploration.md).

-   **Reward Description** – the description of the reward received after accomplishing this objective.

-   **Recommendation** – you can select one of the standard in-game recommendations for this objective here. The corresponding recommendation will be displayed to the player in the UI.

-   **Additional message below Recommendation** – *(optional field)* Some message related to the objective that you want to display below the **Recommendation** text (but with the same formatting), see above.

-   **Don't show reward pop-up** – whether or not the game should display the reward pop-up to the player.

-   **Don't show markers ingame and on minimap** – This option can be used specifically for maps that will be played in Hard Mode. If you enable it, the precise markers for some objects that are shown in the game and on minimap will not be shown to the player. For example, if this option is enabled and the player needs to deliver the particular object located somewhere on the map, then:

    -   In the **Normal** mode, there will be the marker showing the precise location of the object.

    -   In the **Hard Mode**, on the same map, there will be no such marker and, instead of it, the approximate zone where this object might be located will be shown on the navigation map.

-   **minimapList** – This drop-down is used for tweaking the UI of an objective (shown to the player on the minimap) a bit. It has two possible values:

    -   **TINY** – makes the area used for displaying Stages of an objective smaller and allows the player to scroll them.

    -   **DEFAULT** – the stages of the objective are displayed as usual.

-   **isNeedRaceMusic** – This option was made specifically for *DLC7* (*"Season 7: Compete & Conquer"*). It allows you to switch regular music that is played on your map to the predefined racing music used in *DLC 7*.

-   **isCoop** – When enabled, this option will enable the cooperative game logic for this objective and will hide it in the single player game. This option was developed specifically for such cooperative objectives as racing Contests of the *DLC 7* (*"Season 7: Compete & Conquer"*). This option is not intended to work with objectives of different types and will have unpredicted behavior for them (use at your own risk).
    
    **NOTE**: For correct behaviour of racing Contests you will also need to enable the **pvpCoopOn** option in [5.16.2.4. Specific fields for Contests](#specific-fields-for-contests), see below.

-   **isRepeatable** – This option allows you to mark this objective (a Task, Contract or Contest) as a repeatable objective. If this option is enabled, the player becomes able to repeat the execution of the objective after finishing it. In fact, this option works similarly to the "Restart objective" feature, i.e., the objective giver zone will be active after the fulfillment of the objective, all items that were spawned within the Stages of the objective will be re-spawned, necessary zones of the objective will become active again after its start, and so on. This option was created specifically to repeat tasks related to farming, but can be used for other types of objectives too.

-   **Stages** – see [Stages in SnowRunner](./stages/stages_in_snowrunner.md).

-   **ModelBuildingSettings** – see [Model Building Settings](./../model_building_settings/model_building_settings.md).

-   **Blocker Objectives** – the list with the ***names*** of objectives you need to accomplish to receive the current objective (see "*Name*" above).

-   **Special jingle settings** – these settings allow you to specify the special jingle that will be played when the player accomplishes the objective and whether it should be played along with the cinematic (if it exists).

    **WARNING**: Currently, these settings do not work. They will be either fixed, or removed from the future versions of the Editor.

    Particularly:

    -   **Play Jingle with cinematic (if exist)** – If enabled, this option will tell the system to play the specified custom jingle simultaneously with the cinematic that should be played at the accomplishing of the objective (if such cinematic is configured). The configuration of this cinematic can be done via the particular `_objective` Model that contains animation and **Model Building Settings (Depend on Stages)** settings of the objective. See [Model Building Settings](./../model_building_settings/model_building_settings.md) for details on configuring it (**Scenario #2** in this section).

    -   **Special jingle (instead of classic)** – the path and name of the jingle sound file, relative to the `Media\sounds` folder and *without the file extension*. The requirements for the sound file are the following:  
        ***Format***: 44 kHz, Stereo, 16 bit, stored as .wav file.  
        ***Location***: You should put the .wav file of the jingle to the `Media\sounds` folder or a subfolder there. However, if you put it to the subfolder, the value of the **Special jingle (instead of classic)** field must reflect it.  

        E.g, if use the `Media\sounds\music_jingle_sample.wav` file, the value of the **Special jingle (instead of classic)** field will be simply `music_jingle_sample`. However, if you use `Media\sounds\music\music_jingle_sample.wav` the value of the **Special jingle (instead of classic)** field will be `music/music_jingle_sample`.

-   **Forced Daytime** – these settings allow you to set a particular Daytime Preset for the level upon the activation of the objective by the player.

    **WARNING**: Currently, these settings do not work. They will be either fixed, or removed from the future versions of the Editor.

    Particularly:

    -   **daytime** – specifies the name of the existing Daytime Preset specified for the level (see **Daytime Presets** in [Terrain Properties](./../../terrain/terrain_properties.md)). This preset will be automatically set upon the activation of the objective.

    -   **level** – the identifier of the map (the name of the XML file of the map, *without the file extension*).

-   **rewards** – this section allows you to add rewards for the objective. See [Rewards](./rewards.md) for details.

-   **trucksWithoutForceGrounding** – this optional section allows you to list the trucks that will *not* be correctly positioned according to the height of the terrain. To add a truck to this list, assign an Id to it, and add this Id to the list.

-   **FreezeTrailer** – Settings for freezing and unfreezing a particular trailer, with Powered Constraints-based animation, if the trailer has it. See [Freezing Trailers](./freezing_trailers.md) for details.


**NOTE**: However, along with fields listed above, there are also fields that are *specific* to [Contracts](./contracts.md), [Tasks](./tasks.md), and [Contensts](./contests.md).


[zones_overview]: ./../../zones/zones_overview.md