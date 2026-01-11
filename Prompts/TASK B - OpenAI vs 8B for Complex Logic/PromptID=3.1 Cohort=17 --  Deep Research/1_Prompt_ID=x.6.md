You will receive a JSON file and a JSON Configuration.

Your task is to filter the array PrimaryCriteria.CriteriaList.

Rules
	1.	Each item inside CriteriaList contains exactly one top-level key (e.g., ConditionOccurrence, Observation, DrugExposure).
	2.	For each item:
	- Read its top-level key.
	- Look up the same key in JSON Configuration.
	3.	If the configuration value is true:
	- Keep the entire item unchanged.
	4.	If the configuration value is false:
	- Remove the entire item from CriteriaList.
	- Do not keep the item in any form.
	5.	The output CriteriaList must contain only items whose top-level key is mapped to true.
	6.	Do not preserve the original list length.
	7.	Do not add, rename, or modify any fields or keys.
	8.	Keep all other parts of the JSON unchanged.

STRICT MODE
	- DO NOT output Python, pseudocode, or any programming language (Mandatory)
    - Return only the final filtered JSON.
	- No reasoning.
	- No explanations.
	- No comments.

JSON file:
<<<
{ "cdmVersionRange": ">=5.0.0", "PrimaryCriteria": { "CriteriaList": [ { "ConditionOccurrence": { "CodesetId": 9, "ConditionTypeExclude": false } }, { "Observation": { "CodesetId": 8, "ObservationTypeExclude": false } }, { "DrugExposure": { "CodesetId": 8, "First": true, "DrugTypeExclude": false } } ], "ObservationWindow": { "PriorDays": 365, "PostDays": null }, "PrimaryCriteriaLimit": { "Type": "First" } } }
>>>

JSON Configuration:
<<<
{ "ConditionOccurrence": false, "Observation": false, "DrugExposure": true }
>>>

