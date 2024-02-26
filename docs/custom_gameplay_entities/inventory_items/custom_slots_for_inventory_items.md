# Custom Slots for Inventory Items

Inventory Items are stored and transported in the *slots* within the truck. 

If necessary, you can create the necessary amount of custom slots for inventory items. They will be valid for both your custom items and the original ones. 

However, the type of the slot that is valid for the particular item depepends on the "heaviness" of the inventory item:

| "Heaviness"            | **isHeavyItem** option | Type of Slot                       | 
|------------------------|------------------------|------------------------------------|
| Regular Inventory Item | `false`                | [Inventory Slots][inventory_slots] |
| Heavy Inventory Item   | `true`                 | [Cargo Slots][cargo_slots]         |

Please note that the required setup of the slot itself is different for [Inventory Slots][inventory_slots] and for [Cargo Slots][cargo_slots]. 

[inventory_slots]: ./../../truck_modding/new_features/inventory_slots.md
[cargo_slots]: ./../../truck_modding/new_features/cargo_slots.md