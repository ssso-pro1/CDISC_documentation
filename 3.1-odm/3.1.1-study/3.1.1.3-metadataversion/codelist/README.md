---
description: Item에 대해 허용되는 개별 값 집합을 정의
---

# CodeList

```xml
<CodeList OID="CL.1" Name="CL.1" DataType="text">
    <CodeListItem CodedValue="Female">
        <Decode>
            <TranslatedText xml:lang="en">Female</TranslatedText>
            <TranslatedText xml:lang="de">Weiblich</TranslatedText>
        </Decode>
    </CodeListItem>
    <CodeListItem CodedValue="Male">
        <Decode>
            <TranslatedText xml:lang="en">Male</TranslatedText>
            <TranslatedText xml:lang="de">Männlich</TranslatedText>
        </Decode>
    </CodeListItem>
</CodeList>
```



### BODY

(**Description**?, (**CodeListItem**+ | **EnumeratedItem**+ | **ExternalCodeList**), **Alias**\*)



### ATTRIBUTE

|                   |                                       |              |   |
| ----------------- | ------------------------------------- | ------------ | - |
| **OID**           | oid                                   |              |   |
| **Name**          | name                                  |              |   |
| **DataType**      | (integer \| float \| text \| string ) |              |   |
| **SASFormatName** | sasFormat                             | _(optional)_ |   |



### CONTAINED IN

****[**MetaDataVersion**](../)****

****

Defines a discrete set of permitted values for an item. The definition can be an explicit list of values (CodeListItem+ | EnumeratedItem+) or a reference to an externally defined codelist (ExternalCodeList).

The DataType restricts the values that can appear in the CodeList whether internal or external.

The SASFormatName must be a legal SAS format.



Item에 대해 허용되는 개별 값 집합을 정의합니다. 정의는 명시적 값 목록(CodeListItem+ | EnumeratedItem+)이거나 외부에서 정의된 코드 목록(ExternalCodeList)에 대한 참조일 수 있습니다.

DataType은 내부 또는 외부 여부에 관계없이 CodeList에 나타날 수 있는 값을 제한합니다.

SASFormatName은 유효한 SAS 형식이어야 합니다.

