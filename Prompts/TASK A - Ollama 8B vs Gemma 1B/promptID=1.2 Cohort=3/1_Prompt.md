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

1. condition occurrences of 'Dyspnea'.

### Cohort Exit

The cohort end date will be offset from index event's end date plus 14 days.

### Cohort Eras

Entry events will be combined into cohort eras if they are within 0 days of each other.

### Concept sets:

### Dyspnea
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|4305080|Abnormal breathing|386813002|SNOMED|NO|YES|NO|
|4041664|Difficulty breathing|230145002|SNOMED|NO|YES|NO|
|4222908|Borg Breathlessness Score: 0 none at all|401275008|SNOMED|YES|YES|NO|
>>>