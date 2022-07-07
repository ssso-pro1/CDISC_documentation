---
description: 스터디 이벤트(방문)에 대한 임상 데이터.
---

# StudyEventData

Clinical data for a study event (visit). The model supports repeating study events (for example, when the same set of information is collected for a series of patient visits).

스터디 이벤트(방문)에 대한 임상 데이터. 이 모델은 반복되는 연구 이벤트를 지원합니다(예: 일련의 환자 방문에 대해 동일한 정보 세트가 수집되는 경우).&#x20;

```xml
<ClinicalData>
    <SubjectData>
        <StudyEventData StudyEventOID="SE.1">
            <FormData>
                <ItemGroupData></ItemGroupData>
                <ArchiveLayoutRef></ArchiveLayoutRef>
            </FormData>
        </StudyEventData>
        <StudyEventData StudyEventOID="SE.2">
        ...
        </StudyEventData>
    <SubjectData>
</ClinicalData>
```

****

**Body:**\
****(AuditRecord?, Signature?, Annotation\*, FormData\* )



**Attributes:**

| **StudyEventOID**       | oidref                                            |              | Reference to the StudyEventDef.                                                                 |
| ----------------------- | ------------------------------------------------- | ------------ | ----------------------------------------------------------------------------------------------- |
| **StudyEventRepeatKey** | repeatKey                                         | _(optional)_ | A key used to distinguish between repeats of the same type of study event for a single subject. |
| **TransactionType**     | (Insert \| Update \| Remove \| Upsert \| Context) | _(optional)_ | The TransactionType attribute need not be present in a Snapshot document.                       |

* The StudyEventOID and StudyEventRepeatKey are used together to identify a particular study event. This pair of values uniquely identifies a StudyEvent within the containing subject. The `StudyEventRepeatKey` is present if and only if the `StudyEventDef` is repeating.\
  \
  StudyEventOID 및 StudyEventRepeatKey는 특정 연구 이벤트를 식별하기 위해 함께 사용됩니다. 이 값 쌍은 StudyEvent를 고유하게 식별합니다. `StudyEventRepeatKey`는 `StudyEventDef`가 반복되는 경우에만 존재합니다.



**Contained in:**\
****SubjectData











