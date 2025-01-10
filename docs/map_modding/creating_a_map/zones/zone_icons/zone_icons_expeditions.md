# Zone Icons in Expeditions

!!! note

    This topic is valid only for Expeditions. For info on SnowRunner zone icons, see [Zone Icons in SnowRunner](./zone_icons_snowrunner.md).

Expeditions have an internal mechanism that automatically assigns icons to zones. The assigned icon is based on:

-   [Props][props_section] added to this zone.
-   [Objectives][objectives] that use this zone.

In general, this mechanism is applied to all zones of the map, without exceptions. In most cases, you do not need to specify icon names in the **Icon 30x30** and **Icon 40x40** fields in the [zone locator][zone_locator] properties. The icons will be assigned automatically.

However, some game entities – *Climbs*, *Fords*, and *Shortcuts* – have the same props ([*ZonePropertyHiddenHint*][zonepropertyhiddenhint]) and properties, but these entities should have different icons. For them, you can use the icons from the following table:

| **Object** | **Icon 30x30**       | **Icon 40x40**       |
|-------------------|----------------------|----------------------|
| *Climb*           | `exMountainAccess30` | `exMountainAccess40` |
| *Ford*            | `exRiverFord30`      | `exRiverFord40`      |
| *Shortcut*        | `exShortWay30`       | `exShortWay40`       |


[props_section]: ./../zones_overview.md#props
[objectives]: ./../../objectives/objectives_overview.md
[zone_locator]: ./../zones_overview.md#zone-locator
[zonepropertyhiddenhint]: ./../expeditions_zones/hidden_hint_zones.md
