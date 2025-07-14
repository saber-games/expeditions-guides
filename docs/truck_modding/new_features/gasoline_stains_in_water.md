# Disabling the generation of gasoline stains in water

In Season 3, drones received the `NoSpawnOilDecals` parameter that controls gasoline stains generation in water. You can apply this parameter to any wheeled vehicle in the game.

| Stains: on | Stains: off |
|-------------|-------------|
| ![Stains](./media/gasoline_stains_1.png) | ![Stains](./media/gasoline_stains_2.png) |

The `NoSpawnOilDecals` parameter is added to the drone or vehicle's XML file within the `<TruckData>` value block. This is a **boolean** parameter (accepts only *true* or *false* values), and when it is set to **true**, the stains **are not generated**.

![Stains](./media/gasoline_stains_3.png)

The `NoSpawnOilDecals` parameter is *optional* for both drones and vehicles. By default it is set to **false** (the stains are generated).

![Stains](./media/gasoline_stains_4.png)

To change the default value of the parameter, modify it in the `<TruckDefaultVars>` section within the `<TruckData>` value block of the template file `trucks.xml`.
