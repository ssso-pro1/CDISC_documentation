---
description: 외부에서 정의된 질문에 대한 참조 (MedDRA와 같은 외부 의약용어 자료 참조)
---

# ExternalQuestion

_MedDRA_(Medical Dictionary for Regulatory Activities,. 국제의약용어)

```xml
<ExternalCodeList Dictionary="MEDDRA" Version="10.0"/>;
```



### BODY

**empty**



### ATTRIBUTE

| **Dictionary** | text | _(optional)_ | The name of the external question dictionary.                            |
| -------------- | ---- | ------------ | ------------------------------------------------------------------------ |
| **Version**    | text | _(optional)_ | The version designator of the external question dictionary.              |
| **Code**       | text | _(optional)_ | A code selecting the particular question within the external dictionary. |



### CONTAINED IN

****[**ItemDef**](./)****

****

> MedDRA 관련 참고 \
> [https://www.pinnacle21.com/forum/adding-external-dictionaries-definexml-under-codelist-section](https://www.pinnacle21.com/forum/adding-external-dictionaries-definexml-under-codelist-section)



