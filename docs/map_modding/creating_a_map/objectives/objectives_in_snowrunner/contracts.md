# Contracts

*This topic is valid for SnowRunner only.*  
*For info of Contracts in Expeditions, see [Expeditions and Contracts](./../objectives_in_expeditions/expeditions_and_contracts.md).*

In *SnowRunner*, most fields of all objectives are [the same](./common_fields_of_objectives.md).

However, along with them, there are fields that are specific to Contracts.

They are the following:

-   **employer** – the employer of the contract. This field is mandatory for a contract.  
    In this field, you can:

    -   Select one of the existing employers from the list, e.g. "*Husky*", "*KolskyRegionalGov*", etc.

    -   Specify a custom employer, which you need to create. See [Custom Employers](./../custom_employers.md) for details.

-   **failReasons** – specified similarly to **failReasons** for Contests, as described in [Contests](./contests.md). However, *not all* **failReasons** that are valid for Contests can be used for Contracts, see **WARNING** below.
    
    **WARNING**: For Contracts, such stages as **truckDelivery**, **repairTruck**, **changeTruck**, **livingAreaInfo**, **spawnCargoOnStageActive** are totally ***prohibited*** for usage when **failReasons** are specified for a Contract. The correct work of **failReasons** for a Contract is guaranteed *only* for Contracts with only the **visitAllZones** stages. All other stages in Contracts with **failReasons** can be used only on your own risk. *Please always carefully test your map mod with such Contracts before uploading it to public*.


