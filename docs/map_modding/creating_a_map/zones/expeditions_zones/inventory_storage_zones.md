# Inventory Storage zones

*This feature is valid for Expeditions only.*

## Main Function: Storage of Inventory
The *ZonePropertyInventoryStorage* zones work as a storage for various [inventory items](./../../../../custom_gameplay_entities/inventory_items/custom_inventory_items_overview.md), fuel, repair parts, and spare wheels on the map. All these items can be spawned within these zones.

**NOTE**: If necessary, you can specify the *probability* of spawning for items in this zone.

Along with spawning items within them, they allow the player to transfer these items to the truck and, if necessary, perform the reverse transfer of some of these items.

**NOTE**: *ZonePropertyInventoryStorage* zones with the *disabled* **alwaysSpawn** option are spawned *randomly*, see [Inventory Settings][inventory_settings] for details.

## Usage
These zones are used in all locations where storage and trading of inventory items is necessary: in air drops, some FOB modules, storages for various quest items. However, during configuration of zones for FOB modules, the *ZonePropertyInventoryStorage* prop is used not in its pure form, but via props that act as wrappers for it. These wrapper-props are named differently and contain some additional fields:

-   [*ZonePropertyFobModuleStorage*](./zones_of_fob_modules/fob_module_storage_zones.md)
-   [*ZonePropertyDroneDelivery*](./zones_of_fob_modules/drone_delivery_zones.md)
-   [*ZonePropertyParking*](./zones_of_fob_modules/parking_zones.md)

