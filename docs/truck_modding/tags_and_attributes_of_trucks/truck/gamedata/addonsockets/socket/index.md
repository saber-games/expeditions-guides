# Socket

Attachment point for the addon on the truck.  
See also: [`<InstallSocket>`](./../../../../truckaddon/gamedata/installsocket/index.md) tag of the addon.

**NOTE**: This tag may also contain [`<ExtraParent>`](./extraparent/index.md) and [`<AddonsShift>`](./addonsshift/index.md) child tags for explicit attachment of the addon bones (if attachment of one bone is not enough) and shift of the installation point of the addon when another addon is already installed.

Attributes:

-   `Names="Don71FrontBumper"`  
    *(Mandatory.)* Names of the addon *types* that can be istalled to this socket. For every addon, this type is specified in XML class of the addon, in the `Type` attribute of the `<InstallSocket>` tag. For example:

    ```xml
    <InstallSocket Type="Don71FrontBumper" />
    ```
    If multiple *types* of addons are specified within the `Names` attribute as a comma separated list, then all listed types of the addons will be compatible with this socket.

-   `Offset="(3.881; 0.834; -0.322)"`  
    The position of the attachment point in the coordinates of the truck (the zero coordinates of the truck correspond to the origin in the FBX file of the truck).

    **NOTE**: The `Offset` attribute of the `<Socket>` tag of the truck works similarly to the `Offset` attribute of the [`<InstallSocket>`](./../../../../truckaddon/gamedata/installsocket/index.md) tag of the addon. However, the `Offset` specified in [`<InstallSocket>`](./../../../../truckaddon/gamedata/installsocket/index.md) of the addon will define the shift of this particular addon on all trucks; the `Offset` specified in the `<Socket>` tag of the truck will define the shift of this addon on this particular truck only. 

-   `ParentFrame="BoneCabin_cdt"`  
    A bone from the hierarchy of the physical model, which the socket is attached to. If the parameter is not specified, then this is a root bone.

-   `NamesBlock="FrameAddonKung, FrameAddonTank"`  
    Names of addon *types* that are blocked after installation of an addon to this socket.  

    **NOTE**: `NamesBlock` can be specified in any addon from the pair of addons that are blocking each other. I.e., if a socket addon is installed, then any addon from `NamesBlock` is unavailable; and vice versa, if an addon from the `NamesBlock` group is installed, then the socket addon is unavailable.

-   `InCockpit="true"`  
    Whether or not the addon installed to this socket should be rendered and displayed in the Cabin View. 


