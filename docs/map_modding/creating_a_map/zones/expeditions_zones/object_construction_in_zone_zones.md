# Object Construction In Zone zones

*(NEW) This feature is valid for Expeditions only.*


## Main Function: Construction of the Object in a Zone
The *ZonePropertyObjectConstructionInZone* zones allow the player to "build" objects near a particular zone by delivering necessary inventory items and consumables to this zone.

**NOTE**: Unlike similar "building" performed in the **objectConstruction** stages, the "building" in a *ZonePropertyObjectConstructionInZone* zone does not require any setup of the objectives. I.e., the player finds the *ZonePropertyObjectConstructionInZone* zone on a map, delivers the resources to it, and the corresponding object appears on the map – without any assignment on that given to the player.


## "Building" of an Object
The "building" of an object is performed with [Model Building Settings][model_building_settings] and is based on the process of substituting one model's state on the map with another one, with the corresponding animation, if the model has it. 

I.e., it can be used not only for "building", but for any other scenarios that have the corresponding **\_objective** model with multiple states. For example, you can use it not only for building bridges, but for placing a *Camera Trap* on a tree, or installing a *Radio station*, etc. See [Model Building Settings][model_building_settings] for details.

**NOTE**: The Model Building Settings that are set up in the **model** section of the *ZonePropertyObjectConstructionInZone* prop are activated when the last required item is delivered to the zone. 


## ZonePropertyObjectConstructionInZone Prop Settings
Settings of the *ZonePropertyObjectConstructionInZone* prop are the following:

-   **uiDesc** – *(does not work, is not used, and will be removed).*

-   **zoneDiscoverability** – settings related to the zone discovery. See [Discoverability of Zones](./discoverability_of_zones.md). 

-   **model** – *(Optional)* the model that will change its visual state when the **requiredItems** (see below) will be delivered to this zone. See [Model Building Settings][model_building_settings] for details.

-   **modelPlacementZones** – *(Optional)* the list of zones that will block the delivering of the items and "building" of the **model** if there is a truck in one of these zones. Sometimes these zones may be necessary to avoid clipping and visual artifacts when you are "building" something.

-   **requiredltems** – the list of consumables and inventory items required for a **model** to be "built".
    -   **repairsNum** – the number of required *Repair parts*.
    -   **fuelNum** – the amount of required *Fuel*.
    -   **inventory** – the list of records corresponding to required inventory items with their amounts: (`TBD`)

        -   `[0]`, `[1]`, `[2]`, etc. – The record of the particular required inventory item. Has the following properties:
       
            -   **itemName** – *(Optional; Currently not implemented field)* The identifier of the particular required [Inventory Item][inventory_items_overview].
    
            -   **Type** – *(Currently not implemented field)* The type of required [Inventory Item][inventory_items_overview_type]. One of the predefined [types][appendix_types] of inventory items should be selected here. For the full list of these types, see [Appendix: Types of Inventory Items][appendix_types].

                **NOTE**: For the system, the specified **itemName** (see above) of the item has more priority than **Type**. However, if **itemName** is not specified, the necessary item will be required based on **Type**.

            -   **Required num** – *(Currently not implemented field)* The reqired amount of the specified inventory item.

-   **additionalConstructionZones** – *(Optional)* the list of the additional construction zones that allow the player to deliver the same resources and "build" the same **model**. For example, to allow the player to build the bridge over the river using either the zone located on one bank or the zone on another bank. (`TBD`)


[model_building_settings]: ./../../objectives/model_building_settings/model_building_settings.md

[inventory_items_overview]: ./../../../../custom_gameplay_entities/inventory_items/custom_inventory_items_overview.md

[inventory_items_overview_type]: ./../../../../custom_gameplay_entities/inventory_items/custom_inventory_items_overview.md#type

[appendix_types]: ./../../../../custom_gameplay_entities/inventory_items/appendix_types_of_inventory_items.md