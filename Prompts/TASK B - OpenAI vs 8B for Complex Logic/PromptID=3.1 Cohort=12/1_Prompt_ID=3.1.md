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

1. condition occurrences of 'Influenza (including complications) - Conditions'.

2. measurements of 'Influenza (pre-coordinated Positive Measurements)'.

3. measurements of 'Influenza testing (excluding Ab testing)', with value as concept: "detected", "detected", "positive", "positive", "present" or "present".

4. observations of 'Influenza testing (excluding Ab testing)', with value as concept: "detected", "detected", "positive", "positive", "present" or "present".

### Cohort Exit

The cohort end date will be offset from index event's end date plus 0 days.

### Cohort Eras

Entry events will be combined into cohort eras if they are within 0 days of each other.

### Concept sets:

### Influenza (including complications) - Conditions
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|4146943|Encephalitis due to influenza|309789002|SNOMED|NO|YES|NO|
|46274061|Encephalopathy due to Influenza A virus|10677711000119101|SNOMED|NO|YES|NO|
|4266367|Influenza|6142004|SNOMED|NO|YES|NO|
|42537960|Influenza with CNS disorder|738276008|SNOMED|NO|YES|NO|
|4112824|Influenza with gastrointestinal tract involvement|195929004|SNOMED|NO|YES|NO|
|4299935|Myocarditis due to influenza virus|78046005|SNOMED|NO|YES|NO|
|46269706|Otitis media due to influenza|10624951000119108|SNOMED|NO|YES|NO|
|763011|Pneumonia due to Influenza A virus|434921000124108|SNOMED|NO|YES|NO|
|4042202|Post-influenza encephalitis|230188005|SNOMED|YES|YES|NO|
  

### Influenza (pre-coordinated Positive Measurements)
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|45757528|Influenza A virus present|181000124108|SNOMED|NO|YES|NO|
|4262075|Influenza B virus present|441345003|SNOMED|NO|YES|NO|
  

