---
description: 해당 시험 대상자에 대한 임상 데이터.
---

# 📂 SubjectData

Example:

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



**Body:**\
****(AuditRecord?, Signature?, InvestigatorRef?, SiteRef?, Annotation\*, StudyEventData\*)



**Attributes:**\
****

| **SubjectKey**      | subjectKey                                        |              | ex)SubjectKey='monkey'                                                    |
| ------------------- | ------------------------------------------------- | ------------ | ------------------------------------------------------------------------- |
| **TransactionType** | (Insert \| Update \| Remove \| Upsert \| Context) | _(optional)_ | The TransactionType attribute need not be present in a Snapshot document. |

*   Clinical data for a single subject.

    The `SubjectKey` is used to identify a specific subject. This key uniquely identifies a subject within the study specified by the parent ClinicalData element. If the same SubjectKey is used in multiple ClinicalData elements in a single study, this is interpreted as being the same subject.



    해당 시험 대상자에 대한 임상 데이터.&#x20;

    SubjectKey는 특정 시험 대상자를 식별하는 데 사용됩니다. 이 키는 상위 ClinicalData 요소에 의해 지정된 연구 내에서 주제를 고유하게 식별합니다. 해당 스터디의 여러 ClinicalData 요소에 동일한 SubjectKey가 사용되는 경우에, 이는 동일한 대상로 해석됩니다.



**Contained in:**

ClinicalData

\




