# Templates

A template is a piece of XML code that can be reused. Both a single tag with predefined parameters and the whole hierarchy of tags can be used as a template.

The `<_templates>` tag has only one attribute – `Include`.

This attribute enables the current XML file to use templates from the following folder: `/_templates/`.
The value of the `Include` attribute is the name of the particular template from this folder that you want to use.

For example: `<_templates Include="trucks">`

The `/_templates/trucks.xml` file contains common templates for trucks, addons, and trailers.

Templates can be either included from the external files using `Include` or described as children of the `<_templates>` tag directly inside the XML that we work with.

Any existing tags can be used as children of the `<_templates>` tag.

```xml
<_templates Include="trucks">
    <WheelRepairsHide>
        <TemplateName1 />
    </WheelRepairsHide>
    <RepairsHide>
        <TemplateName2 />
    </RepairsHide>
    <FuelHide>
        <TemplateName3 />
        <TemplateName4 />
    </FuelHide>
    ...
</_templates>
```

**TIP**: Templates that are used by XML classes of the original game can be found in the [`initial.pak`][initial_pak], in its `\[media]\_template` subfolder.

[initial_pak]: ./../../../../map_modding/getting_started/file_paths_and_naming/file_paths.md#source-of-info-initialpak-archive