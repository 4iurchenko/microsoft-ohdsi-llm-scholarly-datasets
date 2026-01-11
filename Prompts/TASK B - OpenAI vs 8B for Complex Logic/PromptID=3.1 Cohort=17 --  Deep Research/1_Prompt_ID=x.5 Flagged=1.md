You will receive a JSON file and Configuration file.

Your task:

1. Extract a cleaned JSON file, by keeping the items from PrimaryCriteria -> CriteriaList only if these items are true in the JSON Configuration added below

Do not change column names.
Do not create extra explanations.

STRICT MODE:
Return only the final output. No reasoning, no commentary.

JSON file:
<<<
{ "cdmVersionRange": ">=5.0.0", "PrimaryCriteria": { "CriteriaList": [ { "ConditionOccurrence": { "CodesetId": 9, "ConditionTypeExclude": false } }, { "Observation": { "CodesetId": 8, "ObservationTypeExclude": false } }, { "DrugExposure": { "CodesetId": 8, "First": true, "DrugTypeExclude": false } } ], "ObservationWindow": { "PriorDays": 365, "PostDays": null }, "PrimaryCriteriaLimit": { "Type": "First" } } }
>>>

JSON Configuration:
<<<
{ "ConditionOccurrence": "false", "Observation": "false", "DrugExposure": "true" }
>>>