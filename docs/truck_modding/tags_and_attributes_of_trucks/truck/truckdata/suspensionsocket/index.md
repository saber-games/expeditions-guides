# SuspensionSocket

Description of available suspensions.

Tag attributes contain a link to the XML class of the suspension, the name of the default suspension (described in the suspension class), and a parameter to limit the diameter of the wheel for a low suspension. The suspension is used only with wheels "as a set of tires and rims".

-   `Type="s_international_loadstar_1700"`  
    *(Mandatory.)* The name of the XML class of the suspension. In general, there can be multiple types here, separated by commas. However, the suspension is typically very individual and this is not used.

-   `Default="international_loadstar_1700_suspension_default"`  
    *(Mandatory.)* The name of the default suspension from the XML class of the suspension (it is specified in the `Name` attribute of the `<SuspensionSet>` tag there).

-   `MaxWheelRadiusWithoutSuspension="0.3"`  
    *(Mandatory.)* The maximum radius of the wheel without the suspension. It is logical to calculate this value as the difference between the radius of the largest wheel for the lowest suspension and the height of the lowest suspension. (E.g., if we have `Height` = `0.1` for the suspension, then the radius of the wheel that can be set will be `0.3 + 0.1 = 0.4`).

