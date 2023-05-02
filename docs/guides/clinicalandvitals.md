
This section describes the views available for clinical and vital information recorded for a client. These views can be used to create reports relating to a client's clinical and vital information.<br/> <br/>



## CLIENT_DATA_MEDICATIONS_V1_VIEW

The view groups attributes that relate to a client's medication information, such as the medication name, status, and type. Use this view to report on a client's medications.



| Attribute          | Description                                                                                                                                                                                                                                      | Domain definition | Character size | Nulls allowed |
|:-------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:------------------|:---------------|:--------------|
| MEDICATIONID       | Identifier for a medication record.                                                                                                                                                                                                              | Int 64            | ---            | YES           |
| CLIENTREFERENCE    | Unique reference number that identifies the client in the application.                                                                                                                                                                           | Character         | 200            | NO            |
| MEDICATIONCODES    | Code associated with the medication.                                                                                                                                                                                                             | Character         | 200            | NO            |
| MEDICATIONNAME     | Current status of the medication. For example, active if the client is currently taking the medication, or inactive if the client is no longer taking the medication.                                                                            | Character         | 200            | NO            |
| CODINGSYSTEM       | Coding system for the medication.                                                                                                                                                                                                                | Character         | 500            | NO            |
| COMMENTS           | Comments about the medication record.                                                                                                                                                                                                            | Character         | 500            | NO            |
| DATASOURCE         | Indicates where the record came from, for example, a facility or an external system. Only populated if the record is received from an external system. The field is not displayed in the Merative Integrated Care user interface.               | Character         | 500            | NO            |
| DURATION           | Period of time that the medication is expected to be used for, or the length of time the dispensed medication is expected to last.                                                                                                               | Character         | 50             | NO            |
| FREQUENCY          | Frequency of medication dosages that the client must take.                                                                                                                                                                                       | Character         | 100            | NO            |
| INSTRUCTIONS       | Displays how the client should take their medication, for example, before meals.                                                                                                                                                                  | Character         | 100            | NO            |
| QUANTITYASNUMBER   | Numeric value that represents the quantity of the medication that the client must take per dosage. You can use this value for further arithmetic, comparisons, or graphs. If the medication quantity is not a numeric value, this value is NULL. | Decimal           | ---            | NO            |
| QUANTITYASTEXT     | Value that represents the quantity of the medication that the client must take per dosage, in string format.                                                                                                                                     | Character         | 100            | NO            |
| REASON             | Reason why the client needs to take the medication.                                                                                                                                                                                              | Character         | 500            | NO            |
| ROUTE              | Path by which the medication enters the client's body.                                                                                                                                                                                           | Character         | 200            | NO            |
| SIGCODE            | Displays the values for quantity, strength, dose form, route, frequency, and duration together based on the data that is available.                                                                                                             | Character         | 200            | NO            |
| SOURCE             | Indicates whether the medication information is reported by the client, or where the information is obtained from.                                                                                                                               | Character         | 200            | NO            |
| CREATEDDATE        | Date on which the record was added.                                                                                                                                                                                                              | Timestamp         | ---            | NO            |
| STARTDATE          | Date on which the client started taking the medication.                                                                                                                                                                                          | Timestamp         | ---            | NO            |
| ENDDATE            | Date on which the client ceased taking the medication.                                                                                                                                                                                           | Timestamp         | ---            | NO            |
| STATUS             | Current status of the medication. For example, active if the client is currently taking the medication, or inactive if the client is no longer taking the medication.                                                                            | Character         | 50             | NO            |
| STRENGTH           | Displays how much active ingredient is present in each dosage of the medication, for example, 20 mg/1.                                                                                                                                           | Character         | 100            | NO            |
| TYPE               | Displays whether the client's medication is prescribed or purchased over the counter.                                                                                                                                                            | Character         | 200            | NO            |
| ORDEREDBY          | Provider who ordered the medication.                                                                                                                                                                                                             | Character         | 200            | NO            |
| ORDEREDDATE        | Date when the provider ordered the medication.                                                                                                                                                                                                   | Timestamp         | ---            | NO            |
| PRESCRIPTIONNUMBER | Medication Prescription Number.                                                                                                                                                                                                                  | Character         | 200            | NO            |
| PRESCRIBEDDATE     | Date when the provider prescribed the medication.                                                                                                                                                                                                | Timestamp         | ---            | NO            |
| PRESCRIBEDBY       | Name of the provider who prescribed the medication for the client.                                                                                                                                                                               | Character         | 200            | NO            |
| FILLDATE           | Date when the prescription was filled.                                                                                                                                                                                                           | Character         | 200            | NO            |
| PHARMACY           | Name of the pharmacy that filled the prescription.                                                                                                                                                                                               | Character         | 200            | NO            |
| REVIEWSTATUS       | Indicates the review status of the medication, for example, verified, duplicate, or needs review.                                                                                                                                                   | Timestamp         | ---            | NO            |
| LASTREFILLDATE     | The date of the final prescription refill.                                                                                                                                                                                                       | Character         | 200            | NO            |
| REFILLS            | The number of subsequent times a drug prescription can be obtained.                                                                                                                                                                              | Character         | 200            | NO            |
| REFUSEDREASON      | The reason why the client refuses to take the medication.                                                                                                                                                                                        | Timestamp         | ---            | NO            |
| INGESTIONTIME      | Date and time the record was ingested, supports change data capture.                                                                                                                                                                             | Date Time         | ---            | NO            |




### Links to other data

| Attribute       | Joins to                             | Cardinality                                                                                            |
|:----------------|:-------------------------------------|:-------------------------------------------------------------------------------------------------------|
| CLIENTREFERENCE | CLIENTS_V1_VIEW                      | Cardinality is one-to-one.<br/> A client identifier is associated with one client.  |
| MEDICATIONID    | CLIENT_DATA_MEDICATIONTAKING_V1_VIEW | Cardinality is  one-to-one. <br/>  A medication identifier is associated with one medication record.|

## CLIENT_DATA_MEDICATIONTAKING_V1_VIEW
The view groups attributes that help identify which medications a client is currently taking. Use this view with the CLIENT_DATA_MEDICATIONS_V1_VIEW to report on a client's current medications.


