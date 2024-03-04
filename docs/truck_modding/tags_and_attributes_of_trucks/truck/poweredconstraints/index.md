# PoweredConstraints

The `<PoweredConstraints>` section works as a container for all descriptions of powered constraints that exist in the XML class of the addon and, for SnowRunner, the trailer.

*For Expeditions*:  
The `<PoweredConstraints>` section is used only within XML classes of Addons (`<TruckAddon>` as a root tag). This section is *not* used within XML classes of trucks themselves.

*For SnowRunner*:  
The `<PoweredConstraints>` section is used only within XML classes of trailers (`<Truck Type="Trailer">` as a root tag) and within XML classes of addons (`<TruckAddon>` as a root tag). This section is *not* used within XML classes of trucks themselves.

Powered Constraints within this section are described within the following child tags that can be created within the `<PoweredConstraints>` section:

-   [`<Group>`](./group/index.md) tags – every such tag contains a *group* of powered constraints that are activated simultaneously. Every such group is also called a *Powered Group*. 

-   [`<Chain>`](./chain/index.md) tags – every such tag contains a *chain* of Powered Groups. Groups within a chain are activated one after another, in the order of their appearance within the chain.

For details on the creation of Powered Constraints, see [Powered Constraints: Overview](./../../../additional_info_on_trucks/powered_constraints/powered_constraints_overview.md) in the **Additional Info on Trucks**.

