---
description: FormDef 참조 (특정 StudyEventDef 내에서 해당 폼 사용한다는 뜻)
---

# FormRef



```xml
<StudyEventDef OID="SE.1" Name="Baseline (T0)" Repeating="No" Type="Common">
    <Description>
        <TranslatedText xml:lang="en">Baseline (T0)</TranslatedText>
        <TranslatedText xml:lang="de">Vorbefragung (T0)</TranslatedText>
    </Description>
    <FormRef FormOID="F.1" Mandatory="No"/>
    <FormRef FormOID="F.2" Mandatory="No"/>
</StudyEventDef>
<FormDef OID="F.1" Name="Basis data" Repeating="No">
    <Description>
        <TranslatedText xml:lang="en">Basis data</TranslatedText>
        <TranslatedText xml:lang="de">Basisdaten</TranslatedText>
    </Description>
    <ItemGroupRef ItemGroupOID="IG.1" Mandatory="No"/>
    <ItemGroupRef ItemGroupOID="IG.2" Mandatory="No"/>
</FormDef>
```

![Form 참조](<../../../../.gitbook/assets/화면 캡처 2022-06-29 210038.png>)



### BODY

**empty**



### ATTRIBUTE

| **FormOID**                         | [oidref](../../../dataformat.md)  |              | Reference to the FormDef.   |
| ----------------------------------- | --------------------------------- | ------------ | --------------------------- |
| **OrderNumber**                     | [integer](../../../dataformat.md) | _(optional)_ |                             |
| **Mandatory**                       | (Yes \| No)                       |              |                             |
| **CollectionExceptionConditionOID** | [oidref](../../../dataformat.md)  | _(optional)_ | Reference to a ConditionDef |



### CONTAINED IN

****[**StudyEventDef**](./)****



특정 StudyEventDef 내에서 발생하는 FormDef에 대한 참 양식 유형을 식별. 단일 StudyEventDef 내의 FormRef에는 중복 FormOID 또는 OrderNumber가 없어야 함

* `OrderNumbers` : 양식 목록이 사용자에게 표시될 때 사용할 양식의 순서 제공.
* ConditionDef 참조 : CollectionExceptionConditionOID 속성이 제공되면 이 Form에 대한 데이터가 수집되지 않아야 함을 설명

