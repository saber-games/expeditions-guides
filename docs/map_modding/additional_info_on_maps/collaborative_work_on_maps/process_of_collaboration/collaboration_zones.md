# Collaboration: Zones

A zone is defined by two entities: its locator and its zone properties. They are stored in different locations.

The data of *zone locator* is stored in the `Media\prebuild\<level_name>\_zones.xml`.

However, if a zone is within a particular [group][group], the same info on the zone locator is stored in the `Media\prebuild\<level_name>\subgroups` folder, in the XML file of the group.

The data on *zone properties* is stored in the `zone_settings.json` file within the `Media\levels\<level_name>` folder.

Thus, when a modder adds a zone, this modder needs to send the following to other modders:

-   The piece of XML code with info on *zone locator* – either from `_zones.xml` or from the XML file of the [group][group].

-   The piece of JSON code with *zone properties* – from `zone_settings.json`.

[group]: ./../../../getting_started/ui_overview/groups.md