---
description: >-
  Item 유형 정의. (Item Definition: Item 속성에는 이름, 데이터 유형, 측정 단위, 범위 또는 codelist 제한
  사항 및 기타 여러 속성이 포함.)
---

# ItemDef



```xml
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

![Items](<../../../../.gitbook/assets/createform (3).png>)



### BODY

([**Description**](../studyeventdef/description.md)?, **Question**?, **ExternalQuestion**?, [**MeasurementUnitRef**](measurementunitref.md)\*, [**RangeCheck**](rangecheck/)\*, [**CodeListRef**](codelistref.md)?, **Role\* **_**Deprecated**_, [**Alias**](alias.md)\*)

* `Question` 요소에는 종이나 화면에 item 데이터를 보여줘야할 때 사용자에게 표시되는 텍스트가 포함됨. ExternalQuestion 요소는 동일한 작업을 수행하지만 외부에서 정의된 질문을 참조함. 둘 다 있는 경우 일관성이 있어야 함.
* `MeasurementUnitRefs`는 이 유형의 item의 측정 단위이며, 숫자 항목만 측정 단위를 가질 수 있음. MeasurementUnitRef가 하나만 있는 경우 이 유형의 모든 항목은 기본적으로 이 측정 단위를 사용함.



### ATTRIBUTE

| **OID**               | [oid](../../../dataformat.md)                                                                                                                                                                                                                                                                                                                                |              |   |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------ | - |
| **Name**              | [name](../../../dataformat.md)                                                                                                                                                                                                                                                                                                                               |              |   |
| **DataType**          | [(text \| integer \| float \| date \| time \| datetime](../../../dataformat.md) [\| string \| boolean \| double \| hexBinary \| base64Binary \| hexFloat \| base64Float \| partialDate \| partialTime \| partialDatetime \| durationDatetime \| intervalDatetime \| incompleteDatetime \| incompleteDate \| incompleteTime \| URI )](../../../dataformat.md) |              |   |
| **Length**            | [positiveInteger](../../../dataformat.md) (양의 정수)                                                                                                                                                                                                                                                                                                            | _(optional)_ |   |
| **SignificantDigits** | [nonNegativeInteger](../../../dataformat.md) (음수 아닌 정수?)                                                                                                                                                                                                                                                                                                     | _(optional)_ |   |
| **SASFieldName**      | [sasName](../../../dataformat.md)                                                                                                                                                                                                                                                                                                                            | _(optional)_ |   |
| **SDSVarName**        | [sasName](../../../dataformat.md)                                                                                                                                                                                                                                                                                                                            | _(optional)_ |   |
| **Origin**            | [text](../../../dataformat.md)                                                                                                                                                                                                                                                                                                                               | _(optional)_ |   |
| **Comment**           | [text](../../../dataformat.md)                                                                                                                                                                                                                                                                                                                               | _(optional)_ |   |



### CONTAINED IN

**📁** [**MetaDataVersion**](../)****

****

ItemDef는 연구 내에서 발생할 수 있는 item 유형을 정. Item 속성에는 이름, 데이터 유형, 측정 단위, 범위 또는 codelist 제한 사항 및 기타 여러 속성이 포함.

\-> 즉, ItemDef는 item의 이러한 기타 여러 속성을 정의한 것.

* `DataType` 속성은 해당 값 요소의 데이터 타입 지정.&#x20;
* `Length`속성은 DataType이 text 또는 string일 때 필수이고, integer 또는 float일 때 선택 사항이며, 다른 데이터 유형에는 제공해서는 안 됨.
* `DataType`이 float인 경우 `SignificantDigits` 속성은 선택 사항이며 다른 데이터 유형에 대해서는 제공하면 안 됨 . 또한 `DataType`이 float인 경우 `Length`와 `SignificantDigits`가 모두 제공되거나 둘 다 없어야 함.

{% hint style="info" %}
참고: 버전 1.3.0에서 Length 및 SignificantDigits의 사용법이 모호했으나, 위의 설명에서 이 두 속성의 의도를 명확히 함.
{% endhint %}



* DataType=integer인 경우 Length=N은 수신 시스템이 10N보다 작은 크기의 모든 정수 값을 처리하고 저장할 수 있어야 하는 요구 사항입니다. 더 큰 값은 거부될 수 있습니다.
* DataType=float, Length=N 및 SignificantDigits=S인 경우 수신 시스템이 10-S의 배수인 10N-S 미만의 모든 숫자 값을 처리하고 저장할 수 있어야 합니다. 더 큰 값은 거부될 수 있습니다. 중간 값은 10-S의 가장 가까운 배수로 반올림될 수 있습니다.
* DataType=text인 경우 Length=N은 수신 시스템이 N보다 작거나 같은 길이의 모든 텍스트 문자열 값을 처리하고 저장할 수 있어야 한다는 요구 사항입니다. 모든 문자는 텍스트 문자열 값에 허용됩니다. Text 유형의 데이터는 ItemDataString 요소에서 전송되어야 합니다.&#x20;

{% hint style="info" %}
참고: Length 및 SignificantDigits는 사용되는 문자 수가 아니라 항목의 데이터 값에 대한 설명. 예를 들어 "\&lt" 부등는 "<"로 표시될 수 있음.
{% endhint %}

{% hint style="info" %}
참고: 특정 ODM 파일에 대한 인코딩 문자 집합에 포함되지 않은 데이터 문자는 XML 엔터티 또는 문자 참조를 사용하여 표현해야 함. 예를 들어 "\&#198"는 "Æ"로 나타낼 수 있음.
{% endhint %}



* `SDSVarName`, `Origin` 및 `Comment` 속성은 최신 버전의 CDISC SDTM에 설명된 대로 제출 정보를 전달.

{% hint style="info" %}
참고: ODM 모델에서 모든 internal keys는 변경할 수 없는 것으로 간주한. 이것은 감사 추적 문제가 작동하도록 하기 위해 수행된다: 모델의 SubjectKey가 환자의 실제 external subject identifier (또는 무작위 ID)이고 해당 값이 하나의 ODM 파일에서 잘못 전송된 경우 수정할 방법이 없다.\
이를 수행할 때 external subject key (및 기타 외부에서 볼 수 있는 키 변수)가 메타데이터의 Items으로 정의되어야 한다. 따라서 정상적인 수정/감사 메커니즘을 통해 수정할 수 있다. \
\
이것은 study 키의 수정을 지원하는 문제를 해결하지만, 사용자는 특정 ItemDefs의 의미를 식별할 방법이 없다. 이것이 문제가 되는 가장 명백한 위치는 외부 소스에서 데이터를 로드할 때 환자를 일치시키는 것이다. 환자 ID를 찾을 수 없으면 어떻게 하나?

\
정답은 ItemDef의 `SDSVarName`속성을 사용하는 것이다. SDSVarName은 비즈니스 의미로 Items에 태그를 지정하는 데 사용할 수 있는 선택적 속성이다. ODM 모델에서 가능한 모든 의미를 열거하려고 하기보다 CDISC SDTM에 정의된 변수 이름 집합에 의존하는 것이 가장 좋다. 이 목록은 임상 데이터 관리에 사용되는 핵심 변수를 포함하기 때문이다. \
따라서 ODM 호환 XML 인스턴스를 처리하는 소프트웨어는 SDSVarName 속성의 특정 값을 사용하여 자주 사용되는 표준 변수를 식별할 수 있다. 이 속성의 사용은 SDTM 모델에 정의된 변수로 제한된다. 변수에 태그를 지정할 때 해당 변수에 대한 SDTM 정의와 일치하는 것으로 식별한다. 일반적으로 사용되는 값의 일부 목록은 다음과 같다.\
\
\- STUDYID(제출 내에서 고유한 연구 식별자)&#x20;

USUBJID(제출 내에서 고유한 연구 식별자),&#x20;

SUBJID(연구 내에서 고유한 주제 식별자),

SITEID(연구 사이트의 고유 식별자)&#x20;

SEX(성별 또는 성별, 코드화된 값),&#x20;

VISITNUM(임상 만남 번호)&#x20;

VISIT(임상 만남에 대한 프로토콜 정의 설명),&#x20;

VISITDY (VISIT의 예정된 학습일)&#x20;

SDTM 변수에 대한 자세한 내용은 SDTM 사양 및 구현 가이드를 참조.\
\
\
\
\-> 즉, internal keys는 변경불가 추적 및 수정하기 어려워, 이를 위해 items에 external subject key가 정의되어야 한다. 이를 이용하여 study키의 수정이 가능하다. \
하지만 사용자가 특정 ItemDefs의 의미를 식별할 수 없다는 문제가 있는데, 이 때에 ItemDef의 SDSVarName 속성을 사용한다. &#x20;
{% endhint %}



> SASVarName : SAS는 임상에서 데이터 분석 처리할 때 사용하는 프로그램 이름. 여기서 사용하 변수명이다. (규칙: 8글자 내)\
> \
> SDSVarName: CDASH -> 제출 시 1:1로 맵핑할 때 쓰는 변수명이다. \
> (SASVarName이 8글자 넘어간다면 이거 대신 alias를 사용한다.)\
> \
> SDS: Submission Data Standards

