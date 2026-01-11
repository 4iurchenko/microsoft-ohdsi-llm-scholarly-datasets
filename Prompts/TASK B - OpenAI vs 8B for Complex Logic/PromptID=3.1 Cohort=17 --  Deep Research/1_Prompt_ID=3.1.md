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

People with continuous observation of 365 days before event may enter the cohort when observing any of the following:

1. drug exposure of '[HowOften] IL23 inhibitors' for the first time in the person's history.

Limit cohort entry events to the earliest event per person.

### Inclusion Criteria

#### 1. nested in Plaque psoriasis

Entry events having at least 1 condition occurrence of 'Plaque psoriasis', starting anytime on or before cohort entry start date.

### Cohort Exit

The cohort end date will be based on a continuous exposure to '[HowOften] IL23 inhibitors':
allowing 90 days between exposures, adding 0 days after exposure ends, and using days supply and exposure end date for exposure duration.

### Cohort Eras

Entry events will be combined into cohort eras if they are within 0 days of each other.

### Concept sets:

### [HowOften] IL23 inhibitors
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|35200139|tildrakizumab|2053436|RxNorm|NO|YES|NO|
|1511348|risankizumab|2166040|RxNorm|NO|YES|NO|
|1593700|guselkumab|1928588|RxNorm|NO|YES|NO|
  

### Plaque psoriasis
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|140168|Psoriasis|9014002|SNOMED|NO|NO|NO|
|4307925|Psoriasis vulgaris|200975007|SNOMED|NO|YES|NO|
|4063431|Plaque psoriasis|200965009|SNOMED|NO|YES|NO|
>>>

Concept Set Data JSON:
<<<
[
		{
			"id" : 8,
			"name" : "[HowOften] IL23 inhibitors",
			"expression" : {
				"items" : [
					{
						"concept" : {
							"CONCEPT_ID" : 35200139,
							"CONCEPT_NAME" : "tildrakizumab",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "2053436",
							"DOMAIN_ID" : "Drug",
							"VOCABULARY_ID" : "RxNorm",
							"CONCEPT_CLASS_ID" : "Ingredient"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 1511348,
							"CONCEPT_NAME" : "risankizumab",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "2166040",
							"DOMAIN_ID" : "Drug",
							"VOCABULARY_ID" : "RxNorm",
							"CONCEPT_CLASS_ID" : "Ingredient"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 1593700,
							"CONCEPT_NAME" : "guselkumab",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "1928588",
							"DOMAIN_ID" : "Drug",
							"VOCABULARY_ID" : "RxNorm",
							"CONCEPT_CLASS_ID" : "Ingredient"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					}
				]
			}
		},
		{
			"id" : 9,
			"name" : "Plaque psoriasis",
			"expression" : {
				"items" : [
					{
						"concept" : {
							"CONCEPT_ID" : 140168,
							"CONCEPT_NAME" : "Psoriasis",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "9014002",
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
							"CONCEPT_ID" : 4307925,
							"CONCEPT_NAME" : "Psoriasis vulgaris",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "200975007",
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
							"CONCEPT_ID" : 4063431,
							"CONCEPT_NAME" : "Plaque psoriasis",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "200965009",
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