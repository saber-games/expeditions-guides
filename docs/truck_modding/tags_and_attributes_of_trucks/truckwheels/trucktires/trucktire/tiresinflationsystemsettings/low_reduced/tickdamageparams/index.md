# TickDamageParams
*(NEW) This tag is valid for Expeditions only.*

The `<TickDamageParams>` tag describes the model of the wheel damage used for the corresponding [decreased pressure mode](./../index.md) (its parent tag). This tag is optional.

Attributes:

-   `MinVel = "7.0"`  
    *(Mandatory.)* The minimal threshold of the angular speed after exceeding which the wheels will start to take the `MinDamage` damage from the Tire Inflation System.  
    Value range: `[0; 100]`.

-   `MaxVel = "10.0"`  
    *(Mandatory.)* The maximal threshold of the angular speed after exceeding which the wheels will start to take the `MaxDamage` damage from the Tire Inflation System.     
    Value range: `[0; 100]`.

-   `MinDamage = "2"`  
    *(Mandatory.)* The minimal acceptable damage to the wheel from the Tire Inflation System.  
    Value range: `[0; 100]`.

-   `MaxDamage = "4"`  
    *(Mandatory.)* The maximal acceptable damage to the wheel from the Tire Inflation System.   
    Value range: `[0; 100]`.

-   `DamageTick = "5"`  
    *(Mandatory.)* The time interval of taking damage (and before the start of taking damage) from the Tire Inflation System, in seconds.  
    Value range: `[1; 100]`.

