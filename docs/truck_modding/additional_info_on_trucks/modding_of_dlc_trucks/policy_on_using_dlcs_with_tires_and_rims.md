# Policy on Using DLCs with Tires and Rims

Along with other content, *SnowRunner* and *Expeditions* may have special DLCs that provide Tires and Rims.

For example, for *SnowRunner*, there is a special *"Jack of All Treads Tire Pack"* DLC that provides a lot of variants of tires and rims.

Tires and rims from these paid DLCs are allowed for usage in mods. 

From the point of view of XML files, the technique of their usage is similar to the usage of other tires and rims – they can be referenced in the [`<CompatibleWheels>`][compatiblewheels] and [`<Wheels>`][wheels] tags of the XML class of the truck.

However, there is one important rule of usage: the original identifiers of tires and rims from this DLC must be referenced and used as is if the DLC content is used.

Particularly, if you use content from these DLC for your mod, you must reference the original values of the `Name` attributes of the [`<TruckTire>`][trucktire] and [`<TruckRim>`][truckrim] tags. E.g., for the *"Jack of All Treads Tire Pack"* DLC, `JAT OMS I`, `JAT OMS II`, and so on.

Usage of content from this DLC without linking to original tires and rims from DLC in the way described above is prohibited and mods that violate this rule will be blocked.

[compatiblewheels]: ./../../tags_and_attributes_of_trucks/truck/truckdata/compatiblewheels/index.md
[wheels]: ./../../tags_and_attributes_of_trucks/truck/truckdata/wheels/index.md
[trucktire]: ./../../tags_and_attributes_of_trucks/truckwheels/trucktires/trucktire/index.md
[truckrim]: ./../../tags_and_attributes_of_trucks/truckwheels/truckrims/truckrim/index.md