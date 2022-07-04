---
description: 측정 단위 정의의 대한 참조.
---

# MeasurementUnitRef



```xml
<MeasurementUnit OID="MU.4" Name="years">
    <Symbol>
        <TranslatedText xml:lang="en">years</TranslatedText>
        <TranslatedText xml:lang="de">Jahre</TranslatedText>
    </Symbol>
</MeasurementUnit>

<ItemDef OID="Age" Name="Age" DataType="integer">
    <Question>
        <TranslatedText xml:lang="en">What is your age?</TranslatedText>
        <TranslatedText xml:lang="de">Wie alt sind Sie?</TranslatedText>
    </Question>
    <MeasurementUnitRef MeasurementUnitOID="MU.4"/>
    <RangeCheck Comparator="GE" SoftHard="Hard">
        <CheckValue>18</CheckValue>
    </RangeCheck>
    <RangeCheck Comparator="LT" SoftHard="Hard">
        <CheckValue>120</CheckValue>
    </RangeCheck>
</ItemDef>

```

### BODY

**empty**



### ATTRIBUTE

| <p><br><strong>MeasurementUnitOID</strong></p> | oidref |   | Reference to the MeasurementUnit definition. |
| ---------------------------------------------- | ------ | - | -------------------------------------------- |



### CONTAINED IN

**ItemData**, [**ItemDef**](./), [**RangeCheck**](rangecheck/)****

****

