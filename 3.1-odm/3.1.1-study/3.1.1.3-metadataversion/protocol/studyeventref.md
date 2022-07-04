---
description: StudyEventDef를 참조.
---

# StudyEventRef



```xml
<Protocol>
    <StudyEventRef StudyEventOID="SE.1" Mandatory="No"/>
    <StudyEventRef StudyEventOID="SE.2" Mandatory="No"/>
    <StudyEventRef StudyEventOID="SE.3" Mandatory="No"/>
</Protocol>
```

![Events 참](<../../../../.gitbook/assets/화면 캡처 2022-06-29 210038 (2).png>)

### BODY

([**Description**](../studyeventdef/description.md)?, [**FormRef**](../studyeventdef/formref.md)\*, **Alias**\*)



### ATTRIBUTE

| **StudyEventOID**                   | [oidref](../../../dataformat.md)  |              | Reference to the StudyEventDef. |
| ----------------------------------- | --------------------------------- | ------------ | ------------------------------- |
| **OrderNumber**                     | [integer](../../../dataformat.md) | _(optional)_ |                                 |
| **Mandatory**                       | (Yes \| No)                       |              |                                 |
| **CollectionExceptionConditionOID** | [oidref](../../../dataformat.md)  | _(optional)_ | Reference to a ConditionDef     |



### CONTAINED IN

****[**Protocol**](./)****

