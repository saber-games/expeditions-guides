# Gearbox

The `<Gearbox>` tag corresponds to the gear box of the truck.

Attributes:

- `AWDConsumptionModifier="1.1"`  
  The coefficient of change in fuel consumption during all-wheel drive usage. Default value: `1`. Range of values: `[0; 32]`.

- `CriticalDamageThreshold="0.5"`  
  Percentage of damage, after which the box begins to show signs of failure: the vehicle starts to switch from particular gears to neutral gear from time to time (see `MinBreakFreq` and `MaxBreakFreq` below) and the fuel consumption increases.  
  Default value: `0.7`. Range of values: `[0; 0.999]`.

- `DamageCapacity="120"`  
  Amount of allowable damage.  
  Default value: `0`. Range of values: `[0; 64000]`.

- `DamagedConsumptionModifier="1.4"`  
  The maximum fuel consumption modifier. This multiplier is used for fuel consumption when the gearbox is completely broken.  
  Default value: `1`. Range of values: `[0; 32]`.

- `FuelConsumption="1.8"`  
  Basic fuel consumption of the gearbox.  
  Default value: `0.1`. Range of values: `[0; 10]`.

- `IdleFuelModifier="0.2"`  
  Fuel consumption multiplier when the vehicle stands still with the running engine.  
  Default value: `0.3`. Range of values: `[0; 10]`.

- `Name="g_scout_default"`  
  The name of the gearbox.

- `MinBreakFreq="0.0"`  
  The minimum frequency of switching to neutral gear, at the moment when the durability has reached the `CriticalDamageThreshold`. See `CriticalDamageThreshold` above.  
  Default value: `0`. Range of values: `[0; 60]`.

- `MaxBreakFreq="15.0"`  
  The maximum frequency of switching to neutral gear, at the moment when the durability approaches zero. See `CriticalDamageThreshold` above.  
  Default value: `0`. Range of values: `[0; 60]`.
