# DataFormat

All XML attribute values and some element bodies are text strings. These strings are defined by data format. Each data format specifies the allowable form of the string, the corresponding XML Schema datatype, and the intended use of the value. The set of ODM data formats follows:



|                    |                       |                                                                                                                       |
| ------------------ | --------------------- | --------------------------------------------------------------------------------------------------------------------- |
| **Format Name**    | **Schema Datatype**   | **Allowed String Pattern**                                                                                            |
| integer            | xs:integer            | **-**?digit+                                                                                                          |
| positiveInteger    | xs:positiveInteger    | +?digit+ (and representing an integer number > 0)                                                                     |
| nonNegativeInteger | xs:nonNegativeInteger | +?digit+ (and representing an integer number >= 0)                                                                    |
| float              | xs:decimal            | **-**?digit+(**.**digit+)?                                                                                            |
| date               | xs:date               | YYYY**-**MM**-**DD                                                                                                    |
| time               | xs:time               | hh**:**mm**:**ss(**.**n+)? (((**+**\|**-**)hh**:**mm)\|Z)?                                                            |
| datetime           | xs:dateTime           | YYYY**-**MM**-**DD**T**hh**:**mm**:**ss(**.**n+)?(((**+**\|**-**)hh**:**mm)\|Z)?                                      |
| text               | xs:string             | _any sequence of characters_                                                                                          |
| oid                | xs:string             | _any sequence of characters_ (minLength="1")                                                                          |
| oidref             | xs:string             | _any sequence of characters_ (minLength="1")                                                                          |
| ID                 | xs:ID                 | _any sequence of characters_ (minLength="1")                                                                          |
| IDREF              | xs:IDREF              | _any sequence of characters_ (minLength="1")                                                                          |
| subjectKey         | xs:string             | _any sequence of characters_ (minLength="1")                                                                          |
| repeatKey          | xs:string             | _any sequence of characters_ (minLength="1")                                                                          |
| name               | xs:string             | _any sequence of characters_ (minLength="1")                                                                          |
| sasName            | xs:string             | ( letter \| **\_** )( letter \| digit \| **\_** )\* (maxLength="8")                                                   |
| sasFormat          | xs:string             | ( letter \| **\_** \| **$** )( letter \| digit \| **\_** \| **.** )\* (maxLength="8")                                 |
| fileName           | xs:anyURI             | _any sequence of characters_                                                                                          |
| languageTag        | xs:language           | LL (**-**CC)\* _(see below)_                                                                                          |
| string             | xs:string             | Semantically equivalent to **text** but directly supported as XML Schema datatype                                     |
| boolean            | xs:boolean            | (true \| false \| 1 \| 0)                                                                                             |
| double             | xs:string             | (((\\+\|-)?\[0-9]+(\\.\[0-9]+)?((D\|d\|E\|e)(\\+\|-)\[0-9]+)?)\|(-?INF)\|(NaN))                                       |
| hexBinary          | xs:hexBinary          | hex-encoded binary stream data                                                                                        |
| base64Binary       | xs:base64Binary       | binary stream encoded using Base64 Alphabet                                                                           |
| hexFloat           | xs:hexBinary          | up to 16 characters                                                                                                   |
| base64Float        | xs:base64Binary       | up to 12 characters                                                                                                   |
| partialDate        | xs:date               | **\[**YYYY**\[-**MM**\[-**DD ]]]                                                                                      |
| partialTime        | xs:time               | **\[**hh**\[:**mm**\[:**ss(**.**n+)? (((**+**\|**-**)hh**:**mm)\|Z)?]]]                                               |
| partialDatetime    | xs:dateTime           | **\[**YYYY**\[-**MM**\[-**DD**\[T** hh**\[:**mm**\[:**ss(**.**n+)? ((**+**\|**-**)hh**:**mm)?]]]]]]                   |
| intervalDatetime   | xs:string             | partialDatetime/partialDatetime)\|(durationDatetime/partialDatetime)\|(partialDatetime/durationDatetime)              |
| durationDatetime   | xs:duration           | (((+\|-)?P((((n(n+)?)Y)?((nn+)?)M)?((nn+)?)D)?)(T(((n(n+)?)H)?((n(n+)?)M)?((n(n+)?)((\\.n+)?)S)?)?)?\|(((n(n+)?)W)))) |
| incompleteDatetime | xs:string             | \[YYYY\|-]-\[MM \|-]-\[DD\|-]]]**T**\[hh\|-]:\[mm\|-]:\[ss.s\|-]\[?(+\|-)nn:nn\|Z]                                    |
| incompleteDate     | xs:string             | \[YYYY\|-]-\[MM \|-]-\[DD\|-]                                                                                         |
| incompleteTime     | xs:string             | **T**\[hh\|-]:\[mm\|-]:\[ss.s\|-]\[?(+\|-)nn:nn\|Z]                                                                   |
| URI                | xs:anyURI             |                                                                                                                       |

\


