# Engine

The `<Engine>` tag corresponds to the engine of the truck.

Attributes:

- `Name="ru_scout_old_engine_2"`  
  *(Mandatory).* Name of the engine.

- `FuelConsumption="0.6"`  
  Fuel consumption. By default: `0.5`. Value range: `[0; 100]`.

- `DamageCapacity="120"`  
  Amount of allowed damage. By default: `0`. Value range: `[0; 64000]`.

- `CriticalDamageThreshold="0.9"`  
  Critical damage threshold. By default: `0.7`. Value range: `[0; 0.999]`. After this threshold, fuel consumption and engine power are changed.

- `DamagedConsumptionModifier="1.3"`  
  The maximum value of the change in fuel consumption after engine failure.
  By default: `1`. Value range: `[0.1; 32]`.  
  If engine damage exceeded `DamageCapacity * CriticalDamageThreshold`, then the fuel consumption starts to increase linearly, from `FuelConsumption` to `FuelConsumption * DamagedConsumptionModifier` (the latter value corresponds to the situation when the engine is completely broken).

- `EngineResponsiveness="0.04"`  
  Engine responsiveness (speed of increase of the engine speed). By default: `0.04`. Value range: `[0.01; 1]`.

- `Torque="40000"`  
   *(Mandatory).* Torque. By default: `0`. Value range: `[0; 1000000]`.

- `DamagedMinTorqueMultiplier="1.0"`  
    The multiplier for torque when the damage to the engine has reached the `CriticalDamageThresold` threshold. By default: `0`. Value range: `[0; 1]`.

- `DamagedMaxTorqueMultiplier="0.7"`  
  Multiplier for torque when the engine is close to complete breakdown. By default: `0`. Value range: `[0; 1]`. After passing the threshold, the multiplier value changes linearly from `DamagedMinTorqueMultiplier` to `DamagedMaxTorqueMultiplier`.

- `BrakesDelay="0.5"`  
  Braking Delay. By default: `0`. Value range: `[0; 1]`.

- `MaxDeltaAngVel="0.01"`  
  *(Mandatory).* Limiter for the maximum angular acceleration of the wheels. The smaller it is, the slower the car accelerates. By default: `0`. Value range: `[0; 1000000]`.