| Attribute       | Description                                                          | Domain definition | Character size | Nulls allowed |
|:----------------|:---------------------------------------------------------------------|:------------------|:---------------|:--------------|
| MEDICATIONID    | Identifier for a medication record.                                  | Int 64            | ---            | NO            |
| CURRENTLYTAKING | Indicator of whether the client is currently taking the medication.       | Character         | 20             | NO            |
| INGESTIONTIME   | Date and time the record was ingested, supports change data capture. | Date Time         | ---            | NO            |

### Links to other data

| Attribute    | Joins to                        | Cardinality                                                                       |
|:-------------|:--------------------------------|:----------------------------------------------------------------------------------|
| MEDICATIONID | CLIENT_DATA_MEDICATIONS_V1_VIEW | Cardinality is one-to-one. <br/> A medication identifier is associated with one medication record. |

## CLIENT_DATA_LABS_V1_VIEW

The view groups attributes that relate to a client's laboratory test information, such as the lab name, lab method, and value for the laboratory test result. Use this view to report on a client's laboratory test results.

| Attribute                | Description                                                                                                                                                                                                                  | Domain definition   | Character size   | Nulls allowed |
|:-------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------|:-----------------|:--------------|
| CLIENTREFERENCE          | Unique reference number that identifies the client in the application.                                                                                                                                                       | Character           | 200              | YES           |
| LABID                    | Identifier for a lab record.                                                                                                                                                                                                 | Int 64              | ---              | NO            |
| LABCODE1                 | Code 1 associated with the laboratory test. A laboratory test might be associated with 1 or 2 codes.                                                                                                                         | Character           | 500              | YES           |
| LABCODINGSYSTEM1         | The coding system associated with Lab Code 1.                                                                                                                                                                                | Character           | 500              | YES           |
| LABCODE2                 | Code 2 associated with the laboratory test. A laboratory test might be associated with 1 or 2 codes.                                                                                                                         | Character           | 500              | YES           |
| LABCODINGSYSTEM2         | The coding system associated with Lab Code 2.                                                                                                                                                                                | Character           | 500              | YES           |
| BODYSITEDISPLAY          | Location of the specimen or the body part where the measurement was taken. Only populated if the record is received from an external system. The field is not displayed in the Merative Integrated Care user interface.    | Character           | 500              | YES           |
| COMMENTS                 | Comments about the laboratory test.                                                                                                                                                                                          | Character           | 500              | YES           |
| DATASOURCE               | Indicates where the record came from, for example, a facility or an external system. Only populated if the record is received from an external system. The field is not displayed in the Merative Integrated Care user interface. | Character           | 200              | YES           |
| INTERPRETATION           | Comments about the laboratory test result. Only populated if the record is received from an external system. The field is not displayed in the Merative Integrated Care user interface.                                      | Character           | 500              | YES           |
| LABSNAMESTRING           | Name of the laboratory test.                                                                                                                                                                                                 | Character           | 500              | YES           |
| MEASUREMENTMETHODDISPLAY | Method by which the laboratory test was taken. Only populated if the record is received from an external system. The field is not displayed in the Merative Integrated Care user interface.                                 | Character           | 500              | YES           |
| MEASUREMENTUNITSSTRING   | Measurement units for the laboratory test result, such as mg/dL, ml/min, or litres.                                                                                                                                          | Character           | 500              | YES           |
| MEASUREMENTDATE          | Date on which the measurement was taken.                                                                                                                                                                                     | Date Time           | ---              | YES           |
| SOURCE                   | Indicates where the laboratory test information is obtained from.                                                                                                                                                            | Character           | 500              | YES           |
| STATUS                   | Current status for the laboratory test result, for example, final result.                                                                                                                                                    | Character           | 500              | YES           |
| VALUEASNUMBER            | Numeric decimal value that represents the laboratory test result. You can use this value for further arithmetic, comparisons, or graphs. If the laboratory test result is not a numeric value, this value is NULL.           | Decimal fixed-point | 4 decimal places | YES           |
| VALUE                    | Value that represents the laboratory test result, in string format. This is the value that was captured in Merative Integrated Care, or the value from an external system, depending on the source of the lab record.         | Character           | 500              | YES           |
| RESULTDATE               | The date when the laboratory test result became available.                                                                                                                                                                   | Date                | ---              | YES           |
| INGESTIONTIME            | Date and time the record was ingested, supports change data capture.                                                                                                                                                         | Date Time           | ---              | NO            |

### Links to other data


| Attribute       | Joins to        | Cardinality                                                                                      |
|:----------------|:----------------|:-------------------------------------------------------------------------------------------------|
| CLIENTREFERENCE | CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/> A client identifier is associated with one client.  |

## CLIENT_DATA_ALLERGIES_V1_VIEW

The view groups attributes that relate to a client's allergy information such as the allergy name, symptoms, and severity. Use this view to report on a client's allergies.

| Attribute       | Description                                                                                                                                                                                                                  | Domain definition | Character size | Nulls allowed |
|:----------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:------------------|:---------------|:--------------|
| CLIENTREFERENCE | Unique reference number that identifies the client in the application.                                                                                                                                                       | Character         | 200            | YES           |
| ALLERGYID       | Identifier for an allergy record.                                                                                                                                                                                           | Int 64            | ---            | NO            |
| ALLERGYNAME     | Allergy name.                                                                                                                                                                                                                | Character         | 200            | YES           |
| COMMENTS        | Comments about the allergy record.                                                                                                                                                                                           | Character         | 200            | YES           |
| DATASOURCE      | Indicates where the record came from, for example, a facility or an external system. Only populated if the record is received from an external system. The field is not displayed in the Merative Integrated Care user interface. | Character         | 500            | YES           |
| ENDDATE         | Date when the client stopped experiencing the allergy.                                                                                                                                                                            | Date Time         | ---            | YES           |
| REACTION1       | First symptom of the allergic reaction that the client experiences.                                                                                                                                                          | Character         | 500            | YES           |
| REACTION2       | Second symptom of the allergic reaction that the client experiences.                                                                                                                                                         | Character         | 500            | YES           |
| REACTION3       | Third symptom of the allergic reaction that the client experiences.                                                                                                                                                          | Character         | 500            | YES           |
| SEVERITY1       | Severity associated with the first allergic reaction.                                                                                                                                                                        | Character         | 500            | YES           |
| SEVERITY2       | Severity associated with the second allergic reaction.                                                                                                                                                                       | Character         | 500            | YES           |
| SEVERITY3       | Severity associated with the third allergic reaction.                                                                                                                                                                        | Character         | 500            | YES           |
| ALLERGYSOURCE   | Indicates whether the allergy information is reported by the client, or where the information is obtained from.                                                                                                              | Character         | 500            | YES           |
| STARTDATE       | Date the client started experiencing the allergy.                                                                                                                                                                            | Date Time         | ---            | YES           |
| STATUS          | Current status of the allergy. For example, active if the client is currently experiencing the allergy, or inactive if the client no longer has the allergy.                                                                    | Character         | 500            | YES           |
| TYPE            | Allergy type.                                                                                                                                                                                                                 | Character         | 500            | YES           |
| TYPECODES       | Chemical, substance, or environmental factor that causes the allergic reaction. For example, dust or pollen.                                                                                                                 | Character         | 500            | YES           |
| ALLERGYCODES    | Code associated with the allergy.                                                                                                                                                                                           | Character         | 500            | YES           |
| CODESYSTEM      | Coding system for the allergy.                                                                                                                                                                                               | Character         | 500            | YES           |
| INGESTIONTIME   | Date and time the record was ingested, supports change data capture.                                                                                                                                                         | Date Time         | ---            | NO            |

