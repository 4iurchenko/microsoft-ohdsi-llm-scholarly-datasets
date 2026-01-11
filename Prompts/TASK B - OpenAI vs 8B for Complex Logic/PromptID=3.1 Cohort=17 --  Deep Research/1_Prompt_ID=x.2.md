You will receive text that may describe a Cohort for OHDSI OMOP.

Your task:

1. Extract text information as is from the Cohort Description related to "Cohort Entry Events"
2. Particularly, return only the list of event to be observed

Do not change information.
Do not create extra explanations.
Only that part of that information.

STRICT MODE:
Return only the final output. No reasoning, no commentary.

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