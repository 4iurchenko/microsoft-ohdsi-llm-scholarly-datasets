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

People with continuous observation of 365 days before event may enter the cohort when observing any of the following:

1. drug exposure of '[HowOften] Trimethoprim systemetic' for the first time in the person's history.

Limit cohort entry events to the earliest event per person.

### Inclusion Criteria

#### 1. nested in Acute Typical Pneumonia

Entry events with all of the following criteria:

   1. having at least 1 condition occurrence of 'Acute Typical Pneumonia', starting between 30 days before and 0 days after cohort entry start date.
   2. having no condition occurrences of 'Non Acute Typical Pneumonia', starting between 30 days before and 0 days after cohort entry start date.


### Cohort Exit

The cohort end date will be based on a continuous exposure to '[HowOften] Trimethoprim systemetic':
allowing 30 days between exposures, adding 0 days after exposure ends, and using days supply and exposure end date for exposure duration.

### Cohort Eras

Entry events will be combined into cohort eras if they are within 0 days of each other.

### Concept sets:

### [HowOften] Trimethoprim systemetic
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|40081374|sulfamethoxazole / trimethoprim Injectable Solution|377117|RxNorm|NO|YES|NO|
|36882762|Sulfamethoxazole / Trimethoprim Injectable Suspension|OMOP994039|RxNorm Extension|NO|YES|NO|
|40220482|sulfamethoxazole / trimethoprim Injection|1809082|RxNorm|NO|YES|NO|
|35153537|Sulfamethoxazole / Trimethoprim Oral Granules|OMOP4810565|RxNorm Extension|NO|YES|NO|
|40147374|sulfamethoxazole / trimethoprim Oral Solution|757319|RxNorm|NO|YES|NO|
|40081379|sulfamethoxazole / trimethoprim Oral Suspension|374233|RxNorm|NO|YES|NO|
|40081388|sulfamethoxazole / trimethoprim Oral Tablet|374234|RxNorm|NO|YES|NO|
|1705674|trimethoprim|10829|RxNorm|NO|YES|NO|
|40073114|polymyxin B / trimethoprim Ophthalmic Ointment|376523|RxNorm|YES|YES|NO|
|40073115|polymyxin B / trimethoprim Ophthalmic Solution|379128|RxNorm|YES|YES|NO|
|40180925|sulfamethazine / trimethoprim Topical Solution|991879|RxNorm|YES|YES|NO|
  

### Acute Typical Pneumonia
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|46269693|Chronic pneumonia|102361000119104|SNOMED|YES|YES|NO|
|4193174|Fungal respiratory infection|312149008|SNOMED|YES|YES|NO|
|36712839|Idiopathic pneumonia syndrome|12381000132107|SNOMED|YES|YES|NO|
|4273378|Interstitial pneumonia|64667001|SNOMED|YES|YES|NO|
|256622|Pulmonary disease due to Mycobacteria|84353005|SNOMED|YES|YES|NO|
|4318404|Lung consolidation|95436008|SNOMED|NO|YES|NO|
  

### Non Acute Typical Pneumonia
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|36712839|Idiopathic pneumonia syndrome|12381000132107|SNOMED|NO|YES|NO|
|4193174|Fungal respiratory infection|312149008|SNOMED|NO|YES|NO|
|256622|Pulmonary disease due to Mycobacteria|84353005|SNOMED|NO|YES|NO|
|46269693|Chronic pneumonia|102361000119104|SNOMED|NO|YES|NO|
|4273378|Interstitial pneumonia|64667001|SNOMED|NO|YES|NO|
>>>