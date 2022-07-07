---
description: Item에 대한 임상 데이터이다.
---

# 📌 ItemData

The ItemData element may be used for un-typed transmission of the clinical data for an item. The model does _not_ support repeating items within a single item group.

ItemData 요소는 item에 대한 <mark style="background-color:red;">임상 데이터의 형식화되지 않은 전송</mark>에 사용될 수 있습니다. 이 모델은 하나의 item group 내에서 반복되는 item을 지원하지 않습니다.



**Example:**

```xml
<ItemGroupData ItemGroupOID="IG.3">
    <ItemData ItemOID="I.3" Value="1995-07-01"/>
    <ItemData ItemOID="I.4" Value="27"/>
    <ItemData ItemOID="I.5" Value="2"/>
    <ItemData ItemOID="HEIGHT" Value="180"/>
    <ItemData ItemOID="WEIGHT" Value="70"/>
    <ItemData ItemOID="I.8" Value="21.6"/>
</ItemGroupData>
```



**Body:**\
****(AuditRecord?, Signature?, MeasurementUnitRef?, Annotation\* )



**Attributes:**

| **ItemOID**         | oidref                                            |              | Reference to the ItemDef.                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------- | ------------------------------------------------- | ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **TransactionType** | (Insert \| Update \| Remove \| Upsert \| Context) | _(optional)_ | The TransactionType attribute need not be present in a Snapshot document.                                                                                                                                                                                                                                                                                                                            |
| **Value**           | text                                              | _(optional)_ | The data collected for an item. This data is represented according to DataType attribute of the ItemDef.                                                                                                                                                                                                                                                                                             |
| **IsNull**          | (Yes)                                             | _(optional)_ | IsNull is a flag to signify that an item's value is to be set to null. If the Value attribute is set, IsNull must not be set. If IsNull is set, the Value attribute must not be provided. In the interest of creating non-verbose XML instances, one should not use ItemData elements with IsNull set to "Yes" to indicate uncollected data. The better practice is to transmit only collected data. |

* The `ItemOID` is used to identify a particular item definition. This value uniquely identifies an Item within the containing ItemGroup.
*   The referenced ItemDef defines the DataType of this item. The Value attribute string must obey the rules for that format of data listed in the Data Formats section. For text, string, integer or float datatypes, it must be possible to store the item value within the Length constraint defined in the ItemDef.

    Typed and untyped data must not both be used within a single ODM file.\

* `ItemOID`는 특정 item을 식별하는 데 사용됩니다. 이 값을 포함하는 ItemGroup 내에서 Item을 고유하게 식별합니다.&#x20;
* 참조된 `ItemDef`는 이 항목의 DataType을 정의합니다. 값 속성 문자열은 데이터 형식 섹션에 나열된 데이터 형식에 대한 규칙을 따라야 합니다. 텍스트, 문자열, 정수 또는 부동 소수점 데이터 유형의 경우 ItemDef에 정의된 길이 제약 조건 내에서 항목 값을 저장할 수 있어야 합니다. 유형이 지정된 데이터와 유형이 지정되지 않은 데이터를 모두 단일 ODM 파일 내에서 사용해서는 안 됩니다.



**Contained in:**

ItemGroupData\








