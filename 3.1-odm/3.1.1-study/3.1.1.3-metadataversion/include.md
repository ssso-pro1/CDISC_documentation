---
description: 이전 메타데이터 버전에 대한 참조 정보.
---

# Include



```xml
<Study OID="S.001">
  <MetaDataVersion OID="MDV.001" Name="First Metadata version"> 
    <ItemGroupDef OID="IG.001" Name="First ItemGroup"> 
      <ItemRef ItemOID="I.001" Mandatory="Yes" OrderNumber="1"/> 
      <ItemRef ItemOID="I.002" Mandatory="Yes" OrderNumber="2"/> 
      <Alias Context="Context1" Name="IG1"/> 
      <Alias Context="Context2" Name="FIRST"/> 
    </ItemGroupDef> 
  </MetaDataVersion> 
  
  <MetaDataVersion OID="MDV.002" Name="Second Metadata version"> 
    <Include StudyOID="S.001" MetaDataVersionOID="MDV.001"/>
    <ItemGroupDef OID="IG.001" Name="First ItemGroup (modified)"> 
      <ItemRef ItemOID="I.001" Mandatory="Yes" OrderNumber="1"/> 
      <ItemRef ItemOID="I.003" Mandatory="Yes" OrderNumber="2"/> 
      <ItemRef ItemOID="I.002" Mandatory="Yes" OrderNumber="3"/> 
      <Alias Context="Context1" Name="IG1"/> 
    </ItemGroupDef> 
  </MetaDataVersion> 
</Study>
```

### **BODY**

empty



### ATTRIBUTE

| **StudyOID**           | [oidref](../../dataformat.md) | References the Study that provides a prior metadata version.   |   |
| ---------------------- | ----------------------------- | -------------------------------------------------------------- | - |
| **MetaDataVersionOID** | [oidref](../../dataformat.md) | References the prior MetaDataVersion (within the above Study). |   |



### **CONTAINED IN**:&#x20;

📁 [MetaDataVersion](./)



* 이전 메타데이터 버전에 대한 참조 (ex. MetaDataVersionOID='MDV.001')
* 이 버전은 동일한 ODM파일 혹은 시리즈의 이전 파일에 존재해야 함
* ItemDef와 같은 메타 데이터 요소가 메타데이터 버전에서 재정의되면, 동일한 타입이나 OID를 갖는 모든 메타 데이터 요소는 대체됨. 새 정의에 존재하지 않는 모든 속성 및 자식 요소는 이전 버전에서 삭제됨

