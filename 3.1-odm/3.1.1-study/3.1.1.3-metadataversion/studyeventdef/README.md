---
description: >-
  Study event definition: Baseline, Follow up + Repeating + Scheduled,
  Unscheduled, Common
---

# StudyEventDef

### EX

```xml
<StudyEventDef OID="SE.1" Name="Baseline (T0)" Repeating="No" Type="Common">
    <Description>
        <TranslatedText xml:lang="en">Baseline (T0)</TranslatedText>
        <TranslatedText xml:lang="de">Vorbefragung (T0)</TranslatedText>
    </Description>
    <FormRef FormOID="F.1" Mandatory="No"/>
    <FormRef FormOID="F.2" Mandatory="No"/>
</StudyEventDef>
```

![](<../../../../.gitbook/assets/화면 캡처 2022-06-29 210038 (2).png>)

### BODY

✅ **Description?**

✅ **FormRef**\*

✅ **Alias**\*&#x20;



### ATTRIBUTE

* OID oid
* Name name
* Repeating (Yes | No)
* Type (Scheduled | Unscheduled | Common)
* Category text (선택사항)



### CONTAINED IN

📁 MetaDataVersion



* 연구 단계를 나타내는 것 같음 (ex. Baseline, FollowUp) 에 해당하는 주제에서 수집되는 양식
* `Repeating` 은 해당 연구 이벤트가 반복적으로 발생할 수 있다는 것을 뜻함
* `Scheduled` '예정된 연구'에서 수집되는 일련의 양식
* `unscheduled` '예정되지 않은 연구' 이벤트는 심각한 부작용으로 인한 조기 종료를 위해 작성된 일련의 양식과 같이 특정 주제에 대해 발생하거나 발생하지 않을 수 있는 데이터를 수집
* `common`
  * 유해 사례 또는 병용 약물 로그와 같은 여러 다른 데이터 수집 이벤트에서 사용되는 양식 모음
  * 방문일정 마다(v1, v2, v3)의 병용약물 정보를 각각 보는 게 아닌 공통으로 빼 common에서 한 번에 보는 것. -> visit 마다 따로x, 한꺼번에 볼 수 있도록 함
* `Category` 속성은 연구 이벤트에 적합한 연구 단계를 나타내는 데 사용 (ex. Screening, PreTreatment, Treatment, FollowUp)

