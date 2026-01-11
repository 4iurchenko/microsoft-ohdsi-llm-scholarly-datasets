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

Concept Set Data JSON:
<<<
[
		{
			"id" : 2,
			"name" : "[HowOften] Beta blockers",
			"expression" : {
				"items" : [
					{
						"concept" : {
							"CONCEPT_ID" : 1319998,
							"CONCEPT_NAME" : "acebutolol",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "149",
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
							"CONCEPT_ID" : 1314002,
							"CONCEPT_NAME" : "atenolol",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "1202",
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
							"CONCEPT_ID" : 1322081,
							"CONCEPT_NAME" : "betaxolol",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "1520",
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
							"CONCEPT_ID" : 1338005,
							"CONCEPT_NAME" : "bisoprolol",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "19484",
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
							"CONCEPT_ID" : 1346823,
							"CONCEPT_NAME" : "carvedilol",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "20352",
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
							"CONCEPT_ID" : 1386957,
							"CONCEPT_NAME" : "labetalol",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "6185",
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
							"CONCEPT_ID" : 1307046,
							"CONCEPT_NAME" : "metoprolol",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "6918",
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
							"CONCEPT_ID" : 1313200,
							"CONCEPT_NAME" : "nadolol",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "7226",
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
							"CONCEPT_ID" : 1314577,
							"CONCEPT_NAME" : "nebivolol",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "31555",
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
							"CONCEPT_ID" : 1327978,
							"CONCEPT_NAME" : "penbutolol",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "7973",
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
							"CONCEPT_ID" : 1345858,
							"CONCEPT_NAME" : "pindolol",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "8332",
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
							"CONCEPT_ID" : 1353766,
							"CONCEPT_NAME" : "propranolol",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "8787",
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
		}
	]

>>>