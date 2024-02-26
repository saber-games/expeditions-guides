# InstallSocket

The socket on the truck where this addon is installed to.  
See also: [`<Socket>`](./../../../truck/gamedata/addonsockets/socket/index.md) tag of the truck.

Attributes:

-   `Type="Don71FrontBumper"`  
    *(Mandatory.)* The type of the addon that must be exactely the same as one of the types specified in the `Names` attribute of the [`<Socket>`](./../../../truck/gamedata/addonsockets/socket/index.md) tag in the XML class of the truck where this addon is installed to.

-   `Offset="(0; 0; 0)"`  
    The position of the attachment point of the addon in the coordinates of the addon (relative to its origin).

    **NOTE**: The `Offset` attribute of the `<InstallSocket>` tag of the addon works similarly to the `Offset` attribute of the [`<Socket>`](./../../../truck/gamedata/addonsockets/socket/index.md) tag of the truck. However, the `Offset` specified in `<InstallSocket>` will define the shift of this addon on all trucks; the `Offset` specified in the [`<Socket>`](./../../../truck/gamedata/addonsockets/socket/index.md) tag of the particular truck will define the shift of this addon on this particular truck. 
