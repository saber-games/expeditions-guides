# Files of a Truck

During its creation, all files of a truck mod are stored within a mod folder, whose name typically corresponds to a name of the truck.
For example, `...\Media\Mods\truck_example\`.

Within this folder, there is a standardized set of subfolders with files. Particularly, relative to the mod folder of the truck (`/truck_example/` in our case), these files are mainly the following: 

1. `/meshes/trucks/truck_example.fbx` – the FBX model of the truck. It contains:
     - Truck meshes.
     - Truck skeleton.
     - Collision meshes.

2. `/meshes/trucks/truck_example.xml` – the XML file of the Mesh of the truck. It contains:

     - Paths to truck textures and descriptions of their properties (Blending, AlphaKill, TwoSided, snow cover parameters, and so on).
     - Description of shaft mounting points.
     - MaterialOverrides - info about color customization.

3. `/classes/trucks/truck_example.xml` – the XML file of the Class of the truck. It contains all information on the behaviour of the original truck: description of the physical model dynamics, types and sizes of wheels used by the truck, descriptions of available suspensions and engines, info on lighting (location of lights, their brightness, color, shape, and so on), driver position, position and direction of the exhaust pipe, descriptions of available addons and trailers, price of the truck, and so on.

4. `/classes/truck_replacements/truck_replacement_example.xml` (NEW) – the XML file of the *Truck Replacement* of the truck. It contains all information on the behaviour on the truck replacement that will substitute the data of the original truck. For more information on the Truck Replacements feature, see [Truck Replacements](./../../new_features/truck_replacements.md).
  
5. `/classes/suspensions/s_truck_example.xml` – the description of the suspension.

6. `/classes/gearboxes/` – the description of gearboxes (files of gearboxes are typically not tied to a particular truck, but are common for the particular class of trucks).

7. `/classes/engines/` – the description of engines (files of engines are typically not tied to a particular truck, but are common for the particular class of trucks).


**NOTE**: A sample mod that is generated by the game contains samples of all these files and some other files and folders too. For instructions on generation the sample mod, see the [**Getting Started**](./../../getting_started/intro.md) section.  

