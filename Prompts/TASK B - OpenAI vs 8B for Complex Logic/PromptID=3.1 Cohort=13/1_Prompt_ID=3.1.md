You will receive text that may describe a Cohort for OHDSI OMOP.

Your task:

1. Extract information from the Cohort description
2. Process each <<<TODO: >>> as a separate instruction and replace it with the asked value
3. Check Cohort Entry Events in Cohort Description:
- Add ConditionOccurrence block only if it is existing there
- Add Observation block only if it is existing there
- Add DrugExposure block only if it is existing there
4. Return a JSON with this structure:

{
	"cdmVersionRange" : ">=5.0.0",
	"PrimaryCriteria" : {
		"CriteriaList" : [
			{
				"ConditionOccurrence" : {
					"CodesetId" : <<<TODO:
                                1. Search in Cohort Description the name of Condition and then identify its "id" from "Concept Set Data JSON".
                                2. Insert that id here
								3. Do not use CONCEPT_ID. Use only "id"
                                >>>,
					"ConditionTypeExclude" : false
				}
			},

			{
				"Observation" : {
					"CodesetId" : <<<TODO:
                                1. Search in Cohort Description the name of Observation and then identify its id from "Concept Set Data JSON".
                                2. Insert that id here
								3. Do not use CONCEPT_ID. Use only "id"
                                >>>,
					"ObservationTypeExclude" : false
				}
			},
			{
				"DrugExposure" : {
					"CodesetId" : <<<TODO:
                                1. Search in Cohort Description the name of Drug Exposure and then identify its id from "Concept Set Data JSON".
                                2. Insert that id here
								3. Do not use CONCEPT_ID. Use only "id"
                                >>>,
					"First" : <<<TODO: Identify True or False>>>,
					"DrugTypeExclude" : false
				}
			}
		],
		"ObservationWindow" : {
			"PriorDays" : <<<TODO: 
							1. in Cohort Description, identify the prior days for observation
							2. Use only information from Cohort Entry Events. Ignore the rest of information
							3. If you can't find any, put 0
							>>>,
			"PostDays" : <<<TODO: 
							in Cohort Description, identify the post days for observation
							1. in Cohort Description, identify the post days for observation
							2. Use only information from Cohort Entry Events. Ignore the rest of information
							3. If you can't find any, put 0
							>>>
		},
		"PrimaryCriteriaLimit" : {
			"Type" : <<<TBD: Identify, "First" or "All". If you can't find mentioning First, then All>>>
		}
    }
}

Do not change column names.
Do not create extra explanations.
Only valid JSON.

STRICT MODE:
Return only the final output in the format below. No reasoning, no commentary.

Cohort Description:
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

