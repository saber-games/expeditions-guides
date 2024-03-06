# GameData

The `<GameData>` tag inside `<Truck>` contains info on the interaction of the truck with the environment.

Attributes:

-   `Price="35000"`  
    Price of the truck.

-   `UnlockByExploration="false"`  
    Whether it is unlocked by exploration. I.e., if this option is `true`, the truck will be locked in the Store, until you find it on the map. Please note that locking trucks using the `UnlockByExploration` attribute should be used in the case of [linked mods][linked_mods] *only*.  
    Values: `true`, `false`.

-   `ExcludeAddons="semitrailer_stepdeck_5, semitrailer_gooseneck_4"`  
    Multiple addons can have the same type. And the truck interacts with *types* of addons, not with individual add-ons themselves. So, the `ExcludeAddons` parameter allows you to exclude particular addons from the type (the type of addons the truck interacts with).  
    Values: list of names of xml files of addons.

-   `Country="US"`  
    *(Valid for SnowRunner only, not used in Expeditions)*  
    *For SnowRunner:*  
    Region. Values: `US`, `RU`, `CAS` (corresponds to "Central Asia"). You can specify multiple values here, using comma as a delimiter, e.g. `"RU,CAS"`.

-   `Recallable="true"`  
    *For Expeditions:*  
    Whether or not the truck can return back from an Expedition. This attribute is planned to be supported, but currently does not work.  
    *For SnowRunner:*  
    Is not used, but remains as a legacy from MudRunner.

-   `UnlockByRank="1"`  
    *(Valid for SnowRunner only, has been used in Expeditions only restrictedly)*  
    *For Expeditions:*   
    In *Expeditions*, this attribute had only restricted usage. I.e., but its values other than `1` were locking the purchasing of the corresponding truck. I.e., its value had to be set to `1` for regular purchasable trucks. If its value was different (e.g. `2`), the player was not able to purchase this truck in the Truck Store. Now, the `LockedUnconditionally` attribute can be used instead of this.  
    *For SnowRunner:*  
    Unlocking by the rank.

-   `UnlockByObjective="TSK_SK_01_03_SCOUT_IN_RIVER"`  (NEW)  
    In *Expeditions*, this attribute allows you to lock the ability to purchase the truck in Truck Store until the player accomplishes the particular objective. The identifier (*Name*) of the [objective][objective] is specified as the value of this attribute. For details on identifiers (*Name*) of the [objectives][objective], see [Common Fields of Objectives][common_fields_objectives]. Please note that if the game will not be able to find this objective the truck will be locked without any ability to unlock it. Along with setting the correct value of the `UnlockByObjective` attribute, you also need to set up unlocking this truck as the [reward][reward] for the objective (e.g., using `ObjectiveRewardUnlock`). Please note that locking trucks using the `UnlockByObjective` attribute should be used in the case of [linked mods][linked_mods] *only*. 

-   `RecoveryPrice="1000"`  (NEW)  
    In *Expeditions*, this attribute sets the prices of the truck recovery. Please note that the specified value will be applied starting with the *second* recovery and *not* for the first Region (*"Little Colorado"*).

-   `LockedUnconditionally="false"`  (NEW)  
    *(Technical attribute, Should not be used during modding)*  
    In *Expeditions*, setting this attribute to `true` will hide this truck from the Truck Store without any ability to unlock it there. This is an internal technial attribute and it should not be used in modding. 


[objective]: ./../../../../map_modding/creating_a_map/objectives/objectives_overview.md
[common_fields_objectives]: ./../../../../map_modding/creating_a_map/objectives/objectives_in_expeditions/common_fields_of_objectives.md
[reward]: ./../../../../map_modding/creating_a_map/objectives/objectives_in_expeditions/rewards.md
[linked_mods]: ./../../../../usage_and_uploading_of_mods/linking_mods.md