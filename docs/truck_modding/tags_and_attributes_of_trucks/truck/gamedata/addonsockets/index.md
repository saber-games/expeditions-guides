# AddonSockets

The `<AddonSockets>` section determines the relative positions of addons of a truck.

Addons described inside different `<AddonSockets>` sections are in no way related to each other.

Addons described in one section are mutually exclusive. I.e., if one addon from a section is installed, you cannot install another addon from the same section.  

In addition, the [`<Socket>`](./socket/index.md) tag has the `NamesBlock` attribute, which allows you to make tags from different sections mutually exclusive.

For example:

```xml
<AddonSockets>
    <Socket Names="Addon1"/>
    <Socket Names="Addon2, Addon3"/>
</AddonSockets>
<AddonSockets>
    <Socket Names="Addon4"/>
    <Socket Names="Addon5"/>
    <Socket Names="Addon6", NamesBlock="Addon1"/>
</AddonSockets>
```

Addons #4 and #5 do not depend on whether addons #1, #2, or #3 are installed.  
If addon #1 is installed, then addons #2, #3, and #6 cannot be installed.

Attributes:

-   `DefaultAddon="don_71_front_bumper_default"`  
    The name of the XML file of the default addon. It is used, if the addon should be installed when the player purchases a truck.
    
    **NOTE**: You can specify one of the existing in-game addons in this field. However, in this case, there is a known issue – the game will generate errors while packing the mod and will not pack it. To avoid this issue, you can add the original file of the XML class of this addon (e.g. `don_71_front_bumper_default.xml`) to the folder with addons of the mod (as if you were adding a custom addon). After that, there will be no errors and the mod will be packed correctly. This issue will be fixed in future versions of the game.

