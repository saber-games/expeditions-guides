# "Regional" Contracts

*Currently, this topic is valid for SnowRunner only.*  
*In Expeditions, custom Regions with multiple interconnected maps are currently not supported. However, they are planned to be supported in the next versions of the game.*  

For main info on objectives - see [Objectives: Overview](./../objectives/objectives_overview.md). This section describes only the specifics of the regional Contracts.

The main differences of regional objectives from objectives on the level of the individual map are the following:

1.  You can create **only Contracts** as regional objectives. You can ***not*** create **Tasks or Contests** on the level of the region.

2.  When you are creating regional **Contracts**, you can use zones from all maps of the region.

Regional Contracts are created in the **Region** tab of the Region Settings Plugin dialog. To add an objective, you need to expand the corresponding sections there and then create a Contract in a standard way (see [[5.16. Adding Objectives]](#adding-objectives) for details).\
\
However, to be able to use a zone for a regional objective, you need to create a *zone locator* for it on the corresponding map (in the Editor) and, also, add this zone to the **TERRAIN LOCATORS LIST** with empty **props** section (in the Zone Settings plugin opened for this map, as we have done with Gateway zones in [[5.17. Regions with Multiple Maps]](#regions-with-multiple-maps), in step ***1.e.***).

**NOTE**: Similarly to regular objectives, properties of regional objectives are partially validated during packing and when the game tries to open a region.\
The log of occurring errors can be found in

**Documents\\My Games\\SnowRunner\\base\\logs\\ModMapError.txt**

e.g. **C:\\Users\\\<username\>\\Documents\\My Games\\SnowRunner\\base\\logs\\ModMapError.txt**

For example, we can create a Contract that requires the delivery of wooden planks to 2 different zones on 2 different maps:\
\
![](./media/image357.png)

Other **important notes on regional Contracts**:

-   Please, ensure that all your **Contracts in the region have unique names!\
    **

-   The additional **Map name for player profile** field allows you to specify the map this Contract will be associated with. The value of this field will be used for calculating statistics (the progress by region).

-   To achieve safe respawning of trucks and cargo, there is a limitation on contracts with **changeTruck**, **truckDelivery**, **repairTruck** and **spawnCargo\...** stages:

All vehicles and zones of spawning cargo set up in these Contracts must be *located on one map*, i.e. all objects that are spawned must be located on the map the Contract is linked to). E.g., you cannot create a Contract with two truck deliveries, where one vehicle is spawned on one map and the other vehicle is spawned on another map.

-   There is a limitation on the **Visiting All Zones** and **Seismograph Usage** stages of the regional Contracts:\
    Within one such stage, you can use zones ***from a single map only***.\
    However, you can use zones from one map in one stage, and zones from the other map in another stage, if necessary.

