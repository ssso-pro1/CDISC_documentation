---
description: Item Group 참조.
---

# ItemGroupRef



```xml
<ItemGroupDef OID="IG.1" Name="PersonalItems" Repeating="No">
    <Description>
        <TranslatedText xml:lang="en">Personal questions</TranslatedText>
        <TranslatedText xml:lang="de">Persönliche Fragen</TranslatedText>
    </Description>
    <ItemRef ItemOID="Age" Mandatory="No"/>
    <ItemRef ItemOID="Gender" Mandatory="No"/>
    <ItemRef ItemOID="Weight" Mandatory="No"/>
    <ItemRef ItemOID="Height" Mandatory="No"/>
    <ItemRef ItemOID="BMI" Mandatory="No" MethodOID="M.1"/>
    <ItemRef ItemOID="Pregnant" Mandatory="No" CollectionExceptionConditionOID="C.2"/>
    <ItemRef ItemOID="WeeksPregnant" Mandatory="No" CollectionExceptionConditionOID="C.5"/>
</ItemGroupDef>
```

![Groups 참조](<../../../../.gitbook/assets/createform (2).png>)

### BODY

([**Description**](../studyeventdef/description.md)?, [**ItemRef**](../itemgroupdef/itemref.md)\*, **Alias**\*)



### ATTRIBUTE

| **ItemGroupOID**                    | [oidref](../../../datatype.md)  |              | Reference to the ItemGroupDef. |
| ----------------------------------- | ------------------------------- | ------------ | ------------------------------ |
| **OrderNumber**                     | [integer](../../../datatype.md) | _(optional)_ |                                |
| **Mandatory**                       | (Yes \| No)                     |              |                                |
| **CollectionExceptionConditionOID** | [oidref](../../../datatype.md)  | _(optional)_ | Reference to a ConditionDef    |

### CONTAINED IN

****[**FormDef**](./)****



ItemGroupDef는 연구 내에서 발생할 수 있는 item group 유형을 설명.

* `Repeating` : 이러한 유형의 item group이 포함하는 양식(또는 참조 데이터) 내에서 반복적으로 발생할 수 있음을 나타냄.
* `IsReferenceData`가 Yes인 경우 이 유형의 아이템 그룹은 ReferenceData 요소 내에서만 발생할 수 있음. No이면 ClinicalData 요소 내에서만 발생할 수 있음. 기본값은 No 임. -> ReferenceData, ClinicalData?????
* `Domain`, `Origin`, `Purpose`, `Comment` 속성들은 SDTM 메타데이터 제출 지침에 있는 CDISC 제출 메타데이터 모델에 설명된 대로 제출 정보를 전달. -> ?

{% hint style="info" %}
참고: `Role` 속성은 `Purpose`의 동의어로 간주될 수 있음. 새로운 애플리케이션은 `Role`이 아닌 `Purpose`을 사용해야 함.
{% endhint %}

