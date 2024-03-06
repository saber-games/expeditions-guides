# Internal Technical Props

*(NEW) This feature is valid for Expeditions only.*

Some *prop* types of zones are intendeded only for internal usage within the code of the game.

They are typically called *internal technical props* and should not be used when you select the **props** of your zone manually. Most of these props are either assigned automatically and internally by the game or used for internal inheritance of their properties.

Below is the list of these props:

-   *ZonePropertyFakeVisitZone* – the technical prop that is automatically assigned during the configuration of [Fake Zones](./../../objectives/objectives_in_expeditions/fake_zones.md). Should not be used during manual configuration.

-   *ZonePropertyInventoryStorageQuest* – the technical prop that is automatically assigned to a target zone of the [takeInventory](./../../objectives/objectives_in_expeditions/stages/takeinventory.md) stage during its configuration. Should not be used during the manual setup.

-   *ZonePopertyObjectConstruction* – the technical prop that is automatically assigned. Automatically used for target zones of **objectConstruction** stages. Should not be used during manual configuration. 

    **NOTE**: *ZonePopertyObjectConstruction* is a parent prop for the [*ZonePropertyObjectConstructionInZone*](./object_construction_in_zone_zones.md) prop that allows the player to "build" objects in particular zone(s) without any objectives on it. Unlike *ZonePopertyObjectConstruction*, the [*ZonePropertyObjectConstructionInZone*](./object_construction_in_zone_zones.md) prop should be manually added to the properties of the necessary zone.

-   *ZonePropertyScouting* – the technical prop that is automatically assigned. Should not be used during manual configuration.

