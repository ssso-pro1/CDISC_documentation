---
description: 번역된 텍스트.
---

# TranslatedText

### **EX** :

```xml
<StudyEventDef OID="SE.2" Name="Follow-up (T1)" Repeating="No" Type="Common">
    <Description>
        <TranslatedText xml:lang="en">Follow-up (T1)</TranslatedText>
        <TranslatedText xml:lang="de">Folgebefragung (T1)</TranslatedText>
    </Description>
    <FormRef FormOID="F.3" Mandatory="No"/>
    <FormRef FormOID="F.4" Mandatory="No"/>
</StudyEventDef>
```

### **BODY**:

**text**



### ATTRIBUTE:&#x20;

| **xml:lang** | languageTag | _(optional)_ |
| ------------ | ----------- | ------------ |



### **CONTAINED IN**:&#x20;

**Decode, ErrorMessage, Question, Symbol, Description**

****

Human-readable text that is appropriate for a particular language. TranslatedText elements typically occur in a series, presenting a set of alternative textual renditions for different languages.

To find the text appropriate for a target language with tag LT, search for a TranslatedText element whose xml:lang attribute matches LT exactly (ignoring case). If that fails, remove the ending subtag from LT and repeat. If that fails, search for a TranslatedText without an xml:lang attribute and use that. If none is found, there is no suitable text available. E.g.

| **TranslatedTexts Present**                                                                                               | **Requested** | **Process**                                                                                                                                                                                   |
| ------------------------------------------------------------------------------------------------------------------------- | ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>&#x3C;TranslatedText xml:lang="fr-CA">...<br>&#x3C;TranslatedText xml:lang="en-GB">...<br>&#x3C;TranslatedText>...</p> | fr-FR         | <p>Look for xml:lang="fr-FR".<br>This is not found, so look for xml:lang="fr".<br>This is not found, so look for a TranslatedText with no xml:lang. This is the text that should be used.</p> |

To avoid ambiguity, a particular language tag must not occur more than once in a series of TranslatedText elements. Also, it is not permitted to have more than one TranslatedText element without an xml:lang attribute within the same parent.

**Note:** The xml:lang attribute is part of the XML standard.



