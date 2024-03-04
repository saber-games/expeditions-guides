# Sample Template and Its Usage

Below we describe the template of the `<Wheel>` tag, named as `MyTemplate1`:

```xml
<_templates>
    <Wheel>
        <MyTemplate1 HardpointY="0.5" HardpointZ="0.5" />
    </Wheel>
</_templates>
```

After that, we can use this template in the description of the truck via the `_template` attribute of the `<Wheel>` tag:

```xml
<Truck>
    <TruckData>
        <Wheels>
            <Wheel _template="MyTemplate1" HardpointX="1"/>
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
        </Wheels>
        ...
    </TruckData>
    ...
</Truck>
```


