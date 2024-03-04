# Sounds

Section that describes the sounds of the truck. Sounds are added as child tags.

## Atributes
Attributes:

-   `Origin="(2.8; 1.612; 0)"`  
    The place where the semi-transparent engine is drawn. An emitter for a sound will be created in this position. An emitter is the position from where the sound will be played as a 3D sound.


-   `MinDist="10"`  
    The volume of sounds of the truck decreases after the `MinDist` distance (linearly from the distance). At distances closer than `MinDist`, the volume of sounds does not decrease.


-   `MaxDist="200"`  
    After the distance exceeds `MinDist`, the volume is linearly decreased. At the MaxDist distance, the volume is decreased to zero.
    
    **NOTE**: In addition to these parameters, the volume of the truck sounds decreases (depending on the distance) when rendering through the sound library. For example, when X3DAudio library for PC and Xbox One is used. Thus, the `MinDist` and `MaxDist` parameters provide an additional effect of decreasing the volume with the increase of the distance.


-   `DisableReversePitch="false"`  
    This flag determines the behavior of the `Reverse` sound. If this flag is set to true, then the sound will be reproduced without any changes. If it is false, then the FrequencyRatio of the sound will be changed depending on the speed of movement.

## Child Tags
Child tags:

```xml
			<GearFail		Sound="trucks/common/truck_gear_wrong/truck_gear_wrong_small_modern" />
			<Reverse		Sound="trucks/cotco_canyon/cotco_canyon_low" />
			<BrakePull		Sound="" />
			<BrakeRelease	Sound="" />
			<BrakesSqueal	Sound="trucks/cotco_canyon/cotco_canyon_brakes_squeal" />
			<Gear			Sound="trucks/cotco_canyon/cotco_canyon_gear_shift" />
			<HandbrakeOff	Sound="trucks/cotco_canyon/cotco_canyon_handbrake_off" />
			<AWD			Sound="trucks/cotco_canyon/cotco_canyon_awd" />
			<Honk			Sound="trucks/cotco_canyon/cotco_canyon_honk" />
			<ChassisStress	Sound="trucks/cotco_canyon/cotco_canyon_chassis" />
			<Handbrake		Sound="trucks/cotco_canyon/cotco_canyon_handbrake" />
			<EngineRev		Sound="trucks/cotco_canyon/cotco_canyon_rev" />
			<EngineAccel	Sound="trucks/cotco_canyon/cotco_canyon_acc" />
			<EngineStart	Sound="trucks/cotco_canyon/cotco_canyon_start" />
			<EngineStop		Sound="trucks/cotco_canyon/cotco_canyon_stop" />
			<EngineIdle		Sound="trucks/cotco_canyon/cotco_canyon_idle" />
			<EngineIdle_2d	Sound="trucks/cotco_canyon/cotco_canyon_idle_2d"	IsSound2D="true" />
			<EngineLow		Sound="trucks/cotco_canyon/cotco_canyon_low" />
			<EngineLow_2d	Sound="trucks/cotco_canyon/cotco_canyon_low_2d"	    IsSound2D="true" />
			<EngineHigh		Sound="trucks/cotco_canyon/cotco_canyon_high" />
			<EngineHigh_2d	Sound="trucks/cotco_canyon/cotco_canyon_high_2d"	IsSound2D="true" />
			<EngineHeavy	Sound="trucks/cotco_canyon/cotco_canyon_heavy" />
			<EngineHeavy_2d	Sound="trucks/cotco_canyon/cotco_canyon_heavy_2d"	IsSound2D="true" />
			<AbruptStop		Sound="" />
            <EngineTrans    Sound=""/>
            <EngineTurbo    Sound=""/>
            <DiffLock       Sound=""/>
            <WaterGurgle	Sound="trucks/common/truck_exhaust_water_gurgle_loop" />
			<WaterDropping	Sound="" />
			<EngineStalling	Sound="trucks/common/truck_engine_stalling" />
			<DamagedEngine	Sound="trucks/common/truck_engine_damaged" />
			<Cockpit		Sound="trucks/common/truck_cockpit_loop"            IsSound2D="true"  />
```



Where 

-   `Sound="trucks/cotco_canyon/cotco_canyon_start"`  
    Corresponds to the sound file or a [series of sounds][series_of_sounds] files specified for this *truck sound*.

-   `IsSound2D="true"`  
    A flag indicating that it is not necessary to create an emitter for this sound.
    Sounds without emitters will be played directly to the speakers or headphones in stereo. For such sounds, there is no dependence of the volume from the distance to the truck (it is logical, because only the sounds of engine belong to this category). These sounds will be played in 2D mode when the player is using the 1st person view or is playing from the cockpit, if the corresponding sounds are specified in XML. If the corresponding sounds are not specified in XML, the default sounds are used. E.g., `EngineIdle` is used instead of the `EngineIdle_2d`.




[series_of_sounds]: ./../../../../../map_modding/creating_a_map/sounds_and_music/sounds/series_of_sounds.md










