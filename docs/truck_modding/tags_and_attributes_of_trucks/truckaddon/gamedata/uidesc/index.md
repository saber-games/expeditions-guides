# UiDesc

UI block describing the addon.  
See also: [`<UiDesc>`](./../../../truck/gamedata/uidesc/index.md) for trucks.

Attributes:

-   `UiDesc="UI_MODULE_FRAME_RADAR_DESC"`  
    The short description of this addon that will be displayed in the UI of the game.  

-   `UiIcon30x30="toolHeadLamp30"`  
    The small icon of the addon for the UI. Most of addons have no icons that are displayed in the UI, however, if you create a [Consumable](./../../../../new_features/consumables.md), this icon will be used for the selection of this consumable in the UI.

-   `UiIcon40x40=""`  
    Not used for addons. See `UiIcon40x40` in [`<UiDesc>`](./../../../truck/gamedata/uidesc/index.md) for trucks.

-	`UiIcon60x60="toolHeadLamp60"`  
    The large icon of the addon for the UI. Most of addons have no icons that are displayed in the UI, however, if you create a [Consumable](./../../../../new_features/consumables.md), this icon will be used for the selection of this consumable in the UI.

-   `UiName="UI_MODULE_FRAME_RADAR_NAME"`  
    The name of this addon that will be displayed in the UI of the game.  
    For [Consumables](./../../../../new_features/consumables.md), this text is displayed to the player while selecting a corresponding consumable item within a Resource slot. However, names of predefined consumables (Fuel, Repair parts, Spare wheels) are fixed and cannot be changed by this attribute.

