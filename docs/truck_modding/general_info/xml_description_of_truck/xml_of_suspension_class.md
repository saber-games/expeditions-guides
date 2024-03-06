# XML of Suspension Class

This file is located in `/classes/suspensions/` folder. Typically, the name of this file starts with `s_` suffix + `<name_of_truck>`, e.g. `s_don_71.xml`. 

This file contains a description of the suspensions that are available for the particular truck. More precisely, in the file they are described as a *Suspension Sets* that contain particular front/rear suspensions related to the particular wheels truck.  

Typically, there are three Suspension (Sets) for the truck:

- default (e.g. `"international_loadstar_1700_suspension_default"`)
- lifted (e.g. `"international_loadstar_1700_suspension_high"`)
- offroad/rock-crawler (e.g. `"international_loadstar_1700_suspension_crawler"`)

**NOTE**: If necessary, you can link some of these suspension (sets) to *Truck Replacement*. See [Truck Replacements](./../../new_features/truck_replacements.md) for details.

In this XML file, you can specify:

- Height and stiffness of the suspension

- Maximum detachment of wheels from the truck in case of a broken suspension

- Value of `DamageCapacity`

- Value of `CriticalDamageThreshold`

- Value of `BrokenWheelDamageMultiplier`

- Price of the suspension

- Parameters for unlocking this suspension in the game.

- [Truck Replacement](./../../new_features/truck_replacements.md) that is linked to this suspension (set).

**NOTE**: You can refer to [Tags and Attributes of Trucks](./../../tags_and_attributes_of_trucks/index.md) > [SuspensionSetVariants](./../../tags_and_attributes_of_trucks/suspensionsetvariants/index.md) section and its subsections for details on the XML tags and attributes used in this file.
