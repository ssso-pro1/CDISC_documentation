---
description: 항목의 범위 값에 대한 제약 조건을 정의한다.
---

# RangeCheck

* Itemdata 값이 유효하면 True, 잘못된 경우 False로 평가되는 식을 나타낸다.
* 식은 비교연산자(Comparator)와 CheckValue를 사용하거나 FormalExpression을 사용하여 지정한다.



### **📌** 비교연산자나 CheckValue를 사용한 RangeCheck

* 비교연산자나 CheckValue를 사용한 RangeCheck는 치우친(한쪽으로) 제약 조건을 나타낸다.
*   여러 RangeCheck를 사용하여 복잡한 제약조건을 지정할 수 있다.

    ex) 이상, 이하를 사용하려면 두 개의 RangeCheck가 필요하다.
*   제약조건

    * 실제 데이터 값이 제약 조건을 충족하지 못하면 거부(Hard조건)되거나, 경고(Soft조건)가 생긴다.



    **✅ 비교 연산자**

    |  기호 |   설명  |
    | :-: | :---: |
    |  LT |   미만  |
    |  LE |   이하  |
    |  GT |   초과  |
    |  GE |   이상  |
    |  EQ |   동일  |
    |  NE | 같지 않음 |

    **✅ CheckValue**

    |   기호  |        설명       |
    | :---: | :-------------: |
    |   IN  |     목록 중 하나만    |
    | NOTIN | 목록 값에 존재하지 않는다. |

    * 측정 단위가 지정된 경우, 해당 항목 값에는 바꿀 수 있는 측정 단위가 기본적으로 있어야 한다. RangeCheck의 일부로 단위를 올바르게 바꿔야한다.
    * 측정 단위가 정해져 있지 않을 때, 해당 항목 값은 측정단위가 기본적으로 없어야한다.


*   #### 📃 예제

    * value > 0

    ```
    ## GT : 초과 
    <RangeCheck Comparator="GT" >
        <CheckValue>0</CheckValue>
    </RangeCheck>
    ```

    * 18 <= value <= 65

    ```
    ## GE : 이상 , LE : 이하
    <RangeCheck Comparator="GE" >
        <CheckValue>18</CheckValue>
    </RangeCheck>
    <RangeCheck Comparator="LE" >
        <CheckValue>65</CheckValue>
    </RangeCheck>
    ```

    * 1,5,7 중 하나일 때

    ```
    <RangeCheck Comparator="IN" >
        <CheckValue>1</CheckValue>
        <CheckValue>5</CheckValue>
        <CheckValue>7</CheckValue>
    </RangeCheck>
    ```

****

### **📌** FormalExpression을 사용한 RangeCheck

* FormalExpression을 사용하면 모든 범위를 나타낼 수 있다.
* FormalExpression 자체로 RangeCheck를 표현할 수 있기 때문에 비교연산자나 MeasurementUnitRef를 쓰면 안된다.
* ItemData 요소의 값을 사용하고 식의 결과를 논리(boolean)값으로 반환한다.
* 멀티 FormalExpression은 각가 다른 Context 속성을 가진 경우 제공될 수 있고, 이를 통해 동일한 식이 여러 시스템에 적합한 형식으로 표현될 수 있다.
*   서로 다른 의미를 가진 여러개의 다른 식은 별도의 RangeCheck로 표시되어야 한다.

    #### 📃 예제

    ```
    <ConditionDef OID="C.2" Name="GenderNotFemale">
        <Description>
            <TranslatedText xml:lang="en">GenderNotFemale</TranslatedText>
        </Description>
        <FormalExpression Context="OpenEDC">!(Gender == "Female")</FormalExpression>
    </ConditionDef>
    ```

```xml
<RangeCheck Comparator="GE" SoftHard="Hard">
    <CheckValue>18</CheckValue>
</RangeCheck>
<RangeCheck Comparator="LT" SoftHard="Hard">
    <CheckValue>120</CheckValue>
</RangeCheck>
```

### BODY

(([**CheckValue**](checkvalue.md)+ | **FormalExpression**+), [**MeasurementUnitRef**](../measurementunitref.md)?, [**ErrorMessage**](errormessage.md)?)



### ATTRIBUTE

| **Comparator** | (LT \| LE \| GT \| GE \| EQ \| NE \| IN \| NOTIN) | (optional) | Comparison operator used to compare the item and value(s). |   |
| -------------- | ------------------------------------------------- | ---------- | ---------------------------------------------------------- | - |
| **SoftHard**   | (Soft \| Hard)                                    |            |                                                            |   |



### CONTAINED IN

****[**ItemDef**](../)