### Links to other data



| Attribute       | Joins to        | Cardinality                                                                                    |
|:----------------|:----------------|:-----------------------------------------------------------------------------------------------|
| CLIENTREFERENCE | CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/> A client identifier is associated with one client.  |
| ALLERGYID  |CLIENT_DATA_ACTIVE_ALLERGIES_V1_VIEW | Cardinality is one-to-one. <br /> An allergy identifier is associated with one active allergy record.|

## CLIENT_DATA_ACTIVE_ALLERGIES_V1_VIEW

The view groups attributes that relate to a client's active allergies. Use this view with the CLIENT_DATA_ALLERGIES_V1_VIEW to report on a client's active allergies.

| Attribute       | Description                                                          | Domain definition | Character size | Nulls allowed |
|:----------------|:---------------------------------------------------------------------|:------------------|:---------------|:--------------|
| ALLERGYID       | Identifier for an allergy record.                                    | Int 64            | ---            | NO            |
| CURRENTLYACTIVE | Indicator for whether an allergy is active or not.                   | Character         | 20             | NO            |
| INGESTIONTIME   | Date and time the record was ingested, supports change data capture. | Date Time         | ---            | NO            |


### Links to other data



| Attribute | Joins to                      | Cardinality                                                                                         |
|:----------|:------------------------------|:----------------------------------------------------------------------------------------------------|
| ALLERGYID | CLIENT_DATA_ALLERGIES_V1_VIEW | Cardinality is one-to-one. <br /> An active allergy indicator is associated to one allergy record. |



## CLIENT_DATA_COVERAGE_V1_VIEW

The view groups attributes that relate to a client's medical or insurance plan information. Use this view to report on a client's coverage information.



| Attribute              | Description                                                            | Domain definition | Character size | Nulls allowed |
|:-----------------------|:-----------------------------------------------------------------------|:------------------|:-----|:--------------|
| CLIENTREFERENCE        | Unique reference number that identifies the client in the application. | Character         | 200  | YES           |
| COVERAGEID             | Identifier for a coverage record.                                      | Int 64            |  ---    | NO            |
| STARTDATE              | Start date of the coverage period.                                      | Date Time         |  ---    | YES           |
| ENDDATE                | End date of the coverage period.                                        | Date Time         |  ---    | YES           |
| GROUPDESCRIPTIONEMR    | Name of the group that includes the medical or insurance plan.          | Character         | 500  | YES           |
| PLANDESCRIPTIONEMR     | Name of the medical or insurance plan.                                  | Character         | 500  | YES           |
| SUBGROUPDESCRIPTIONEMR | Name of the subgroup or subsection of the group.                        | Character         | 500  | YES           |
| MEMBERIDEMR            | Identification number assigned to the client by the insurer.            | Character         | 200  | YES           |
| PRECEDENCEEMR          | Order to which the cover applies when the client has multiple coverages.   | Character         | 500  | YES           |
| STATUS                 | Status of the coverage record.                                          | Character         | 200  | YES           |
| SOURCE                 | Origin of the coverage information.                                     | Character         | 500  | YES           |
| INGESTIONTIME          | Date and time the record was ingested, supports change data capture.    | Date Time         |  ---    | YES           |

### Links to other data

| Attribute       | Joins to             | Cardinality                                                              |
|:----------------|:--------------------------|:-------------------------------------------------------------------------|
| CLIENTREFERENCE | Joins to CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/> A client identifier is associated with one client.  |


## CLIENT_DATA_CONDITIONS_V1_VIEW
The view groups attributes that relate to a client's condition information, such as the condition name, start date, and end date for the condition.  Use this view to report on a client's conditions.


| Attribute       | Description                                                                | Domain definition | Character size | Nulls allowed |
|:----------------|:---------------------------------------------------------------------------|:------------------|:-----|:--------------|
| CLIENTREFERENCE | Unique reference number that identifies the client in the application.     | Character         | 200  | YES           |
| CONDITIONID     | Identifier for a condition.                                                | Int 64            |  ---    | NO            |
| CODINGSYSTEM    | Coding system for the condition.                                           | Character         | 500  | YES           |
| CONDITIONCODES  | Code associated with the condition.                                        | Character         | 200  | YES           |
| CONDITIONNAME   | Name of the condition.                                                      | Character         | 500  | YES           |
| DATASOURCE       | Indicates where the data came from.                                        | Character         | 500  | YES           |
| STARTDATE       | Date on which the client was identified as having the condition.           | Date Time         |   ---   | YES           |
| ENDDATE         | Date on which the client was identified as no longer having the condition. | Date Time         | ---     | YES           |
| STATUS          | Current status of the condition.                                           | Character         | 500  | YES           |
| SOURCE          | Indicates where the data came from.                                        | Character         | 200  | YES           |
| COMMENTS        | Comments relating to the condition.                                        | Character         | 1000 | YES           |
| INGESTIONTIME   | Date and time the record was ingested, supports change data capture.       | Date Time         |  ---    | YES           |

