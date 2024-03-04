# Modding of DLC Trucks

If you want to create a mod of the truck which is available in one of the DLCs, you need to set an appropriate value in the `OriginalTruck` attribute of the [`<Truck>`](./../../tags_and_attributes_of_trucks/truck/index.md) tag.

For example:

```xml
<Truck OriginalTruck="chevy_apache">
      ...
</Truck>
```

As the value of this attribute, you need to specify the identifier of the target DLC truck. 

You can view this identifier in the Editor (when adding this truck) or using the Proving Grounds map from the MOD BROWSER (the id of the truck can be viewed in the **TOOLS \> Create \> SPAWN TRUCK** window).

**WARNING**: To view the identifier of the target truck in the Editor or on Proving Grounds, you need to have the corresponding DLC. If you do not have the DLC, you will not see the target truck there.

After setting this attribute, your truck mod will be available only for players who have purchased the DLC with the target truck. 

However, the mod will still be available for subscription for all players and the player will be able to enable it even if he/she has not purchased the DLC. But, if the DLC has not been purchased, the player will not be able to use the mod of the truck – it will not appear in the Truck Store, even when the corresponding mod is enabled in the MOD BROWSER.

So, if you link your truck to one of the DLC trucks, please warn the players about the fact that your mod will be available only for those who have DLC. You can do it in the description of your mod.

Along with that, there also a policy on using *parts* of DLC trucks in mods, see [Policy on Using Parts of DLC Trucks](./policy_on_using_parts_of_dlc_trucks.md).

