# Inheritance

Using the `<_parent>` tag, an XML file can be inherited from another XML file.

Working with inheritance is similar to working with templates. I.e., you can change, add, or remove any tags, attributes, and values of the parent XML file. To access a specific tag, you must recreate the hierarchy of its parent tags.

For example, let's assume that we havе the following sample files: `/classes/trucks/example_parentfile.xml` and `/classes/trucks/example_truck.xml`

*`example_parentfile.xml`*:

```xml
<Truck>
    <PhysicsModel Mesh="trucks/example_parentfile">
        <Body Mass="10">
            <Body Mass="1">
                <Constraint Type="Fixed" />
            </Body>
            <Body Mass="2">
                <Constraint Type="Prismatic" />
            </Body>
        </Body>
    </PhysicsModel>
    ...
</Truck>
```

*`example_truck.xml`*:

```xml
<_parent File="example_parentfile" />
<Truck>
    <PhysicsModel Mesh="trucks/example_truck"/>
</Truck>
```

In this example, the contents of the *`example_truck.xml`* are equivalent to the following:

```xml
<Truck>
    <PhysicsModel Mesh="trucks/example_truck">
        <Body Mass="10">
            <Body Mass="1">
                <Constraint Type="Fixed" />
            </Body>
            <Body Mass="2">
                <Constraint Type="Prismatic" />
            </Body>
        </Body>
    </PhysicsModel>
    ...
</Truck>
```

