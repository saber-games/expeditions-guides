# XML of Wheel Class

Depending on the [type of the wheel][type_of_the_wheel], the hierarchy of tags in the XML file(s) of Wheel Class(es) is the following:

**Wheel as single entity**

```xml
<_templates />
<_parent />
<TruckWheel>
    <WheelTracks />
    <WheelSoftness />
    <WheelFriction />	
</TruckWheel>
```

**Set of tires and rims**

```xml
<_templates />
<_parent />
<TruckWheels>
    <TruckTires>
        <TruckTire>
            <TiresInflationSystemSettings>  <!-- NEW, valid for Expeditions only -->
                <Low>                       <!-- NEW, valid for Expeditions only -->
                    <TickDamageParams/>     <!-- NEW, valid for Expeditions only -->
                </Low>                      <!-- NEW, valid for Expeditions only -->
                <Reduced>                   <!-- NEW, valid for Expeditions only -->
                    <TickDamageParams/>     <!-- NEW, valid for Expeditions only -->
                </Reduced>                  <!-- NEW, valid for Expeditions only -->
            </TiresInflationSystemSettings> <!-- NEW, valid for Expeditions only -->
            <WheelTracks />
            <WheelTracks Rear="true"/>
            <WheelSoftness />
            <WheelFriction />
            <GameData>
                <UiDesc/>
            </GameData>
        </TruckTire>
    <TruckTires>
    <TruckRims>
        <TruckRim>
            <GameData>
                <UiDesc />
            </GameData>
        </TruckRim>
    </TruckRims>
</TruckWheels>
```

**TIP 1**: You can refer to [Tags and Attributes of Trucks](./../../../tags_and_attributes_of_trucks/index.md) \> [TruckWheels](./../../../tags_and_attributes_of_trucks/truckwheels/index.md) section and its subsections for details on most XML tags and attributes used in the XML class of wheel as set of tires and rims. 

**TIP 2**: For the wheel as a single entity, the [TruckWheel](./../../../tags_and_attributes_of_trucks/truckwheel/index.md) section there has similar info.

[type_of_the_wheel]: ./../../wheels_description/wheels_overview.md
