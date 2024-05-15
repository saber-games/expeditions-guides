# Supply Shop zones

*This feature is valid for Expeditions only.*

The *ZonePropertySupplyShop* prop is used for setting up the *Store* (Supply Shop) [FOB module zone](./zones_of_fob_modules_overview.md).

**NOTE**: Use this prop only to [configure custom FOB Modules][creation_of_custom_fob_module]. Do not assign this prop to common standalone zones. If you do it, this might cause a crash.

**NOTE**: From the player's perspective, the *Store* (Supply Shop) is always available along with the *Base module* (Base Module) of the FOB. However, internally it is configured separately, as a separate FOB Module.

Settings:

-   **moduleId** – links this zone to the custom FOB module. In this field, you need to specify the [*identifier*][fob_module_identifier] of this custom FOB module. I.e., in the **moduleId** field you need to specify exactely the same value as you have specified in the **name** field in the general properties of this custom FOB module.

-   **zoneDiscoverability** – *(Optional)* settings related to the zone discovery. See [Discoverability of Zones](./../discoverability_of_zones.md). Typically not specified, since it is a FOB module.


[fob_module_identifier]: ./../../../../../custom_gameplay_entities/fob_modules/general_properties_of_fob_modules.md
[creation_of_custom_fob_module]: ./../../../../../custom_gameplay_entities/fob_modules/creation_of_custom_fob_module.md