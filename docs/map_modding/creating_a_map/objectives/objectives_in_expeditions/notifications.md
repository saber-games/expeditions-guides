# Notifications

*(NEW) This feature is valid for Expeditions only.*

## Overview
In Expeditions, you can display notifications to the player in the following situations:

-   *when the player accomplishes the whole [substage][stages_and_substages] of an objective.*  
    In this case, the notification data is configured in the **notification** section of the [substage][stages_and_substages].  
    For example, in the **visitAllZones** \> **notification** section.

-   *when the player accomplishes the particular [zone-related assignment][zone_related_assignment] of the [substage][stages_and_substages] of an objective.*  
    In this case, the notification data is configured in the **notification** section *within the zone-related settings* of the [substage][stages_and_substages].  
    For example, in the **visitAllZones** \> **zones** \> `[0]`, `[1]`, etc. \> **notification** section.

-   *when the player visits one of the [Fake Zones][fake_zones].*  
    In this case, the notification data is configured in the **notification** section *within the [Fake Zones][fake_zones]-related settings* of the [substage][stages_and_substages].  
    For example, in the **visitAllZones** \> **zones** \> `[0]`, `[1]`, etc. \> **Fake Zones** > `[0]`, `[1]`, etc. \> **notification** section.

-   *when the player visits a [ZonePropertyNotification][notification_zones] zone on the map.*  
    In this case, the notification data is configured in the **notification** section within the [*ZonePropertyNotification*][notification_zones] prop of the zone.  
    I.e., in the **ZonePropertyNotification** prop \> **notification** section.

Notifications for [zone-related assignments][zone_related_assignment] are currently supported for **objectConstruction**, **takeInventory**, **truckDelivery**, **visitAllZones**, **minigameInfo**, **scoutingInfo**, and **Seismograph Settings** types of substages.


## Setup
Settings with the **notification** section are the same for all cases listed above. They are the following:

-   **notification** section – settings of displayed notification. You can select 3 classes here: **NotificationBase**, **NotificationFromBase**, **NotificationFromSpecialist**. However, currently, only the **NotificationBase** class is used in the game, others are reserved for the possible future use. All of them have almost the same properties, see below:

    -   **Timeout** – the timeout before the notification, in seconds.
    -   **Image** – the image to be displayed along with the textual notification. Custom images for this field are not supported.
    -   **UI Text** – the list of textual notifications to be shown. However, in the current version of the game, only the first record (`[0]`) from this list is shown. Other records were reserved for the possible future use and are currently not displayed.



[stages_and_substages]: ./stages/stages_in_expeditions.md
[zone_related_assignment]: ./stages/stages_in_expeditions.md#multiple-zone-related-assignments-within-substage
[fake_zones]: ./fake_zones.md
[notification_zones]: ./../../zones/expeditions_zones/notification_zones.md