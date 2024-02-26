# Notification zones

*(NEW) This feature is valid for Expeditions only.*

## Main Function: Notification of the Player
A *ZonePropertyNotification* zone allows you to display a certain notification to the player when they reach the particular zone on the map.

**NOTE**: Zone locators are shown for these zones only in the Editor. I.e., in the game, the player has no visual signs for these zones – the player only sees their notifications.

These zones show the specified notification either *every time* the player reaches them, or *once*.


## ZonePropertyNotification Prop Settings
Settings of the *ZonePropertyNotification* prop are the following:

-   **executedOnce** – whether this notification should be shown once (enabled option) or every time (disabled option).

-   **zoneDiscoverability** – *(should not be used for this zone, since this zone is not displayed in the game anyway)* settings related to the zone discovery. See [Discoverability of Zones](./discoverability_of_zones.md). 

-   **notification** – settings of the notification displayed to the player. The settings here are identical to settings of notifications displayed upon the completion of the substage of an objective. See [Notifications](./../../objectives/objectives_in_expeditions/notifications.md) for details.

