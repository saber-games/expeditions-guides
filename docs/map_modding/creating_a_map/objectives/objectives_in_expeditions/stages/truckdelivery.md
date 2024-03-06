# truckDelivery

*(NEW) This feature is valid for Expeditions only.*  
*For the **truckDelivery** substage in SnowRunner, see [Truck Delivery][truck_delivery_snowrunner].*

## Overview
The **truckDelivery** [substage][stages_and_substages] corresponds to an assignment where the player needs to deliver the target truck located somewhere on the map to the particular zone(s).

To configure the **takeInventory** substage, you will need to add this target truck to the map in the Editor. And, in the properties of this truck in the Editor, specify the certain value of the **Id** field. After that, *exactly the same value* should be specified as **Truck Uid** for this truck in the **takeInventory** settings.

**NOTE**: This substage may have [multiple target trucks][zone_related_assignments] that the player should deliver. These trucks correspond to records within the **truckDelivery** section: `[0]`, `[1]`, etc. The target zones where these trucks should be delivered and the **Truck Uid** values of these trucks are set up on the per truck basis (within these records).


## Setup
The **takeInventory** section contains the following settings:

-   `[0]`, `[1]`, `[2]`, etc. – The record of the particular [zone-related assignment][zone_related_assignments] corresponding to the particular truck that the player needs to deliver.

    -   **Truck Uid** – The identifier of the truck that the player will need to deliver to the target zone. Should be exactly the same as **Id** in the properties of the target truck, see [above](#overview).

    -   **Truck UI Name** – The name of the target truck that will be displayed in the UI.

    -   **afterStageFinished** – The action that the game will perform with the target truck after the substage and/or the whole objective is accomplished:

        -   `REWARD` – *(Not used in Expeditions. Currently, does not work.)* Give the truck involved in the assignment as a reward to the player after the objective is finished. 
            
            **NOTE**: Currently, the `REWARD` option works as `DO_NOTHING`. I.e., if it is selected, the target truck remains on the map after the stage is finished. And, in this case, *no* new trucks are added to the player's list of trucks, the target truck type is *not* unlocked, and, correspondingly, the target truck is *not* shown on the REWARDS screen.
            *Alternatively*, you can give a new truck (even *not* the one from the map) as a reward to the player using the **ObjectiveRewardItem** type in the rewards list of the objective. Or, unlock this truck type using **ObjectiveRewardUnlock**. For details, see [Rewards][rewards].

        -   `DETACH` – *(Not used in Expeditions, but still available.)* After the stage is finished, the system will detach the truck involved in the assignment (if it has been attached to the player’s vehicle using the winch).

        -   `DESTROY` – *(Objectives in Expeditions use this option.)* After the stage is finished, the system will remove the truck involved in the assignment from the map.

        -   `DO_NOTHING` – *(Not used in Expeditions, but still available.)* After the stage is finished, the system will do nothing. I.e., the system will not destroy the truck, detach it, or give it as a reward.
    
    -   **Destroy After Substage (Dangerous!)** – By default, disabled. When enabled, removes the truck involved in the assignment from the map *not* after accomplishing the stage, but after accomplishing the particular **truckDelivery** substage. For example, if the Stage `[0]` of your objective consists of two substage assignments – **truckDelivery** and **vizitAllZones**, you can remove the target truck involved in **truckDelivery** directly after completion of this substage, without waiting for the whole Stage `[0]` to finish.

    -   **uiDesc** – The name of the substage that will be displayed in the UI of the game.

    -   **notification** – *(Optional)* The notification to be displayed after the truck delivery. See [Notifications][notifications] for details.

    -   **globalZoneDeliveryId** – The target zone which this truck needs to be delivered to.    

    -   **radiusSett** – *(Optional)* The radius of the [Zone Search Area][zone_search_area] where you want the player to search for the target zone, if you do *not* want to give the player its explicit location. See [Zone Search Area][zone_search_area] for details.

    -   **additionalDeliveryZones** – *(Optional)* the list of additional zones where the specified truck may be delivered (instead of the main target zone). 

[truck_delivery_snowrunner]: ./../../objectives_in_snowrunner/stages/truck_delivery.md
[stages_and_substages]: ./stages_in_expeditions.md
[zone_related_assignments]: ./stages_in_expeditions.md#multiple-zone-related-assignments-within-substage
[rewards]: ./../rewards.md
[notifications]: ./../notifications.md
[zone_search_area]: ./../zone_search_area.md

