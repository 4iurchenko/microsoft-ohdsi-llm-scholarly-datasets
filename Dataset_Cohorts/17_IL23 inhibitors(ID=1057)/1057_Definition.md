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