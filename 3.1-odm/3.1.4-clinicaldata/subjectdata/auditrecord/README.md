---
description: AuditRecord는 임상 데이터의 생성, 삭제 또는 수정과 관련된 정보를 전달합니다.
---

# 📌 AuditRecord

An AuditRecord carries information pertaining to the creation, deletion, or modification of clinical data. This information includes who performed that action, and where, when, and why that action was performed.

AuditRecord는 임상 데이터의 생성, 삭제 또는 수정과 관련된 정보를 전달합니다. 이 정보에는 해당 작업을 수행한 사람과 해당 작업이 수행된 장소, 시기 및 이유가 포함됩니다.

```xml
<AuditRecord>
    <UserRef UserOID="U.1"/>
    <LocationRef LocationOID="L.1"/>
    <DateTimeStamp>2022-07-05T07:38:33.559Z</DateTimeStamp>
</AuditRecord>
```



**Body:**

(UserRef, LocationRef, DateTimeStamp, ReasonForChange?, SourceID?)\


**Attributes:**

| **EditPoint**            | (Monitoring \| DataManagement \| DBAudit) | _(optional)_ |                                                                                                   |
| ------------------------ | ----------------------------------------- | ------------ | ------------------------------------------------------------------------------------------------- |
| **UsedImputationMethod** | (Yes \| No)                               | _(optional)_ |                                                                                                   |
| **ID**                   | ID                                        | _(optional)_ | If an AuditRecord is contained within an AuditRecords element, the ID attribute must be provided. |

* The `EditPoint` attribute identifies the phase of data processing in which action occurred.
* The `UsedImputationMethod` attribute indicates whether the action involved the use of a Method. (Note: In ODM 1.3, the new element MethodDef was introduced and the ImputationMethod element was deprecated).\

* `EditPoint` 특성은 작업이 발생한 데이터 처리 단계를 식별한다.
* `UsedImputationMethod` 특성은 작업에 메서드 사용이 포함되었는지 여부를 나타냅니다. (참고: ODM 1.3에서 새로운 요소인 MethodDef가 도입되었으며 ImputationMethod 요소는 더 이상 사용되지 않습니다.)



**Contained in:**

FormData, ItemData, ItemGroupData, StudyEventData, SubjectData, AuditRecords



**Note:** The monitoring phase includes any data collection and correction involving the clinician, study-site personnel, or study monitor. The data management phase includes any changes made for internal data processing reasons (for example, coding or updating derived data) and before database lock. The DB audit phase occurs after database lock.

AuditRecord information describes a change to clinical data, but is not itself clinical data. The value of some clinical data can always be changed by a subsequent transaction, but history cannot be changed -- only added to.

Whenever an element has a TransactionType (either explicit or inherited), an AuditRecord must be provided. However, an AuditRecord has no meaning in a Snapshot transfer.

As with the TransactionType attribute, an AuditRecord is inherited by any subelement that is allowed to have an AuditRecord and does not already have one attached.

**Note:** Contrast with Signature.\
