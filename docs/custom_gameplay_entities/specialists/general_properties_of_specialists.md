# General Properties of Specialists

## Main Properties 
When creating a Specialist, you always begin with specifying the following main properties:

-   **name** – the *identifier* of the Specialist. The specified value should contain only Latin characters, digits, and underscores (`_`). It must not contain spaces (` `).

-   **SpecialistSettings** – The settings of the Specialist. You should select the `SpecialistDesc` class here.


## General Properties
General properties are specified for all [Specialists](./custom_specialists_overview.md). 

They are the following:

-   **rang** – *(Optional. Not used. Will be removed)* This field is not used. It will be removed (`TBD`).

-   **speciality** – the [*class*][class] of the Specialist. Can be one of the following:

    -   `MECHANIC`
    -   `LOGISTIC_SPECIALIST`
    -   `HYDROLOGIST`
    -   `JAEGER`
    -   `OPERATOR`
    -   `MANAGER`

    **WARNING**: You must not select the `NONE` class in the **speciality** field. Specialists with the `NONE` class will crash the game. 

-   **cost** – The cost of hiring this Specialist.
-   **isLocked** – Whether or not this Specialist is locked. Locked specialists may be unlocked using a special reward granted after accomplishing the particular objective. See [Rewards][rewards] for details.

-   **upgradeToUnlock** – *(Optional. Not used. Will be removed)* This field is not used. It will be removed (`TBD`).

-   **uiName** – The name of the Specialist in the UI. If localization is necessary, you can use UI_IDENTIFIERS for localization strings within this text field. See [Localization][localization] for details. The name of the Specialist should not exceed `20` characters, including spaces.

-   **uiDesc** – The description of the Specialist in the UI. If localization is necessary, you can use UI_IDENTIFIERS for localization strings within this text field. See [Localization][localization] for details. The description of the Specialist should not exceed `280` characters, including spaces.

-   **bg** – The name of the medium-sized image of Specialist that will be displayed in the list of specialists at the **TEAM RECRUITMENT** screen and in the **Team Composition** list at the **EXPEDITION SETUP** screen. Format: `PNG`, Dimensions: `380 x 92`. Typically, this image has the transparent background and the image of the Specialist at the left side of it. Location of the image: This image should be put to the [folder of this specialist][folder_of_specialist] within `Documents\My Games\Expeditions\Media\Mods\`, into the `ui\textures` subfolder there. The name of the image in this field should be specified without its file extension.

-   **bgSmall** – The name of the small image of Specialist that will be displayed in the upper list of specialist slots at the **TEAM RECRUITMENT** screen. Format: `PNG`, Dimensions: `124 x 52`. Typically, this image has the transparent background and the image of the Specialist at the center of it. Location of the image: This image should be put to the [folder of this specialist][folder_of_specialist] within `Documents\My Games\Expeditions\Media\Mods\`, into the `ui\textures` subfolder there. The name of the image in this field should be specified without its file extension.

-   **bage** – The name of the badge picture of the Specialist, without the file extension. This picture will be displayed within the badge of this specialist at the **TEAM RECRUITMENT** screen. Typically, this image has the transparent background and the image of the Specialist at the center of it. Format: `PNG`, Dimensions: `293 х 293`. Location of the image: This image should be put to the [folder of this specialist][folder_of_specialist] within `Documents\My Games\Expeditions\Media\Mods\`, into the `ui\textures` subfolder there. 

-   **dbg_hided** – *(Optional. Will be removed)* Enabling this option will hide this Specialist at the **TEAM RECRUITMENT** screen. This field will be removed (`TBD`).

-   **modifiers** – the list of [*modifiers*][modifiers_definition] of this Specialist. For the list of possible modifiers, see [Modifiers of Specialists][modifiers].

[class]: ./custom_specialists_overview.md#class
[modifiers_definition]: ./custom_specialists_overview.md#modifiers
[modifiers]: ./modifiers_of_specialists.md
[rewards]: ./../../map_modding/creating_a_map/objectives/objectives_in_expeditions/rewards.md
[localization]: ./../../map_modding/additional_info_on_maps/localization/localization.md
[folder_of_specialist]: ./creation_of_custom_specialist.md#source-files