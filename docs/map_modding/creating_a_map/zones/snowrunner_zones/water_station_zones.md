# WaterStation zones

*This topic is valid for SnowRunner only.*  

The **ZonePropertyWaterStation** zones allow the player to perform various operations with water.

![](./media/image210.png)

The **ZonePropertyWaterStation** zone has the following properties:

-   **stationUIName** – the name of the zone for the UI. Default value of this field corresponds to the "Water Station" as a localized string.

-   **stationType** – the type of the zone:

    -   **PICK_UP** – these zones allow the player to *fill the water tanks of their truck* (this tank can be an addon or a trailer or a semitrailer). They allow only the "picking up" of water, i.e. water from the zone can fill the truck, but cannot go in the reverse direction.

    -   **DROP** – these zones allow the player to *fill the water tank of the zone from their truck tank*. They allow only the "dropping" of water, i.e. water from the truck can fill the zone, but cannot go in the reverse direction.

    -   **TRANSIT** – these zones allow the player to *transfer water from one such zone to another*. They act as a common reservoir connected to the certain amount of shared zones of TRANSIT type where each such zone can be used for both input and output of water. I.e, the water here is common for all shared zones and can go in both directions: player can either fill the water tank of their truck from this common reservoir, or fill this common reservoir from their truck tank.

-   **Water** – the *initial* *amount* of water (in liters) in the water reservoir of this zone. If you set the **Capacity** of the zone to infinity, you can also set its initial amount to the same value, by specifying `-1` as a value of this field.

-   **Capacity** – the *total capacity* of the water reservoir of this zone. The `-1` value means that the total capacity of the water reservoir is infinite.

-   **Is water delivery objective zone** – this option needs to be enabled, if this zone is the zone of the DROP type and, at the same time, is the target zone of some water delivery objective. Enabling this option will hide this zone before the activation of the objective and when the currect Stage of the objective is not using it as the target zone. For details, see [Water Delivery Objectives](./../../water_as_resource/water_delivery_objectives.md). For PICK_UP and TRANSIT zones – that are not used in objectives – this option should be disabled.

-   **Shared Water Zones** – *(valid for **TRANSIT** zones only)* The list of the **TRANSIT** zones that share the same water reservoir as this zone.

**NOTE**: For some hints on the setup of the zones of these types, see [Water as a Resource](./../../water_as_resource/water_as_resource.md) section.

