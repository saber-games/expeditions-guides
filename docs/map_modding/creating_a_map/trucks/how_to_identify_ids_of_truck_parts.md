# How to Identify IDs of Truck Parts

## Overview
When creating the truck in the Editor, you need to know the identifiers of all truck parts fill in some of the fields. 

You can view these IDs either in the game itself, or in its [`initial.pak`][initial_pak].

## Viewing IDs in the Game
To view the IDs of truck parts in the game:

1.  [Open the Proving Grounds][open_proving_grounds].

2.  At the Proving Grounds, select **Garage** in the **TOOLS** menu.

3.  In the appearing menu, you can see all the necessary IDs.

## Viewing IDs in the XML files
Identifiers of trucks correspond to names of XML classes of trucks, without the `.xml` extension. These XML classes are located in the [`initial.pak`][initial_pak] archive, within the `[media]\classes\trucks` subfolder there. 

**NOTE**: DLC trucks and XML classes related to them are available in the `[media]\_dlc` folder.

Identifiers of all car components can be seen in their XML classes within [`initial.pak`][initial_pak] too. For example, the XML classes with Engine variants compatible with every truck are located at `[media]\classes\engines`.


[initial_pak]: ./../../getting_started/file_paths_and_naming/file_paths.md#source-of-info-initialpak-archive
[open_proving_grounds]: ./../../../truck_modding/getting_started/sample_mod_by_the_game/opening_the_proving_ground.md