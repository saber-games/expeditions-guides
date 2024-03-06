# Main Principles

Main principles of describing trucks and their components in XML files are the following:

-   The names of tags, attributes, and values are case-sensitive.

-   All values of attributes, including numeric values, must be in quotation marks.

-   XML has a hierarchy of tags. Any tag has its own place in the general hierarchy and must not violate it.

-   Each opened tag must be closed.

    -   If a tag is located on the lowest level of hierarchy and, correspondingly, has no children tags, it is written in the form similar to:

        ```xml
        <TagName Attr1="a" Attr2="b" />
        ```

    -   If a tag has children tags, it is written in the form similar to:

        ```xml
        <TagName Attr1="a" Attr2="b">
            Children Tags
        </TagName>
        ```

-   The order of tags that are located on the same level in hierarchy is *typically* not important. However, there are exceptions from this rule that are described separately.

-   Each tag has its own particular set of *attributes*. Any attribute of a tag can be either mandatory or optional.

-   Tags with the same name, but with different parent tags, have different purposes.

-   You can use common and local [templates][templates] (`_templates`) in the XML file.

-   An XML file can be [inherited][inheritance] from another XML file (`_parent`) that is located in the same folder.

**TIP 1**: *Most* of popular tags and their attributes are described in the [Tags and Attributes of Trucks][tags_and_attributes_of_trucks].

**TIP 2**: The hierachy of sections and topics within [Tags and Attributes of Trucks][tags_and_attributes_of_trucks] corresponds to the hierarchy of these tags.

[templates]: ./templates/templates.md
[inheritance]: ./inheritance.md
[tags_and_attributes_of_trucks]: ./../../tags_and_attributes_of_trucks/index.md