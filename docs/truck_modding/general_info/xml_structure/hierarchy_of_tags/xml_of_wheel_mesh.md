# XML of Wheel Mesh

Depending on the [type of the wheel][type_of_the_wheel], the hierarchy of tags in the XML file(s) of Wheel Mesh(es) is the following:

**Wheel as a single entity**

```xml
<CombineXMesh Type="Wheel">
    <WheelMesh/>
    <Material />
</CombineXMesh>
```

**Tire or Rim**

```xml
<CombineXMesh Type="Wheel">
    <Material />
</CombineXMesh>
```

[type_of_the_wheel]: ./../../wheels_description/wheels_overview.md