# Inventory Slots
*(NEW) This feature is valid for Expeditions only.*

*Inventory Slots* are available only when prepairing for the particular Expedition and allow the player to buy [inventory items](./../../custom_gameplay_entities/inventory_items/custom_inventory_items_overview.md), such as anchors, jackscrews, and so on. 

**NOTE**: These slots should not be mixed up with [Cargo Slots](./cargo_slots.md) and with [Slots for Consumables](./consumables.md). Inventory Slots have different game mechanics and are a separate game entity.

In the XML class of the truck, you can specify the number of these slots, within the `<Inventory>` tag of `<TruckData>`:

```xml
<Truck>
    ...
	<TruckData ...>
		<Inventory MaxLimit="5" />
        ...
	</TruckData>
    ...
</Truck>
```

**NOTE**: Due to current UI limitations, the maximum amount of Inventory Slots (specified in `MaxLimit`) is `8` now.

[Inventory items](./../../custom_gameplay_entities/inventory_items/custom_inventory_items_overview.md) to be placed in these slots are selected by the player.