### Links to other data


| Attribute       | Joins to                               | Cardinality                                                                                                      |
|:----------------|:--------------------------------------------|:---------------------------------------------------------------------------------------|
| CLIENTREFERENCE |  CLIENTS_V1_VIEW                   | Cardinality is one-to-one.<br/> A client identifier is associated with one client.                |
| CONDITIONID     | CLIENT_DATA_CONDITIONCLASS_V1_VIEW | Cardinality is one-to-one. <br/> An active condition classification indicator is associated to one condition record. |

## CLIENT_DATA_CONDITIONCLASS_V1_VIEW
The view groups attributes that relate to a client's condition classification, such as whether the condition is a primary or secondary condition. Use this view with the CLIENT_DATA_CONDITIONS_V1_VIEW to report on a client's conditions.


| Attribute      | Description                                                            | Domain definition | Character size | Nulls allowed |
|:---------------|:-----------------------------------------------------------------------|:------------------|:-----|:--------------|
| CONDITIONID    | Identifier for a condition record.                                   | Int 64            |  ---    | NO            |
| CLASSIFICATION | Indicator for whether the classification is primary, secondary, or null. | Character         | 20   | YES           |
| INGESTIONTIME  | Date and time the record was ingested, supports change data capture.   | Date Time         |  ---    | NO            |

### Links to other data


| Attribute   | Joins to                      | Cardinality                                                                                                            |
|:------------|:------------------------------|:-----------------------------------------------------------------------------------------------------------------------|
| CONDITIONID | CLIENT_DATA_CONDITION_V1_VIEW | Cardinality is one-to-one. <br /> A condition classification indicator is associated to one condition record. |


## CLIENT_DATA_RISKS_V1_VIEW

The view groups attributes that relate to a client's risk information such as the risk name, type, and score. Use this view to report on a client's risks.

| Attribute       | Description                                                                                                                                                                                                                  | Domain definition   | Character size   | Nulls allowed |
|:----------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------|:-----------------|:--------------|
| CLIENTREFERENCE | Unique reference number that identifies the client in the application.                                                                                                                                                       | Character           | 200              | YES           |
| RISKID          | Identifier for a risk record.                                                                                                                                                                                                | Int 64              | ---              | NO            |
| CATEGORY        | Category of the risk record.                                                                                                                                                                                                 | Character           | 200              | YES           |
| DATASOURCE      | Indicates where the record came from, for example, a facility or an external system. Only populated if the record is received from an external system. The field is not displayed in the Merative Integrated Care user interface. | Character           | 200              | YES           |
| DATE            | Date on which the client's risk information was recorded.                                                                                                                                                                    | Date Time           | ---              | YES           |
| RISKTYPE        | Type of risk records.                                                                                                                                                                                                        | Character           | 200              | YES           |
| NAME            | Risk name.                                                                                                                                                                                                                   | Character           | 200              | YES           |
| SCOREASNUMBER   | Risk score in floating point number.                                                                                                                                                                                         | Decimal fixed-point | 4 decimal places | YES           |
| SCOREASTEXT     | Risk score in text.                                                                                                                                                                                                          | Character           | 200              | YES           |
| SOURCE          | Indicates where the data came from.                                                                                                                                                                                          | Character           | 200              | YES           |
| INGESTIONTIME   | Date and time the record was ingested, supports change data capture.                                                                                                                                                         | Date Time           | ---              | NO            |

### Links to other data



| Attribute       | Joins to        | Cardinality                                                               |
|:----------------|:----------------|:--------------------------------------------------------------------------|
| CLIENTREFERENCE | CLIENTS_V1_VIEW | Cardinality is one-to-one. <br /> A client is associated with one client. |


## CLIENT_VITAL_OXYGEN_V1_VIEW

The view groups attributes that relate to a client's oxygen measurement information, such as the measurement number, status, and data source. Use this view to report on a client's oxygen measurement results.

| Attribute               | Description                                                                                                                                                       | Domain definition   | Character size   | Nulls allowed |
|:------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------|:-----------------|:--------------|
| CLIENTREFERENCE         | Unique reference number that identifies the client in the application.                                                                                            | Character           | 200              | NO            |
| OXYGENMEASUREMENTID     | Identifier for the oxygen measurement record.                                                                                                                     | Int 64              | ---              | NO            |
| CODE1                   | First code associated with the oxygen measurement.                                                                                                                | Character           | 500              | YES           |
| CODINGSYSTEM1           | First coding system for the oxygen measurement.                                                                                                                   | Character           | 500              | YES           |
| CODE2                   | Second code associated with the oxygen measurement.                                                                                                               | Character           | 500              | YES           |
| CODINGSYSTEM2           | Second coding system for the oxygen measurement.                                                                                                                  | Character           | 500              | YES           |
| MEASUREMENTASNUMBER     | Numeric decimal value that represents the percentage of oxygenated haemoglobin in the client's blood, relative to the total amount of haemoglobin in their blood. | Decimal fixed-point | 4 decimal places | NO            |
| MEASUREMENTASTEXT       | Percentage of oxygenated haemoglobin in the client's blood, relative to the total amount of haemoglobin in their blood in string format.                          | Character           | 500              | NO            |
| MEASUREMENTUNITS        | Unit of measurement.                                                                                                                                              | Character           | 500              | NO            |
| DISPLAYMEASUREMENTUNITS | Displays the oxygen measurement result with units.                                                                                                                | Character           | 500              | NO            |
| MEASUREMENTDATETIME     | Date when the client's oxygen was measured.                                                                                                                       | Timestamp           | ---              | NO            |
| SOURCESYTEM             | Source system for the oxygen measurement.                                                                                                                         | Character           | 500              | YES           |
| SOURCE                  | Indicates whether the oxygen information is reported by the client, or where the information is obtained from.                                                    | Character           | 500              | NO            |
| STATUS                  | Status of the oxygen measurement, includes completed, canceled, duplicate, amended, invalid, registered, and unknown.                                             | Character           | 500              | NO            |
| VERIFIEDBY              | The name of the healthcare professional who took the oxygen measurement and verified that it was accurate.                                                        | Character           | 500              | YES           |
| COMMENTS                | Comments about the oxygen measurement.                                                                                                                            | Character           | 500              | YES           |
| DATASOURCE              | Indicates where the record came from, for example, a facility or an external system. Only populated if the record is received from an external system.            | Character           | 500              | YES           |
| INGESTIONTIME           | Date and time the record was ingested, supports change data capture.                                                                                              | Date Time           | ---              | NO            |




