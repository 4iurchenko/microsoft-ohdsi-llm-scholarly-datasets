You will receive text that may contain one or more data tables.
It describes a Cohort for OHDSI OMOP.

Your task:

1. Identify all tables in the input that reflect Concept Sets.
2. Extract each table separately.
3. Return them in strict JSON with this structure:

{
  "tables": [
    {
      "table_id": "table_1",
      "name": "Try to extract table name from the title…",
      "rows": [
        {
             "Concept_ID": "...", 
             "Concept_Name": "…",
             "Code": "…”,
             "Vocabulary": "…”,
             "Excluded": "…”,
             "Descendants": "…”,
             "Mapped": "…"
        },
        {
             …
        }
      ]
    },
    {
      "table_id": "table_2",
      "name": ""Try to extract table name from the title…"",
      "rows": [
        {...}
      ]
    }
  ]
}

Do not merge tables.
Do not change column names.
Do not create extra explanations.
Only valid JSON.

STRICT MODE:
Return only the final output in the format below. No reasoning, no commentary.

Data
<<<
# Cohort Definition

## Human Readable Cohort Definition

### Cohort Entry Events

People enter the cohort when observing any of the following:

1. condition occurrences of 'Type 2 Diabetes Mellitus'.

2. observations of 'History of diabetes'.

### Cohort Exit

The cohort end date will be offset from index event's end date plus 0 days.

### Cohort Eras

Entry events will be combined into cohort eras if they are within 0 days of each other.

### Concept sets:

### Type 2 Diabetes Mellitus
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|201820|Diabetes mellitus|73211009|SNOMED|NO|YES|NO|
|442793|Complication due to diabetes mellitus|74627003|SNOMED|NO|YES|NO|
|443238|Diabetic - poor control|268519009|SNOMED|NO|YES|NO|
|201254|Type 1 diabetes mellitus|46635009|SNOMED|YES|YES|NO|
|4058243|Diabetes mellitus during pregnancy, childbirth and the puerperium|199223000|SNOMED|YES|YES|NO|
|435216|Disorder due to type 1 diabetes mellitus|420868002|SNOMED|YES|YES|NO|
|40484648|Type 1 diabetes mellitus uncontrolled|444073006|SNOMED|YES|YES|NO|


### History of diabetes
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|40769338|History of Diabetes (regardless of treatment) [PhenX]|66678-4|LOINC|NO|YES|NO|
|43021173|History of diabetes mellitus type 2|472969004|SNOMED|NO|YES|NO|
|42539022|History of diabetes related lower limb amputation|735199000|SNOMED|NO|YES|NO|
|46270562|History of small vessel disease due to diabetes mellitus|59801000119102|SNOMED|NO|YES|NO|
>>>