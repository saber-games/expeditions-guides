# freeRoamInfo

*(NEW) This feature is valid for Expeditions only.*  

## Overview
The **freeRoamInfo** [substage][stages_and_substages] can be used to support the *Free Roam* mechanics for your map. It is a special substage that is used only for that.

**NOTE**: When players perform a *Free Roam*, they are able to explore the map without any restrictions or requirements. If they want to, they are able to accomplish standalone tasks and contracts during this process, but they have no regular primary [Expedition][expedition] objective whose accomplishment is required. From the point of view of the system, the [Expedition][expedition] still needs to be created in this case, but it is created in the special way, see below.

Particularly, if you want the player to be able to *Free Roam* on the map, you need to:

1.  Create the *separate* [Expedition][expedition] for this map.
2.  Add only one [Stage][stages_and_substages] to this Expedition.
3.  Add the **freeRoamInfo** substage inside this stage and fill in its properties (see [below](#setup)).

The created Expedition of the *Free Roam* type will be available along with other Expeditions for your map.

**TIP**: If necessary, you can unlock the *Free Roam* mechanics for your map only after the player accomplishes the particular objective(s) on this map. You can use the **Blocker Objectives** list within the properties of the *Free Roam* Expedition for that.

**NOTE**: The name of the created *Free Roam* Expedition will be displayed in the UI when the player performs *Free Roam* on the map. Below it, the **Ui Desc** text from the **freeRoamInfo** substage will be displayed. When a player activates a task or a contract on the map, this info is replaced with the info of this task or contract.


## Setup
After selecting the appropriate settings type, the **freeRoamInfo** section will contain the following settings:

-   **Ui Desc** – The text that will be displayed in the UI when the player performs the *Free Roam* on the map, along with the name of the *Free Roam* Expedition itself, see [above](#overview).
-   **map** – The name of the XML file of the map, without the `.xml` file extension. For example, `level_my_map_07` for `level_my_map_07.xml`.


[stages_and_substages]: ./stages_in_expeditions.md
[expedition]: ./../expeditions_and_contracts.md