# ItemData\[TYPE]

**Body:**\
****(PCDATA)



**Attributes:**\
****

| **ItemOID**            | oidref                                            |              | Reference to the ItemDef.                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ---------------------- | ------------------------------------------------- | ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **TransactionType**    | (Insert \| Update \| Remove \| Upsert \| Context) | _(optional)_ | The TransactionType attribute need not be present in a Snapshot document.                                                                                                                                                                                                                                                                                                                                                                                |
| **AuditRecordID**      | IDREF                                             | _(optional)_ | Reference to AuditRecord.                                                                                                                                                                                                                                                                                                                                                                                                                                |
| **SignatureID**        | IDREF                                             | _(optional)_ | Reference to Signature.                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **AnnotationID**       | IDREF                                             | _(optional)_ | Reference to Annotation.                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **MeasurementUnitOID** | oidref                                            | _(optional)_ | Reference to the MeasurementUnit definition.                                                                                                                                                                                                                                                                                                                                                                                                             |
| **IsNull**             | (Yes)                                             | _(optional)_ | <p>Only allowed for ItemDataAny.<br>IsNull is a flag to signify that an item's value is to be set to null. If element content (PCDATA) is given, IsNull must not be set. If IsNull is set, element content (PCDATA) must not be provided. In the interest of creating non-verbose XML instances, one should not use ItemData elements with IsNull set to "Yes" to indicate uncollected data. The better practice is to transmit only collected data.</p> |



**Contained in:**\
****ItemGroupData



ItemData_\[TYPE]_ elements provide typed data content as element PCDATA. The PCDATA datatype must match the DataType attribute in the corresponding ItemDef. For example, an ItemDataInteger element can be used only for items where the corresponding ItemDef Datatype attribute value is integer. Additionally in this case, the PCDATA content must be a parseable integer value. See also ItemDataAny for content parsing exceptions.

Typed and untyped data must not both be used within a single ODM file.

The following ItemData_\[TYPE]_ elements are valid:

| ItemData**Any**                |
| ------------------------------ |
| ItemData**String**             |
| ItemData**Integer**            |
| ItemData**Float**              |
| ItemData**Date**               |
| ItemData**Time**               |
| ItemData**Datetime**           |
| ItemData**Boolean**            |
| ItemData**HexBinary**          |
| ItemData**Base64Binary**       |
| ItemData**HexFloat**           |
| ItemData**Base64Float**        |
| ItemData**PartialDate**        |
| ItemData**PartialTime**        |
| ItemData**PartialDatetime**    |
| ItemData**DurationDatetime**   |
| ItemData**IntervalDatetime**   |
| ItemData**IncompleteDatetime** |
| ItemData**IncompleteDate**     |
| ItemData**IncompleteTime**     |
| ItemData**URI**                |

To transmit a value where the DataType does not match the _TYPE_, an ItemDataAny element must be used. An application receiving ItemDataAny data is not required to load these data values into the corresponding data fields.

To transmit a value where the DataType does not match the TYPE, an ItemDataAny element can be used.

Examples:

_\[Typed (version 1.3) Data Transmission]_

| Valid data   | \<ItemDataInteger ItemOID="ID.INT">1\</ItemDataInteger>    |               |
| ------------ | ---------------------------------------------------------- | ------------- |
| Invalid data | \<ItemDataAny ItemOID="ID.INT">text\</ItemDataAny>         | **correct**   |
| Invalid data | \<ItemDataInteger ItemOID="ID.INT">text\</ItemDataInteger> | **incorrect** |

_\[Un-typed (version 1.2) Data Transmission]_

| Valid data   | \<ItemData ItemOID="ID.INT" Value="1"/>    |   |
| ------------ | ------------------------------------------ | - |
| Invalid data | \<ItemData ItemOID="ID.INT" Value="text"/> |   |

\
