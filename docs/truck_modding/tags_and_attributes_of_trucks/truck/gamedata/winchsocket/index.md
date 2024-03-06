# WinchSocket

Winch mounting location.

**NOTE**: When configuring this tag in an addon, you need to take into account that the winch can exist for it only if this addon contains at least one physical bone. Usage of this tag for the addon when it contains no physical bones can result in a crash.

Attributes:

-   `Pos="(3.881; 0.834; -0.322)"`    
    Position of the winch mounting location.


-   `ParentFrame=\"BoneCabin_cdt"`  
    A bone from the hierarchy of the physical model, which the winch is attached to. If the parameter is not specified, then this is a root bone.
