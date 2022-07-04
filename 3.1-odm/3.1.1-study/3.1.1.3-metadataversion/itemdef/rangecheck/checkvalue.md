---
description: RangeCheck에 사용되는 비교값
---

# CheckValue

```xml
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

CheckValue가 속한 ItemDef에 선언된 값의 type과 동일해야 한다.



### BODY

**value**



### ATTRIBUTE

none



### CONTAINED IN

[**RangeCheck**](./)****

****
