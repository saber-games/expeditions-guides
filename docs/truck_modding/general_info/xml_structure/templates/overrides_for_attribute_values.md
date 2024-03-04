# Overrides for Attribute Values

If both a template and a tag that links to it use the same attribute and the tag contains the value of this attribute, then the value specified in the tag will override the value from the template.

For example, in the following XML piece, the value of the `HardpointY` attribute from the template is overwritten by the value of the same attribute from the tag:

```xml
<_templates>
    <Wheel>
        <MyTemplate1 HardpointY="0.5" HardpointZ="0.5" />
    </Wheel>
</_templates>

<Truck>
    <TruckData>
        <Wheels>
            <Wheel _template="MyTemplate1" HardpointX="1" HardpointY="1" />
        </Wheels>
        ...
    </TruckData>
    ...
</Truck>
```

So, this piece of XML without the template will look like the following:

```xml
<Truck>
    <TruckData>
        <Wheels>
            <Wheel HardpointX="1" HardpointY="1" HardpointZ="0.5" />
        </Wheels>
        ...
    </TruckData>
    ...
</Truck>
```


