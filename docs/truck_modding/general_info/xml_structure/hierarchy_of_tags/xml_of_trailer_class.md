# XML of Trailer Class

*This feature is valid for SnowRunner only.*

In *SnowRunner*, the hierarchy of tags in XML file of Trailer Class is the following:

**Minimum set**

```xml
<Truck Type="Trailer">
    <TruckData>
        <Wheels>
            <Wheel />
        </Wheels>
        <Constraint />
    <TruckData>
    <PhysicsModel>
        <Body />
    </PhysicsModel>
</Truck>
```


**All tags**

```xml
<_templates />
<_parent />
<Truck Type="Trailer">
    <TruckData>
        <Wheels>
            <Wheel />
        </Wheels>
        <OcclusionMap />
        <LimitedFluid />
        <Constraint>
            <Motor />
            <PlaneMotor />
            <ConeMotor />
            <TwistMotor />
            <AllMotor />
        </Constraint>
        <CompatibleWheels />
        <Camera />
        <Axles>
            <Axle />
        </Axles>
    <TruckData>
    <PoweredConstraints>
        <Group />
    </PoweredConstraints>
    <PhysicsModel>
        <NetSync />
        <FarmingBoundingBoxN />
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
    </ModelAttachments>
    <Landmark />
    <GameData>
        <WinchSocket />
        <UiDesc />
        <RequiredAddon />
        <InstallSocket />
        <CraneSocket />
        <AddonSlots />
    </GameData>
    <FuelMass>
        <Body />
    </FuelMass>
    <WaterMass>
        <Body />
    </WaterMass>
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