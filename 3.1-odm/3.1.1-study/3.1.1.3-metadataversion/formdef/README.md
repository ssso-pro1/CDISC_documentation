---
description: 'Form 정의 (FormDefinition: Basis data, Medical history, ...)'
---

# FormDef



```xml
<FormDef OID="F.1" Name="Basis data" Repeating="No">
    <Description>
        <TranslatedText xml:lang="en">Basis data</TranslatedText>
        <TranslatedText xml:lang="de">Basisdaten</TranslatedText>
    </Description>
    <ItemGroupRef ItemGroupOID="IG.1" Mandatory="No"/>
    <ItemGroupRef ItemGroupOID="IG.2" Mandatory="No"/>
</FormDef>
<FormDef OID="F.2" Name="Medical history" Repeating="No">
    <Description>
        <TranslatedText xml:lang="en">Medical history</TranslatedText>
        <TranslatedText xml:lang="de">Vorerkrankungen</TranslatedText>
    </Description>
    <ItemGroupRef ItemGroupOID="IG.3" Mandatory="No"/>
    <ItemGroupRef ItemGroupOID="IG.4" Mandatory="No"/>
</FormDef>
```

![Form](<../../../../.gitbook/assets/화면 캡처 2022-06-29 210038.png>)



### BODY

(**Description**?, **ItemGroupRef**\*, **ArchiveLayout**\*, **Alias**\*)

* ArchiveLayout : 폼에서 데이터를 수집할때 사용하는 화면의 레이아웃 사진. Study를 저장할때 유용. 예를 들어 중증도를 수치화 할때 각 조건들을 표로 정리하여 이미지로 저장해 놓는 것.
* Alias : 별칭



### ATTRIBUTE

| **OID**       | [oid](../../../datatype.md)  |   |   |
| ------------- | ---------------------------- | - | - |
| **Name**      | [name](../../../datatype.md) |   |   |
| **Repeating** | (Yes \| No)                  |   |   |



### CONTAINED IN

**📁** [**MetaDataVersion**](../)****

****

FormDef는 스터디에서 발생하는 form의 유형을 의미.

