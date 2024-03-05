# Custom Specialists: Overview

*(NEW) This feature is valid for Expeditions only.*

**NOTE**: In the current version of Expeditions, there is an issue that saving a custom specialist may not work when this specialist is created *for the first time*. As the result of this issue, you will see the "*Can’t open file: ...*" message. This issue occurs because the `Media\Mods` folder is not created automatically. The temporary solution for this is to create this folder manually. Or, as an alternative, create and *pack* any map. This issue is known and will be fixed in the next versions of the Editor.   

## Overview
Specialists modify certain parameters of gameplay.

They affect these parameters using specific *modifiers* that are added to them during setting up, in addition to [general properties][general_properties].

Every specialist has a class: `MECHANIC`, `HYDROLOGIST`, and so on.


## Modifiers
Every modifier corresponds to a certain ability of the Specialist.

For example, the *SpecialistModifierDroneScoutRadius* modifier increases the radius of exploration with the *Drone*.  
Or, *SpecialistModifierDroneRadius* increases the maximum flight distance of the *Drone*. 

The set of these modifiers is predefined, but rather large. Every modifier affects its own parameters and has corresponding fields during the setup. 

When creating custom specialists, you can add any modifiers to them. However, a modifier of the particular type (e.g. *SpecialistModifierDroneRadius*) can be added only once.

For the list of available modifiers and their fields, see [Modifiers][modifiers].

### Descriptions and Groups in UI
Every modifier has a single or multiple **...UiDesc** settings depending on the number of parameters affected by it.
Every **...UiDesc** section corresponds to the UI description of changes to this parameter.

For example, the *SpecialistModifierDroneRadius* modifier has the **droneRadiusIncreasedMetersUiDesc** section that allows you to specify text to be displayed in the UI for the change of the **droneRadiusIncreasedMeters** parameter, with the necessary prefix (typically `+` or `-`), type of value (e.g. `Meters`) and icon.

And, if necessary, you can define the particular **group** that will be displayed in the UI and will group multiple modifiers that are related to each other. E.g. `Drone:`. Or `Outposts:`.

For example, the setup can be the following:

![](./media/sample_modifier.png)

Where the value of changes to affected parameter is taken from **droneRadiusIncreasedMeters** and other fields define the **...UiDesc** text around it and the **group** of modifiers where it will be displayed. 

## Class
The class (**speciality**) of the specialist defines the category of this specialist when selecting it in the UI.

The list of classes is predefined:

-   `MECHANIC`
-   `LOGISTIC_SPECIALIST`
-   `HYDROLOGIST`
-   `JAEGER`
-   `OPERATOR`
-   `MANAGER`

**WARNING**: You must not select the `NONE` class in the **speciality** field. Specialists with the `NONE` class will crash the game. (`TBD`) 

In the original game, modifiers of the specialist are typically related to the specialist's class. However, there is no required connection between the two – i.e., you are able to add any modifiers regardless of the selected class.


## Locking and Unlocking
By default, custom specialists are unlocked and available from the start. 

However, by enabling the **isLocked** option in the [general properties][general_properties] of the specialists, you can lock them.

Locked specialists may be unlocked using a special reward granted after accomplishing the particular objective. See [Rewards][rewards] for details.

However, this locking should be used only if you provide this Specialist as a [linked mod][linked_mods].


[modifiers]: ./modifiers_of_specialists.md
[general_properties]: ./general_properties_of_specialists.md
[rewards]: ./../../map_modding/creating_a_map/objectives/objectives_in_expeditions/rewards.md
[linked_mods]: ./../../usage_and_uploading_of_mods/linking_mods.md