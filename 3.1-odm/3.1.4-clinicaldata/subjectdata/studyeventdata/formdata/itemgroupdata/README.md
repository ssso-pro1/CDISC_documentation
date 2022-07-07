---
description: 아이템 그룹(기록)에 대한 임상 데이터.
---

# ItemGroupData

Clinical data for an item group (record). The model supports repeating item groups in a single form (for example, when several previous hospitalizations are reported in one history), or within reference data.

아이템 그룹(기록)에 대한 임상 데이터입니다. 이 모델은 **하나의 폼에서 아이템 그룹이 반복** (예: 하나의 기록에 여러 이전 입원 기록) 또는 참조 데이터 내에서 반복 아이 그룹을 지원합니다.

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

****

**Body:**\
****(AuditRecord?, Signature?, Annotation\*, (ItemData\* | ItemData\[TYPE]\*))



**Attributes:**

| **ItemGroupOID**       | oidref                                            |              | Reference to the ItemGroupDef.                                                                 |
| ---------------------- | ------------------------------------------------- | ------------ | ---------------------------------------------------------------------------------------------- |
| **ItemGroupRepeatKey** | repeatKey                                         | _(optional)_ | A key used to distinguish between repeats of the same type of item group within a single form. |
| **TransactionType**    | (Insert \| Update \| Remove \| Upsert \| Context) | _(optional)_ | The TransactionType attribute need not be present in a Snapshot document.                      |

*   The `ItemGroupOID` and `ItemGroupRepeatKey` are used together to identify a particular item group. This pair of values uniquely identifies an ItemGroup within the containing Form. The ItemGroupRepeatKey is present if and only if the ItemGroupDef is repeating.

    ItemGroupData can also occur as reference data. In that case, the ItemGroupOID and ItemGroupRepeatKey pair must be unique within the reference data.\
    \
    `ItemGroupOID` 및 `ItemGroupRepeatKey`는 특정 ItemGroup을 식별하기 위해 함께 사용됩니다. 이 값 쌍은 포함하는 Form 내에서 ItemGroup을 고유하게 식별합니다. ItemGroupDef가 반복되는 경우에만 ItemGroupRepeatKey가 존재합니다. \
    ItemGroupData는 참조 데이터로도 발생할 수 있습니다. 이 경우 ItemGroupOID 및 ItemGroupRepeatKey 쌍은 참조 데이터 내에서 고유해야 합니다.



**Contained in:**

FormData, ReferenceData

\








