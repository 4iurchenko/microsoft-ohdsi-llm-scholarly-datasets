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

1. condition occurrences of 'Suicide or injury that is potentially self inflicted'.

2. observations of 'Suicide or injury that is potentially self inflicted'.

### Cohort Exit

The cohort end date will be offset from index event's end date plus 30 days.

### Cohort Eras

Entry events will be combined into cohort eras if they are within 0 days of each other.

### Concept sets:

### Suicide or injury that is potentially self inflicted
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|439235|Self inflicted injury|276853009|SNOMED|NO|YES|NO|
|4181216|Self-administered poisoning|363293009|SNOMED|NO|YES|NO|
|444362|Suicidal deliberate poisoning|86849004|SNOMED|NO|YES|NO|
|440925|Suicide|44301001|SNOMED|NO|YES|NO|
|4303690|Intentionally harming self|418420002|SNOMED|NO|YES|NO|
|4219484|Suicide attempt|82313006|SNOMED|NO|YES|NO|
|435446|Late effect of self inflicted injury|219174008|SNOMED|NO|YES|NO|
|4092411|Self-injurious behavior|248062006|SNOMED|NO|YES|NO|
|443272|Injury undetermined whether accidentally or purposely inflicted|269735005|SNOMED|NO|YES|NO|
>>>