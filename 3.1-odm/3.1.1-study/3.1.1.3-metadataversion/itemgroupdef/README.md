---
description: >-
  Item Group 정의. (ItemGroupDefinition: Personal questions, Demographic
  questions, ... )
---

# ItemGroupDef



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

![Groups](<../../../../.gitbook/assets/createform (1).png>)

### BODY

([**Description**](../studyeventdef/description.md)?, [**ItemRef**](itemref.md)\*, **Alias**\*)



### ATTRIBUTE

|                     |                                   |              |              |
| ------------------- | --------------------------------- | ------------ | ------------ |
| **OID**             | [oid](../../../dataformat.md)     |              |              |
| **Name**            | [name](../../../dataformat.md)    |              |              |
| **Repeating**       | (Yes \| No)                       |              |              |
| **IsReferenceData** | (Yes \| No)                       | _(optional)_ |              |
| **SASDatasetName**  | [sasName](../../../dataformat.md) | _(optional)_ |              |
| **Domain**          | [text](../../../dataformat.md)    | _(optional)_ |              |
| **Origin**          | [text](../../../dataformat.md)    | _(optional)_ |              |
| **Role**            | [name](../../../dataformat.md)    | _(optional)_ | _Deprecated_ |
| **Purpose**         | [text](../../../dataformat.md)    | _(optional)_ |              |
| **Comment**         | [text](../../../dataformat.md)    | _(optional)_ |              |



### CONTAINED IN

**📁** [**MetaDataVersion**](../)****

****

ItemGroupDef는 연구 내에서 발생할 수 있는 item group 유형의 정의.

* `Repeating` : 이러한 유형의 item group이 포함하는 양식(또는 참조 데이터) 내에서 반복적으로 발생할 수 있음을 나타냄.
* `IsReferenceData`가 Yes인 경우 이 유형의 item group은 ReferenceData 요소 내에서만 발생할 수 있음. No이면 ClinicalData 요소 내에서만 발생할 수 있음. 기본값은 No 임.
  * ex) 피를 뽑아 헤모글로빈 정상 수치 참조 -> 말 그대로 이런 reference 임
  * lab normal range : 실험 데이터의 정상 범
* `Domain`, `Origin`, `Purpose`, `Comment` 속성들은 SDTM 메타데이터 제출 지침에 있는 CDISC 제출 메타데이터 모델의 규칙에 따라 제출 정보를 전달.&#x20;

{% hint style="info" %}
참고: `Role` 속성은 `Purpose`의 동의어로 간주될 수 있음. 새로운 애플리케이션은 `Role`이 아닌 `Purpose`을 사용해야 함.
{% endhint %}



