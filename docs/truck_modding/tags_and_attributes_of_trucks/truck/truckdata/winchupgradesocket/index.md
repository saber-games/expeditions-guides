# WinchUpgradeSocket

Description of available winches.

Tag attributes contain a link to the XML class of the winch and the name of the default winch (described in this winch class).

Attributes:

-   `Type="winches_scouts"`  
    *(Mandatory.)* The name of the XML class of the winch. You can specify multiple types, separating them by commas: `"winches_scouts, winches_medium_trucks.xml"`.

-   `Default="w_scout_default"`  
    *(Mandatory.)* Name of the default winch, from the XML class of the winch (it is specified in the `Name` attribute of the `<Winch>` tag there).

-   `IsUpgradable="true"`  
    Internal attribute that is used for debugging – whether or not the winch may be upgraded from the Debug Garage menu. May be removed soon.