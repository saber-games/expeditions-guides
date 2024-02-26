# XML of Truck Class

This file is located in `classes/trucks/` folder.

It contains all information on the behavior of the truck in the game engine. 

Here is a partial list of what is described there:

- (NEW) The price of the truck usage in the Expedition.

- (NEW) Internal Inventory of the Truck.

- Description of the type of the object – a truck, an addon, or a trailer.

- Description of Havok physical model (characteristics of the interaction of physical bones with each other and with the environment).

- Description of the behavior of bones that are not related to the physical engine:
    - shakers (vibrations, the intensity of which depends on current "engine power")
    - bones of inverse cinematics (the behavior of which depends on positions of other bones, but not from the physical simulation)
    - other bones not related to physics.

- Assignment of control buttons.

- Positions and description of characteristics of light sources.

- Available engines, suspensions, gearboxes.

- Whether or not the truck has the differential.

- Types, sizes, and positions of wheels.

- Types of the wheel drive.

- Descriptions of cast shadows.

- The behavior of the steering wheel and wheels that are connected to it.

- Sounds.

- Position and direction of airflow and the exhaust.

- Position of the driver.

- Position of external camera and position of the first-person camera.

- Damage characteristics for the engine and fuel tanks.

- Positions of the addons and their interactions with the truck and with each other.

- Length of the winch.

- Attachment points for the winch.

- Attachment points for the crane rope.

- Price of the truck.

- Description of the truck model on the map

- *For trucks*: Positions of cameras in the garage.  
  *For addons*: The camera that is active when the addon is selected.

**NOTE**: You can refer to [Tags and Attributes of Trucks](./../../tags_and_attributes_of_trucks/index.md) > [Truck](./../../tags_and_attributes_of_trucks/truck/index.md) section and its subsections for details on the XML tags and attributes used in this file.