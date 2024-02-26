# XML of Addon Class

The hierarchy of tags in XML file of Addon Class is the following:

**Minimum set**

```xml
<TruckAddon>
    <PhysicsModel />
    <GameData>
        <InstallSocket />
    </GameData>  
</TruckAddon>
```

**All tags**

```xml
<_templates />
<_parent />
<TruckAddon>
    <WheelRepairsHide>
        <Mesh />
    </WheelRepairsHide>
    <RepairsHide>
        <Mesh />
    </RepairsHide>
    <FuelHide>
        <Mesh />
    </FuelHide>
    <Vibrator />
    <TruckData>
        <Shakers>
            <Shaker />
        </Shakers>
        <Intake />
        <LimitedFluid />
        <Damage>
            <Multiplier />
        </Damage>
    </TruckData>
    <Snorkel />
    <Rotator />
    <PoweredConstraints>
        <Group>
            <Constraint/>
        </Group>
        <Chain>
            <Group>
                <Constraint />
            </Group>
        </Chain>
    </PoweredConstraints>
    <PhysicsModel>
        <NetSync />
        <Body>
            <Constraint>
                <Motor />
                <PlaneMotor />
                <ConeMotor />
                <TwistMotor />
                <AllMotor />
            </Constraint>
        </Body>
    </PhysicsModel>
    <ModelAttachments>
        <Lightbar>
            <Model />
            <Light />
            <Flare />
        </Lightbar>
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
        <MainHeadLight>
            <Model />
            <Light />
            <Flare />
        </MainHeadLight>
    </ModelAttachments>
    <MainHeadLight />
    <GameData>
        <UiDesc />
        <RequiredAddonType />
        <RequiredAddon />
        <InstallSocket />
        <InstallSlot />
        <Sounds />
        <SoundPoweredGroupStop />
        <SoundPoweredGroupStart />
        <SoundPoweredGroupLoop />
        <SoundIKStop />
        <SoundIKStart />
        <SoundIKLoop />
        <SoundOpenStart />
        <SoundOpenLoop />
        <SoundOpenStop />
        <SoundClose />
        <CraneSourceSocket />
        <Chain>
            <Group>
                <Constraint />
            </Group>
        <Chain>
        <AddonType />
        <AddonSlots />
        <SideboardSlots />          <!-- NEW, valid for Expeditions only -->
        <RequiredSuspension />      <!-- NEW, valid for Expeditions only -->
    </GameData>  
    <FuelMass>
        <Body />
    </FuelMass>
    <WaterMass>
        <Body />
    </WaterMass>
    <ExplicitParents>
        <ExplicitParent />
    </ExplicitParents>
    <Exhaust />
    <ControlledIK>
        <Chain>
            <ConstraintStartPosition />
        </Chain>
    </ControlledIK> 
    <AutomaticIK>
        <IKBone>
            <IKJoint />
            <IKBone>
                <IKJoint />
            </IKBone>           
        </IKBone>
    </AutomaticIK>
    <AddonCamera />
    <ActionGroups>
        <Group>
            <Vibrator />
            <Rotator/>
            <Attachment/>
        </Group>
    </ActionGroups>
    <HeavyInventorySlotsMeshes>     <!-- NEW, valid for Expeditions only -->
        <Mesh/>                     <!-- NEW, valid for Expeditions only -->
    </HeavyInventorySlotsMeshes>    <!-- NEW, valid for Expeditions only -->
</TruckAddon>
```

**TIP**: You can refer to [Tags and Attributes of Trucks](./../../../tags_and_attributes_of_trucks/index.md) \> [TruckAddon](./../../../tags_and_attributes_of_trucks/truckaddon/index.md) section and its subsections for details on some XML tags and attributes used in this file. However, some of child tags of the [TruckAddon](./../../../tags_and_attributes_of_trucks/truckaddon/index.md) work similarly to the same tags of the [Truck](./../../../tags_and_attributes_of_trucks/truck/index.md).