**NOTE**: However, during the confugiration of the *Base module* of the FOB within the [Deploy zone](./deploy_zones.md), the *ZonePropertyInventoryStorage* prop is used without wrappers. See [Deploy zones](./deploy_zones.md#base-module-and-store) for details.


## ZonePropertyInventoryStorage Prop Settings
Settings of the *ZonePropertyInventoryStorage* prop themself (without wrappers) are the following:

-   **capacity** – the maximum amount of slots for *regular (not heavy)* inventory items in this zone. If **capacity** is greater than the actual amount of slots with *regular* inventory items (the number of records with *regular* inventory items in the **slotsSettings** list), the remaining slots will remain empty, allowing the player to use them to transfer items from the truck.

    **NOTE**: When adding an inventory zone, make sure to change the default capacity, which is set to `0`. If the capacity is set to `0`, the inventory will not be displayed in the zone even if the items are properly configured.

-   **heavylnvCapacity** – the maximum amount of slots for *heavy* inventory items in this zone. If **heavylnvCapacity** is greater than the actual amount of slots with *heavy* inventory items (the number of records with *heavy* inventory items in the **slotsSettings** list), the remaining slots will remain empty, allowing the player to use them to transfer items from the truck.

-   **alwaysSpawn** – this option specifies whether or not this zone itself should be spawned during *every* Expedition to this map. If **alwaysSpawn** is enabled, this zone will be spawned always. If it is disabled, the zone will participate in the random selection of zones for spawning: the system will randomly select a certain amount of zones – set by the **maxInventoryZones** parameter in the [**inventorySettings**][inventory_settings] of the map – from all *ZonePropertyInventoryStorage* zones with disabled **alwaysSpawn** flag on this map, and spawn only these zones. Please note that if the zone itself is spawned, the items within zone will be spawned with *the specified probabilities*, see **slotsSettings** below. See [Inventory Settings][inventory_settings] for details.

-   **expandedConsumablesCapacity** – this parameter sets the multiplier that defines the *upper limits* for consumable slots those *current* values are set up in **fuelSIotSettings**, **repairsSlotSettings**, and **wheelsSlotSettings**. These upper limits are calculated using the following formulas:
    ```text
    Fuel Limit = (expandedConsumablesCapacity - 1) * amount_in_predefined_Fuel_item + fuelSlotSettings.quantity

    Repair Parts Limit = (expandedConsumablesCapacity - 1) * amount_in_predefined_RepairParts_item + repairsSlotSettings.quantity

    Wheels Limit = (expandedConsumablesCapacity - 1) * amount_in_predefined_Wheels_item + wheelsSlotSettings.quantity
    ``` 
    Where amounts of consumables in predefined inventory items are the following: fuel – `50`, repairs – `100`, wheels – `1`.

    **NOTE**: Currently, this field does not work as described above. (`TBD`)

-   **isAffectedByAdditionalOutpostResourcesAbility** – whether or not the amounts of Consumables in this zone are affected by the **additionalRepairs**, **additionalWheels**, and **additionalFuel** passive abilities of the Specialist. Typically, should be enabled for FOB Modules.

-   **isAffectedByAdditionalAirdropResourcesAbility** – whether or not the amounts of Consumables in this zone are affected by the **additionalAirdropRepairs**, **additionalAirdropWheels**, and **additionalAirdropFuel** passive abilities of the Specialist. Typically, should be enabled for air drops.

-   **isAtDeployZone** – whether or not this *ZonePropertyInventoryStorage* props is used for the configuration of the *Base module* of the FOB. Particularly, this option should be enabled if this *ZonePropertyInventoryStorage* props is added to the properties of the Deploy zone, along with the [*ZonePropertyDeploy*](./deploy_zones.md) prop itself. This option affects the saving of the inventory items and heavy inventory items within this zone – i.e., if **isAtDeployZone** is enabled, the items that the player has transfered to this zone will be saved at the end of the expedition and the same items will appear again at the beginning of the next expedition to the same map. If **isAtDeployZone** is disabled, the items within this zone will be reset in the next expedition. And, also, enabling this option tells the system to display the correct header for the Trade screen of *Base module*, in the UI of the game. This option should be enabled for configuration of *Base module* and disabled in all other cases. See [Deploy zones](./deploy_zones.md) for details.

-   **zoneDiscoverability** – settings related to the zone discovery. See [Discoverability of Zones](./discoverability_of_zones.md). 

-   **model** – *(Optional)* the model that will change its visual state depending on whether or not this zone is spawned. For example, you can set up the zone in the following way: if this zone is spawned, the **\_objective** model set up in Model Building Settings will be in its "stage_visible" state too and will display some visuals for zone resources. On the contrary, if this zone is not spawned, this model will be in its "stage_hidden" state and will not be visible (as the zone itself). See [Model Building Settings](./../../objectives/model_building_settings/model_building_settings.md) for details.

-   **slotsSettings**: – the list of slots where regular inventory items and heavy inventory items may appear with ceratin probabibilty. Every record in this list corresponds to a separate slot. For every slot the list of items that can be possibly spawned in this slot and their probabilities are configured.
    -   *[every slot]*:
        -   **possibleItems**: – the list of items that can be possibly spawned in this slot.
            -   *[every possible item]*:
                -   **type** – the type of the possible item to be spawned. See [Custom Inventory Items: Overview](./../../../../custom_gameplay_entities/inventory_items/custom_inventory_items_overview.md#type) and [Appendix: Types of Inventory Items](./../../../../custom_gameplay_entities/inventory_items/appendix_types_of_inventory_items.md).
                -   **chance** – the probability of spawning of this inventory item. Possible values: from `0` to `1`. For example, `0.75` corresponds to `75%` probability of spawning.
                **NOTE**: By default, the chance of spawning an item is set to `0`.
                -   **itemName** – *(Optional)* the identifier of the inventory item. For example, *Anchor* and *Removable Anchor* have the same **type** and can be distinguished only by their [identifiers](./../../../../custom_gameplay_entities/inventory_items/appendix_types_of_inventory_items.md#identifiers). The identifier of the *custom* inventory item can be also specified here, if you want to use it as a [linked mod][linked_mods]. If this identifier is not specified, the game will use any item with the specified **type** instead.

                **NOTE 1**: If the total number of slots with regular/heavy items in **slotsSettings** will be greater than corresponding values of **capacity** and **heavylnvCapacity**, then the list of slots will be automatically cut to match these values.

                **NOTE 2**: At least one slot in **slotsSettings** should have the sum of probabilities of possible items equal to `1`. Otherwise, there is a chance that the zone will be spawned without any items at all.

-   **fuelSlotSettings** – settings of the *Fuel* resource of the zone:
    -   **quantity** – the amount of Fuel that may be spawned.
    -   **chance** – the probability of spawning for this Fuel.
    -   **tradeFromTruckToZone** – whether or not the reverse transfer of Fuel is possible – i.e., whether the Fuel can be transfered from the truck to the zone.

-   **repairsSlotSettings** – same as **fuelSlotSettings**, but for *Repair parts*.

-   **wheelsSlotSettings** – same as **fuelSlotSettings**, but for *Spare wheels*.


[inventory_settings]: ./../../objectives/objectives_in_expeditions/inventory_settings.md
[linked_mods]: ./../../../../usage_and_uploading_of_mods/linking_mods.md
