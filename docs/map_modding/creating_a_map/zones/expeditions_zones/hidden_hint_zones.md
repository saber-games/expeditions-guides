# Hidden Hint zones

*(NEW) This feature is valid for Expeditions only.*

## Main Function: Displaying Various Helper Objects 

Zones with *ZonePropertyHiddenHint* prop allow you to mark on the map a particular area that can be interesting to the player. 

Particularly, in the original game, these zones are used to display hints about new *Climbs*, *Fords*, and *Shortcuts*.

These zones will have no *zone locator* visible on the level. However, they will be visible via Binoculars, Drone, and in the Map mode.

Similarly to other zones, icons and names of this zones are set up in the properties of the *zone locator* in the Editor. Particularly, for *Climbs*, *Fords*, and *Shortcuts* the default icons are the following:

| **Helper object** | **Icon 30x30**       | **Icon 40x40**       |
|-------------------|----------------------|----------------------|
| *Climb*           | `exMountainAccess30` | `exMountainAccess40` |
| *Ford*            | `exRiverFord30`      | `exRiverFord40`      |
| *Shortcut*        | `exShortWay30`       | `exShortWay40`       |

## ZonePropertyHiddenHint Prop Settings
Settings of the *ZonePropertyHiddenHint* prop are the following:

-   **zoneDiscoverability** – settings related to the zone discovery. See [Discoverability of Zones](./discoverability_of_zones.md). 

