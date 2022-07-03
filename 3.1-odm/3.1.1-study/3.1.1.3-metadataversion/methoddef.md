# MethodDef



```xml
<MethodDef OID="M.1" Name="M.1" Type="Computation">
    <Description>
        <TranslatedText xml:lang="en">M.1</TranslatedText>
    </Description>
    <FormalExpression Context="OpenEDC">Weight / Height ^ 2</FormalExpression>
</MethodDef>
<MethodDef OID="M.2" Name="M.2" Type="Computation">
    <Description>
        <TranslatedText xml:lang="de">M.1</TranslatedText>
    </Description>
    <FormalExpression Context="OpenEDC">(WHO.Q-WHO.1 + WHO.Q-WHO.2 + WHO.Q-WHO.3 + WHO.Q-WHO.4 + WHO.Q-WHO.5) * 4</FormalExpression>
</MethodDef>
```

![Items 참조](<../../../.gitbook/assets/createform (1).png>)



### BODY

([**Description**](studyeventdef/description.md), **FormalExpression\***, **Alias**\*)



### ATTRIBUTE

|          |                                                                        |   |   |
| -------- | ---------------------------------------------------------------------- | - | - |
| OID      | [oid](../../datatype.md)                                               |   |   |
| **Name** | [name](../../datatype.md)                                              |   |   |
| **Type** | [(Computation \| Imputation \| Transpose \| Other)](../../datatype.md) |   |   |



### CONTAINED IN

****[**MetaDataVersion**](./)****



A MethodDef defines how a data value can be obtained from a collection of other data values. The Description element must be provided and should include a prose description. This is the normative content of the MethodDef.

If a FormalExpression is provided, it must contain a machine-readable expression that implements the Description and will return a value. Multiple FormalExpressions can be provided if each has a different Context attribute, allowing the same expression to be represented in forms appropriate to multiple systems.