Concept Set Data JSON:
<<<
[
		{
			"id" : 2,
			"name" : "Inpatient or ER visit",
			"expression" : {
				"items" : [
					{
						"concept" : {
							"CONCEPT_ID" : 262,
							"CONCEPT_NAME" : "Emergency Room and Inpatient Visit",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "ERIP",
							"DOMAIN_ID" : "Visit",
							"VOCABULARY_ID" : "Visit",
							"CONCEPT_CLASS_ID" : "Visit"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 9203,
							"CONCEPT_NAME" : "Emergency Room Visit",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "ER",
							"DOMAIN_ID" : "Visit",
							"VOCABULARY_ID" : "Visit",
							"CONCEPT_CLASS_ID" : "Visit"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 9201,
							"CONCEPT_NAME" : "Inpatient Visit",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "IP",
							"DOMAIN_ID" : "Visit",
							"VOCABULARY_ID" : "Visit",
							"CONCEPT_CLASS_ID" : "Visit"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					}
				]
			}
		},
		{
			"id" : 5,
			"name" : "Gastrointestinal hemorrhage GI bleeding",
			"expression" : {
				"items" : [
					{
						"concept" : {
							"CONCEPT_ID" : 4138962,
							"CONCEPT_NAME" : "Acute duodenal ulcer without hemorrhage AND without perforation",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "32490005",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4195231,
							"CONCEPT_NAME" : "Acute gastric ulcer without hemorrhage AND without perforation",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "67964002",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4147683,
							"CONCEPT_NAME" : "Acute gastrojejunal ulcer without hemorrhage AND without perforation",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "30514008",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : false,
						"includeDescendants" : false,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4163865,
							"CONCEPT_NAME" : "Acute peptic ulcer without hemorrhage AND without perforation",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "45485004",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 195584,
							"CONCEPT_NAME" : "Acute peptic ulcer without hemorrhage AND without perforation but with obstruction",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "58085004",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40482685,
							"CONCEPT_NAME" : "Angiodysplasia of duodenum",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "442267002",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 28779,
							"CONCEPT_NAME" : "Bleeding esophageal varices",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "17709002",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4222896,
							"CONCEPT_NAME" : "Chronic duodenal ulcer without hemorrhage AND without perforation",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "40214005",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4296611,
							"CONCEPT_NAME" : "Chronic gastric ulcer without hemorrhage AND without perforation",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "76796008",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 200769,
							"CONCEPT_NAME" : "Chronic gastric ulcer without hemorrhage, without perforation AND without obstruction",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "1567007",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4177387,
							"CONCEPT_NAME" : "Chronic gastrojejunal ulcer without hemorrhage AND without perforation",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "4269005",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 434400,
							"CONCEPT_NAME" : "Chronic gastrojejunal ulcer without hemorrhage AND without perforation but with obstruction",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "56579005",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 438795,
							"CONCEPT_NAME" : "Chronic gastrojejunal ulcer without hemorrhage, without perforation AND without obstruction",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "41626001",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4204555,
							"CONCEPT_NAME" : "Chronic peptic ulcer without hemorrhage AND without perforation",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "5492000",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 24973,
							"CONCEPT_NAME" : "Chronic peptic ulcer without hemorrhage AND without perforation but with obstruction",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "12384004",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 23808,
							"CONCEPT_NAME" : "Chronic peptic ulcer without hemorrhage, without perforation AND without obstruction",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "60400003",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 2002608,
							"CONCEPT_NAME" : "Control of hemorrhage and suture of ulcer of stomach or duodenum",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "44.4",
							"DOMAIN_ID" : "Procedure",
							"VOCABULARY_ID" : "ICD9Proc",
							"CONCEPT_CLASS_ID" : "3-dig nonbill code"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 198798,
							"CONCEPT_NAME" : "Dieulafoy's vascular malformation",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "109558001",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4198381,
							"CONCEPT_NAME" : "Ulcer of duodenum",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "51868009",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4209746,
							"CONCEPT_NAME" : "Duodenal ulcer without hemorrhage AND without perforation",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "56776001",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4112183,
							"CONCEPT_NAME" : "Esophageal varices with bleeding, associated with another disorder",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "195475003",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 2108900,
							"CONCEPT_NAME" : "Esophagogastroduodenoscopy, flexible, transoral; with control of bleeding, any method",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "43255",
							"DOMAIN_ID" : "Procedure",
							"VOCABULARY_ID" : "CPT4",
							"CONCEPT_CLASS_ID" : "CPT4"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 2108878,
							"CONCEPT_NAME" : "Esophagoscopy, flexible, transoral; with control of bleeding, any method",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "43227",
							"DOMAIN_ID" : "Procedure",
							"VOCABULARY_ID" : "CPT4",
							"CONCEPT_CLASS_ID" : "CPT4"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4265600,
							"CONCEPT_NAME" : "Gastric ulcer",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "397825006",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4248429,
							"CONCEPT_NAME" : "Gastric ulcer without hemorrhage AND without perforation",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "73481001",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 192671,
							"CONCEPT_NAME" : "Gastrointestinal hemorrhage",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "74474003",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4101104,
							"CONCEPT_NAME" : "Gastrojejunal ulcer without hemorrhage AND without perforation",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "2783007",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 443530,
							"CONCEPT_NAME" : "Hematochezia",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "405729008",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 197925,
							"CONCEPT_NAME" : "Hemorrhage of rectum and anus",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "266464001",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4027663,
							"CONCEPT_NAME" : "Peptic ulcer",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "13200003",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4291028,
							"CONCEPT_NAME" : "Peptic ulcer without hemorrhage AND without perforation",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "37442009",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					}
				]
			}
		}
	]
>>>