### Influenza testing (excluding Ab testing)
|Concept ID|Concept Name|Code|Vocabulary|Excluded|Descendants|Mapped
|:---|:---------------------------------------|:--|:-----|:--:|:--:|:--:|
|44789502|Avian infl virus nucl acid det|204271000000104|SNOMED|NO|YES|NO|
|37392948|Avian influenza virus RNA (ribonucleic acid) detection assay|1010721000000107|SNOMED|NO|YES|NO|
|37394408|Avian influenza virus nucleic acid detection assay|1031631000000102|SNOMED|NO|YES|NO|
|36676235|Detection of Influenza A virus using PCR - polymerase chain reaction technique|772835009|SNOMED|NO|YES|NO|
|37066972|Equine influenza virus A1 Ab | Serum | Microbiology|LP379343-9|LOINC|YES|YES|NO|
|3001703|Equine influenza virus A1 Ag [Titer] in Unspecified specimen by Hemagglutination inhibition|23102-7|LOINC|NO|YES|NO|
|3016424|Equine influenza virus A1 Ag [Units/volume] in Unspecified specimen|31821-2|LOINC|NO|YES|NO|
|3002696|Equine influenza virus A2 Ab [Presence] in Serum|15470-8|LOINC|YES|YES|NO|
|3000619|Equine influenza virus A2 Ab [Presence] in Serum by Complement fixation|23103-5|LOINC|YES|YES|NO|
|3023674|Equine influenza virus A2 Ab [Titer] in Serum|22303-2|LOINC|YES|YES|NO|
|3001047|Equine influenza virus A2 Ab [Titer] in Serum by Hemagglutination inhibition|15471-6|LOINC|YES|YES|NO|
|3007341|Equine influenza virus A2 Ab [Units/volume] in Serum|31380-9|LOINC|YES|YES|NO|
|3038149|Equine influenza virus A2 Ag [Titer] in Unspecified specimen by Hemagglutination inhibition|23104-3|LOINC|NO|YES|NO|
|3016676|Equine influenza virus A2 Ag [Units/volume] in Unspecified specimen|31822-0|LOINC|NO|YES|NO|
|3017256|Equine influenza virus Ag [Presence] in Nose|31823-8|LOINC|NO|YES|NO|
|3020370|Equine influenza virus Ag [Presence] in Nose by Immunoassay|15472-4|LOINC|NO|YES|NO|
|2213094|Infectious agent antigen detection by immunoassay technique, (eg, enzyme immunoassay [EIA], enzyme-linked immunosorbent assay [ELISA], immunochemiluminometric assay [IMCA]) qualitative or semiquantitative, multiple-step method; Influenza, A or B, each|87400|CPT4|NO|YES|NO|
|2213181|Infectious agent antigen detection by immunoassay with direct optical observation; Influenza|87804|CPT4|NO|YES|NO|
|2213063|Infectious agent antigen detection by immunofluorescent technique; influenza A virus|87276|CPT4|NO|YES|NO|
|2213062|Infectious agent antigen detection by immunofluorescent technique; influenza B virus|87275|CPT4|NO|YES|NO|
|40757077|Infectious agent detection by nucleic acid (DNA or RNA); influenza virus, for multiple types or sub-types, includes multiplex reverse transcription, when performed, and multiplex amplified probe technique, first 2 types or sub-types|87502|CPT4|NO|YES|NO|
|40756898|Infectious agent detection by nucleic acid (DNA or RNA); influenza virus, includes reverse transcription, when performed, and amplified probe technique, each type or subtype|87501|CPT4|NO|YES|NO|
|37398130|Influenza (A and B) serology|996211000000100|SNOMED|YES|YES|NO|
|4039357|Influenza A and B virus antigen assay|118089005|SNOMED|NO|YES|NO|
|4201049|Influenza A antibody level|315142009|SNOMED|YES|YES|NO|
|37393224|Influenza A antibody level|1014261000000103|SNOMED|YES|YES|NO|
|37392223|Influenza A antigen level|1001341000000106|SNOMED|NO|YES|NO|
|44806470|Influenza A nucleic acid detection|801631000000107|SNOMED|NO|YES|NO|
|37394297|Influenza A nucleic acid detection assay|1029881000000100|SNOMED|NO|YES|NO|
|44805899|Influenza A virus IgG antibody measurement|819431000000106|SNOMED|YES|YES|NO|
|4044987|Influenza A virus antigen assay|122349003|SNOMED|NO|YES|NO|
|45757528|Influenza A virus present|181000124108|SNOMED|YES|YES|NO|
|4039358|Influenza A, B, and C virus antigen assay|118090001|SNOMED|NO|YES|NO|
|37393225|Influenza B antibody level|1014271000000105|SNOMED|YES|YES|NO|
|4196405|Influenza B antibody level|315143004|SNOMED|YES|YES|NO|
|37392224|Influenza B antigen level|1001351000000109|SNOMED|NO|YES|NO|
|44807860|Influenza B nucleic acid detection|838281000000105|SNOMED|NO|YES|NO|
|37394300|Influenza B nucleic acid detection assay|1029911000000100|SNOMED|NO|YES|NO|
|44805900|Influenza B virus IgG antibody measurement|819441000000102|SNOMED|YES|YES|NO|
|4044988|Influenza B virus antigen assay|122350003|SNOMED|NO|YES|NO|
|4262075|Influenza B virus present|441345003|SNOMED|YES|YES|NO|
|37392761|Influenza B virus ribonucleic acid detection assay|1008251000000105|SNOMED|NO|YES|NO|
|40760327|Influenza vaccination received in Reporting Period [CMS Assessment]|57208-1|LOINC|YES|YES|NO|
|40653953|Influenza virus|LG32757-3|LOINC|NO|YES|NO|
|40655680|Influenza virus A & B Ag|Prid|Sys:ANYResp|LG34146-7|LOINC|NO|YES|NO|
|37048815|Influenza virus A Ab | Body fluid | Microbiology|LP378370-3|LOINC|YES|YES|NO|
|37058506|Influenza virus A Ab | Cerebral spinal fluid | Microbiology|LP378371-1|LOINC|YES|YES|NO|
|37055728|Influenza virus A Ab | Egg yolk | Microbiology|LP378372-9|LOINC|YES|YES|NO|
|37040765|Influenza virus A Ab | Serum | Microbiology|LP378373-7|LOINC|YES|YES|NO|
|37023170|Influenza virus A Ab/Positive control | Serum | Microbiology|LP378507-0|LOINC|YES|YES|NO|
|40655681|Influenza virus A Ag|PrThr|Sys:ANYResp|LG34020-4|LOINC|NO|YES|NO|
|37075082|Influenza virus A Bangkok Ab | Cerebral spinal fluid | Microbiology|LP378398-4|LOINC|YES|YES|NO|
|37041511|Influenza virus A Bangkok Ab | Serum | Microbiology|LP378399-2|LOINC|YES|YES|NO|
|37066453|Influenza virus A England Ab | Serum | Microbiology|LP378401-6|LOINC|YES|YES|NO|
|37057346|Influenza virus A H1 2009 pandemic Ab | Serum | Microbiology|LP378452-9|LOINC|YES|YES|NO|
|40655682|Influenza virus A H1 2009 pandemic RNA|PrThr|Sys:ANYResp|LG34094-9|LOINC|NO|YES|NO|
|37054344|Influenza virus A H1 Ab | Serum | Microbiology|LP378404-0|LOINC|YES|YES|NO|
|40655683|Influenza virus A H1 RNA|PrThr|Sys:ANYResp|LG34092-3|LOINC|NO|YES|NO|
|37022661|Influenza virus A H10 Ab | Serum | Microbiology|LP378442-0|LOINC|YES|YES|NO|
|37067997|Influenza virus A H11 Ab | Serum | Microbiology|LP378443-8|LOINC|YES|YES|NO|
|37028300|Influenza virus A H12 Ab | Serum | Microbiology|LP378444-6|LOINC|YES|YES|NO|
|37054453|Influenza virus A H13 Ab | Serum | Microbiology|LP378445-3|LOINC|YES|YES|NO|
|37036578|Influenza virus A H14 Ab | Serum | Microbiology|LP378446-1|LOINC|YES|YES|NO|
|37078464|Influenza virus A H15 Ab | Serum | Microbiology|LP378447-9|LOINC|YES|YES|NO|
|37067504|Influenza virus A H16 Ab | Serum | Microbiology|LP378448-7|LOINC|YES|YES|NO|
|37070652|Influenza virus A H2 Ab | Serum | Microbiology|LP378413-1|LOINC|YES|YES|NO|
|37048012|Influenza virus A H3 Ab | Serum | Microbiology|LP378414-9|LOINC|YES|YES|NO|
|40655684|Influenza virus A H3 RNA|PrThr|Sys:ANYResp|LG34093-1|LOINC|NO|YES|NO|
|37071077|Influenza virus A H4 Ab | Serum | Microbiology|LP378421-4|LOINC|YES|YES|NO|
|37042025|Influenza virus A H5 Ab | Serum | Microbiology|LP378422-2|LOINC|YES|YES|NO|
|40655685|Influenza virus A H5 Asian RNA|ThreshNum|Sys:ANYResp|LG34153-3|LOINC|NO|YES|NO|
|37024679|Influenza virus A H6 Ab | Serum | Microbiology|LP378431-3|LOINC|YES|YES|NO|
|37042070|Influenza virus A H7 Ab | Serum | Microbiology|LP378433-9|LOINC|YES|YES|NO|
|37052164|Influenza virus A H8 Ab | Serum | Microbiology|LP378438-8|LOINC|YES|YES|NO|
|37037245|Influenza virus A H9 Ab | Serum | Microbiology|LP378439-6|LOINC|YES|YES|NO|
|37072518|Influenza virus A Hong Kong Ab | Serum | Microbiology|LP378457-8|LOINC|YES|YES|NO|
|37044556|Influenza virus A IgA | Cerebral spinal fluid | Microbiology|LP378375-2|LOINC|YES|YES|NO|
|37025175|Influenza virus A IgA | Serum | Microbiology|LP378376-0|LOINC|YES|YES|NO|
|37063376|Influenza virus A IgG | Cerebral spinal fluid | Microbiology|LP378377-8|LOINC|YES|YES|NO|
|37068553|Influenza virus A IgG | Serum | Microbiology|LP378378-6|LOINC|YES|YES|NO|
|37045806|Influenza virus A IgM | Cerebral spinal fluid | Microbiology|LP378379-4|LOINC|YES|YES|NO|
|37036252|Influenza virus A IgM | Serum | Microbiology|LP378380-2|LOINC|YES|YES|NO|
|37064420|Influenza virus A Leningrad Ab | Serum | Microbiology|LP378459-4|LOINC|YES|YES|NO|
|37037941|Influenza virus A Mississippi Ab | Serum | Microbiology|LP378464-4|LOINC|YES|YES|NO|
|37062169|Influenza virus A N1 Ab | Serum | Microbiology|LP378466-9|LOINC|YES|YES|NO|
|37076139|Influenza virus A N2 Ab | Serum | Microbiology|LP378468-5|LOINC|YES|YES|NO|
|37034233|Influenza virus A N3 Ab | Serum | Microbiology|LP378470-1|LOINC|YES|YES|NO|
|37051887|Influenza virus A N4 Ab | Serum | Microbiology|LP378471-9|LOINC|YES|YES|NO|
|37075960|Influenza virus A N5 Ab | Serum | Microbiology|LP378472-7|LOINC|YES|YES|NO|
|37022372|Influenza virus A N6 Ab | Serum | Microbiology|LP378473-5|LOINC|YES|YES|NO|
|37031117|Influenza virus A N7 Ab | Serum | Microbiology|LP378474-3|LOINC|YES|YES|NO|
|37073627|Influenza virus A N8 Ab | Serum | Microbiology|LP378475-0|LOINC|YES|YES|NO|
|37057853|Influenza virus A N9 Ab | Serum | Microbiology|LP378476-8|LOINC|YES|YES|NO|
|37042870|Influenza virus A Phillipines Ab | Serum | Microbiology|LP378484-2|LOINC|YES|YES|NO|
|37075259|Influenza virus A Port Chalmers Ab | Serum | Microbiology|LP378491-7|LOINC|YES|YES|NO|
|40655686|Influenza virus A RNA|PrThr|Sys:ANYResp|LG34064-2|LOINC|NO|YES|NO|
|37030627|Influenza virus A Texas Ab | Serum | Microbiology|LP378505-4|LOINC|YES|YES|NO|
|37059249|Influenza virus A Victoria Ab | Serum | Microbiology|LP378506-2|LOINC|YES|YES|NO|
|37037961|Influenza virus A and B Ab | Body fluid | Microbiology|LP378508-8|LOINC|YES|YES|NO|
|37047321|Influenza virus A avian origin nucleoprotein Ab/Negative control | Serum | Microbiology|LP378397-6|LOINC|YES|YES|NO|
|37075847|Influenza virus A porcine origin nucleoprotein Ab.IgA/Positive control | XXX | Microbiology|LP378489-1|LOINC|YES|YES|NO|
|37073492|Influenza virus A porcine origin nucleoprotein Ab.IgG/Positive control | XXX | Microbiology|LP378490-9|LOINC|YES|YES|NO|
|37080282|Influenza virus A subtype|Prid|Sys:ANYResp|LG50856-0|LOINC|NO|YES|NO|
|37056311|Influenza virus A+B Ab | Body fluid | Microbiology|LP378509-6|LOINC|YES|YES|NO|
|37029363|Influenza virus A+B Ab | Serum | Microbiology|LP378510-4|LOINC|YES|YES|NO|
|40655687|Influenza virus A+B Ag|PrThr|Sys:ANYResp|LG34021-2|LOINC|NO|YES|NO|
|40655688|Influenza virus A+B+C Ag|PrThr|Sys:ANYResp|LG34022-0|LOINC|NO|YES|NO|
|37023424|Influenza virus Ab | Cerebral spinal fluid | Microbiology|LP378526-0|LOINC|YES|YES|NO|
|37073273|Influenza virus Ab | Serum | Microbiology|LP378527-8|LOINC|YES|YES|NO|
|37076384|Influenza virus B Ab | Body fluid | Microbiology|LP378529-4|LOINC|YES|YES|NO|
|37069805|Influenza virus B Ab | Cerebral spinal fluid | Microbiology|LP378530-2|LOINC|YES|YES|NO|
|37026917|Influenza virus B Ab | Serum | Microbiology|LP378531-0|LOINC|YES|YES|NO|
|40655689|Influenza virus B Ag|PrThr|Sys:ANYResp|LG34023-8|LOINC|NO|YES|NO|
|37048913|Influenza virus B IgA | Cerebral spinal fluid | Microbiology|LP378533-6|LOINC|YES|YES|NO|
|37074405|Influenza virus B IgA | Serum | Microbiology|LP378534-4|LOINC|YES|YES|NO|
|37040736|Influenza virus B IgG | Cerebral spinal fluid | Microbiology|LP378535-1|LOINC|YES|YES|NO|
|37076803|Influenza virus B IgG | Serum | Microbiology|LP378536-9|LOINC|YES|YES|NO|
|37075491|Influenza virus B IgM | Cerebral spinal fluid | Microbiology|LP378537-7|LOINC|YES|YES|NO|
|37072743|Influenza virus B IgM | Serum | Microbiology|LP378538-5|LOINC|YES|YES|NO|
|40655690|Influenza virus B RNA|PrThr|Sys:ANYResp|LG34065-9|LOINC|NO|YES|NO|
|4047171|Influenza virus culture|122262002|SNOMED|NO|YES|NO|
|40655691|Influenza virus identified|Prid|Sys:ANYResp|LG34086-5|LOINC|NO|YES|NO|
|40758391|Influenza virus immunization status|55262-0|LOINC|YES|YES|NO|
|42869813|Influenza virus vaccination received|72058-1|LOINC|YES|YES|NO|
|40758149|Influenza virus vaccine received in facility [CMS Assessment]|55019-4|LOINC|YES|YES|NO|
|3043198|Influenza virus vaccine received in facility [Minimum Data Set]|45953-7|LOINC|YES|YES|NO|
|4017924|Influenzavirus antibody assay|104310006|SNOMED|YES|YES|NO|
|40484560|Measurement of Influenza A virus subtype H1N1 antigen|443995002|SNOMED|NO|YES|NO|
|37050279|Porcine influenza virus A Ab | Serum | Microbiology|LP379495-7|LOINC|YES|YES|NO|
|3002988|Porcine influenza virus A Ag [Presence] in Tissue by Immune stain|23769-3|LOINC|NO|YES|NO|
|3026510|Swine influenza virus Ab [Presence] in Serum|23437-7|LOINC|YES|YES|NO|
|3027889|Swine influenza virus Ab [Presence] in Serum by Hemagglutination inhibition|23438-5|LOINC|YES|YES|NO|
|3002646|Swine influenza virus Ag [Presence] in Tissue by Immune stain|23782-6|LOINC|NO|YES|NO|
|3003682|Swine influenza virus Ag [Presence] in Tissue by Immunofluorescence|23781-8|LOINC|NO|YES|NO|
>>>

