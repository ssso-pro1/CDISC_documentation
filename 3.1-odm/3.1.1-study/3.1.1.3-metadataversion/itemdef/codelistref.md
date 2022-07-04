---
description: CodeList 정의 참조
---

# CodeListRef

CodeList를 참조하는 데이터 타입과 포함된 ItemDef는 동일해야 한다.

```xml
<CodeList OID="CL.2" Name="CL.2" DataType="text">
    <CodeListItem CodedValue="France">
        <Decode>
            <TranslatedText xml:lang="en">France</TranslatedText>
            <TranslatedText xml:lang="de">Frankreich</TranslatedText>
        </Decode>
    </CodeListItem>
    <CodeListItem CodedValue="Germany">
        <Decode>
            <TranslatedText xml:lang="en">Germany</TranslatedText>
            <TranslatedText xml:lang="de">Deutschland</TranslatedText>
        </Decode>
    </CodeListItem>
    <CodeListItem CodedValue="Greece">
        <Decode>
            <TranslatedText xml:lang="en">Greece</TranslatedText>
            <TranslatedText xml:lang="de">Griechenland</TranslatedText>
        </Decode>
    </CodeListItem>
    ...
</CodeList>
```

```xml
<ItemDef OID="CountryOfBirth" Name="CountryOfBirth" DataType="text">
    <Question>
        <TranslatedText xml:lang="en">What is your country of birth?</TranslatedText>
        <TranslatedText xml:lang="de">Wo sind Sie geboren?</TranslatedText>
    </Question>
    <CodeListRef CodeListOID="CL.2"/>
</ItemDef>
```

### BODY

**empty**



### ATTRIBUTE

| **CodeListOID** | oidref |   | Reference to the CodeList definition. |
| --------------- | ------ | - | ------------------------------------- |



### CONTAINED IN

****[**ItemDef**](./)****

****