### Links to other data

| Attribute       | Joins to        | Cardinality                                                                                                    |
|:----------------|:----------------|:---------------------------------------------------------------------------------------------------------------|
| CLIENTREFERENCE | CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/> A client identifier is associated with one client.  |



## CLIENT_VITAL_BLOODPRESSURE_V1_VIEW

The view groups attributes that relate to a client's blood pressure measurement information, such as the systolic or diastolic measurement, and unit of measurement. Use this view to report on a client's blood pressure measurement results.


| Attribute | Description                                                                                                                                            | Domain definition |Character size | Nulls allowed |
| :-------------- |:-------------------------------------------------------------------------------------------------------------------------------------------------------|:------ |:------ |:--------------|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application.    | Character| 200| NO            |
| BLOODPRESSUREMEASUREMENTID| Identifier for the blood pressure measurement record.           |  Int 64| ---| NO            |
| CODE1| First code associated with the blood pressure measurement.                           | Character| 500| YES           |
| CODINGSYSTEM1| First coding system for the blood pressure measurement.                      | Character| 500| YES           |
| CODE2| Second code associated with the blood pressure measurement.                          | Character| 500| YES           |
| CODINGSYSTEM2| Second coding system for the blood pressure measurement.                     | Character| 500| YES           |
| MEASUREMENTUNITS| Unit of measurement, mmHg or kPa.                                              | Character| 1000| NO            |
| MEASUREMENT| Blood pressure measurement result, systolic or diastolic.                          | Character| 500| NO            |
| MEASUREMENTDATETIME| Date and time when the blood pressure reading was taken from the client. | Date Time|--- | NO            |
| MEASUREMENTSITE| Location of the client where the healthcare professional took the blood pressure reading. | Character| 500| NO            |
| SOURCE| Indicates whether the blood pressure information is reported by the client, or where the information is obtained from. | Character| 500| YES |
| STATUS| Status of the blood pressure measurement, includes completed, canceled, duplicate, amended, invalid, registered, and unknown.| Character| 500| NO   |
| VERIFIEDBY| The name of the healthcare professional who took the blood pressure reading and verified that it was accurate.| Character| 500| YES           |
| COMMENTS| Comments about the blood pressure reading.     | Character| 500| YES           |
| DATASOURCE| Indicates where the record came from, for example, a facility or an external system. Only populated if the record is received from an external system. | Character| 500| YES           |
| OBSERVATIONMETHOD| Position of the client's body when the blood pressure reading was recorded. | Character| 500| YES           |
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|--- | NO            |

### Links to other data

| Attribute       | Joins to        | Cardinality                                                                                                          |
|:----------------|:----------------|:---------------------------------------------------------------------------------------------------------------------|
| CLIENTREFERENCE | CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/> A client identifier is associated with one client.  |



## CLIENT_VITAL_HEIGHT_V1_VIEW


The view groups attributes that relate to a client's height measurement information, such as the measurement number, status, and data source. Use this view to report on a client's height measurement results.


| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| Unique reference number that identifies the client in the application.  | Character| 200|NO|
| HEIGHTMEASUREMENTID| Identifier for the height measurement record.                   |  Int 64|--- |NO|
| CODE1               | First code associated with the height measurement.                                                                                                     | Character         | 500            | YES           |
| CODINGSYSTEM1       | First coding system for the height measurement.                                                                                                        | Character         | 500            | YES           |
| CODE2               | Second code associated with the height measurement.                                                                                                    | Character         | 500            | YES           |
| CODINGSYSTEM2       | Second coding system for the height measurement.                                                                                                       | Character         | 500            | YES           |
| MEASUREMENT| Result of height measurement. | Character | 500|YES|
| MEASUREMENTUNIT| Unit of measurement result.    | Character| 500|YES|
| DISPLAYMEASUREMENTUNITS| Displayed height measurement result with units.  | Character| 500|YES|
| MEASUREMENTDATETIME         | Date when the client measure height.                                                                                                                   | Timestamp         | ---            | NO            |
| SOURCE              | Indicates whether the height information is reported by the client, or where the information is obtained from.                                         | Character         | 500            | NO           |
| STATUS              | Status of the height measurement, includes completed, canceled, duplicate, amended, invalid, registered, and unknown.                                   | Character         | 500            | NO            |
| VERIFIEDBY              | The name of the healthcare professional who took the height measurement and verified that it was accurate.                                                                                                          | Character         | 500            | YES           |
| COMMENTS            | Comments about the height measurements.                                                                                                                | Character         | 500            | YES           |
| DATASOURCE          | Indicates where the record came from, for example, a facility or an external system. Only populated if the record is received from an external system. | Character         | 500            | NO            |
| INGESTIONTIME       | Date and time the record was ingested, supports change data capture.                                                                                   | Date Time         | ---            | NO            |



### Links to other data

| Attribute       | Joins to        | Cardinality                                                                                                    |
|:----------------|:----------------|:---------------------------------------------------------------------------------------------------------------|
| CLIENTREFERENCE | CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/> A client identifier is associated with one client.  |



## CLIENT_VITAL_BODYMASS_V1_VIEW

The view groups attributes that relate to a client's body mass information, such as the measurement number, measurement date, status, and data source. Use this view to report on a client's body mass measurement results.

