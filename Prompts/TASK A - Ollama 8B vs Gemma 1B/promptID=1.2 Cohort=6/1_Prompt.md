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

1. condition occurrences of 'Sore throat'.

2. observations of 'Sore throat'.

### Cohort Exit

The cohort end date will be offset from index event's end date plus 14 days.

### Cohort Eras

Entry events will be combined into cohort eras if they are within 0 days of each other.

### Concept sets:

### Sore throat
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|4036632|Has a sore throat|162388002|SNOMED|NO|YES|NO|
|4173027|Acute laryngitis and/or tracheitis|276443001|SNOMED|NO|YES|NO|
|259153|Pain in throat|162397003|SNOMED|NO|YES|NO|
|24969|Laryngitis|45913009|SNOMED|NO|YES|NO|
|4148121|Tonsil and/or adenoid hypertrophy|266343004|SNOMED|NO|YES|NO|
|4226263|Pharyngitis|405737000|SNOMED|NO|YES|NO|
|4083666|Inflamed tonsils|281795003|SNOMED|NO|YES|NO|
|432347|Chronic disease of tonsils AND/OR adenoids|16358007|SNOMED|NO|YES|NO|
|4170621|Vesicular pharyngitis|274102007|SNOMED|NO|YES|NO|
|4049240|Vincent's laryngitis|232427004|SNOMED|NO|YES|NO|
|4095420|Traumatic hemorrhagic laryngitis|262677003|SNOMED|NO|YES|NO|
|44808497|Acute bacterial laryngitis|849571000000102|SNOMED|NO|YES|NO|
|30333|Gonorrhea of pharynx|74372003|SNOMED|NO|YES|NO|
|46270516|Laryngeal obstruction due to supraglottitis|36491000119101|SNOMED|NO|YES|NO|
>>>