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

People may enter the cohort when observing any of the following:

1. condition occurrences of 'Gastrointestinal hemorrhage GI bleeding'.

Restrict entry events to having at least 1 visit occurrence of 'Inpatient or ER visit', starting anytime on or before cohort entry start date and ending between 0 days before and all days after cohort entry start date.  

### Cohort Exit

The cohort end date will be offset from index event's end date plus 0 days.

### Cohort Eras

Entry events will be combined into cohort eras if they are within 0 days of each other.

### Concept sets:

### Inpatient or ER visit
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|262|Emergency Room and Inpatient Visit|ERIP|Visit|NO|YES|NO|
|9203|Emergency Room Visit|ER|Visit|NO|YES|NO|
|9201|Inpatient Visit|IP|Visit|NO|YES|NO|
  

### Gastrointestinal hemorrhage GI bleeding
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|4138962|Acute duodenal ulcer without hemorrhage AND without perforation|32490005|SNOMED|YES|YES|NO|
|4195231|Acute gastric ulcer without hemorrhage AND without perforation|67964002|SNOMED|YES|YES|NO|
|4147683|Acute gastrojejunal ulcer without hemorrhage AND without perforation|30514008|SNOMED|NO|NO|NO|
|4163865|Acute peptic ulcer without hemorrhage AND without perforation|45485004|SNOMED|YES|YES|NO|
|195584|Acute peptic ulcer without hemorrhage AND without perforation but with obstruction|58085004|SNOMED|YES|YES|NO|
|40482685|Angiodysplasia of duodenum|442267002|SNOMED|NO|YES|NO|
|28779|Bleeding esophageal varices|17709002|SNOMED|NO|YES|NO|
|4222896|Chronic duodenal ulcer without hemorrhage AND without perforation|40214005|SNOMED|YES|YES|NO|
|4296611|Chronic gastric ulcer without hemorrhage AND without perforation|76796008|SNOMED|YES|YES|NO|
|200769|Chronic gastric ulcer without hemorrhage, without perforation AND without obstruction|1567007|SNOMED|YES|YES|NO|
|4177387|Chronic gastrojejunal ulcer without hemorrhage AND without perforation|4269005|SNOMED|YES|YES|NO|
|434400|Chronic gastrojejunal ulcer without hemorrhage AND without perforation but with obstruction|56579005|SNOMED|YES|YES|NO|
|438795|Chronic gastrojejunal ulcer without hemorrhage, without perforation AND without obstruction|41626001|SNOMED|YES|YES|NO|
|4204555|Chronic peptic ulcer without hemorrhage AND without perforation|5492000|SNOMED|YES|YES|NO|
|24973|Chronic peptic ulcer without hemorrhage AND without perforation but with obstruction|12384004|SNOMED|YES|YES|NO|
|23808|Chronic peptic ulcer without hemorrhage, without perforation AND without obstruction|60400003|SNOMED|YES|YES|NO|
|2002608|Control of hemorrhage and suture of ulcer of stomach or duodenum|44.4|ICD9Proc|NO|YES|NO|
|198798|Dieulafoy's vascular malformation|109558001|SNOMED|NO|YES|NO|
|4198381|Ulcer of duodenum|51868009|SNOMED|NO|YES|NO|
|4209746|Duodenal ulcer without hemorrhage AND without perforation|56776001|SNOMED|YES|YES|NO|
|4112183|Esophageal varices with bleeding, associated with another disorder|195475003|SNOMED|NO|YES|NO|
|2108900|Esophagogastroduodenoscopy, flexible, transoral; with control of bleeding, any method|43255|CPT4|NO|YES|NO|
|2108878|Esophagoscopy, flexible, transoral; with control of bleeding, any method|43227|CPT4|NO|YES|NO|
|4265600|Gastric ulcer|397825006|SNOMED|NO|YES|NO|
|4248429|Gastric ulcer without hemorrhage AND without perforation|73481001|SNOMED|YES|YES|NO|
|192671|Gastrointestinal hemorrhage|74474003|SNOMED|NO|YES|NO|
|4101104|Gastrojejunal ulcer without hemorrhage AND without perforation|2783007|SNOMED|YES|YES|NO|
|443530|Hematochezia|405729008|SNOMED|YES|YES|NO|
|197925|Hemorrhage of rectum and anus|266464001|SNOMED|YES|YES|NO|
|4027663|Peptic ulcer|13200003|SNOMED|NO|YES|NO|
|4291028|Peptic ulcer without hemorrhage AND without perforation|37442009|SNOMED|YES|YES|NO|
>>>