# Extension of Hierarchy

You can add or change attributes or tags in the piece of XML provided by the template. 

However, when a template describes some hierarchy of tags and you need to add or change an attribute or tag, you will need to recreate all hierarchy of its parent tags.

*For example:*

```xml
<_templates>
    <Body>
        <MyTemplate4 Mass="5">
            <Constraint Type="Fixed" />
            <Body Mass="1">
                <Constraint Type="Hinge" />
                <Body Mass="2">
                    <Constraint Type="Ragdoll" />
                </Body>
            </Body>
        </MyTemplate4>
    </Body>
</_templates>

<Truck>
    <PhysicsModel Mesh="trucks/example_truck">
        <Body Mass="10">
            <Body _template="MyTemplate4">
                <Body>
                    <Body>
                        <Constraint AxisLocal="(1; 0; 0)" />
                    </Body>
                </Body>
            </Body>
            <Body _template="MyTemplate4">
                <Body>
                    <Body>
                        <Body Mass="0.1">
                            <Constraint Type="Fixed" />
                        </Body>
                    </Body>
                </Body>
            </Body>
        </Body>
    </PhysicsModel>
    ...
</Truck>
```

The same piece of XML without the template will look like the following:

```xml
<Truck>
    <PhysicsModel Mesh="trucks/example_truck">
        <Body Mass="10">
            <Body Mass="5">
                <Constraint Type="Fixed" />
                <Body Mass="1">
                    <Constraint Type="Hinge" />
                    <Body Mass="2">
                        <Constraint AxisLocal="(1; 0; 0)" Type="Ragdoll" />
                    </Body>
                </Body>
            </Body>
            <Body Mass="5">
                <Constraint Type="Fixed" />
                <Body Mass="1">
                    <Constraint Type="Hinge" />
                    <Body Mass="2">
                        <Constraint Type="Ragdoll" />
                        <Body Mass="0.1">
                            <Constraint Type="Fixed" />
                        </Body>
                    </Body>
                </Body>
            </Body>
        </Body>
    </PhysicsModel>
    ...
</Truck>
```

