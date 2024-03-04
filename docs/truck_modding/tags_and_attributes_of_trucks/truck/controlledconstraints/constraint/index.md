# Constraint

The description of the Controlled Constraint of the Truck. I.e., the description of the way of *controlling* a specific constraint of the physical model of the truck.

**NOTE 1**: For general information on Controlled Constraints *of a Truck*, see [ControlledConstraints](./../index.md).

**NOTE 2**: For information on Controlled Constraints *for Addons*, see [FastMode. Controlled Constraints of Addon](./../../../../additional_info_on_trucks/addons_selected_info/fast_mode.md) and its subsections.


Attributes:

-   `Id="chassis_steer"`  
    *(Mandatory.)* A required attribute that does nothing (its old logic has been deleted, the new logic has not been implemented yet).


-   `IsLinkedSteering="true"`  
    An attribute that synchronizes the behavior of the motor of the constraint with a steering.


-   `Name="TieRodSteer"`  
    *(Mandatory.)* The name of the constraint of the physical model for which the control is assigned. See the `Name` attribute of the [`<Constraint>`](./../../physicsmodel/body/constraint/index.md) tag of the [`<PhysicsModel>`](./../../physicsmodel/index.md).

**NOTE**: Attributes of the Controlled Constraints of an Addon are different, for details, see [Controls for Controlled Constraints of Addon](./../../../../additional_info_on_trucks/addons_selected_info/controls_for_controlled_constraints.md).