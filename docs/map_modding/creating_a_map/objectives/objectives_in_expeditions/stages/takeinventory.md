# takeInventory

*(NEW) This feature is valid for Expeditions only.*

## Overview
The **takeInventory** [substage][stages_and_substages] corresponds to an assignment where the player needs to take a set of different [Inventory Items][inventory_item] from the particular zone(s).

**NOTE**: This substage may have [multiple target zones][zone_related_assignments] that the player can take items from. These zones correspond to records in the **zoneToTakeInvFrom** list.

Similarly to [**objectConstruction**][objectconstruction] substage, taking items from a target zone can be tied to some object on the map being "built" and "installed" or, on the contrary, being "dismantled" or hidden. This process can be configured using the [Model Building Settings][model_building_settings] section of this substage. However, it is optional and gathering of items will work without it.


## Setup
After selecting the appropriate settings type, the **takeInventory** section will contain the following settings:

-   **zoneToTakeInvFrom** list – The list of [zone-related assignments][zone_related_assignments] corresponding to zones that the player needs to take items from. At least one record in this list is required. If you add multiple records to this list, the player will need to take items from *all* of these zones, in any order, with the particular items to be taken specified on the per zone basis.

    -   `[0]`, `[1]`, `[2]`, etc. – The record of the particular [zone-related assignment][zone_related_assignments] corresponding to the particular zone that the player needs to take items from.

        -   **OptionalToPerform** – *(Optional)* Enabling this option will mark this substage as optional. By default, this option is disabled and the substage is required. See [Optional Substages][optional_substages] for details.

        -   **uiDesc** – The name of the substage that will be displayed in the UI of the game.

        -   **notification** – *(Optional)* The notification to be displayed after completion of this [zone-related assignment][zone_related_assignments] of the substage. See [Notifications][notifications] for details.

        -   **Fake Zones** – *(Optional)* The list of initially possible, but, after exploration, *unsuitable* zones for the execution of this assignment. See [Fake Zones][fake_zones] for details.

        -   **globalZoneId** – The target zone from which the specified items should be taken.

        -   **inventoryToTake** – The list of all [Inventory Items][inventory_item] that need to be taken from this zone. Should contain at least one record.

            -   `[0]`, `[1]`, `[2]`, etc. – The record of the particular [Inventory Item][inventory_item] that needs to be taken from this zone. For every record the following settings are specified:

                -   **Inventory Type to bring** – The type of [Inventory Item][inventory_item] that needs to be taken from this zone. One of the predefined [types][inventory_item_list_of_types] of inventory items should be selected here. For the full list of these types, see [Appendix: Types of Inventory Items][inventory_item_list_of_types].

                -   **Inventory Id to bring** – *(Optional)* The identifier of the particular [Inventory Item][inventory_item] that needs to be taken from this zone. For example, *Anchor* and *Removable Anchor* have the same **Inventory Type to bring** and can be distinguished only by their [identifiers](./../../../../../custom_gameplay_entities/inventory_items/appendix_types_of_inventory_items.md#identifiers). The identifier of the *custom* inventory item can be also specified here, if you want to use it as a [linked mod][linked_mods].

                    **NOTE**: For the system, the specified identifier (**Inventory Id to bring**) of the item has more priority than its type (**Inventory Type to bring**). However, if identifier is not specified, the necessary item will be selected based on the specified type.

                -   **Amount** – The *amount* of the specified inventory item that needs to be taken from this zone.     

        -   **radiusSett** – *(Optional)* The radius of the [Zone Search Area][zone_search_area] where you want the player to search for the target zone, if you do *not* want to give the player its explicit location. See [Zone Search Area][zone_search_area] for details.

        -   **Model Building Settings** – the settings of the model that will change its visual state (e.g., it will be "built", "installed", "dismantled", or hidden) when the specified items will be taken from the target zone. See [Model Building Settings][model_building_settings] for details.



[stages_and_substages]: ./stages_in_expeditions.md
[zone_related_assignments]: ./stages_in_expeditions.md#multiple-zone-related-assignments-within-substage
[objectconstruction]: ./objectconstruction.md
[inventory_item]: ./../../../../../custom_gameplay_entities/inventory_items/custom_inventory_items_overview.md
[inventory_item_list_of_types]: ./../../../../../custom_gameplay_entities/inventory_items/appendix_types_of_inventory_items.md
[model_building_settings]: ./../../model_building_settings/model_building_settings.md
[notifications]: ./../notifications.md
[optional_substages]: ./../optional_substages.md
[fake_zones]: ./../fake_zones.md
[zone_search_area]: ./../zone_search_area.md
[linked_mods]: ./../../../../../usage_and_uploading_of_mods/linking_mods.md
