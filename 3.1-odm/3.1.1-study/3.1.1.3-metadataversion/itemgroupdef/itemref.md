---
description: ItemGroupDef 내의 ItemDef 참조. Item 유형을 식별.
---

# ItemRef

```xml
// ItemRef
<ItemGroupDef OID="INCLUSION" Name="Inclusion Criteria" >
   ...
   <ItemRef ItemOID="IDef.GENDER" Mandatory="Yes"/>
   <ItemRef ItemOID="IDef.ISPREG" Mandatory="Yes" CollectionExceptionConditionOID="CECID.ISMALE"/>
</ItemGroupDef>

<ConditionDef OID="CECID.ISMALE">
  <TranslatedText xml:lang="en">Do not collect data for Male subjects </TranslatedText>
      <FormalExpression context="PL/SQL">
	 INCLUSION.IDef.GENDER = 'Male'
      </FormalExpression>
</ConditionDef>
```

```xml
// ItemDef
<ItemDef OID="Weight" Name="Weight" DataType="float">
    <Question>
        <TranslatedText xml:lang="en">What is your weight?</TranslatedText>
        <TranslatedText xml:lang="de">Wie viel wiegen Sie?</TranslatedText>
    </Question>
    <MeasurementUnitRef MeasurementUnitOID="MU.1"/>
    <RangeCheck Comparator="GE" SoftHard="Hard">
        <CheckValue>40</CheckValue>
    </RangeCheck>
    <RangeCheck Comparator="LE" SoftHard="Hard">
        <CheckValue>160</CheckValue>
    </RangeCheck>
</ItemDef>
```

![Items 참조](<../../../../.gitbook/assets/createform (1) (1).png>)



### BODY

**empty**



### ATTRIBUTE

| **ItemOID**                         | [oidref](../../../dataformat.md)           |              | Reference to the ItemDef.   |
| ----------------------------------- | ------------------------------------------ | ------------ | --------------------------- |
| **OrderNumber**                     | [integer](../../../dataformat.md)          | _(optional)_ |                             |
| **Mandatory**                       | (Yes \| No)                                |              |                             |
| **KeySequence**                     | [integer](../../../dataformat.md)          | _(optional)_ |                             |
| **MethodOID**                       | [oidref](../../../dataformat.md)           | _(optional)_ |                             |
| **ImputationMethodOID**             | __[_Deprecated_](../../../dataformat.md)__ |              |                             |
| **Role**                            | [text](../../../dataformat.md)             | _(optional)_ |                             |
| **RoleCodeListOID**                 | [oidref](../../../dataformat.md)           | _(optional)_ |                             |
| **CollectionExceptionConditionOID** | [oidref](../../../dataformat.md)           | _(optional)_ | Reference to a ConditionDef |



### CONTAINED IN

****[**ItemGroupDef**](./)



특정 ItemGroupDef 내에서 발생하는 ItemDef에 대한 참조.&#x20;

* 단일 ItemGroupDef 내의 ItemRef에는 중복된 `ItemOID` 또는 `OrderNumber`가 없어야 함. `OrderNumbers`는 사용자에게 제공 시 사용할 Items (Item Group 내)에 대한 순서를 제공.&#x20;
* `Mandatory`는 포함하는 아이템 그룹의 인스턴스에 대한 임상 데이터가 이러한 유형의 아이템 인스턴스 없이는 불완전할 것임을 나타냄. 즉, Yes 이면 반드시 있어야하는 항목임을 나타냄.
* `KeySequence`(있는 경우)는 이 item이 포함하는 item group의 키임을 나타냄. 또한 키에 대한 순서를 제공.&#x20;
* `MethodOID`는 이 item의 값을 파생하는 데 사용되는 **** [**MethodDef**](../methoddef.md)를 참조.
* `Role`은 이 데이터 item의 역할을 설명하는 름을 제공.\
  `Role`이 표준 용어로 정의되면 `RoleCodeListOID`를 사용하여 Role 속성 값을 가져오는 전체 세트 역할을 정의하는 [**CodeList** ](../codelist/)를  참조할 수 있음. \
  `Role` 속성이 정의X : 이 속성 존재X, 정의O:  RoleCodeListOID는 여전히 선택 사항임.
* `CollectionExceptionConditionOID`가 제공되면 아이템 컬렉션이 생략될 수 있는 상황(예: FormalExpression이 True로 평가되는 경우)을 정의하는 [**ConditionDef**](../conditiondef/) 를 참조함. \
  예를 들어, 항목 그룹 'InclusionCriteria'에 대한 항목 'IsPregnant'에 대한 데이터를 수집할 때, 남성 피험자에 대해 생략 가능. \
  참조된 ConditionDef는 위의 예시 같이 정의. FormalExpression이 True로 평가되면 OID가 IG.ISPREG인 항목을 수집할 필요가 없음.

