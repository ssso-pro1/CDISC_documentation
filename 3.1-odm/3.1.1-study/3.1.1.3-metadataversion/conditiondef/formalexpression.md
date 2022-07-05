# FormalExpression

![](<../../../../.gitbook/assets/MicrosoftTeams-image (4).png>)

![](<../../../../.gitbook/assets/MicrosoftTeams-image (5).png>)

![](<../../../../.gitbook/assets/MicrosoftTeams-image (3).png>)

```xml
<MethodDef OID="M.1" Name="M.1" Type="Computation">
    <Description>
        <TranslatedText xml:lang="en">M.1</TranslatedText>
    </Description>
    <FormalExpression Context="OpenEDC">Weight / Height ^ 2</FormalExpression>
</MethodDef>
```



### BODY <a href="#body" id="body"></a>

(PCDATA)



### ATTRIBUTE <a href="#attribute" id="attribute"></a>

| **Context** | text | A free-form qualifier to suggest an appropriate computer language to be used when evaluating the FormalExpression content.​​ |
| ----------- | ---- | ---------------------------------------------------------------------------------------------------------------------------- |

### &#x20;<a href="#contained-in" id="contained-in"></a>

### CONTAINED IN <a href="#contained-in" id="contained-in"></a>

[ConditionDef](./), [MethodDef](../methoddef.md), [RangeCheck](../itemdef/rangecheck/)

****

A FormalExpression used within a ConditionDef or a RangeCheck must evaluate to True or False. A FormalExpression referenced within a MethodDef having Type Imputation, Computation or Transpose must evaluate to the correct DataType for an Item that may be imputed or computed using the Method.

****

**​**

