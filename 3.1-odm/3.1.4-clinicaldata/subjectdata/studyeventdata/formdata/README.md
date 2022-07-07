---
description: 폼(페이지)에 대한 임상 데이터.
---

# FormData

Clinical data for a form (page). The model supports repeating forms in a single study event (for example, when several adverse events are recorded in a single patient visit).

양식(페이지)에 대한 임상 데이터. 이 모델은 단일 연구 이벤트에서 반복되는 폼을 지원합니다(예: 한 명의 환자 방문에서 여러 부작용이 기록된 경우).&#x20;



```xml
<StudyEventData StudyEventOID="SE.1">
    <FormData FormOID="F.1" TransactionType="Insert">
        <AuditRecord>
            <UserRef UserOID="U.1"/>
            <LocationRef LocationOID="L.1"/>
            <DateTimeStamp>2022-07-06T23:47:54.453Z</DateTimeStamp>
        </AuditRecord>
        <Annotation SeqNum="1">
            <Flag>
                <FlagValue CodeListOID="OpenEDC.DataStatus">3</FlagValue>
            </Flag>
        </Annotation>
        <ItemGroupData ItemGroupOID="IG.1">
            <ItemData ItemOID="I.1" Value="2022-07-01"/>
            <ItemData ItemOID="I.2" Value="1"/>
        </ItemGroupData>
    </FormData>
    <FormData FormOID="F.2" TransactionType="Insert">
        <AuditRecord>
            <UserRef UserOID="U.1"/>
            <LocationRef LocationOID="L.1"/>
            <DateTimeStamp>2022-07-06T23:48:47.181Z</DateTimeStamp>
        </AuditRecord>
        <Annotation SeqNum="1">
            <Flag>
                <FlagValue CodeListOID="OpenEDC.DataStatus">3</FlagValue>
            </Flag>
        </Annotation>
        <ItemGroupData ItemGroupOID="IG.3">
            <ItemData ItemOID="I.3" Value="1995-07-01"/>
            <ItemData ItemOID="I.4" Value="27"/>
            <ItemData ItemOID="I.5" Value="2"/>
            <ItemData ItemOID="HEIGHT" Value="180"/>
            <ItemData ItemOID="WEIGHT" Value="70"/>
            <ItemData ItemOID="I.8" Value="21.6"/>
        </ItemGroupData>
    </FormData>
</StudyEventData>
```

****

**Body:**\
****(AuditRecord?, Signature?, ArchiveLayoutRef?, Annotation\*, ItemGroupData\* )



**Attributes:**

| **FormOID**         | oidref                                            | Reference to the FormDef. |                                                                                                 |
| ------------------- | ------------------------------------------------- | ------------------------- | ----------------------------------------------------------------------------------------------- |
| **FormRepeatKey**   | repeatKey                                         | _(optional)_              | A key used to distinguish between repeats of the same type of form within a single study event. |
| **TransactionType** | (Insert \| Update \| Remove \| Upsert \| Context) | _(optional)_              | The TransactionType attribute need not be present in a Snapshot document.                       |

* The FormOID and FormRepeatKey are used together to identify a particular form. This pair of values uniquely identifies a Form within the containing StudyEvent. The FormRepeatKey is present if and only if the FormDef is repeating.\
  \
  FormOID와 FormRepeatKey는 특정 양식을 식별하기 위해 함께 사용됩니다. 이 값 쌍은 포함하는 StudyEvent 내에서 양식을 고유하게 식별합니다. FormDef가 반복되는 경우에만 FormRepeatKey가 있습니다.



**Contained in:**

StudyEventData





