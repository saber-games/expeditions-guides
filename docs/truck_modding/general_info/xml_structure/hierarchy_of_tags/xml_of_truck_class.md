# XML of Truck Class

The hierarchy of tags in [XML file of Truck Class][xml_file_of_truck_class] is the following:

**Minimum set**

```xml
<Truck>
    <TruckData>
        <Wheels>
            <Wheel/>
        </Wheels>
        <SuspensionSocket />
        <GearboxSocket />
        <EngineSocket />
        <CompatibleWheels />
    </TruckData>
    <PhysicsModel>
        <Body />
    </PhysicsModel>
</Truck>
```

**All tags**

```xml
<_templates />
<_parent />
<Truck>
    <TruckData>
        <Winch/>
        <Wheels>
            <Wheel/>
        </Wheels>
        <SuspensionSocket />
        <SteeringWheel />
        <SteeringRack />
        <Steam />
        <SoundsWheels>
            <WheelWater />
            <WheelSteer />
            <WheelSpinning />
            <WheelMud />
            <WheelExtrude />
            <WheelDamaged />
            <WheelChains />
            <WaterHit />
        </SoundsWheels>
        <SoundsDamage>
            <Wheels />
            <Suspension />
            <Gearbox />
            <FuelTank />
            <Engine />
            <Critical />
            <Common />
        </SoundsDamage>
        <Sounds>
            <Honk />
            <Handbrake />
            <HandbrakeOff />
            <BrakePull />
            <BrakeRelease />
            <BrakesSqueal />
            <Reverse />
            <Gear />
            <EngineTrans />
            <EngineAccel />
            <EngineRev />
            <EngineStart />
            <EngineStop />
            <EngineIdle />
            <EngineIdle_2d />
            <EngineLow />
            <EngineLow_2d />
            <EngineHigh />
            <EngineHigh_2d />
            <EngineHeavy />
            <EngineHeavy_2d />
            <EngineTurbo />
            <DiffLock />
            <ChassisStress />
            <AWD />
            <AbruptStop />
        </Sounds>
        <Shakers>
            <Shaker />
        </Shakers>
        <Shafts>
            <Shaft />
        </Shafts>
        <OcclusionMap />
        <Messages />
        <LimitedFluid />
        <Intake />
        <GearboxSocket />
        <FuelTank />
        <Exhaust />
        <EngineSocket />
        <WinchUpgradeSocket />
        <Driver />
        <Dashboard>
            <Gauge />
        </Dashboard>
        <Damage>
            <DamageArea />
        </Damage>
        <CompatibleWheels />
        <Camera>
            <Cockpit>
                <Rear />
                <Mirror />
                    <SecondaryView />
                </Mirror>
            </Cockpit>
        </Camera>
        <Axles>
            <Axle />
        </Axles>
        <Inventory/>    <!-- NEW, valid for Expeditions only -->
        <DeployCost/>   <!-- NEW, valid for Expeditions only -->
    </TruckData>
    <Snorkel />
    <Rotator />
    <PhysicsModel>
        <NetSync />
        <Body>
            <Body>
                <Constraint>
                    <Motor />
                    <PlaneMotor />
                    <ConeMotor />
                    <TwistMotor />
                    <AllMotor />
                </Constraint>
            </Body>
        </Body>
    </PhysicsModel>
    <ModelAttachments>
        <StopSignals>
            <Model />
            <Light />
            <Flare />
        </StopSignals>
        <ReverseSignals>
            <Model />
            <Light />
            <Flare />
        </ReverseSignals>
        <Ignition>
            <Model />
            <Light />
            <Flare />
        </Ignition>
        <HeadLight>
            <Model />
            <Light />
            <Flare />
        </HeadLight>
    </ModelAttachments>
    <Landmark />
    <HeadLight />
    <GameData>
        <WinchSocket />
        <UiDesc />
        <CustomizationCameras>
            <CameraPos />
        <CustomizationCameras />
        <CraneSocket />
        <AddonSockets>
            <Socket>
                <ExtraParent />
                <AddonsShift />
            </Socket>
        <AddonSockets />
        <AddonSlots />
    </GameData>
    <ControlledConstraints>
        <Constraint />
    </ControlledConstraints>
    <AutomaticIK>
        <IKBone>
            <IKJoint />
            <IKBone>
                <IKJoint />
            </IKBone>
        </IKBone>
    </AutomaticIK>
</Truck>
```

**TIP**: You can refer to [Tags and Attributes of Trucks](./../../../tags_and_attributes_of_trucks/index.md) \> [Truck](./../../../tags_and_attributes_of_trucks/truck/index.md) section and its subsections for details on most XML tags and attributes used in this file.

[xml_file_of_truck_class]: ./../../xml_description_of_truck/xml_of_truck_class.md