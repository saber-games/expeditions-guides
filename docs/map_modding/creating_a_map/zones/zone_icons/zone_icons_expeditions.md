# Zone Icons in Expeditions

*(NEW) This topic is valid for Expeditions only.*  
*For info on zone icons for SnowRunner, see [Zone Icons in SnowRunner](./zone_icons_snowrunner.md).*  

In *Expeditions*, there is a special internal mechanics that assigns icons of zones automatically.

The assigned icon is based on:

-   [props][props_section] added to this zone.
-   [objectives][objectives] that use this zone.

In general, this mechanics is applied to all zones of the map, without exceptions.

So, for most cases, there is no need to specify names of icons in the **Icon 30x30** and **Icon 40x40** fields in the [zone locator][zone_locator] properties. They will be assigned automatically.

However, currently, some game entities – such as *Climbs*, *Fords*, and *Shortcuts* – have the same props ([*ZonePropertyHiddenHint*][zonepropertyhiddenhint]) and the same properties, but should display different icons. 

For them, you can use icons from the following table:

| **Helper object** | **Icon 30x30**       | **Icon 40x40**       |
|-------------------|----------------------|----------------------|
| *Climb*           | `exMountainAccess30` | `exMountainAccess40` |
| *Ford*            | `exRiverFord30`      | `exRiverFord40`      |
| *Shortcut*        | `exShortWay30`       | `exShortWay40`       |


[props_section]: ./../zones_overview.md#props
[objectives]: ./../../objectives/objectives_overview.md
[zone_locator]: ./../zones_overview.md#zone-locator
[zonepropertyhiddenhint]: ./../expeditions_zones/hidden_hint_zones.md

