---
description: 여러 주제에 대한 임상 데이터.
---

# 3.1.4 ClinicalData

Clinical data for multiple subjects.

여러 주제에 대한 임상 데이터.&#x20;

```xml
<ClinicalData StudyOID="P2006-101" MetadataVersionOID="101.01">
   <SubjectData SubjectKey="1000" TransactionType="Insert">
      <StudyEventData StudyEventOID="Screen">
         <FormData FormOID="DEMOG">
            <ItemGroupData ItemGroupOID="DM">
                <ItemDataString ItemOID="USUBJID">101-001-001</ItemDataString>
                <ItemDataString ItemOID="SEX">F</ItemDataString>
            </ItemGroupData>
        </FormData>
        <FormData FormOID="LABDATA">
            <ItemGroupData ItemGroupOID="LB">
                <ItemDataDatetime ItemOID="LBDTC">2006-07-14T14:48</ItemDataDatetime>
                <ItemDataString ItemOID="LBTESTCD">ALT</ItemDataString>
                <ItemDataString ItemOID="LBORRES">245</ItemDataString>
            </ItemGroupData>
        </FormData>
      </StudyEventData>
  </SubjectData>
</ClinicalData>
<ClinicalData StudyOID="P2006-101" MetadataVersionOID="101.02">
  <SubjectData SubjectKey="1000" TransactionType="Insert">
      <StudyEventData>
        <FormData FormOID="AENONSER">
            <ItemGroupData ItemGroupOID="AE">
                <ItemDataString ItemOID="AETERM">Fever</ItemDataString>
                <ItemDataDate ItemOID="AESTDTC">2006-08-21</ItemDataDate>
            </ItemGroupData>
        </FormData>
        <FormData FormOID="LABDATA">
            <ItemGroupData ItemGroupOID="LB">
                <ItemDataDatetime ItemOID="LBDTC">2006-07-14T14:48</ItemDataDatetime>
                <ItemDataString ItemOID="LBTESTCD">ALT</ItemDataString>
                <ItemDataString ItemOID="LBORRES">300</ItemDataString>
            </ItemGroupData>
        </FormData>
      </StudyEventData>
  </SubjectData>
</ClinicalData>
```

****

**Body:**\
****(SubjectData\*, AuditRecords\*, Signatures\*, Annotations\*)



**Attributes:**

| **StudyOID**           | oidref |   | References the Study that uses the data nested within this element.                                       |
| ---------------------- | ------ | - | --------------------------------------------------------------------------------------------------------- |
| **MetaDataVersionOID** | oidref |   | References the MetaDataVersion (within the above Study) that governs the data nested within this element. |

*   The `StudyOID` and `MetaDataVersionOID` attributes select a particular metadata version. All metadata references (OIDs) occurring within this ClinicalData element refer to definitions within the selected metadata version.



    StudyOID 및 MetaDataVersionOID 속성은 특정 메타데이터 버전을 선택합니다. 이 ClinicalData 요소 내에서 발생하는 모든 메타데이터 참조(OID)는 선택한 메타데이터 버전 내의 정의를 참조합니다.



**Contained in:**

ODM\








