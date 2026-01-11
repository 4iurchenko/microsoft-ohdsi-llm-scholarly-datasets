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

1. drug exposure of '[HowOften] Beta blockers' for the first time in the person's history.

Limit cohort entry events to the earliest event per person.

### Cohort Exit

The cohort end date will be based on a continuous exposure to '[HowOften] Beta blockers':
allowing 90 days between exposures, adding 0 days after exposure ends, and using days supply and exposure end date for exposure duration.

### Cohort Eras

Entry events will be combined into cohort eras if they are within 0 days of each other.

### Concept sets:

### [HowOften] Beta blockers
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|1319998|acebutolol|149|RxNorm|NO|YES|NO|
|1314002|atenolol|1202|RxNorm|NO|YES|NO|
|1322081|betaxolol|1520|RxNorm|NO|YES|NO|
|1338005|bisoprolol|19484|RxNorm|NO|YES|NO|
|1346823|carvedilol|20352|RxNorm|NO|YES|NO|
|1386957|labetalol|6185|RxNorm|NO|YES|NO|
|1307046|metoprolol|6918|RxNorm|NO|YES|NO|
|1313200|nadolol|7226|RxNorm|NO|YES|NO|
|1314577|nebivolol|31555|RxNorm|NO|YES|NO|
|1327978|penbutolol|7973|RxNorm|NO|YES|NO|
|1345858|pindolol|8332|RxNorm|NO|YES|NO|
|1353766|propranolol|8787|RxNorm|NO|YES|NO|
>>>