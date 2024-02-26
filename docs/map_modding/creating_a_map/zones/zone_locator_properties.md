# Zone Locator Properties

**NOTE**: For general info on *zones*, *zone locators*, and *zone props*, see [Zones: Overview][zones_overview].

Along with modification of the zone logic using [props][zones_overview_props], you may want to modify the properties of the [zone locator][zones_overview_zone_locator] itself. 

You can do it in the Editor, after selecting a [zone locator][zones_overview_zone_locator] in the **Zones** list in **Scene View**.

The properties of the zone locator are the following:

-   **Org X**, **Org Z** – Coordinates of the zone on the map.

-   **Dir** – The direction vector of the zone on the map. The direction of the zone is marked with the purple arrow within its zone locator.

-   **Id** – The identifier of the zone locator. This particular identifier is used to identify the zone in the Editor and the Zone Settings plugin.

-   **Icon 30x30**, **Icon 40x40** – In these fields, you can specify the identifiers of icons that will be used for the zone on the mini-map and in the game.

    **NOTE**: Lists of possible values for icon identifiers can be found in [Zone Icons in Expeditions][zone_icons_expeditions] and [Zone Icons in SnowRunner][zone_icons_snowrunner]. 

-   **Name** – The name of the zone that will be displayed in the UI.

-   **Is Visible On Minimap** – Whether the zone is visible on the map in the game. `True` will make it visible (if it is properly configrued). `False` will hide it. 

-   **Wall** section – Initially, the zone lies on the surface of the map. However, sometimes it is necessary to raise it above the surface. In this case, you can use the following settings:

    -   **Is Wall** – Make the 3D zone.

    -   **Height** – The height to which the zone will be raised.

-   **Shape Type** – The shape of the zone (rectangular or circle).

-   **Dimensions** – Settings of the actual dimensions of the zone:

    -   **Length or diameter** – The length or, if **Shape Type** = `Circle`, the diameter of the zone.

    -   **Width** – The width of the zone.

-   **Border** section – Settings of the border of the zone:

    -   **Rounding Radius** – The radius for rounded corners of the zone border.

    -   **Thickness** – The thickness of the border

    -   **Scroll Speed and direction** – The speed of movement of the dashed line on the zone border and the direction of such movement. The direction is specified by the minus sign (`-`) or its absence.

    -   **Opacity** – The transparency of the border.

-   **Distributions group name** – The special field that is used in *SnowRunner* only, see below.  
    *In Expeditions:*  
    Not used.  
    *In SnowRunner:*  
    The name of the specific group of distributions created during the setup of a [Farming][farming_overview] objective.


[zones_overview]: ./zones_overview.md
[zones_overview_props]: ./zones_overview.md#props
[zones_overview_zone_locator]: ./zones_overview.md#zone-locator
[zone_icons_expeditions]: ./zone_icons/zone_icons_expeditions.md
[zone_icons_snowrunner]: ./zone_icons/zone_icons_snowrunner.md
[farming_overview]: ./../farming/farming_overview.md