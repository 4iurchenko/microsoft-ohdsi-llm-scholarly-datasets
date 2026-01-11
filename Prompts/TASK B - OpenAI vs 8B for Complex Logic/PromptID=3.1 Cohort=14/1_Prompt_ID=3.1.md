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

Concept Set Data JSON:
<<<
[
		{
			"id" : 1,
			"name" : "Suicide or injury that is potentially self inflicted",
			"expression" : {
				"items" : [
					{
						"concept" : {
							"CONCEPT_ID" : 439235,
							"CONCEPT_NAME" : "Self inflicted injury",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "276853009",
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
							"CONCEPT_ID" : 4181216,
							"CONCEPT_NAME" : "Self-administered poisoning",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "363293009",
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
							"CONCEPT_ID" : 444362,
							"CONCEPT_NAME" : "Suicidal deliberate poisoning",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "86849004",
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
							"CONCEPT_ID" : 440925,
							"CONCEPT_NAME" : "Suicide",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "44301001",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4303690,
							"CONCEPT_NAME" : "Intentionally harming self",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "418420002",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Event"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4219484,
							"CONCEPT_NAME" : "Suicide attempt",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "82313006",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 435446,
							"CONCEPT_NAME" : "Late effect of self inflicted injury",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "219174008",
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
							"CONCEPT_ID" : 4092411,
							"CONCEPT_NAME" : "Self-injurious behavior",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "248062006",
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
							"CONCEPT_ID" : 443272,
							"CONCEPT_NAME" : "Injury undetermined whether accidentally or purposely inflicted",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "269735005",
							"DOMAIN_ID" : "Condition",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					}
				]
			}
		}
	]

>>>