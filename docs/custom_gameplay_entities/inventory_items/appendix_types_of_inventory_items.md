# Appendix: Types of Inventory Items

## Overview
[Below](#types) you can find in-game inventory items with their **type** and other characteristics.

And, also, [identifiers](#identifiers) of some items that have the same **type**.

**NOTE 1**: When you will be creating your own custom items, you can change their characteristics as necessary. The table below is just an illustration of possible characteristics and all possible values of **type**.  

**NOTE 2**: The "With Ability" VS "Quest Item" characteristics in the table below are listed from the *internal and modding perspective*, not from the point of the view of the player. For details, see [Custom Inventory Items: Overview](./custom_inventory_items_overview.md).

## Types

| Inventory item(s)           |  **type**                    | With Ability | Quest Item | Treasure Item | Heavy |
|-----------------------------|------------------------------|--------------|------------|---------------|-------|
| Amulet                      | AMULET                       | -            | +          | -             | -     |
| Removable Anchor, Anchor    | ANCHOR_SETUP                 | +            | -          | -             | -     |
| Camera Trap                 | ANIMAL_TRAIL_CAMERA          | -            | +          | -             | -     |
| Archeological Set           | ARCH_EQUIPMENT               | -            | +          | -             | -     |
| Batteries                   | BATTERY                      | -            | +          | -             | -     |
| Binoculars (always avail.)  | BINOCULAR                    | +            | -          | -             | -     |
| H-M Station Part            | BROKEN_HYDRO                 | -            | +          | -             | -     |
| Cactus Sap                  | CACTUS                       | -            | +          | -             | -     |
| Candles                     | CANDLES                      | -            | +          | -             | -     |
| Reed                        | CANE                         | -            | +          | -             | -     |
| Cones                       | CONES                        | -            | +          | -             | -     |
| Tree Crust                  | CRUST                        | -            | +          | -             | -     |
| Dinosaur bone               | DINO_BONE                    | -            | +          | -             | -     |
| Drone (always avail.)       | DRONE                        | +            | -          | -             | -     |
| Echo Sounder (always avail.)| ECHOLOT                      | +            | -          | -             | -     |
| Equipment Box               | EQUIPMENT_BOX                | -            | +          | -             | -     |
| Fish                        | FISH                         | -            | +          | -             | -     |
| Flight Recorder             | FLIGHT_RECORDER              | -            | -          | +             | -     |
| *(not used)*                | FUEL_CANISTER                | N/A          | N/A        | N/A           | N/A   |
| Portable Rig Part           | GEOLOGICAL_RIG               | -            | +          | -             | +     |
| Gold Nugget                 | GOLD_PRILL                   | -            | +          | -             | -     |
| Golden Toad                 | GOLDEN_TOAD                  | -            | +          | -             | -     |
| Hydro-Monitoring System     | HYDROLOGICAL_SYSTEM          | -            | +          | -             | +     |
| Jack-Screw                  | JACK_SCREW                   | +            | -          | -             | -     |
| Jammer                      | JAMMER                       | -            | +          | -             | -     |
| Light Beacon                | LED_FLARES                   | -            | +          | -             | -     |
| Hand Drawn Map              | MAP                          | -            | +          | -             | -     |
| Memory Card                 | MEMORY_CARD                  | -            | +          | -             | -     |
| Metal Box                   | METAL_BOX                    | -            | +          | -             | -     |
| Metal Nugget                | METAL_PRILL                  | -            | +          | -             | -     |
| Mushrooms                   | MUSHROOMS                    | -            | +          | -             | -     |
| *(not used)*                | NONE                         | N/A          | N/A        | N/A           | N/A   |
| *(not used)*                | PENALTY_ITEM                 | N/A          | N/A        | N/A           | N/A   |
| Portable Meteostation       | PORTABLE_METEOSTATION        | -            | +          | -             | +     |
|*(Universal Quest Item type)*| QUEST_ITEM                   | -            | +          | -             | -     |
| Supplies                    | QUEST_SUPPLIES               | -            | +          | -             | -     |
| Radio station               | RADIO_STATION                | -            | +          | -             | +     |
| Rig Parts                   | RIG_PARTS                    | -            | +          | -             | -     |
| Scientific Equipment        | SCIENTIST_EQUIPMENT          | -            | +          | -             | -     |
| Scrap metal (recyclable)    | SCRAP_FOR_WARKSHOP           | -            | -          | +             | -     |
| Pile of metal               | SCRAP_METAL                  | -            | +          | -             | -     |
| Rangefinder                 | SURVEY_RANGEFINDER           | -            | +          | -             | -     |
| *(not used)*                | TOOLKIT                      | N/A          | N/A        | N/A           | N/A   |
| Dinosaur femur, rib, skull  | TREASURE                     | -            | -          | +             | -     |
| Quartz, Onyx, Ruby          | TREASURE                     | -            | -          | +             | -     |
| Flowers                     | UNIQUE_FLOWERS               | -            | +          | -             | -     |
| Camcorder                   | VIDEO_CAMERA                 | -            | +          | -             | -     |
| Water Sample                | WATER_ANALYZIS               | -            | +          | -             | -     |
| GPS Tracker                 | GPS_TRACKER                  | -            | -          | -             | -     |
| Signal Amplifier            | SIGNAL_AMPLIFIER_SETUP       | -            | +          | -             | -     |

**NOTE 3**: *Fuel*, *Repair parts*, and *Spare wheels* are not Inventory Items from the modding perspective, see [Custom Inventory Items: Overview](./custom_inventory_items_overview.md#note-on-fuel-repair-parts-and-spare-wheels).

## Identifiers

For some items with the same **type**, *identifiers* may be necessary:

| Inventory item           |  **type**                    | *Identifier*            | 
|--------------------------|------------------------------|-------------------------|
| Anchor                   | ANCHOR_SETUP                 | `Anchor_not_removable`  | 
| Removable Anchor         | ANCHOR_SETUP                 | `Anchor`                |