| Attribute             | Description                                                                                                                                            | Domain definition   | Character size   | Nulls allowed |
|:----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------|:-----------------|:--------------|
| CLIENTREFERENCE       | Unique reference number that identifies the client in the application.                                                                                 | Character           | 200              | NO            |
| BODYMASSMEASUREMENTID | Identifier for the body mass measurement record.                                                                                                       | Int 64              | ---              | NO            |
| CODE1                 | First code associated with the body mass measurement.                                                                                                  | Character           | 500              | YES           |
| CODINGSYSTEM1         | First coding system for the body mass measurement.                                                                                                     | Character           | 500              | YES           |
| CODE2                 | Second code associated with the body mass measurement.                                                                                                 | Character           | 500              | YES           |
| CODINGSYSTEM2         | Second coding system for the body mass measurement.                                                                                                    | Character           | 500              | YES           |
| MEASUREMENTASNUMBER   | Measurement number of the body mass.                                                                                                                   | Decimal fixed-point | 4 decimal places | YES           |
| MEASUREMENTASTEXT     | Measurement result in text string.                                                                                                                     | Character           | 500              | YES           |
| MEASUREMENTDATETIME   | Date when the client's measurement was taken.                                                                                                          | Timestamp           | ---              | NO            |
| SOURCE                | Indicates whether the body mass information is reported by the client, or where the information is obtained from.                                      | Character           | 500              | NO            |
| STATUS                | Status of the body mass measurement, includes completed, canceled, duplicate, amended, invalid, registered, and unknown.                               | Character           | 500              | NO            |
| VERIFIEDBY            | The name of the healthcare professional who took the body mass measurement and verified that it was accurate.                                          | Character           | 500              | YES           |
| SOURCESYTEM           | Source system for the body mass measurement.                                                                                                           | Character           | 500              | YES           |
| COMMENTS              | Comments about the body mass measurements.                                                                                                             | Character           | 500              | YES           |
| DATASOURCE            | Indicates where the record came from, for example, a facility or an external system. Only populated if the record is received from an external system. | Character           | 500              | NO            |
| INGESTIONTIME         | Date and time the record was ingested, supports change data capture.                                                                                   | Date Time           | ---              | NO            |

### Links to other data

| Attribute       | Joins to        | Cardinality                                                                        |
|:----------------|:----------------|:-----------------------------------------------------------------------------------|
| CLIENTREFERENCE | CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/> A client identifier is associated with one client. |

## CLIENT_VITAL_HEART_V1_VIEW

The view groups attributes that relate to a client's heart rate measurement information, such as the measurement number, status, and data source. Use this view to report on a client's heart rate measurement results.

| Attribute               | Description                                                                                                                                            | Domain definition   | Character size   | Nulls allowed |
|:------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------|:-----------------|:--------------|
| CLIENTREFERENCE         | Unique reference number that identifies the client in the application.                                                                                 | Character           | 200              | NO            |
| HEARTMEASUREMENTID      | Identifier for the heart rate measurement record.                                                                                                      | Int 64              | ---              | NO            |
| CODE1                   | First code associated with the  measurement.                                                                                                           | Character           | 500              | YES           |
| CODINGSYSTEM1           | First coding system for the  measurement.                                                                                                              | Character           | 500              | YES           |
| CODE2                   | Second code associated with the measurement.                                                                                                           | Character           | 500              | YES           |
| CODINGSYSTEM2           | Second coding system for the measurement.                                                                                                              | Character           | 500              | YES           |
| MEASUREMENTASNUMBER     | Measurement number of the heart rate.                                                                                                                  | Decimal fixed-point | 2 decimal places | YES           |
| MEASUREMENTASTEXT       | Measurement result in text string.                                                                                                                     | Character           | 500              | YES           |
| DISPLAYMEASUREMENTUNITS | Displayed heart rate measurement result with units.                                                                                                    | Character           | 500              | YES           |
| MEASUREMENTUNITS        | Unit of measurement result.                                                                                                                            | Character           | 500              | YES           |
| MEASUREMENTMETHOD       | Method of heart rate measurement, auscultation, EKG, and palpation.                                                                                    | Character           | 500              | YES           |
| MEASUREMENTDATETIME     | Date when the client's heart rate was measured.                                                                                                        | Timestamp           | ---              | NO            |
| SOURCE                  | Indicates whether the heart rate information is reported by the client, or where the information is obtained from.                                     | Character           | 500              | NO            |
| STATUS                  | Status of the heart rate measurement, includes completed, canceled, duplicate, amended, invalid, registered, and unknown.                              | Character           | 500              | NO            |
| VERIFIEDBY              | The name of the healthcare professional who took the heart rate reading and verified that it was accurate.                                             | Character           | 500              | YES           |
| SOURCESYTEM             | Source system for the heart rate measurement.                                                                                                          | Character           | 500              | YES           |
| COMMENTS                | Comments about the heart rate measurements.                                                                                                            | Character           | 500              | YES           |
| DATASOURCE              | Indicates where the record came from, for example, a facility or an external system. Only populated if the record is received from an external system. | Character           | 500              | NO            |
| INGESTIONTIME           | Date and time the record was ingested, supports change data capture.                                                                                   | Date Time           | ---              | NO            |

### Links to other data

| Attribute       | Joins to        | Cardinality                                                                        |
|:----------------|:----------------|:-----------------------------------------------------------------------------------|
| CLIENTREFERENCE | CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/> A client identifier is associated with one client. |

## CLIENT_VITAL_WEIGHT_V1_VIEW

The view groups attributes that relate to a client's weight measurement information, such as the measurement number, status, and data source. Use this view to report on a client's weight measurement results.

| Attribute               | Description                                                                                                                                            | Domain definition   | Character size   | Nulls allowed |
|:------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------|:-----------------|:--------------|
| CLIENTREFERENCE         | Unique reference number that identifies the client in the application.                                                                                 | Character           | 200              | NO            |
| WEIGHTMEASUREMENTID     | Identifier for the weight measurement record.                                                                                                          | Int 64              | ---              | NO            |
| CODE1                   | First code associated with the  measurement.                                                                                                           | Character           | 500              | YES           |
| CODINGSYSTEM1           | First coding system for the  measurement.                                                                                                              | Character           | 500              | YES           |
| CODE2                   | Second code associated with the measurement.                                                                                                           | Character           | 500              | YES           |
| CODINGSYSTEM2           | Second coding system for the measurement.                                                                                                              | Character           | 500              | YES           |
| MEASUREMENTASNUMBER     | Measurement number of the weight.                                                                                                                      | Decimal fixed-point | 2 decimal places | YES           |
| MEASUREMENTASTEXT       | Measurement result in text string.                                                                                                                     | Character           | 500              | YES           |
| MEASUREMENTUNITS        | Unit of measurement result.                                                                                                                            | Character           | 500              | YES           |
| DISPLAYMEASUREMENTUNITS | Displays the weight measurement result with units.                                                                                                     | Character           | 500              | YES           |
| MEASUREMENTDATETIME     | Date when the client's weight was measured.                                                                                                            | Timestamp           | ---              | NO            |
| SOURCE                  | Indicates whether the weight information is reported by the client, or where the information is obtained from.                                         | Character           | 500              | NO            |
| STATUS                  | Status of the weight measurement, includes completed, canceled, duplicate, amended, invalid, registered, and unknown.                                  | Character           | 500              | NO            |
| VERIFIEDBY              | The name of the healthcare professional who took the weight reading and verified that it was accurate.                                                 | Character           | 500              | YES           |
| COMMENTS                | Comments about the weight measurements.                                                                                                                | Character           | 500              | YES           |
| DATASOURCE              | Indicates where the record came from, for example, a facility or an external system. Only populated if the record is received from an external system. | Character           | 500              | NO            |
| INGESTIONTIME           | Date and time the record was ingested, supports change data capture.                                                                                   | Date Time           | ---              | NO            |

