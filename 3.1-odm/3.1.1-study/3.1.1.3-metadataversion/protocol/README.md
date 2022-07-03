---
description: 프로토콜. 연구 이벤트의 종류 (Protocol = Study event?)
---

# Protocol

### **EX** :

```xml
<Protocol>
    <StudyEventRef StudyEventOID="SE.1" Mandatory="No"/>
    <StudyEventRef StudyEventOID="SE.2" Mandatory="No"/>
    <StudyEventRef StudyEventOID="SE.3" Mandatory="No"/>
</Protocol>
```

### **BODY**:

([**Description**](../studyeventdef/description.md)?, [**StudyEventRef**](studyeventref.md)\*, **Alias**\*)



### ATTRIBUTE:&#x20;

**NONE**



### **CONTAINED IN**:&#x20;

📁 [**MetaDataVersion**](../)****



연구의 특정 버전 내에서 발생할 수 있는 스터디 이벤트 를 나열. 모든 임상 데이터는 이러한 연구 이벤트 중 하나 내에서 발생해야 함

{% hint style="info" %}
참고: 메타데이터에 프로토콜 정의가 포함되지 않은 연구는 임상 데이터를 가질 수 없음. 이러한 연구는 ‘공통 메타데이터 사전’의 역할을 할 수 있어 연구 간 메타데이터를 공유할 수 있음
{% endhint %}







