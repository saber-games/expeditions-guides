# RequiredAddon

The particular addon required by the current addon. 

**NOTE**: By specifying multiple names of addons within this tag (as a value of the `Types` attribute), you can specify a logical `OR` condition for them. By usage of multiple `<RequiredAddon>` tags, you can specify a logical `AND` condition for them. See [Addon Changes](./../../../../new_features/addon_changes.md) for details.

Attributes:

-   `Types="frame_module_flatbed, frame_module_flatbed_short"`  
    *(Mandatory.)* The name of the XML class of the target required addon, without file extension. When multiple names of addons are specified as comma separated list within the value of the attribute – they are combined using the logical `OR` condition (i.e. *any* addon from the specified list is required).


