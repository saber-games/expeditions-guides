# General Properties of Inventory Items

## Main Properties 
As we stated in [Creation of Custom Inventory Item][creation_of_custom_inventory_item], you always begin with specifying the following main properties:

-   **name** – the *identifier* of the custom inventory item. The specified value should contain only Latin characters, digits, and underscores (`_`). It must not contain spaces (` `).

-   **InventoryItemDesc** – The *class* of the the custom inventory item. See [Creation of Custom Inventory Item][class] for details.


## General Properties
After selecting the class of the custom [Inventory Item][inventory_items_overview] in **InventoryltemDesc**, you can specify its general properties.

These general properties are the same for all available classes:

-   **type** – the category of the item. See [Custom Inventory Items: Overview](./custom_inventory_items_overview.md#type) for details.

-   **defaultUseCount** – the number of "charges" of this inventory item. These charges are spent at the moment of its usage. The `-1` value means that the number of charges is infinite. [Quest Items][quest_items] and [Treasure Items][treasure_items] typically have the value of `1` in this field, which means that there is `1` piece of this item.

-   **cost** - the purchase cost of this inventory item when preparing for the Expedition. Should be an integer value.

-   **recycleRepairsCost** – the Recycle Price of this inventory item, in *Repair parts*. Any positive values in this field mean that item can be recycled to the specified number of *Repair parts* in the **Workshop** FOB module. The special `-1` value means that this item can not be recycled.

-   **craftRepairsCost** – the Craft Price of this inventory item, in repair parts. Any positive values in this field mean that item can be crafted from the specified number of *Repair parts* and will be available in the **Workshop** FOB module. The special `-1` value means that this item can not be crafted. See also: **craftUseCount** below.

-   **craftUseCount** – the number of "charges" of this inventory item that will be available in the resulting item when it will be crafted. See also: **craftRepairsCost** above.

-   **isUsable** – this flag specifies whether or not this item can be used by the player in the game by pressing a corresponding button. For example, the player can "use" an item to execute its ability (e.g., Drone). Typically, quest items that just remain in the inventory have this parameter set to `false`, since they can not be used. And, items with ability have this parameter set to `true`, since they can be used. However, theoretically, there can be abilities that are used without execution of the "Use" command by the player, so these are just *typical* values.

-   **isHeavyItem** – this flag specifies whether or not this item is a "Heavy". Heavy Inventory Items can placed only in the truck's Sideboard. See [Custom Inventory Items: Overview](./custom_inventory_items_overview.md#heavy-inventory-items) for details.

-   **isTreasure** – this flag specifies whether or not this item is a "Treasure Item". Treasure Items can be sold at the end of the Expedition. See [Custom Inventory Items: Overview](./custom_inventory_items_overview.md#treasure-items) for details.

-   **canTakeInHq** – this flag specifies whether or not this item is purchasable in the **HEADQUARTERS**, when preparing for the Expedition. Please note that, currently, there is a limit on the *simultaneously* enabled mods of Inventory Items that are available in Headquarters, see [Custom Inventory Items: Overview](./custom_inventory_items_overview.md#limit-on-number-of-enabled-cantakeinhq-mods) for details.

-   **notForSale** – TBD

-   **Requested Ability type** – the type of the ability that is used by this item. The set of abilities is fixed and the value in this field can be one of following:
    -   `NONE` – items with no ability, quest items.
    -   `BINOCULAR` – items with the [Binoculars](./ability_specific_properties_of_inventory_items.md#binocular) ability.
    -   `ANCHOR` – items with the [Anchor](./ability_specific_properties_of_inventory_items.md#anchor) ability.
    -   `JACKSCREW` – items with the [Jack-Screw](./ability_specific_properties_of_inventory_items.md#jackscrew-jack-screw) ability.
    -   `ECHOLOT` – items with the [Echo Sounder](./ability_specific_properties_of_inventory_items.md#echolot-echo-sounder) ability.
    -   `TOOLKIT` – *(obsolete test ability, should not be used, will be removed)*
    -   `PORTABLE_METEOSTATION` – *(obsolete test ability, should not be used, will be removed)*
    -   `FUEL_CANISTER` – *(obsolete test ability, should not be used, will be removed)*
    -   `INSPECTION` – *(obsolete test ability, should not be used, will be removed)*
    -   `DRONE`– items with the [Drone](./ability_specific_properties_of_inventory_items.md#drone) ability.

    **<mark>IMPORTANT</mark>**: Currently, along with the selection of the correct **type** and **Requested Ability type**, you need also to create instance of the correct *class* when creating an Item with Ability. See [Creation of Custom Inventory Item](./creation_of_custom_inventory_item.md) for details. 

-   **Icon 20** – the identifier of the icon used in the UI, for requirements in HQ. The icon's dimensions are `20х20`, its format is PNG. Currently, custom icons are not supported in this field. However, you can use the name of an original in-game icon in this field. See [Appendix: Icons of Inventory Items and Consumables][appendix_icons_of_inv_items_n_cons] for details.

-   **Icon 30** – the identifier of the icon used in the UI, for Summary and Specialist screens. The icon's dimensions are `30х30`, its format is PNG. Currently, custom icons are not supported in this field. However, you can use the name of an original in-game icon in this field. See [Appendix: Icons of Inventory Items and Consumables][appendix_icons_of_inv_items_n_cons] for details.

-   **Icon 40** – the identifier of the icon used in the UI, on the map. The icon's dimensions are `40х40`, its format is PNG. Currently, custom icons are not supported in this field. However, you can use the name of an original in-game icon in this field. See [Appendix: Icons of Inventory Items and Consumables][appendix_icons_of_inv_items_n_cons] for details.

-   **Icon 60** – the identifier of the icon used in the UI, in the Inventory. The icon's dimensions are `60х60`, its format is PNG. Currently, custom icons are not supported in this field. However, you can use the name of an original in-game icon in this field. See [Appendix: Icons of Inventory Items and Consumables][appendix_icons_of_inv_items_n_cons] for details.

-   **uiName** – the localization string of the item's *name* that will be used in the UI. The length of the localization string is limited to 20 characters, including spaces.

-   **uiDesc** – the localization string of the item's *description* that will be used in the UI. The length of the localization string is limited to 80 characters.

-   ***Icon Desc*** – *(Not customizable during modding)*.

[inventory_items_overview]: ./custom_inventory_items_overview.md
[creation_of_custom_inventory_item]: ./creation_of_custom_inventory_item.md
[class]: ./creation_of_custom_inventory_item.md#classes-of-inventory-items
[quest_items]: ./custom_inventory_items_overview.md#quest-items
[treasure_items]: ./custom_inventory_items_overview.md#treasure-items
[appendix_icons_of_inv_items_n_cons]: ./appendix_icons_of_inventory_items_and_consumables.md