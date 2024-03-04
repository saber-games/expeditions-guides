# Discoverability of Zones

*(NEW) This feature is valid for Expeditions only.*

The **zoneDiscoverability** settings in the properties of a zone specify how this zone can be discovered, set its current state and requirements for the zone discovery, and other settings related to the discovery of the zone.

The fields in this section are the following:

-   **state** – the "discoverability" state of the zone at the moment of its spawning, can be one of the following:

    -   `NOT_EXPLORED` – the zone is not discovered by the player. It does not appear on the map.
    -   `SEEN_BY_OPTCS_QUESTION_MARK` – the zone has been *partially* discovered by the player. It appears on the map as a question mark.
    -   `SEEN_BY_OPTCS_DISCOVERED` – the zone has been fully discovered by the player using Binoculars. It appears on the map as fully opened marker of the zone.
    -   `EXPLORED_BY_DRONE_FLIGHT_IN` – the zone has been fully discovered by the player using the Drone. It appears on the map as fully opened marker of the zone. 
    -   `EXPLORED_BY_TRUCK` – the zone has been fully discovered by the player using their truck. It appears on the map as fully opened marker of the zone.

-   **requiredSpecialistDrone** – the type of Specialist required to discover this zone *using the Drone*. The `NONE` value disables this requirement.

-   **requiredSpecialistBinocular** – the type of Specialist required to discover this zone *using the Binoculars*. The `NONE` value disables this requirement.

-   **discoverableByTruck** – whether or not this zone can be the player using *their truck*.

-   **discoverableByDrone** – whether or not this zone can be the player using *the Drone*.

-   **discoverableByBinocular** – whether or not this zone can be the player using *the Binoculars*.

-   **discoveryMessage** – the message that will appear in the UI upon the disovery of the zone.

-   **discoveryRewardMoney** – the reward that will be given to the player upon the disovery of the zone. Two classes of rewards are available here, but only one of them should be used:
    -   **ObjectiveRewardMoney** – allows you to specify the **amount** of money that will be given to the player upon the zone discovery.
    -   **ContestResultRewards** – *should not been used here.*
