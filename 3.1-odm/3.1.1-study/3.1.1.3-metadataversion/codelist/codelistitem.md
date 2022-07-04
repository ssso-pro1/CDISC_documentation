---
description: 데이터 형식을 포함하여 codelist의 개별 구성원 값을 정의
---

# CodeListItem



```xml
<CodeList OID="CL.1" Name="CL.1" DataType="text">
    <CodeListItem CodedValue="Female">
        <Decode>
            <TranslatedText xml:lang="en">Female</TranslatedText>
            <TranslatedText xml:lang="de">Weiblich</TranslatedText>
        </Decode>
    </CodeListItem>
    <CodeListItem CodedValue="Male">
        <Decode>
            <TranslatedText xml:lang="en">Male</TranslatedText>
            <TranslatedText xml:lang="de">Männlich</TranslatedText>
        </Decode>
    </CodeListItem>
</CodeList>
```



### BODY

(**Decode**, [**Alias**](../itemdef/alias.md)\*)



### ATTRIBUTE

| **CodedValue**  | [text](../../../dataformat.md)    | Value of the codelist item (as it would occur in clinical data). |                                                                                                                                                                                                                       |
| --------------- | --------------------------------- | ---------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Rank**        | [float](../../../dataformat.md)   | _(optional)_                                                     | <p>Numeric significance of the CodeListItem relative to others in the CodeList.<br>Rank is optional, but if given for any CodeListItems in a CodeList it must be given for all.</p>                                   |
| **OrderNumber** | [integer](../../../dataformat.md) | _(optional)_                                                     | Ordering on the Items (within a containing CodeListItem) for use whenever a list of Items is presented to a user. OrderNumber is optional, but if given for any CodeListItems in a CodeList it must be given for all. |



### CONTAINED IN

****[**CodeList**](./)****

****

Defines an individual member value of a codelist including display format. The actual value is given, along with a set of print/display-forms. The CodedValue must be an acceptable value of the DataType of the containing CodeList.

데이터 형식을 포함하여 codelist의 개별 구성원 값을 정의합니다. 실제 값이 인쇄/표시 형식 세트와 함께 제공됩니다. CodedValue의 데이터 형식은 상위 CodeList의 DataType과 일치해야 한다.&#x20;



The CodeListItems within a single CodeList must not have duplicate CodedValues (as interpreted by the CodeList's DataType).

단일 CodeList 내의 CodeListItems에는 중복 CodedValues가 없어야 한다.(CodeValues: CodeList의 DataType에 의해 해석된 값).



The Rank attribute may be used where the relative value corresponding to an enumeration cannot or should not be determined by its lexical order. For example, if you have a list of enumerated text values including "Low", "Medium", and "High" and wish to assign these relative numeric values 1, 2, and 3 respectively, you should include a Rank attribute for each CodeListItem defined. Without the applied rank attribute, the normal lexical ordering would be "High", "Low", and "Medium".

Rank 속성은 열거되는 CodeListItem 들이 어휘 순서에 의해 결정될 수 없거나 결정되어서는 안 되는 경우에 사용될 수 있다. 예를 들어 "Low", "Medium" 및 "High"을 포함하는 열거된 텍스트 값 목록이 있고 이러한 상대 숫자 값 1, 2 및 3을 각각 할당하려는 경우 각 CodeListItem에 대한 Rank 속성을 포함해야 한다. 적용된 순위 속성이 없으면 일반적인 어휘 순서는 "High(1)", "Low(2)" 및 "Medium(3)"로 할당된다.

\-> 이러한 문제를 해결하기 위해 각 값들에 Rank 속성을 포함해준다.



The OrderNumbers provide an ordering on the CodeListItems (within a containing CodeList) for use whenever a list of CodeList Items is presented to a user. They do not imply anything about event scheduling, time ordering, or data correctness.

The CodeListItems within a single CodeList must not have duplicate Ranks or OrderNumbers.

OrderNumbers는 CodeList 항목 목록이 사용자에게 표시될 때마다 사용할 CodeListItems(포함하는 CodeList 내)에 대한 순서를 제공한다. 이벤트 일정, 시간 순서 또는 데이터 정확성에 대해서는 아무 것도 제공하지 않는다. 단일 CodeList 내의 CodeListItems에는 중복된 Rank 또는 OrderNumbers가 없어야 한다.



