# objectConstruction

*(NEW) This feature is valid for Expeditions only.*

## Overview
The **objectConstruction** [substage][stages_and_substages] corresponds to an assignment where the player needs to deliver to the particular zone(s) any of the following:

-   An [Inventory Item][inventory_item] of the particular type, in any necessary amount.
-   The particular amount of *Fuel*.
-   The particular amount of *Repair parts*.

**NOTE 1**: This substage may have [multiple target zones][zone_related_assignments] for the delivery of items. These zones correspond to records in the **zoneToFill** list.

**NOTE 2**: You can setup a delivery of *all* objects listed above by filling in the corresponding fields. Or, you can set up the delivery of only the particular objects. For example, if you want the player to deliver only *Fuel*, specify non-zero amount in the **fuelNum** field and leave **repairsNum** as zero and **inventory** as `null`.

This delivery is frequently tied to some object being "built" or "installed" on the map, which is reflected in the name of this substage. This "construction" is configured using the [Model Building Settings][model_building_settings] section of this substage. However, this "construction" is optional and the delivery will work without it.

## Setup

After selecting the appropriate settings type, the **objectConstruction** section will contain the following settings:

-   **notification** section – *(Optional; Currently does not work.)* Settings of the notification displayed to the player upon accomplishing the whole substage. See [Notifications][notifications] for details.

-   **zoneToFill** list – The list of [zone-related assignments][zone_related_assignments]. At least one record in this list is required. If you add multiple records to this list, the player will need to deliver items to *all* of these zones, in any order, with the particular items to be delivered specified on the per zone basis.

    -   `[0]`, `[1]`, `[2]`, etc. – The record of the particular [zone-related assignment][zone_related_assignments].

        -   **OptionalToPerform** – *(Optional)* Enabling this option will mark this substage as optional. By default, this option is disabled and the substage is required. See [Optional Substages][optional_substages] for details.

        -   **uiDesc** – The name of the substage that will be displayed in the UI of the game.

        -   **repairsNum** – *(Optional)* The amount of *Repair parts* that needs to be delivered to the target zone. For example, for repairing some object.

        -   **fuelNum** – *(Optional)* The amount of *Fuel* that needs to be delivered to the target zone. For example, for refueling some machinery.

            **NOTE**: At least one field from **repairsNum**, **fuelNum** and **inventory** (see below) must be filled in to specify the item that needs to be delivered.

        -   **notification** – *(Optional)* The notification to be displayed after completion of this [zone-related assignment][zone_related_assignments] of the substage. See [Notifications][notifications] for details.

        -   **Fake Zones** – *(Optional)* The list of initially possible, but, after exploration, *unsuitable* zones for the execution of this assignment. See [Fake Zones][fake_zones] for details.

        -   **globalZoneId** – The target zone where the specified item(s) (**repairsNum**, **fuelNum**, and/or **inventory**) need to be delivered.

        -   **radiusSett** – *(Optional)* The radius of the [Zone Search Area][zone_search_area] where you want the player to search for the target zone, if you do *not* want to give the player its explicit location. See [Zone Search Area][zone_search_area] for details.

        -   **inventory** – *(Optional)* Settings of the [Inventory Item][inventory_item] that needs to be delivered. If necessary, can be left as `null`, in this case – the player will be delivering only *Repair parts* (**repairsNum**, see above) and/or *Fuel* (**fuelNum**, see above). If **inventory** is filled in, it contains the following settings:

            -   **Inventory Type to bring** – The type of [Inventory Item][inventory_item] to be delivered. One of the predefined [types][inventory_item_list_of_types] of inventory items should be selected here. For the full list of these types, see [Appendix: Types of Inventory Items][inventory_item_list_of_types].

            -   **Inventory Id to bring** – *(Optional)* The identifier of the particular [Inventory Item][inventory_item] that needs to be delivered. For example, *Anchor* and *Removable Anchor* have the same **Inventory Type to bring** and can be distinguished only by their [identifiers](./../../../../../custom_gameplay_entities/inventory_items/appendix_types_of_inventory_items.md#identifiers). The identifier of the *custom* inventory item can be also specified here, if you want to use it as a [linked mod][linked_mods].

                **NOTE**: For the system, the specified identifier (**Inventory Id to bring**) of the item has more priority than its type (**Inventory Type to bring**). However, if identifier is not specified, the necessary item will be selected based on the specified type.

            -   **Amount** – The *amount* of the specified inventory item to be delivered.     

        -   **Model Building Settings (Depened On Cargo)** – the settings of the model that will change its visual state (e.g., it will be "built" or "installed") when the required items will be delivered to the target zone. See [Model Building Settings][model_building_settings] for details.

        -   **additionalUnloadZones** – the list of additional zones where the required items may be delivered (instead of the main target zone). In the original game, this setting was typically used for bridges that can be "built" from two opposite sides and, correspondingly, have two delivery zones.

        -   **modelPlacementZones** – the list of zones that will block the delivering of the items and, if configured, "building" of the model if there is a truck in one of these zones. Sometimes these zones may be necessary to avoid clipping and visual artifacts when you are "building" something.

## Additional Info
If necessary, items may be delivered and, if configured, corresponding objects may be "built" even without the **objectConstruction** substage.

I.e., you are able to configure the separate zone on the map that will not be tied to any objectives, but will wait for some items to be delivered and will be "building" something.

See [Object Construction In Zone zones][object_construction_in_zone_zones] for details.


[stages_and_substages]: ./stages_in_expeditions.md
[zone_related_assignments]: ./stages_in_expeditions.md#multiple-zone-related-assignments-within-substage
[inventory_item]: ./../../../../../custom_gameplay_entities/inventory_items/custom_inventory_items_overview.md
[inventory_item_list_of_types]: ./../../../../../custom_gameplay_entities/inventory_items/appendix_types_of_inventory_items.md
[model_building_settings]: ./../../model_building_settings/model_building_settings.md
[notifications]: ./../notifications.md
[optional_substages]: ./../optional_substages.md
[fake_zones]: ./../fake_zones.md
[zone_search_area]: ./../zone_search_area.md
[object_construction_in_zone_zones]: ./../../../zones/expeditions_zones/object_construction_in_zone_zones.md
[linked_mods]: ./../../../../../usage_and_uploading_of_mods/linking_mods.md