# Template for Hierarchy of Tags

A template may contain a whole hierarchy of tags.

*For example:*

Declaration of the template:

```xml
<_templates>
    <Body>
        <MyTemplate3 Mass="5">
            <Constraint Type="Hinge" MinLimit="-1" MaxLimit="1">
                <Motor Damping="0.3" Spring="25" Type="Spring" />
            </Constraint>
        </MyTemplate3>
    </Body>
</_templates>
```

Its usage:

```xml
<Truck>
    <PhysicsModel Mesh="trucks/example_truck">
        <Body _template="MyTemplate3">
        </Body>
    </PhysicsModel>
    ...
<Truck>
```

The same piece of XML without the template will look like the following:

```xml
<Truck>
    <PhysicsModel Mesh="trucks/example_truck">
        <Body Mass="5">
            <Constraint Type="Hinge" MinLimit="-1" MaxLimit="1">
                <Motor Damping="0.3" Spring="25" Type="Spring" />
            </Constraint>
        </Body>
    </PhysicsModel>
    ...
<Truck>

```