### Links to other data

| Attribute       | Joins to        | Cardinality                                                                        |
|:----------------|:----------------|:-----------------------------------------------------------------------------------|
| CLIENTREFERENCE | CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/> A client identifier is associated with one client. |

## CLIENT_VITAL_WAISTTOHEIGHT_V1_VIEW

The view groups attributes that relate to a client's waist-to-height measurement information, such as the measurement number, status, and data source. Use this view to report on a client's waist-to-height measurement results.

| Attribute                  | Description                                                                                                                                            | Domain definition | Character size | Nulls allowed |
|:---------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------|:------------------|:---------------|:--------------|
| CLIENTREFERENCE            | Unique reference number that identifies the client in the application.                                                                                 | Character         | 200            | NO            |
| WAISTTOHEIGHTMEASUREMENTID | Identifier for the waist-to-height measurement record.                                                                                                 | Int 64            | ---            | NO            |
| CODE1                      | First code associated with the  measurement.                                                                                                           | Character         | 500            | YES           |
| CODINGSYSTEM1              | First coding system for the  measurement.                                                                                                              | Character         | 500            | YES           |
| CODE2                      | Second code associated with the measurement.                                                                                                           | Character         | 500            | YES           |
| CODINGSYSTEM2              | Second coding system for the measurement.                                                                                                              | Character         | 500            | YES           |
| MEASUREMENT                | Measurement result of the waist-to-height.                                                                                                             | Character         | 500            | YES           |
| MEASUREMENTDATETIME        | Date when the client's waist-to-height was measured.                                                                                                   | Timestamp         | ---            | NO            |
| SOURCE                     | Indicates whether the waist-to-height information is reported by the client, or where the information is obtained from.                                | Character         | 500            | NO            |
| STATUS                     | Status of the waist-to-height measurement, includes completed, canceled, duplicate, amended, invalid, registered, and unknown.                         | Character         | 500            | NO            |
| VERIFIEDBY                 | The name of the healthcare professional who took the waist-to-height reading and verified that it was accurate.                                        | Character         | 500            | YES           |
| COMMENTS                   | Comments about the waist-to-height measurements.                                                                                                       | Character         | 500            | YES           |
| DATASOURCE                 | Indicates where the record came from, for example, a facility or an external system. Only populated if the record is received from an external system. | Character         | 500            | NO            |
| INGESTIONTIME              | Date and time the record was ingested, supports change data capture.                                                                                   | Date Time         | ---            | NO            |

### Links to other data

| Attribute       | Joins to        | Cardinality                                                                        |
|:----------------|:----------------|:-----------------------------------------------------------------------------------|
| CLIENTREFERENCE | CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/> A client identifier is associated with one client. |

## CLIENT_VITAL_TEMPERATURE_V1_VIEW

The view groups attributes that relate to a client's temperature measurement information, such as the measurement number, status, and data source. Use this view to report on a client's temperature measurement results.

| Attribute                | Description                                                                                                                                            | Domain definition   | Character size   | Nulls allowed |
|:-------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------|:-----------------|:--------------|
| CLIENTREFERENCE          | Unique reference number that identifies the client in the application.                                                                                 | Character           | 200              | NO            |
| TEMPERATUREMEASUREMENTID | Identifier for the temperature measurement record.                                                                                                     | Int 64              | ---              | NO            |
| CODE1                    | First code associated with the  measurement.                                                                                                           | Character           | 500              | YES           |
| CODINGSYSTEM1            | First coding system for the  measurement.                                                                                                              | Character           | 500              | YES           |
| CODE2                    | Second code associated with the measurement.                                                                                                           | Character           | 500              | YES           |
| CODINGSYSTEM2            | Second coding system for the measurement.                                                                                                              | Character           | 500              | YES           |
| MEASUREMENTASNUMBER      | Measurement number of the temperature.                                                                                                                 | Decimal fixed-point | 2 decimal places | YES           |
| MEASUREMENTASTEXT        | Measurement result in text string.                                                                                                                     | Character           | 500              | YES           |
| DISPLAYMEASUREMENTUNITS  | Displays the temperature measurement result with units.                                                                                                | Character           | 500              | YES           |
| MEASUREMENTUNITS         | Unit of measurement result.                                                                                                                            | Character           | 500              | YES           |
| MEASUREMENTDATETIME      | Date when the client's temperature was measured.                                                                                                       | Timestamp           | ---              | NO            |
| MEASUREMENTSITE          | Location of the client where the healthcare professional took the temperature reading.                                                                 | Character           | 500              | NO            |
| MEASUREMENTMETHOD        | Method of temperature measurement.                                                                                                                     | Character           | 500              | YES           |
| SOURCE                   | Indicates whether the temperature information is reported by the client, or where the information is obtained from.                                    | Character           | 500              | NO            |
| SOURCESYTEM              | Source system for the temperature measurement.                                                                                                         | Character           | 500              | YES           |
| STATUS                   | Status of the temperature measurement, includes completed, canceled, duplicate, amended, invalid, registered, and unknown.                             | Character           | 500              | NO            |
| VERIFIEDBY               | The name of the healthcare professional who took the temperature reading and verified that it was accurate.                                            | Character           | 500              | YES           |
| COMMENTS                 | Comments about the temperature measurements.                                                                                                           | Character           | 500              | YES           |
| DATASOURCE               | Indicates where the record came from, for example, a facility or an external system. Only populated if the record is received from an external system. | Character           | 500              | NO            |
| INGESTIONTIME            | Date and time the record was ingested, supports change data capture.                                                                                   | Date Time           | ---              | NO            |