Concept Set Data JSON:
<<<
[
		{
			"id" : 0,
			"name" : "Influenza (including complications) - Conditions",
			"expression" : {
				"items" : [
					{
						"concept" : {
							"CONCEPT_ID" : 4146943,
							"CONCEPT_NAME" : "Encephalitis due to influenza",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "309789002",
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
							"CONCEPT_ID" : 46274061,
							"CONCEPT_NAME" : "Encephalopathy due to Influenza A virus",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "10677711000119101",
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
							"CONCEPT_ID" : 4266367,
							"CONCEPT_NAME" : "Influenza",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "6142004",
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
							"CONCEPT_ID" : 42537960,
							"CONCEPT_NAME" : "Influenza with CNS disorder",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "738276008",
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
							"CONCEPT_ID" : 4112824,
							"CONCEPT_NAME" : "Influenza with gastrointestinal tract involvement",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "195929004",
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
							"CONCEPT_ID" : 4299935,
							"CONCEPT_NAME" : "Myocarditis due to influenza virus",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "78046005",
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
							"CONCEPT_ID" : 46269706,
							"CONCEPT_NAME" : "Otitis media due to influenza",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "10624951000119108",
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
							"CONCEPT_ID" : 763011,
							"CONCEPT_NAME" : "Pneumonia due to Influenza A virus",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "434921000124108",
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
							"CONCEPT_ID" : 4042202,
							"CONCEPT_NAME" : "Post-influenza encephalitis",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "230188005",
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
		},
		{
			"id" : 1,
			"name" : "Influenza (pre-coordinated Positive Measurements)",
			"expression" : {
				"items" : [
					{
						"concept" : {
							"CONCEPT_ID" : 45757528,
							"CONCEPT_NAME" : "Influenza A virus present",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "181000124108",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4262075,
							"CONCEPT_NAME" : "Influenza B virus present",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "441345003",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					}
				]
			}
		},
		{
			"id" : 2,
			"name" : "Influenza testing (excluding Ab testing)",
			"expression" : {
				"items" : [
					{
						"concept" : {
							"CONCEPT_ID" : 44789502,
							"CONCEPT_NAME" : "Avian infl virus nucl acid det",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "204271000000104",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Procedure"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37392948,
							"CONCEPT_NAME" : "Avian influenza virus RNA (ribonucleic acid) detection assay",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "1010721000000107",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Observable Entity"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37394408,
							"CONCEPT_NAME" : "Avian influenza virus nucleic acid detection assay",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "1031631000000102",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Observable Entity"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 36676235,
							"CONCEPT_NAME" : "Detection of Influenza A virus using PCR - polymerase chain reaction technique",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "772835009",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Procedure"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37066972,
							"CONCEPT_NAME" : "Equine influenza virus A1 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP379343-9",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 3001703,
							"CONCEPT_NAME" : "Equine influenza virus A1 Ag [Titer] in Unspecified specimen by Hemagglutination inhibition",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "23102-7",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Lab Test"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 3016424,
							"CONCEPT_NAME" : "Equine influenza virus A1 Ag [Units/volume] in Unspecified specimen",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "31821-2",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Lab Test"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 3002696,
							"CONCEPT_NAME" : "Equine influenza virus A2 Ab [Presence] in Serum",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "15470-8",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Lab Test"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 3000619,
							"CONCEPT_NAME" : "Equine influenza virus A2 Ab [Presence] in Serum by Complement fixation",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "23103-5",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Lab Test"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 3023674,
							"CONCEPT_NAME" : "Equine influenza virus A2 Ab [Titer] in Serum",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "22303-2",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Lab Test"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 3001047,
							"CONCEPT_NAME" : "Equine influenza virus A2 Ab [Titer] in Serum by Hemagglutination inhibition",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "15471-6",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Lab Test"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 3007341,
							"CONCEPT_NAME" : "Equine influenza virus A2 Ab [Units/volume] in Serum",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "31380-9",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Lab Test"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 3038149,
							"CONCEPT_NAME" : "Equine influenza virus A2 Ag [Titer] in Unspecified specimen by Hemagglutination inhibition",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "23104-3",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Lab Test"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 3016676,
							"CONCEPT_NAME" : "Equine influenza virus A2 Ag [Units/volume] in Unspecified specimen",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "31822-0",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Lab Test"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 3017256,
							"CONCEPT_NAME" : "Equine influenza virus Ag [Presence] in Nose",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "31823-8",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Lab Test"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 3020370,
							"CONCEPT_NAME" : "Equine influenza virus Ag [Presence] in Nose by Immunoassay",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "15472-4",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Lab Test"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 2213094,
							"CONCEPT_NAME" : "Infectious agent antigen detection by immunoassay technique, (eg, enzyme immunoassay [EIA], enzyme-linked immunosorbent assay [ELISA], immunochemiluminometric assay [IMCA]) qualitative or semiquantitative, multiple-step method; Influenza, A or B, each",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "87400",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "CPT4",
							"CONCEPT_CLASS_ID" : "CPT4"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 2213181,
							"CONCEPT_NAME" : "Infectious agent antigen detection by immunoassay with direct optical observation; Influenza",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "87804",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "CPT4",
							"CONCEPT_CLASS_ID" : "CPT4"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 2213063,
							"CONCEPT_NAME" : "Infectious agent antigen detection by immunofluorescent technique; influenza A virus",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "87276",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "CPT4",
							"CONCEPT_CLASS_ID" : "CPT4"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 2213062,
							"CONCEPT_NAME" : "Infectious agent antigen detection by immunofluorescent technique; influenza B virus",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "87275",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "CPT4",
							"CONCEPT_CLASS_ID" : "CPT4"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40757077,
							"CONCEPT_NAME" : "Infectious agent detection by nucleic acid (DNA or RNA); influenza virus, for multiple types or sub-types, includes multiplex reverse transcription, when performed, and multiplex amplified probe technique, first 2 types or sub-types",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "87502",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "CPT4",
							"CONCEPT_CLASS_ID" : "CPT4"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40756898,
							"CONCEPT_NAME" : "Infectious agent detection by nucleic acid (DNA or RNA); influenza virus, includes reverse transcription, when performed, and amplified probe technique, each type or subtype",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "87501",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "CPT4",
							"CONCEPT_CLASS_ID" : "CPT4"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37398130,
							"CONCEPT_NAME" : "Influenza (A and B) serology",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "996211000000100",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Observable Entity"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4039357,
							"CONCEPT_NAME" : "Influenza A and B virus antigen assay",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "118089005",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Procedure"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4201049,
							"CONCEPT_NAME" : "Influenza A antibody level",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "315142009",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Procedure"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37393224,
							"CONCEPT_NAME" : "Influenza A antibody level",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "1014261000000103",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Observable Entity"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37392223,
							"CONCEPT_NAME" : "Influenza A antigen level",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "1001341000000106",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Observable Entity"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 44806470,
							"CONCEPT_NAME" : "Influenza A nucleic acid detection",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "801631000000107",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Procedure"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37394297,
							"CONCEPT_NAME" : "Influenza A nucleic acid detection assay",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "1029881000000100",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Observable Entity"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 44805899,
							"CONCEPT_NAME" : "Influenza A virus IgG antibody measurement",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "819431000000106",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Procedure"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4044987,
							"CONCEPT_NAME" : "Influenza A virus antigen assay",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "122349003",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Procedure"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 45757528,
							"CONCEPT_NAME" : "Influenza A virus present",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "181000124108",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4039358,
							"CONCEPT_NAME" : "Influenza A, B, and C virus antigen assay",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "118090001",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Procedure"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37393225,
							"CONCEPT_NAME" : "Influenza B antibody level",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "1014271000000105",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Observable Entity"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4196405,
							"CONCEPT_NAME" : "Influenza B antibody level",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "315143004",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Procedure"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37392224,
							"CONCEPT_NAME" : "Influenza B antigen level",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "1001351000000109",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Observable Entity"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 44807860,
							"CONCEPT_NAME" : "Influenza B nucleic acid detection",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "838281000000105",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Procedure"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37394300,
							"CONCEPT_NAME" : "Influenza B nucleic acid detection assay",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "1029911000000100",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Observable Entity"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 44805900,
							"CONCEPT_NAME" : "Influenza B virus IgG antibody measurement",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "819441000000102",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Procedure"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4044988,
							"CONCEPT_NAME" : "Influenza B virus antigen assay",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "122350003",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Procedure"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4262075,
							"CONCEPT_NAME" : "Influenza B virus present",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "441345003",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Clinical Finding"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37392761,
							"CONCEPT_NAME" : "Influenza B virus ribonucleic acid detection assay",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "1008251000000105",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Observable Entity"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40760327,
							"CONCEPT_NAME" : "Influenza vaccination received in Reporting Period [CMS Assessment]",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "57208-1",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Survey"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40653953,
							"CONCEPT_NAME" : "Influenza virus",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LG32757-3",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Group"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40655680,
							"CONCEPT_NAME" : "Influenza virus A & B Ag|Prid|Sys:ANYResp",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LG34146-7",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Group"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37048815,
							"CONCEPT_NAME" : "Influenza virus A Ab | Body fluid | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378370-3",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37058506,
							"CONCEPT_NAME" : "Influenza virus A Ab | Cerebral spinal fluid | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378371-1",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37055728,
							"CONCEPT_NAME" : "Influenza virus A Ab | Egg yolk | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378372-9",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37040765,
							"CONCEPT_NAME" : "Influenza virus A Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378373-7",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37023170,
							"CONCEPT_NAME" : "Influenza virus A Ab/Positive control | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378507-0",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40655681,
							"CONCEPT_NAME" : "Influenza virus A Ag|PrThr|Sys:ANYResp",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LG34020-4",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Group"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37075082,
							"CONCEPT_NAME" : "Influenza virus A Bangkok Ab | Cerebral spinal fluid | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378398-4",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37041511,
							"CONCEPT_NAME" : "Influenza virus A Bangkok Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378399-2",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37066453,
							"CONCEPT_NAME" : "Influenza virus A England Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378401-6",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37057346,
							"CONCEPT_NAME" : "Influenza virus A H1 2009 pandemic Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378452-9",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40655682,
							"CONCEPT_NAME" : "Influenza virus A H1 2009 pandemic RNA|PrThr|Sys:ANYResp",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LG34094-9",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Group"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37054344,
							"CONCEPT_NAME" : "Influenza virus A H1 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378404-0",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40655683,
							"CONCEPT_NAME" : "Influenza virus A H1 RNA|PrThr|Sys:ANYResp",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LG34092-3",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Group"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37022661,
							"CONCEPT_NAME" : "Influenza virus A H10 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378442-0",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37067997,
							"CONCEPT_NAME" : "Influenza virus A H11 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378443-8",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37028300,
							"CONCEPT_NAME" : "Influenza virus A H12 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378444-6",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37054453,
							"CONCEPT_NAME" : "Influenza virus A H13 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378445-3",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37036578,
							"CONCEPT_NAME" : "Influenza virus A H14 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378446-1",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37078464,
							"CONCEPT_NAME" : "Influenza virus A H15 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378447-9",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37067504,
							"CONCEPT_NAME" : "Influenza virus A H16 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378448-7",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37070652,
							"CONCEPT_NAME" : "Influenza virus A H2 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378413-1",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37048012,
							"CONCEPT_NAME" : "Influenza virus A H3 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378414-9",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40655684,
							"CONCEPT_NAME" : "Influenza virus A H3 RNA|PrThr|Sys:ANYResp",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LG34093-1",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Group"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37071077,
							"CONCEPT_NAME" : "Influenza virus A H4 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378421-4",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37042025,
							"CONCEPT_NAME" : "Influenza virus A H5 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378422-2",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40655685,
							"CONCEPT_NAME" : "Influenza virus A H5 Asian RNA|ThreshNum|Sys:ANYResp",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LG34153-3",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Group"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37024679,
							"CONCEPT_NAME" : "Influenza virus A H6 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378431-3",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37042070,
							"CONCEPT_NAME" : "Influenza virus A H7 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378433-9",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37052164,
							"CONCEPT_NAME" : "Influenza virus A H8 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378438-8",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37037245,
							"CONCEPT_NAME" : "Influenza virus A H9 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378439-6",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37072518,
							"CONCEPT_NAME" : "Influenza virus A Hong Kong Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378457-8",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37044556,
							"CONCEPT_NAME" : "Influenza virus A IgA | Cerebral spinal fluid | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378375-2",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37025175,
							"CONCEPT_NAME" : "Influenza virus A IgA | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378376-0",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37063376,
							"CONCEPT_NAME" : "Influenza virus A IgG | Cerebral spinal fluid | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378377-8",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37068553,
							"CONCEPT_NAME" : "Influenza virus A IgG | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378378-6",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37045806,
							"CONCEPT_NAME" : "Influenza virus A IgM | Cerebral spinal fluid | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378379-4",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37036252,
							"CONCEPT_NAME" : "Influenza virus A IgM | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378380-2",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37064420,
							"CONCEPT_NAME" : "Influenza virus A Leningrad Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378459-4",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37037941,
							"CONCEPT_NAME" : "Influenza virus A Mississippi Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378464-4",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37062169,
							"CONCEPT_NAME" : "Influenza virus A N1 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378466-9",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37076139,
							"CONCEPT_NAME" : "Influenza virus A N2 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378468-5",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37034233,
							"CONCEPT_NAME" : "Influenza virus A N3 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378470-1",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37051887,
							"CONCEPT_NAME" : "Influenza virus A N4 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378471-9",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37075960,
							"CONCEPT_NAME" : "Influenza virus A N5 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378472-7",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37022372,
							"CONCEPT_NAME" : "Influenza virus A N6 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378473-5",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37031117,
							"CONCEPT_NAME" : "Influenza virus A N7 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378474-3",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37073627,
							"CONCEPT_NAME" : "Influenza virus A N8 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378475-0",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37057853,
							"CONCEPT_NAME" : "Influenza virus A N9 Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378476-8",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37042870,
							"CONCEPT_NAME" : "Influenza virus A Phillipines Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378484-2",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37075259,
							"CONCEPT_NAME" : "Influenza virus A Port Chalmers Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378491-7",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40655686,
							"CONCEPT_NAME" : "Influenza virus A RNA|PrThr|Sys:ANYResp",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LG34064-2",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Group"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37030627,
							"CONCEPT_NAME" : "Influenza virus A Texas Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378505-4",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37059249,
							"CONCEPT_NAME" : "Influenza virus A Victoria Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378506-2",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37037961,
							"CONCEPT_NAME" : "Influenza virus A and B Ab | Body fluid | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378508-8",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37047321,
							"CONCEPT_NAME" : "Influenza virus A avian origin nucleoprotein Ab/Negative control | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378397-6",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37075847,
							"CONCEPT_NAME" : "Influenza virus A porcine origin nucleoprotein Ab.IgA/Positive control | XXX | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378489-1",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37073492,
							"CONCEPT_NAME" : "Influenza virus A porcine origin nucleoprotein Ab.IgG/Positive control | XXX | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378490-9",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37080282,
							"CONCEPT_NAME" : "Influenza virus A subtype|Prid|Sys:ANYResp",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LG50856-0",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Group"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37056311,
							"CONCEPT_NAME" : "Influenza virus A+B Ab | Body fluid | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378509-6",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37029363,
							"CONCEPT_NAME" : "Influenza virus A+B Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378510-4",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40655687,
							"CONCEPT_NAME" : "Influenza virus A+B Ag|PrThr|Sys:ANYResp",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LG34021-2",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Group"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40655688,
							"CONCEPT_NAME" : "Influenza virus A+B+C Ag|PrThr|Sys:ANYResp",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LG34022-0",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Group"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37023424,
							"CONCEPT_NAME" : "Influenza virus Ab | Cerebral spinal fluid | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378526-0",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37073273,
							"CONCEPT_NAME" : "Influenza virus Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378527-8",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37076384,
							"CONCEPT_NAME" : "Influenza virus B Ab | Body fluid | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378529-4",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37069805,
							"CONCEPT_NAME" : "Influenza virus B Ab | Cerebral spinal fluid | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378530-2",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37026917,
							"CONCEPT_NAME" : "Influenza virus B Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378531-0",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40655689,
							"CONCEPT_NAME" : "Influenza virus B Ag|PrThr|Sys:ANYResp",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LG34023-8",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Group"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37048913,
							"CONCEPT_NAME" : "Influenza virus B IgA | Cerebral spinal fluid | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378533-6",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37074405,
							"CONCEPT_NAME" : "Influenza virus B IgA | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378534-4",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37040736,
							"CONCEPT_NAME" : "Influenza virus B IgG | Cerebral spinal fluid | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378535-1",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37076803,
							"CONCEPT_NAME" : "Influenza virus B IgG | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378536-9",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37075491,
							"CONCEPT_NAME" : "Influenza virus B IgM | Cerebral spinal fluid | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378537-7",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37072743,
							"CONCEPT_NAME" : "Influenza virus B IgM | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP378538-5",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40655690,
							"CONCEPT_NAME" : "Influenza virus B RNA|PrThr|Sys:ANYResp",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LG34065-9",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Group"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4047171,
							"CONCEPT_NAME" : "Influenza virus culture",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "122262002",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Procedure"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40655691,
							"CONCEPT_NAME" : "Influenza virus identified|Prid|Sys:ANYResp",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LG34086-5",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Group"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40758391,
							"CONCEPT_NAME" : "Influenza virus immunization status",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "55262-0",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Clinical Observation"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 42869813,
							"CONCEPT_NAME" : "Influenza virus vaccination received",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "72058-1",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Survey"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40758149,
							"CONCEPT_NAME" : "Influenza virus vaccine received in facility [CMS Assessment]",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "55019-4",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Survey"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 3043198,
							"CONCEPT_NAME" : "Influenza virus vaccine received in facility [Minimum Data Set]",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "45953-7",
							"DOMAIN_ID" : "Observation",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Survey"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 4017924,
							"CONCEPT_NAME" : "Influenzavirus antibody assay",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "104310006",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Procedure"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 40484560,
							"CONCEPT_NAME" : "Measurement of Influenza A virus subtype H1N1 antigen",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "443995002",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "SNOMED",
							"CONCEPT_CLASS_ID" : "Procedure"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 37050279,
							"CONCEPT_NAME" : "Porcine influenza virus A Ab | Serum | Microbiology",
							"STANDARD_CONCEPT" : "C",
							"STANDARD_CONCEPT_CAPTION" : "Classification",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "LP379495-7",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "LOINC Hierarchy"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 3002988,
							"CONCEPT_NAME" : "Porcine influenza virus A Ag [Presence] in Tissue by Immune stain",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "23769-3",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Lab Test"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 3026510,
							"CONCEPT_NAME" : "Swine influenza virus Ab [Presence] in Serum",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "23437-7",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Lab Test"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 3027889,
							"CONCEPT_NAME" : "Swine influenza virus Ab [Presence] in Serum by Hemagglutination inhibition",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "23438-5",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Lab Test"
						},
						"isExcluded" : true,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 3002646,
							"CONCEPT_NAME" : "Swine influenza virus Ag [Presence] in Tissue by Immune stain",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "23782-6",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Lab Test"
						},
						"isExcluded" : false,
						"includeDescendants" : true,
						"includeMapped" : false
					},
					{
						"concept" : {
							"CONCEPT_ID" : 3003682,
							"CONCEPT_NAME" : "Swine influenza virus Ag [Presence] in Tissue by Immunofluorescence",
							"STANDARD_CONCEPT" : "S",
							"STANDARD_CONCEPT_CAPTION" : "Standard",
							"INVALID_REASON" : "V",
							"INVALID_REASON_CAPTION" : "Valid",
							"CONCEPT_CODE" : "23781-8",
							"DOMAIN_ID" : "Measurement",
							"VOCABULARY_ID" : "LOINC",
							"CONCEPT_CLASS_ID" : "Lab Test"
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