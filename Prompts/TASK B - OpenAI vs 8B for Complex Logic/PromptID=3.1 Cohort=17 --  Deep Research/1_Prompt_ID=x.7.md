You will receive a JSON file and a JSON Configuration.

Task
- Filter PrimaryCriteria.CriteriaList.

Rules
	1.	Each item in CriteriaList has one top-level key.
	2.	If that key maps to true in JSON Configuration → keep the item unchanged.
	3.	If that key maps to false → remove the entire item.
	4.	The final CriteriaList must contain only items mapped to true.
	5.	Do not change keys, field names, or any other parts of the JSON.

STRICT MODE
	- Return only the final JSON.
	- No reasoning, no explanations.

JSON file:
<<<
{ "cdmVersionRange": ">=5.0.0", "PrimaryCriteria": { "CriteriaList": [ { "ConditionOccurrence": { "CodesetId": 9, "ConditionTypeExclude": false } }, { "Observation": { "CodesetId": 8, "ObservationTypeExclude": false } }, { "DrugExposure": { "CodesetId": 8, "First": true, "DrugTypeExclude": false } } ], "ObservationWindow": { "PriorDays": 365, "PostDays": null }, "PrimaryCriteriaLimit": { "Type": "First" } } }
>>>

JSON Configuration:
<<<
{ "ConditionOccurrence": false, "Observation": false, "DrugExposure": true }
>>>