### Links to other data

| Attribute       | Joins to        | Cardinality                                                                        |
|:----------------|:----------------|:-----------------------------------------------------------------------------------|
| CLIENTREFERENCE | CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/> A client identifier is associated with one client. |


## CLIENT_VITAL_RESPIRATORY_V1_VIEW

The view groups attributes that relate to a client's respiratory rate measurement information, such as the measurement number, status, and data source. Use this view to report on a client's respiratory rate measurement results.

| Attribute                | Description                                                                                                                                            | Domain definition | Character size | Nulls allowed |
|:-------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------|:------------------|:---------------|:--------------|
| CLIENTREFERENCE          | Unique reference number that identifies the client in the application.                                                                                 | Character         | 200            | NO            |
| RESPIRATORYMEASUREMENTID | Identifier for the respiratory rate measurement record.                                                                                                | Int 64            | ---            | NO            |
| CODE1                    | First code associated with the  measurement.                                                                                                           | Character         | 500            | YES           |
| CODINGSYSTEM1            | First coding system for the  measurement.                                                                                                              | Character         | 500            | YES           |
| CODE2                    | Second code associated with the measurement.                                                                                                           | Character         | 500            | YES           |
| CODINGSYSTEM2            | Second coding system for the measurement.                                                                                                              | Character         | 500            | YES           |
| MEASUREMENT              | Measurement result of the respiratory rate.                                                                                                            | Character         | 500            | YES           |
| MEASUREMENTUNITS         | Unit of measurement result.                                                                                                                            | Character         | 500            | YES           |
| DISPLAYMEASUREMENTUNITS  | Displays the respiratory rate measurement result with units.                                                                                           | Character         | 500            | NO            |
| MEASUREMENTDATETIME      | Date when the client's respiratory rate was measured.                                                                                                  | Timestamp         | ---            | NO            |
| SOURCE                   | Indicates whether the respiratory rate information is reported by the client, or where the information is obtained from.                               | Character         | 500            | NO            |
| STATUS                   | Status of the respiratory rate measurement, includes completed, canceled, duplicate, amended, invalid, registered, and unknown.                        | Character         | 500            | NO            |
| VERIFIEDBY               | The name of the healthcare professional who took the respiratory rate reading and verified that it was accurate.                                       | Character         | 500            | YES           |
| COMMENTS                 | Comments about the respiratory rate measurements.                                                                                                      | Character         | 500            | YES           |
| DATASOURCE               | Indicates where the record came from, for example, a facility or an external system. Only populated if the record is received from an external system. | Character         | 500            | NO            |
| INGESTIONTIME            | Date and time the record was ingested, supports change data capture.                                                                                   | Date Time         | ---            | NO            |

### Links to other data

| Attribute       | Joins to        | Cardinality                                                                                                        |
|:----------------|:----------------|:-------------------------------------------------------------------------------------------------------------------|
| CLIENTREFERENCE | CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/> A client identifier is associated with one client. |

## CLIENT_VITAL_WAIST_V1_VIEW

The view groups attributes that relate to a client's waist circumference measurement information, such as the measurement number, unit, status, and data source. Use this view to report on a client's waist circumference measurement results.

| Attribute               | Description                                                                                                                                            | Domain definition   | Character Size             | Nulls allowed |
|:------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------|:-----------------|:--------------|
| CLIENTREFERENCE         | Unique reference number that identifies the client in the application.                                                                                 | Character           | 200              | YES           |
| WAISTMEASUREMENTID      | Identifier for the waist measurement record.                                                                                                           | Int 64              |                  | NO            |
| CODE1                   | First code associated with the  measurement.                                                                                                           | Character           | 500              | YES           |
| CODINGSYSTEM1           | First coding system for the  measurement.                                                                                                              | Character           | 500              | YES           |
| CODE2                   | Second code associated with the measurement.                                                                                                           | Character           | 500              | YES           |
| CODINGSYSTEM2           | Second coding system for the measurement.                                                                                                              | Character           | 500              | YES           |
| MEASUREMENTASNUMBER     | Measurement number of the waist circumference.                                                                                                           | Decimal fixed-point | 4 decimal places | YES           |
| MEASUREMENTASTEXT       | Measurement result in text string.                                                                                                           | Character           | 500              | YES           |
| MEASUREMENTUNITS        | Unit of waist measurement.                                                                                                                             | Character           | 500              | YES           |
| DISPLAYMEASUREMENTUNITS | Displays the waist measurement result with units.                                                                                                      | Character           | 500              | YES           |
| MEASUREMENTDATETIME     | Date when the client's waist was measured.                                                                                                             | Date Time           |                  | YES           |
| SOURCE                  | Indicates whether the waist measurement information is reported by the client, or where the information is obtained from.                              | Character           | 500              | YES           |
| STATUS                  | Status of the waist measurement, includes completed, canceled, duplicate, amended, invalid, registered, and unknown.                                   | Character           | 500              | YES           |
| VERIFIEDBY              | The name of the healthcare professional who took the waist measurement reading and verified that it was accurate.                                      | Character           | 500              | YES           |
| COMMENTS                | Comments about the waist measurements.                                                                                                                 | Character           | 500              | YES           |
| DATASOURCE              | Indicates where the record came from, for example, a facility or an external system. Only populated if the record is received from an external system. | Character           | 500              | YES           |
| INGESTIONTIME           | Date and time the record was ingested, supports change data capture.                                                                                   | Date Time           |                  | YES           |

### Links to other data


| Attribute       | Joins to               | Cardinality                                                                        |
|:----------------|:--------------------------|:-----------------------------------------------------------------------------------|
| CLIENTREFERENCE | CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/> A client identifier is associated with one client. |


© Merative US L.P. 2016, 2023. 
Merative is a trademark of Merative US L.P. in the United States and other countries.
