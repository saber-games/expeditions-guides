# Templates for Multiple Tags

Declaration of templates for multiple tags of different types looks like the following:

```xml
<_templates>
    <Wheel>
        <MyTemplate1 HardpointY="0.5" HardpointZ="0.5" />
    </Wheel>
    <Body>
        <MyTemplate2 Mass="1"/>
        <MyTemplate3 Mass="5"/>
    </Body>
</_templates>
```

Where `MyTemplate1` - is the template of `<Wheel>` tag, and `MyTemplate2`, `MyTemplate3` - are two different templates for the `<Body>` tag.

