# ConditionDef

### BODY <a href="#body" id="body"></a>

([**Description**](https://app.gitbook.com/s/W8FVNr6JfpxtukiZpAMX/3.1-odm/3.1.1-study/3.1.1.3-metadataversion/studyeventdef/description)?, ([**CodeListItem**](https://app.gitbook.com/s/W8FVNr6JfpxtukiZpAMX/3.1-odm/3.1.1-study/3.1.1.3-metadataversion/codelist/codelistitem)+ | **EnumeratedItem**+ | **ExternalCodeList**), [**Alias**](https://app.gitbook.com/s/W8FVNr6JfpxtukiZpAMX/3.1-odm/3.1.1-study/3.1.1.3-metadataversion/itemdef/alias)\*)​

### ATTRIBUTE <a href="#attribute" id="attribute"></a>

**OID**​[oid](https://app.gitbook.com/s/W8FVNr6JfpxtukiZpAMX/3.1-odm/dataformat)​​​**Name**​[name](https://app.gitbook.com/s/W8FVNr6JfpxtukiZpAMX/3.1-odm/dataformat)​​​**DataType**​[(integer | float | text | string )](https://app.gitbook.com/s/W8FVNr6JfpxtukiZpAMX/3.1-odm/dataformat)​​​**SASFormatName**​[sasFormat](https://app.gitbook.com/s/W8FVNr6JfpxtukiZpAMX/3.1-odm/dataformat)​_(optional)_​​

### CONTAINED IN <a href="#contained-in" id="contained-in"></a>

**​**[**MetaDataVersion**](https://app.gitbook.com/s/W8FVNr6JfpxtukiZpAMX/3.1-odm/3.1.1-study/3.1.1.3-metadataversion)**​​**Defines a discrete set of permitted values for an item. The definition can be an explicit list of values (CodeListItem+ | EnumeratedItem+) or a reference to an externally defined codelist (ExternalCodeList).
