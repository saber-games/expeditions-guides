# GameData

The `<GameData>` tag inside `<TruckAddon>` contains info on the interaction of the addon with the environment.

It has additional attributes and child-tags relative to [`<GameData>`](./../../truck/gamedata/index.md) inside `<Truck>`.

Attributes:

-   `Price="2000"`  
    The price of the addon.

-   `UnlockByExploration="false"`  
    Whether it is unlocked by exploration. I.e., if this option is `true`, the addon will be locked in the UI, until you find it on the map. Please note that locking addons using the `UnlockByExploration` attribute should be used in the case of [linked mods][linked_mods] *only*.  
    Values: `true`, `false`.

-   `AddonUnlockByObjective="true"`  (NEW)  
    Whether or not the addon is granted as a reward for the particular objective that belongs to the particular map. If `true`, the addon will be locked in the UI, until the accomplishment of this objective. Please note that locking addons using the `AddonUnlockByObjective` attribute should be used in the case of [linked mods][linked_mods] *only*.   
    Values: `true`, `false`.  

-   `CameraPreset="roof"`  
    The camera preset during installation of this addon. For [Consumables](./../../../new_features/consumables.md), this preset is typically the same as `CameraPreset` specified for the *parent addon of the consumable*.  
    Values: `default`, `roof`, `rear`, `addon_1`, `side_l`, `side_r`, `hoods`, `wheels`, `roofrack2`.

-   `Category="top"`  
    The category of the addon that defines the customization category in the UI of the Garage. For [Consumables](./../../../new_features/consumables.md), the location (category) of the corresponding Resource Slot is determined automatically, based on category of the addon that is required for this consumable. However, for them, this value should be the same as the value of the same `Category` attribute of the *parent addon of the consumable*.  
    Possible values of the `Category` attribute can be looked up in `.../classes/addons_category/addons_category.xml`.  
    For example: `top`, `bumper`, `engine`, `gearbox`, `fender_front`, `frame_addons`, etc.       

-   `Subcategory="module"`  (NEW)  
    The subcategory of addon for the UI. Particulary, the `module` value of this attribute should be used for frame modules that are isntalled to frame addons (e.g. to a flatbed). 

-   `Priority="1"`  (NEW)  
    Priority of the frame module that defines the order of modules on the frame addon when multiple modules are installed. The less is the value of `Priority`, the closer the corresponding addon is installed to the cabin. 

-   `IsCustomizable="false"`  (NEW)  
    Whether or not this addon should be painted along with the truck itself. If `true` the addon will be painted with the truck when Color Customization is set up for it. For details, see [Color Customization](./../../../additional_info_on_trucks/color_customization/color_customization.md). If `false` the addon will have a separate colors. For [Consumables](./../../../new_features/consumables.md), this attribute is typically set to `false`, since they are not painted along with the truck, as a rule. However, if necessary, this can be set up using the same scheme as for regular addons.  
    Values: `true`, `false`.  
 
-   `IsConsumable="true"`  (NEW)  
    Whether or not this addon is a Consumable item and should be installed to a Resource Slot.  If `IsConsumable="true"`, this addon will be installed to a Resource Slot. The value of the `IsConsumable` must be `false` for regular addons. See [Addon Changes](./../../../new_features/addon_changes.md) and [Consumables](./../../../new_features/consumables.md) for details.  
    Values: `true`, `false`.

-   `UnlockByRank="5"`  
    *(Valid for SnowRunner only, used in Expeditions only restrictedly)*  
    *For Expeditions:*   
    **WARNING**: In Expeditions, this attribute has only restricted usage. It is still read and processed by the system, but its values other than `1` lock the purchasing of the corresponding addon. I.e., its value must be set to `1` for regular purchasable addons. If its value is different (e.g. `2`), the player will not be able to purchase this addon in the Customize menu.  
    *For SnowRunner:*  
    Unlocking by the rank.    

-   `SoundByGroups="true"`  
    This attribute specifies whether or not the addon should play the sounds of powered constaints that are set up by the `<SoundBrand>` child-tags of the `<Group>` tags within `<PoweredConstraints>`. If `true` these sounds will be played during usage of the corresponding groups of constaints. If `false`, these sounds will be ignored and the usage of the addon's powered constraints will be silent.


[linked_mods]: ./../../../../usage_and_uploading_of_mods/linking_mods.md