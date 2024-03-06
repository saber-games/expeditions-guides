# Repeated Usage

The same template can be used multiple times:

```xml
<Truck>
    <TruckData>
        <Wheels>
            <Wheel _template="MyTemplate1" HardpointX="1" />
            <Wheel _template="MyTemplate1" HardpointX="1" RightSide="true"/>
            <Wheel _template="MyTemplate1" HardpointX="-1" />
            <Wheel _template="MyTemplate1" HardpointX="-1" RightSide="true"/>
        </Wheels>
        ...
    </TruckData>
    ...
</Truck>
```

The same piece of XML without the template will look like the following:

```xml
<Truck>
    <TruckData>
        <Wheels>
            <Wheel HardpointX="1" HardpointY="0.5" HardpointZ="0.5"/>
            <Wheel 
                HardpointX="1" 
                RightSide="true" 
                HardpointY="0.5" 
                HardpointZ="0.5" 
            />
            <Wheel HardpointX="-1" HardpointX="1" HardpointY="0.5"/>
            <Wheel 
                HardpointX="-1" 
                RightSide="true" 
                HardpointY="0.5" 
                HardpointZ="0.5" 
            />
        </Wheels>
        ...
    </TruckData>
    ...
</Truck>
```

