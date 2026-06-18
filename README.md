# Bannerlord-Schemas

### How to Use?

I have defined the commonly used Bannerlord GauntletUI widget structures and definitions within the XSD.

The reason `Children` and `ItemTemplate` appear globally rather than strictly under specific widgets is to ensure that even for widgets not yet defined in the XSD, their child widgets can still inherit and apply the correct structure and definitions, even if the parent widget itself doesn't get attribute suggestions. Instead of defining every single widget globally, I compromised by setting only Children and ItemTemplate as global elements.

This is a workaround due to the limitations of `XSD 1.0`. While `XSD 1.1` could likely resolve this issue, I decided to stick with `XSD 1.0` to ensure broader compatibility across various development platforms and environments.

Prefab Example (https://echieve-works.github.io/Bannerlord-Schemas/GauntletUI/GauntletUI.xsd)
```xml
<Prefab xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://echieve-works.github.io/Bannerlord-Schemas/GauntletUI/GauntletUI.xsd">
    <Parameters>
        <Parameter Name="Width" DefaultValue="100" />
    </Parameters>
    <Constants>
        <Constant Name="Height" Value="100" />
    </Constants>
    <Window>
        <Widget WidgetSizePolicy="Fixed" HeightSizePolicy="Fixed" SuggestedWidth="*Width" SuggestedHeight="!Height">
            <Children>
                <TextWidget Text="Hello World!" WidthSizePolicy="StretchToParent" HeightSizePolicy="StretchToParent" />
            </Children>
        </Widget>
    </Window>
</Prefab>
```

Widget-Only Example (https://echieve-works.github.io/Bannerlord-Schemas/GauntletUI/GauntletUIWidgets.xsd)
```xml
<Widget xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://echieve-works.github.io/Bannerlord-Schemas/GauntletUI/GauntletUIWidgets.xsd"
        WidgetSizePolicy="Fixed" HeightSizePolicy="Fixed" SuggestedWidth="100" SuggestedHeight="100">
    <Children>
        <TextWidget Text="Hello World!" WidthSizePolicy="StretchToParent" HeightSizePolicy="StretchToParent" />
    </Children>
</Widget>
```