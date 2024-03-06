# Custom Prices for Trucks and Upgrades

*This topic is valid for SnowRunner only.*  
*In Expeditions, these options are not used. They will be removed in the next versions of Expeditions Editor.*  

The **Custom Prices** section allows you to specify custom prices for trucks and upgrades. Specified prices will override default prices for these items.

Similarly to the [**Lock/Unlock Content**](./locking_and_unlocking_trucks_and_upgrades.md) section, you need to specify the IDs of necessary trucks and upgrades in this list. These IDs should be specified manually, as text.

For upgrades, these IDs can be identified using the game itself or located in XML files – see [How to Identify IDs of Truck Parts](./../../trucks/how_to_identify_ids_of_truck_parts.md) for details.

For trucks, you need to specify the ID of the *type* of the truck, which is displayed in the Editor, in the properties of the truck (e.g. `chevrolet_kodiakc70`).

**WARNING**: When you set a custom price for a truck in the Editor, you change the *base price* of the truck. However, the *total price* for the truck – displayed in the Truck Store – may be higher than its *base price*, since its also includes the sum of prices of all its default addons.

If you want to see the approximate price of all default addons of the truck in the Truck Store, set `1` as the custom price of the truck. 

**NOTE**: `0` as the custom price of the truck here is the special value. if you set it as the custom price of the truck, the truck will be available free of charge, *regardless of the price of the default addons*.

However, if you want to lower the *total price* of the truck below its minimum price, you can do so by decreasing *both* its base price and *prices of its default addons*. 

I.e., in this case, you will need to specify decreased prices for all (or some of) its default addons in the **Custom Prices** section. 

The ids of the default addons can be identified using the game itself or located in XML files – see [How to Identify IDs of Truck Parts](./../../trucks/how_to_identify_ids_of_truck_parts.md) for details. Please note that some addons can be used by multiple trucks.
