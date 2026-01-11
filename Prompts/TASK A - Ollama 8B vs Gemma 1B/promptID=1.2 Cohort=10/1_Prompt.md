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

1. condition occurrences of 'Acute respiratory distress syndrome (ARDS) or Acute Respiratory Failure'.

### Cohort Exit

The cohort end date will be offset from index event's end date plus 0 days.

### Cohort Eras

Entry events will be combined into cohort eras if they are within 0 days of each other.

### Concept sets:

### Acute respiratory distress syndrome (ARDS) or Acute Respiratory Failure
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|4191650|Acute respiratory distress|373895009|SNOMED|YES|YES|NO|
|4195694|Acute respiratory distress syndrome|67782005|SNOMED|NO|YES|NO|
|319049|Acute respiratory failure|65710008|SNOMED|NO|YES|NO|
|258866|Respiratory distress syndrome in the newborn|46775006|SNOMED|YES|YES|NO|
>>>