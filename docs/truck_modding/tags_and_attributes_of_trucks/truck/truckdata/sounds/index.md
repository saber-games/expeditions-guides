### 8.1.9. \<Sounds\>

Section that describes the sounds of the truck.

-   Origin=\"(2.8; 1.612; 0)\"\
    The place where the semi-transparent engine is drawn. An emitter for a sound will be created in this position. An emitter is the position from where the sound will be played as a 3D sound.


-   MinDist=\"10\"\
    The volume of sounds of the truck decreases after the MinDist distance (linearly from the distance). At distances closer than MinDist, the volume of sounds does not decrease.


-   MaxDist=\"200\"\
    After the distance exceeds MinDist, the volume is linearly decreased. At the MaxDist distance, the volume is decreased to zero.\
    **NOTE**: In addition to these parameters, the volume of the truck sounds decreases (depending on the distance) when rendering through the sound library. For example, when X3DAudio library for PC and Xbox One is used. Thus, the MinDist and MaxDist parameters provide an additional effect of decreasing the volume with the increase of the distance.


-   DisableReversePitch=\"false\"\
    This flag determines the behavior of the Reverse sound. If this flag is set to true, then the sound will be reproduced without any changes. If it is false, then the FrequencyRatio of the sound will be changed depending on the speed of movement.

\<Honk Sound=\"\"/\>\
\<Handbrake Sound=\"\"/\>\
\<HandbrakeOff Sound=\"\"/\>\
\<BrakePull Sound=\"\"/\>\
\<BrakeRelease Sound=\"\"/\>\
\<BrakesSqueal Sound=\"\"/\>\
\<Reverse Sound=\"\"/\>\
\<Gear Sound=\"\"/\>\
\<EngineTrans Sound=\"\"/\>\
\<EngineAccel Sound=\"\"/\>\
\<EngineRev Sound=\"\"/\>\
\<EngineStart Sound=\"\"/\>\
\<EngineStop Sound=\"\"/\>\
\<EngineIdle Sound=\"\"/\>\
\<EngineIdle_2d Sound=\"\" IsSound2D=\"true\"/\>

-   IsSound2D=\"true\"\
    A flag indicating that it is not necessary to create an emitter for this sound.\
    Sounds without emitters will be played directly to the speakers or headphones in stereo. For such sounds, there is no dependence of the volume from the distance to the truck (it is logical, because only the sounds of engine belong to this category). These sounds will be played in 2D mode when the player is using the 1st person view or is playing from the cockpit, if the corresponding sounds are specified in XML. If the corresponding sounds are not specified in XML, the default sounds are used. E.g., EngineIdle is used instead of the EngineIdle_2d.

\<EngineLow Sound=\"\"/\>\
\<EngineLow_2d Sound=\"\" IsSound2D=\"true\"/\>\
\<EngineHigh Sound=\"\"/\>\
\<EngineHigh_2d Sound=\"\" IsSound2D=\"true\"/\>\
\<EngineHeavy Sound=\"\"/\>\
\<EngineHeavy_2d Sound=\"\" IsSound2D=\"true\"/\>\
\<EngineTurbo Sound=\"\"/\>\
\<DiffLock Sound=\"\"/\>\
\<ChassisStress Sound=\"\"/\>\
\<AWD Sound=\"\"/\>\
\<AbruptStop Sound=\"\"/\>

