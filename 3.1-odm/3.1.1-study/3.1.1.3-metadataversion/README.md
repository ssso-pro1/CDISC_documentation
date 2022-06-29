---
description: 연구 데이터를 구성하는 연구 이벤트, 양식, 항목 그룹 및 항목의 유형을 정의
---

# 🗂 3.1.1.3 MetaDataVersion

### **EX** :

```xml
<MetaDataVersion OID="MDV.1" Name="MetaDataVersion">
    <Protocol>
        <StudyEventRef StudyEventOID="SE.3" Mandatory="No"/>
    </Protocol>
		<StudyEventDef OID="SE.1" Name="Baseline (T0)" Repeating="No" Type="Common">
        <Description></Description>
        <FormRef FormOID="F.1" Mandatory="No"/>
    </StudyEventDef>		
		<FormDef OID="F.1" Name="Basis data" Repeating="No">
				<Description></Description>		
				<ItemGroupRef ItemGroupOID="IG.1" Mandatory="No"/>
		</FormDef>
		<ItemGroupDef OID="IG.1" Name="PersonalItems" Repeating="No">
		    <Description></Description>
		    <ItemRef ItemOID="Age" Mandatory="No"/>
		</ItemGroupDef>
		<ItemDef OID="Gender" Name="Gender" DataType="text">
		    <Question></Question>
		    <CodeListRef CodeListOID="CL.1"/>
		</ItemDef>
		<CodeList OID="CL.1" Name="CL.1" DataType="text">
        <CodeListItem CodedValue="Female"></CodeListItem>
    </CodeList>
</MetaDataVersion>
```

### **BODY**:

* Include
* Protocol
* StudyEventDef
* FormDef
* ItemGroupDef
* ItemDef
* CodeList
* Imputationmethod Deprecated
* Presentation
* ConditionDef
* MethodDef



### ATTRIBUTE:&#x20;

* OID oid
* Name name
* Description text (선택사항)



### **CONTAINED IN**:&#x20;

📁 Study[MetaDataVersion](./)



* 메타데이터 버전은 연구 데이터를 구성하는 연구 이벤트, 양식, 항목 그룹 및 항목의 유형을 정의
* Include요소는 이전 메타 데이터 버전을 참조하며, 이전 버전의 모든 정의가 해당 버전에 자동으로 포함됨. 이러한 정의는 새 버전에서 동일한 OID를 사용 하여 재정의할 수 있음
