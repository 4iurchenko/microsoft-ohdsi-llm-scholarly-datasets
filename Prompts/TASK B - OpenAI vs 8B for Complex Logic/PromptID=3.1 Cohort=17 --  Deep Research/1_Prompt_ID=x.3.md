You will receive text that may describe a Cohort for OHDSI OMOP.

Your task:

1. Extract what types of events are mentioned in the Cohort Entry Events
2. Return a JSON with this structure:

{
	"ConditionOccurrence": true/false,
	"Observation": true/false,
	"DrugExposure": true/false
}

Do not change information.
Do not create extra explanations.
Only that part of that information.

STRICT MODE:
Return only the final output. No reasoning, no commentary.

Cohort Entry Events:
<<<
1. drug exposure of '[HowOften] IL23 inhibitors' for the first time in the person's history.
>>>