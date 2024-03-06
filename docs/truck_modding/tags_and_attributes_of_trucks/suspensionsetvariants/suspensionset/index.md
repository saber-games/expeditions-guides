# SuspensionSet

The `<SuspensionSet>` tag contains suspensions. This section contains a set of suspensions for all axes of the truck.

Attributes:

- `Name="ank_mk38_suspension_default"`  
  *(Mandatory).* The name of a set of suspensions.

- `UiName=""`  
  *(Not used).* This field is currently *not used* and has no effect on the UI name of the suspension. The UI name of the suspension should be specified within the `UiName` attribute of the [`<UiDesc>`](./suspension/gamedata/uidesc/index.md) tag within the XML class of the suspension.

- `DamageCapacity="200"`  
  Amount of the allowed damage. By default: `0`. Value range: `[0; 64000]`.

- `CriticalDamageThreshold="0.4"`  
  Critical damage threshold. By default: `0.7`. Value range: `[0; 0.999]`.

- `BrokenWheelDamageMultiplier="2"`  
  This coefficient is responsible for increasing the damage to the suspension when a wheel is broken (has a flat tire). By default: `1`. Value range: `[0; 100]`.  
  When a blow goes to a particular wheel and it becomes broken, the damage to the suspension is multiplied by this coefficient.

- `TruckReplacement="don_71_1"` (NEW)  
  *(Optional).* The name of the XML class of the paticular Truck Replacement, without file extension. The specified Truck Replacement will substitute the original truck when the player will select this suspension set. For details, see [Truck Replacements](./../../../new_features/truck_replacements.md).
