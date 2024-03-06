# GameData

Info on the interaction of the engine with the environment.

Attributes:

-   `Price="4200"`  
    Price.

-   `UnlockByExploration="false"`   
    Whether it is unlocked by exploration. I.e., if this option is `true`, the engine will be locked in the Customization screen, until you find it on the map. Please note that locking engines using the `UnlockByExploration` attribute should be used in the case of [linked mods][linked_mods] *only*.  
    Values: `true`, `false`.

-   `AddonUnlockByObjective="false"`  
    Whether or not the engine is granted as a reward for the particular objective that belongs to the particular map. If `true`, the engine will be locked in the UI, until the accomplishment of this objective. Please note that locking engine using the `AddonUnlockByObjective` attribute should be used in the case of [linked mods][linked_mods] *only*.  
    Values: `true`, `false`. 

-   `UnlockByRank="1"`  
    *(Valid for SnowRunner only, used in Expeditions only restrictedly)*  
    *For Expeditions:*  
    **WARNING**: In *Expeditions*, this attribute has only restricted usage. It is still read and processed by the system, but its values other than `1` lock the purchasing of the corresponding engine. I.e., its value must be set to `1` for regular purchasable engines. If its value is different (e.g. `2`), the player will not be able to purchase this engine in the Customize menu.  
    *For SnowRunner:*   
    Unlocking by the rank.

[linked_mods]: ./../../../../../usage_and_uploading_of_mods/linking_mods.md
