# minigameInfo

*(NEW) This feature is valid for Expeditions only.*  

## Overview
The **minigameInfo** [substage][stages_and_substages] corresponds to an assignment where the player needs to play the  [minigame(s)][minigame] of the particular type.

**NOTE**: Most of the minigame settings – including settings specific for the particular type of the [minigame][minigame] – are set up during the configuration of the *zone* of the minigame, within its *ZonePropertyMinigame* prop.

The general process of configuring the minigame zone and minigame substage is desribed in [Minigames: Overview][minigame]. 

The minigame type-specific settings are described in the corresponding topics of the [**Minigames**][minigame] section: [Visual Inspection][visual_inspection], [Taking Photos][taking_photos], and so on.

This topic contains only the description of fields of the **minigameInfo** substage itself, for other info please refer to the topics mentioned above. 

**TIP**: Actualy, the most important settings of the **minigameInfo** substage are **globalZoneId** and **name** that link this substage to the particular zone with the *ZonePropertyMinigame* prop and the particular minigame configured within it, correspondingly. Other settings of this substage are typical for most substages.  

**NOTE**: The **minigameInfo** substage may have [multiple target zones][zone_related_assignments] where the player will need to play minigames. Or, in other words, this substage can include multiple minigames to be played at their zones. These minigames correspond to records in the **minigames** list: `[0]`, `[1]`, etc. The **globalZoneId** and **name** values of these minigames (and other substage settings) are set up within these records.


## Setup
After selecting the appropriate settings type, the **minigameInfo** section will contain the following settings:

-   **minigames** list – The list of minigames to be played. At least one record in this list is required. If you add multiple records to this list, the player will need to play *all* these minigames, in any order.

    -   `[0]`, `[1]`, `[2]`, etc. – The record of the particular minigame that needs to be played.

        -   **OptionalToPerform** – *(Optional)* Enabling this option will mark this substage as optional. By default, this option is disabled and the substage is required. See [Optional Substages][optional_substages] for details.

        -   **name** –  The identifier of the *particular minigame* that is configured within the minigame zone (the **zoneGloballd** field below). Should be exactly the same as the **name** value specified for this minigame in the settings of this zone (*ZonePropertyMinigame* \> **setting** \> **name**).

        -   **uiDesc** – The name of the substage that will be displayed in the UI of the game.

        -   **notification** – *(Optional)* The notification to be displayed after completion of this minigame-related assignment of the substage. See [Notifications][notifications] for details.

        -   **Fake Zones** – *(Optional)* The list of initially possible, but, after exploration, *unsuitable* zones for the execution of this assignment. See [Fake Zones][fake_zones] for details.

        -   **globalZoneId** – The target zone where the player will play the minigame. Should have all settings of this minigame configured within the *ZonePropertyMinigame* prop that needs to be added to this zone, see [above](#overview).

        -   **radiusSett** – *(Optional)* The radius of the [Zone Search Area][zone_search_area] where you want the player to search for the target zone, if you do *not* want to give the player its explicit location. See [Zone Search Area][zone_search_area] for details.

## Additional Info
If necessary, you can configure the minigame to be always enabled within the particular zone, without an objective. See [Minigames: Overview][minigame] for details.



[minigame]: ./../../../minigames/minigames_overview.md
[visual_inspection]: ./../../../minigames/visual_inspection.md
[taking_photos]: ./../../../minigames/taking_photos.md
[stages_and_substages]: ./stages_in_expeditions.md
[zone_related_assignments]: ./stages_in_expeditions.md#multiple-zone-related-assignments-within-substage
[notifications]: ./../notifications.md
[optional_substages]: ./../optional_substages.md
[fake_zones]: ./../fake_zones.md
[zone_search_area]: ./../zone_search_area.md


