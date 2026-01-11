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

People with continuous observation of 365 days before event enter the cohort when observing any of the following:

1. condition occurrence of 'Primary malignant neoplasm of kidney' for the first time in the person's history.

Limit cohort entry events to the earliest event per person.

### Cohort Exit

The person exits the cohort at the end of continuous observation.

### Cohort Eras

Entry events will be combined into cohort eras if they are within 0 days of each other.

### Concept sets:

### Primary malignant neoplasm of kidney
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|198985|Primary malignant neoplasm of kidney|93849006|SNOMED|NO|YES|NO|
|4215373|Renal cell carcinoma|41607009|SNOMED|NO|NO|NO|
>>>