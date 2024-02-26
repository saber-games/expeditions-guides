# Optional Substages

*(NEW) This feature is valid for Expeditions only.*

## Overview
The *Optional Substages* mechanics allows you to mark certain [substages][stages_and_substages] within the stage of an objective as optional and do not require their execution by the player.

In this case, the player may perform or not perform these optional substages. The [stage][stages_and_substages] will be accomplished when the player executes all its substages that are *not* marked as optional. 

Typically, optional substages are used:

-   to enhance the variety of assignments available for the player
-   to avoid "blocking" of objectives that require the item that the player may not have

For example, a player may have a task with the **objectConstruction** [substage][stages_and_substages] that tells the player to deliver and install a *Camera Trap* in the particular zone.  Obviously, the player needs a *Camera Trap* [inventory item][inventory_item] to execute this substage. So, we can create an additional **takeInventory** [substage][stages_and_substages] that will allow the player to obtain this item. However, the player may have this item in the Inventory from the start, so we will make this **takeInventory** substage optional to allow the player to skip it.

**NOTE 1**: The example above is only *one of the possible variants* of describing gameplay scenarios using objectives. For example, as another variant, we could have created another objective that would provide this item. Or, due to our narrative, we could decide that obtaining this item should be required in any way (even if the player has the similar item) and would add **takeInventory** into a separate preceding [stage][stages_and_substages] (in this case, we would need to make this **takeInventory** substage required, not optional, see below).  

**NOTE 2**: When we make a particular substage optional, this should be supported by the corresponding narrative (**uiDesc** fields) to make the optional state of the assignment clear for the player.


## Setup
To mark the substage is optional, you will need to enable the **OptionalToPerform** option in this substage. This option is disabled by default – i.e., by default all created substages are required.

This option is available for all [substages][stages_and_substages], except **truckDelivery** and **freeRoamInfo**.

Thus, the process is the following:

1.  You set up a [substage][stages_and_substages] in a regular way.
2.  You enable the **OptionalToPerform** option for it.
3.  You specify the corresponding **uiDesc** text (or its localization) to notify that this substage is optional.
4.  You ensure that the *parent [stage][stages_and_substages]* of this optional substage has at least one *required* substage with disabled **OptionalToPerform**, see below.

**IMPORTANT**: Every stage of the objective must have *at least one* required substage where the **OptionalToPerform** option is *disabled*. I.e., stages where *all* substages are *optional* are prohibited and will lead to an error.

For example, we can create stage `[0]` with two substages:

*Stage `[0]`:*

-   **takeInventory** – *(optional, enabled **OptionalToPerform**)* allows the player to obtain some item from some zone. 
-   **objectConstruction** – *(required, disabled **OptionalToPerform**)* tells the player to deliver this item to another zone. 

Please note, that if we created two stages (`[0]` and `[1]`) and added **takeInventory** to a separate stage, it could *not* be optional (if it was the only substage). 

I.e., in this case, we would need to make this substage required:

*Stage `[0]`:*

-   **takeInventory** – *(required, disabled **OptionalToPerform**)* requires the player to obtain some item from some zone. 

*Stage `[1]`:*

-   **objectConstruction** – *(required, disabled **OptionalToPerform**)* tells the player to deliver this item to another zone. 



[stages_and_substages]: ./stages/stages_in_expeditions.md
[inventory_item]: ./../../../../custom_gameplay_entities/inventory_items/custom_inventory_items_overview.md