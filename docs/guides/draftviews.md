





## PATIENTS_UNDER_MANAGEMENT_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| MONTHYEAR| tbc | Date| |NO|
| PATIENTID| tbc |  Int 64| |NO|
| MONTH| tbc | Character| 40|NO|
| YEAR| tbc |  Int 32| |NO|
| ACTIVELYMANAGEDDAYS| tbc |  Int 32| |NO|
| RECORDSTATUS| tbc | Character| 40|NO|
| UNIQUEREF| tbc | Character| 200|YES|
| FIRSTNAME| tbc | Character| 200|YES|
| LASTNAME| tbc | Character| 200|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data



| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| -| - | -|



## UTILIZATIONS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| UTILIZATIONID| tbc |  Int 64| |NO|
| CLIENTREFERENCE| tbc | Character| 200|YES|
| ATTENDEDDATE| tbc | Date| |YES|
| ADMITTEDIND| tbc | Character| 1|YES|
| DISCHARGEDDATE| tbc | Date| |YES|
| OTHERSOURCE| tbc | Character| 500|YES|
| OTHERTYPE| tbc | Character| 200|YES|
| OTHERLOCATION| tbc | Character| 500|YES|
| OTHERDISPOSITION| tbc | Character| 500|YES|
| ADDEDBY| tbc | Character| 256|YES|
| CREATEDON| tbc | Date Time| |YES|
| TYPE| tbc | Character| 200|YES|
| DISPOSITION| tbc | Character| 200|YES|
| SOURCE| tbc | Character| 200|YES|
| LOCATION| tbc | Character| 200|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|
| CREATEDBY | joins to USERS_V1_VIEW. | Cardinality is one-to-many. An alert joins to 1 user. |
| CLOSEDBY | Joins to USERS_V1_VIEW.| Cardinality is zero-to-one. An alert joins to 1 user if closed. |
| ALERTID | Joins to ALERT_NOTIFICATIONS_V1_VIEW.| Cardinality is zero-to-many. |






CLINICALDATA_MEDICATIONTAKING_MEASUREMENTS_V1_VIEW and condition classifiction should link to a parent please create a ticket to resolve.


## CLINICALDATA_ALLERGIES_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| tbc | Character| 200|YES|
| ALLERGYID| tbc |  Int 64| |NO|
| ALLERGYNAME| tbc | Character| 200|YES|
| COMMENTS| tbc | Character| 200|YES|
| DATASOURCE| tbc | Character| 500|YES|
| ENDDATE| tbc | Date Time| |YES|
| REACTION1| tbc | Character| 500|YES|
| REACTION2| tbc | Character| 500|YES|
| REACTION3| tbc | Character| 500|YES|
| SEVERITY1| tbc | Character| 500|YES|
| SEVERITY2| tbc | Character| 500|YES|
| SEVERITY3| tbc | Character| 500|YES|
| ALLERGYSOURCE| tbc | Character| 500|YES|
| STARTDATE| tbc | Date Time| |YES|
| STATUS| tbc | Character| 500|YES|
| TYPE| tbc | Character| 500|YES|
| TYPECODES| tbc | Character| 500|YES|
| ALLERGYCODES| tbc | Character| 500|YES|
| CODESYSTEM| tbc | Character| 500|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## CLINICALDATA_ALLERGYACTIVES_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| ALLERGYACTIVEID| tbc |  Int 64| |YES|
| CURRENTLYACTIVE| tbc | Character| 20|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## CLINICALDATA_BLOODPRESSURE_MEASUREMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| tbc | Character| 200|YES|
| BLOODPRESSUREMEASUREMENTID| tbc |  Int 64| |NO|
| CODE1| tbc | Character| 500|YES|
| CODINGSYSTEM1| tbc | Character| 500|YES|
| CODE2| tbc | Character| 500|YES|
| CODINGSYSTEM2| tbc | Character| 500|YES|
| MEASUREMENTUNITS| tbc | Character| 1000|YES|
| MEASUREMENT| tbc | Character| 500|YES|
| MEASUREMENTDATETIME| tbc | Date Time| |YES|
| MEASUREMENTSITE| tbc | Character| 500|YES|
| SOURCE| tbc | Character| 500|YES|
| STATUS| tbc | Character| 500|YES|
| VERIFIEDBY| tbc | Character| 500|YES|
| COMMENTS| tbc | Character| 500|YES|
| DATASOURCE| tbc | Character| 500|YES|
| OBSERVATIONMETHOD| tbc | Character| 500|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## CLINICALDATA_BODYMASS_MEASUREMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| tbc | Character| 200|YES|
| BODYMASSMEASUREMENTID| tbc |  Int 64| |NO|
| CODE1| tbc | Character| 500|YES|
| CODINGSYSTEM1| tbc | Character| 500|YES|
| CODE2| tbc | Character| 500|YES|
| CODINGSYSTEM2| tbc | Character| 500|YES|
| MEASUREMENTASNUMBER| tbc | Decimal fixed-point| 4 decimal places|YES|
| MEASUREMENTASTEXT| tbc | Character| 500|YES|
| MEASUREMENTDATETIME| tbc | Date Time| |YES|
| SOURCE| tbc | Character| 500|YES|
| STATUS| tbc | Character| 500|YES|
| VERIFIEDBY| tbc | Character| 500|YES|
| SOURCESYTEM| tbc | Character| 500|YES|
| COMMENTS| tbc | Character| 500|YES|
| DATASOURCE| tbc | Character| 500|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## CLINICALDATA_CONDITION_CLASSIFICATIONS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CONDITIONCLASSIFICATIONID| tbc |  Int 64| |YES|
| CLASSIFICATION| tbc | Character| 20|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|
| CREATEDBY | joins to USERS_V1_VIEW. | Cardinality is one-to-many. An alert joins to 1 user. |
| CLOSEDBY | Joins to USERS_V1_VIEW.| Cardinality is zero-to-one. An alert joins to 1 user if closed. |
| ALERTID | Joins to ALERT_NOTIFICATIONS_V1_VIEW.| Cardinality is zero-to-many. |

## CLINICALDATA_CONDITION_MEASUREMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| tbc | Character| 200|YES|
| CONDITIONID| tbc |  Int 64| |NO|
| CODINGSYSTEM| tbc | Character| 500|YES|
| CONDITIONCODES| tbc | Character| 200|YES|
| CONDITIONNAME| tbc | Character| 500|YES|
| DATASOURE| tbc | Character| 500|YES|
| STARTDATE| tbc | Date Time| |YES|
| ENDDATE| tbc | Date Time| |YES|
| STATUS| tbc | Character| 500|YES|
| SOURCE| tbc | Character| 200|YES|
| COMMENTS| tbc | Character| 1000|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## CLINICALDATA_COVERAGE_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| tbc | Character| 200|YES|
| COVERAGEID| tbc |  Int 64| |NO|
| STARTDATE| tbc | Date Time| |YES|
| ENDDATE| tbc | Date Time| |YES|
| GROUPDESCRIPTIONEMR| tbc | Character| 500|YES|
| PLANDESCRIPTIONEMR| tbc | Character| 500|YES|
| SUBGROUPDESCRIPTIONEMR| tbc | Character| 500|YES|
| MEMBERIDEMR| tbc | Character| 200|YES|
| PRECEDENCEEMR| tbc | Character| 500|YES|
| STATUS| tbc | Character| 200|YES|
| SOURCE| tbc | Character| 500|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## CLINICALDATA_HEART_MEASUREMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| tbc | Character| 200|YES|
| HEARTMEASUREMENTID| tbc |  Int 64| |NO|
| CODE1| tbc | Character| 500|YES|
| CODINGSYSTEM1| tbc | Character| 500|YES|
| CODE2| tbc | Character| 500|YES|
| CODINGSYSTEM2| tbc | Character| 500|YES|
| MEASUREMENTASNUMBER| tbc | Decimal fixed-point| 2 decimal places|YES|
| MEASUREMENTASTEXT| tbc | Character| 500|YES|
| DISPLAYMEASUREMENTUNITS| tbc | Character| 500|YES|
| MEASUREMENTUNITS| tbc | Character| 500|YES|
| MEASUREMENTMETHOD| tbc | Character| 500|YES|
| MEASUREMENTDATETIME| tbc | Date Time| |YES|
| SOURCE| tbc | Character| 500|YES|
| STATUS| tbc | Character| 500|YES|
| VERIFIEDBY| tbc | Character| 500|YES|
| SOURCESYTEM| tbc | Character| 500|YES|
| COMMENTS| tbc | Character| 500|YES|
| DATASOURCE| tbc | Character| 500|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## CLINICALDATA_HEIGHT_MEASUREMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| tbc | Character| 200|YES|
| HEIGHTMEASUREMENTID| tbc |  Int 64| |NO|
| CODE1| tbc | Character| 500|YES|
| CODINGSYSTEM1| tbc | Character| 500|YES|
| CODE2| tbc | Character| 500|YES|
| CODINGSYSTEM2| tbc | Character| 500|YES|
| MEASUREMENT| tbc | Character| 500|YES|
| MEASUREMENTUNIT| tbc | Character| 500|YES|
| DISPLAYMEASUREMENTUNITS| tbc | Character| 500|YES|
| MEASUREMENTDATETIME| tbc | Date Time| |YES|
| SOURCE| tbc | Character| 500|YES|
| STATUS| tbc | Character| 500|YES|
| VERIFIEDBY| tbc | Character| 500|YES|
| COMMENTS| tbc | Character| 500|YES|
| DATASOURCE| tbc | Character| 500|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## CLINICALDATA_LABS_MEASUREMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| tbc | Character| 200|YES|
| LABMEASUREMENTID| tbc |  Int 64| |NO|
| LABCODE1| tbc | Character| 500|YES|
| LABCODINGSYSTEM1| tbc | Character| 500|YES|
| LABCODE2| tbc | Character| 500|YES|
| LABCODINGSYSTEM2| tbc | Character| 500|YES|
| BODYSITEDISPLAY| tbc | Character| 500|YES|
| COMMENTS| tbc | Character| 500|YES|
| DATASOURCE| tbc | Character| 200|YES|
| INTERPRETATION| tbc | Character| 500|YES|
| LABSNAMESTRING| tbc | Character| 500|YES|
| MEASUREMENTMETHODDISPLAY| tbc | Character| 500|YES|
| MEASUREMENTUNITSSTRING| tbc | Character| 500|YES|
| MEASUREMENTDATE| tbc | Date Time| |YES|
| SOURCE| tbc | Character| 500|YES|
| STATUS| tbc | Character| 500|YES|
| VALUEASNUMBER| tbc | Decimal fixed-point| 2 decimal places|YES|
| VALUE| tbc | Character| 500|YES|
| RESULTDATE| tbc | Date| |YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## CLINICALDATA_MEDICATION_MEASUREMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| tbc | Character| 200|YES|
| MEDICATIONID| tbc |  Int 64| |NO|
| MEDICATIONCODES| tbc | Character| 200|YES|
| MEDICATIONNAME| tbc | Character| 200|YES|
| CODINGSYSTEM| tbc | Character| 500|YES|
| COMMENTS| tbc | Character| 500|YES|
| DATASOURE| tbc | Character| 500|YES|
| DURATION| tbc | Character| 50|YES|
| FREQUENCY| tbc | Character| 100|YES|
| INSTRUCTIONS| tbc | Character| 200|YES|
| QUANTITYASNUMBER| tbc | Decimal fixed-point| 2 decimal places|YES|
| QUANTITYASTEXT| tbc | Character| 100|YES|
| REASON| tbc | Character| 500|YES|
| ROUTE| tbc | Character| 200|YES|
| SIGCODE| tbc | Character| 200|YES|
| SOURCE| tbc | Character| 200|YES|
| DATE| tbc | Date Time| |YES|
| STARTDATE| tbc | Date Time| |YES|
| ENDDATE| tbc | Date Time| |YES|
| STATUS| tbc | Character| 50|YES|
| STRENGTH| tbc | Character| 100|YES|
| TYPE| tbc | Character| 200|YES|
| ORDEREDBY| tbc | Character| 200|YES|
| ORDEREDDATE| tbc | Date Time| |YES|
| PRESCRIPTIONNUMBER| tbc | Character| 200|YES|
| PRESCRIBEDDATE| tbc | Date Time| |YES|
| PRESCRIBEDBY| tbc | Character| 200|YES|
| FILLDATE| tbc | Date Time| |YES|
| PHARMACY| tbc | Character| 200|YES|
| REVIEWSTATUS| tbc | Character| 200|YES|
| LASTREFILLDATE| tbc | Date Time| |YES|
| REFILLS| tbc | Character| 200|YES|
| REFUSEDREASON| tbc | Character| 200|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## CLINICALDATA_MEDICATIONTAKING_MEASUREMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| MEDICATIONTAKINGID| tbc |  Int 64| |YES|
| CURRENTLYTAKING| tbc | Character| 20|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## CLINICALDATA_OXYGEN_MEASUREMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| tbc | Character| 200|YES|
| OXYGENMEASUREMENTID| tbc |  Int 64| |NO|
| CODE1| tbc | Character| 500|YES|
| CODINGSYSTEM1| tbc | Character| 500|YES|
| CODE2| tbc | Character| 500|YES|
| CODINGSYSTEM2| tbc | Character| 500|YES|
| MEASUREMENTASNUMBER| tbc | Decimal fixed-point| 4 decimal places|YES|
| MEASUREMENTASTEXT| tbc | Character| 500|YES|
| MEASUREMENTUNITS| tbc | Character| 500|YES|
| DISPLAYMEASUREMENTUNITS| tbc | Character| 500|YES|
| MEASUREMENTDATETIME| tbc | Date Time| |YES|
| SOURCESYTEM| tbc | Character| 500|YES|
| SOURCE| tbc | Character| 500|YES|
| STATUS| tbc | Character| 500|YES|
| VERIFIEDBY| tbc | Character| 500|YES|
| COMMENTS| tbc | Character| 500|YES|
| DATASOURCE| tbc | Character| 500|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## CLINICALDATA_RESPIRATORY_MEASUREMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| tbc | Character| 200|YES|
| RESPIRATORYMEASUREMENTID| tbc |  Int 64| |NO|
| CODE1| tbc | Character| 500|YES|
| CODINGSYSTEM1| tbc | Character| 500|YES|
| CODE2| tbc | Character| 500|YES|
| CODINGSYSTEM2| tbc | Character| 500|YES|
| MEASUREMENT| tbc | Character| 500|YES|
| MEASUREMENTUNITS| tbc | Character| 500|YES|
| DISPLAYMEASUREMENTUNITS| tbc | Character| 500|YES|
| MEASUREMENTDATETIME| tbc | Date Time| |YES|
| SOURCE| tbc | Character| 500|YES|
| STATUS| tbc | Character| 500|YES|
| VERIFIEDBY| tbc | Character| 500|YES|
| COMMENTS| tbc | Character| 500|YES|
| DATASOURCE| tbc | Character| 500|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## CLINICALDATA_RISKS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| tbc | Character| 200|YES|
| RISKID| tbc |  Int 64| |NO|
| CATEGORY| tbc | Character| 200|YES|
| DATASOURCE| tbc | Character| 200|YES|
| DATE| tbc | Date Time| |YES|
| RISKTYPE| tbc | Character| 200|YES|
| NAME| tbc | Character| 200|YES|
| SCOREASNUMBER| tbc | Decimal fixed-point| 2 decimal places|YES|
| SCOREASTEXT| tbc | Character| 200|YES|
| SOURCE| tbc | Character| 200|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## CLINICALDATA_TEMPERATURE_MEASUREMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| tbc | Character| 200|YES|
| TEMPERATUREMEASUREMENTID| tbc |  Int 64| |NO|
| CODE1| tbc | Character| 500|YES|
| CODINGSYSTEM1| tbc | Character| 500|YES|
| CODE2| tbc | Character| 500|YES|
| CODINGSYSTEM2| tbc | Character| 500|YES|
| MEASUREMENTASNUMBER| tbc | Decimal fixed-point| 4 decimal places|YES|
| MEASUREMENTASTEXT| tbc | Character| 500|YES|
| DISPLAYMEASUREMENTUNITS| tbc | Character| 500|YES|
| MEASUREMENTUNITS| tbc | Character| 500|YES|
| MEASUREMENTDATETIME| tbc | Date Time| |YES|
| MEASUREMENTSITE| tbc | Character| 500|YES|
| MEASUREMENTMETHOD| tbc | Character| 500|YES|
| SOURCE| tbc | Character| 500|YES|
| SOURCESYTEM| tbc | Character| 500|YES|
| STATUS| tbc | Character| 500|YES|
| VERIFIEDBY| tbc | Character| 500|YES|
| COMMENTS| tbc | Character| 500|YES|
| DATASOURCE| tbc | Character| 500|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## CLINICALDATA_WAIST_MEASUREMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| tbc | Character| 200|YES|
| WAISTMEASUREMENTID| tbc |  Int 64| |NO|
| CODE1| tbc | Character| 500|YES|
| CODINGSYSTEM1| tbc | Character| 500|YES|
| CODE2| tbc | Character| 500|YES|
| CODINGSYSTEM2| tbc | Character| 500|YES|
| MEASUREMENTASNUMBER| tbc | Decimal fixed-point| 2 decimal places|YES|
| MEASUREMENTASTEXT| tbc | Character| 500|YES|
| MEASUREMENTUNITS| tbc | Character| 500|YES|
| DISPLAYMEASUREMENTUNITS| tbc | Character| 500|YES|
| MEASUREMENTDATETIME| tbc | Date Time| |YES|
| SOURCE| tbc | Character| 500|YES|
| STATUS| tbc | Character| 500|YES|
| VERIFIEDBY| tbc | Character| 500|YES|
| COMMENTS| tbc | Character| 500|YES|
| DATASOURCE| tbc | Character| 500|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## CLINICALDATA_WAISTTOWEIGHT_MEASUREMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| tbc | Character| 200|YES|
| WAISTTOWEIGHTMEASUREMENTID| tbc |  Int 64| |NO|
| CODE1| tbc | Character| 500|YES|
| CODINGSYSTEM1| tbc | Character| 500|YES|
| CODE2| tbc | Character| 500|YES|
| CODINGSYSTEM2| tbc | Character| 500|YES|
| MEASUREMENT| tbc | Character| 500|YES|
| MEASUREMENTDATETIME| tbc | Date Time| |YES|
| SOURCE| tbc | Character| 500|YES|
| STATUS| tbc | Character| 500|YES|
| VERIFIEDBY| tbc | Character| 500|YES|
| COMMENTS| tbc | Character| 500|YES|
| DATASOURCE| tbc | Character| 500|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## CLINICALDATA_WEIGHT_MEASUREMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| tbc | Character| 200|YES|
| WEIGHTMEASUREMENTID| tbc |  Int 64| |NO|
| CODE1| tbc | Character| 500|YES|
| CODINGSYSTEM1| tbc | Character| 500|YES|
| CODE2| tbc | Character| 500|YES|
| CODINGSYSTEM2| tbc | Character| 500|YES|
| MEASUREMENTASNUMBER| tbc | Decimal fixed-point| 2 decimal places|YES|
| MEASUREMENTASTEXT| tbc | Character| 500|YES|
| MEASUREMENTUNITS| tbc | Character| 500|YES|
| DISPLAYMEASUREMENTUNITS| tbc | Character| 500|YES|
| MEASUREMENTDATETIME| tbc | Date Time| |YES|
| SOURCE| tbc | Character| 500|YES|
| STATUS| tbc | Character| 500|YES|
| VERIFIEDBY| tbc | Character| 500|YES|
| COMMENTS| tbc | Character| 500|YES|
| DATASOURCE| tbc | Character| 500|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|



This section describes data available for budgets.



## BUDGETS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| BUDGETID| tbc |  Int 64| |NO|
| CLIENTREFERENCE| tbc | Character| 200|YES|
| ROWNUM| tbc |  Int 64| |YES|
| WEEKLYBUDGETAMOUNT| tbc | Decimal fixed-point| 2 decimal places|YES|
| STARTDATE| tbc | Date| |YES|
| ENDDATE| tbc | Date| |YES|
| REASON| tbc | Character| 200|YES|
| COMMENTS| tbc | Character| 900|YES|
| ADDEDON| tbc | Date Time| |YES|
| ADDEDBY| tbc | Character| 524|YES|
| STATUS| tbc | Character| 200|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data



| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|
| ADDEDON | joins to USERS_V1_VIEW. | Cardinality is one-to-many. An alert joins to 1 user. |
| ADDEDBY | Joins to USERS_V1_VIEW.| Cardinality is zero-to-one. An alert joins to 1 user if closed. |



## BUDGET_CONTRIBUTIONS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| BUDGETCONTRIBUTIONID| tbc |  Int 64| |NO|
| BUDGETID| tbc |  Int 64| |NO|
| CONTRIBUTORNAME| tbc | Character| 200|YES|
| APPROVALTYPE| tbc | Character| 200|YES|
| CONTRIBUTIONAMOUNT| tbc | Decimal fixed-point| 2 decimal places|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data



| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| BUDGETID| Joins to BUDGETS_V1_VIEW. | Cardinality is zero-to-many.  A budget has zero-to-many contributions|


## BUDGET_HISTORIES_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| BUDGETID| tbc |  Int 64| |NO|
| STATUS| tbc | Character| 200|YES|
| UPDATEDON| tbc | Date Time| |YES|
| UPDATEDBY| tbc | Character| 256|YES|
| DRAFTAMOUNT| tbc | Decimal fixed-point| 2 decimal places|YES|
| STATUSCOMMENT| tbc | Character| 900|YES|
| UPDATEDAMOUNT| tbc | Decimal fixed-point| 2 decimal places|YES|
| BUDGETHISTORYID| tbc |  Int 64| |YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data



| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| BUDGETID| Joins to BUDGETS_V1_VIEW. | Cardinality is zero-to-many.  A budget has zero-to-many contributions|
| UPDATEDBY | joins to USERS_V1_VIEW. | Cardinality is one-to-many. An alert joins to 1 user. |

## BUDGET_SERVICES_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| SERVICEDELIVERYID| tbc |  Int 64| |NO|
| BUDGETID| tbc |  Int 64| |NO|
| INGESTIONTIME| tbc | Date Time| |YES|
| CLIENTREFERENCE| tbc | Character| 200|YES|
| PROVIDEROFFERINGID| tbc |  Int 64| |YES|
| SERVICEOFFERINGID| tbc |  Int 64| |NO|
| PROVIDERID| tbc |  Int 64| |YES|
| NAME| tbc | Character| 200|YES|
| DESCRIPTION| tbc | Character| 1000|YES|
| STATUS| tbc | Character| 200|YES|
| CATEGORIES| tbc | Character| 1000|YES|
| UNITVALUE| tbc | Character| 32|YES|
| UNITVALUEASNUMBER| tbc | Decimal fixed-point| 2 decimal places|YES|
| UNITTYPE| tbc | Character| 100|YES|
| STARTDATE| tbc | Date| |YES|
| CREATIONDATE| tbc | Date| |NO|
| EXPECTEDENDDATE| tbc | Date| |YES|
| COMPLETIONDATE| tbc | Date| |YES|
| FREQUENCY| tbc | Character| 200|YES|
| UNITCOST| tbc | Decimal fixed-point| 2 decimal places|YES|
| OUTCOME| tbc | Character| 200|YES|
| CREATEDBY| tbc | Character| 256|NO|
| COMPLETEDBY| tbc | Character| 256|YES|
| PAYMENTAUTHSTATUS| tbc | Character| 200|YES|
| AUTHSTATUSUPDATEDON| tbc | Date| |YES|
| AUTHSTATUSUPDATEDBY| tbc | Character| 200|YES|

### Links to other data



| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| BUDGETID| Joins to BUDGETS_V1_VIEW. | Cardinality is zero-to-many.  A budget has zero-to-many contributions|
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|
| CREATEDBY | joins to USERS_V1_VIEW. | Cardinality is one-to-many. An alert joins to 1 user. |
| CREATEDBY | Joins to USERS_V1_VIEW.| Cardinality is zero-to-one. An alert joins to 1 user if closed. |
| COMPLETEDBY | Joins to USERS_V1_VIEW.| Cardinality is zero-to-one. An alert joins to 1 user if closed. |



This section describes data available for barriers.





## BARRIERS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| BARRIERID| tbc |  Int 64| |NO|
| CLIENTREFERENCE| tbc | Character| 200|YES|
| NOTEID| tbc |  Int 64| |YES|
| NAME| tbc | Character| 1024|YES|
| CATEGORY| tbc | Character| 100|YES|
| STATUS| tbc | Character| 100|YES|
| ADDEDBY| tbc | Character| 200|NO|
| ADDEDON| tbc | Date Time| |NO|
| RESOLVEDBY| tbc | Character| 200|YES|
| RESOLVEDON| tbc | Date| |YES|
| NOTETEXT| tbc | Character| 1024|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data



| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|
| RESOLVEDBY | joins to USERS_V1_VIEW. | Cardinality is one-to-many. An alert joins to 1 user. |







This section describes data available for alerts.


## GOAL_BARRIERS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| BARRIERID| Unique identifier of the Goal Barrier |  Int 64| |NO|
| GOALID| Unique identifier of the Goal |  Int 64| |NO|
| GOALNAME| Name of the Goal | Character| 1024|YES|
| BARRIERNAME| Name of the Barrier | Character| 1024|YES|
| INGESTIONTIME| Date and Time the record was ingested, supports change data capture | Date Time| |YES|

### Links to other data



| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| GOALID| Joins to GOALS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many goals|
| BARRIERID | joins to BARRIERS_V1_VIEW. | Cardinality is one-to-many. A goal joins to 1 barrier. |

## GOAL_CLIENTACTIONS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| GOALID| Unique identifier of the Goal |  Int 64| |NO|
| ACTIONID| Unique identifier of the Goal Action |  Int 64| |NO|
| GOALNAME| Name of the Goal | Character| 1024|YES|
| ACTION| Name of the Client Action | Character| 1024|YES|
| INGESTIONTIME| Date and Time the record was ingested, supports change data capture | Date Time| |YES|

### Links to other data



| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| GOALID|GOALS_V1_VIEW | Cardinality is one-to-many.  A client has zero-to-many goals|

## GOAL_PROGRESSCOMMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| PROGRESSID| Unique identifier of the Goal Progress |  Int 64| |NO|
| GOALID| Unique identifier of the Goal |  Int 64| |NO|
| CREATIONDATE| Date when the comment was added to the progress update | Date Time| |NO|
| CREATEDBY| First name and last name of the user who added the Progress Comment | Character| 256|NO|
| COMMENTS| Comment recorded when the goal progress was updated | Character| 8000|YES|
| PROGRESS| Date and Time the record was ingested, supports change data capture | Character| 256|YES|

### Links to other data



| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| GOALID| Joins to GOALS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many goals|

## GOAL_TEAMACTIONS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| GOALID| Unique identifier of the Goal |  Int 64| |NO|
| ACTIONID| Unique identifier of the Goal Action |  Int 64| |NO|
| GOALNAME| Name of the Goal | Character| 1024|YES|
| ACTION| Name of the Action | Character| 1024|YES|
| INGESTIONTIME| Date and Time the record was ingested, supports change data capture | Date Time| |YES|

### Links to other data



| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| GOALID| Joins to GOALS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many goals|




This section describes data available for inquiries.





## INQUIRIES_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| INQUIRYID| tbc |  Int 64| |NO|
| CLIENTREFERENCE| tbc | Character| 200|YES|
| SERVICEOFFERINGID| tbc |  Int 64| |NO|
| SERVICENAME| tbc | Character| 500|YES|
| REFERENCENUMBER| tbc |  Int 64| |NO|
| RECORDEDON| tbc | Date Time| |YES|
| RECORDEDBY| tbc | Character| 256|YES|
| RESPONSEREQUIREDBY| tbc | Date| |YES|
| UNITTYPE| tbc | Character| 200|YES|
| UNITVALUE| tbc | Character| 50|YES|
| EXPECTEDSTARTDATE| tbc | Date| |YES|
| EXPECTEDENDDATE| tbc | Date| |YES|
| FREQUENCY| tbc | Character| 200|YES|
| STATUS| tbc | Character| 200|YES|
| DAYS| tbc | Character| 500|YES|
| REASON| tbc | Character| 200|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data


| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many inquiry|
| RECORDEDBY | joins to USERS_V1_VIEW. | Cardinality is one-to-many. An alert joins to 1 user. |


## INQUIRY_COMMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| INQUIRYID| tbc |  Int 64| |NO|
| RECORDEDON| tbc | Date Time| |NO|
| RECORDEDBY| tbc | Character| 256|NO|
| COMMENT| tbc | Character| 8000|YES|
| INQUIRYEVENTID| tbc |  Int 64| |NO|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data



| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| INQUIRYID| Joins to INQUIRIES_V1_VIEW. | Cardinality is one-to-many.  A inquiry has zero-to-many comments|
| RECORDEDBY | joins to USERS_V1_VIEW. | Cardinality is one-to-many. An alert joins to 1 user. |


## INQUIRY_RESPONSES_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| INQUIRYLINEITEMID| tbc |  Int 64| |NO|
| INQUIRYID| tbc |  Int 64| |NO|
| PROVIDERID| tbc |  Int 64| |NO|
| SERVICEOFFERINGID| tbc |  Int 64| |NO|
| CLIENTREFERENCE| tbc | Character| 200|YES|
| RESPONDER| tbc | Character| 400|NO|
| STATUS| tbc | Character| 200|YES|
| OFFEREXPIRYDATE| tbc | Date| |YES|
| OFFEREDUNITS| tbc | Character| 32|YES|
| OFFEREDRATE| tbc | Decimal fixed-point| 2 decimal places|YES|
| RECORDEDON| tbc | Date Time| |YES|
| RECORDEDBY| tbc | Character| 256|YES|
| COMMENTS| tbc | Character| 8000|YES|
| ISRESPONSECOMMENT| tbc |  Int 32| |NO|
| TYPE| tbc | Character| 200|NO|
| INQUIRYLINEITEMEVENTID| tbc |  Int 64| |NO|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data


| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|
| INQUIRYID| Joins to INQUIRIES_V1_VIEW. | Cardinality is one-to-many.  A inquire has zero-to-many responses|
| PROVIDERID| Joins to PROVIDERS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|





This section describes data available for notes.








## NOTE_COMMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| NOTEID| tbc |  Int 64| |NO|
| NOTETYPE| tbc | Character| 40|NO|
| MODIFIEDDATETIME| tbc | Date Time| |YES|
| POSITION| tbc |  Int 32| |NO|
| AUTHOR| tbc | Character| 100|YES|
| CONTENT| tbc | Character| 32592|YES|
| CREATIONDATE| tbc | Date Time| |YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data



| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| NOTEID| Joins to NOTES_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|




This section describes data available for providers.




## PROVIDERS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| PROVIDERID| tbc |  Int 64| |NO|
| NAME| tbc | Character| 500|YES|
| PHONECOUNTRYCODE| tbc | Character| 20|YES|
| PHONEAREACODE| tbc | Character| 32|YES|
| PHONENUMBER| tbc | Character| 80|YES|
| PHONEEXTENSION| tbc | Character| 60|YES|
| EMAILADDRESS| tbc | Character| 256|YES|
| WEBSITE| tbc | Character| 400|YES|
| STATUS| tbc | Character| 200|YES|
| STARTDATE| tbc | Date| |NO|
| CREATEDBY| tbc | Character| 256|NO|
| CQCPROVIDERID| tbc | Character| 80|YES|
| PAYPALSIGNUP| tbc | Character| 1|NO|
| DESCRIPTION| tbc | Character| 2000|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| -| - | -  |





## PROVIDER_ADDRESSES_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| PROVIDERID| tbc |  Int 64| |NO|
| STATUS| tbc | Character| 200|YES|
| PRIMARYADDRESS| tbc | Character| 1|NO|
| COUNTRY| tbc | Character| 200|YES|
| ADD1| tbc | Character| 1024|YES|
| ADD2| tbc | Character| 1024|YES|
| ADD3| tbc | Character| 1024|YES|
| CITY| tbc | Character| 100|YES|
| STATE| tbc | Character| 100|YES|
| ZIP| tbc | Character| 30|YES|
| PROVIDERADDRESSID| tbc |  Int 64| |YES|
| ADDRESSID| tbc |  Int 64| |YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| PROVIDERID| Joins to PROVIDERS_V1_VIEW. | Cardinality is zero-to-many.  A provider has zero-to-many alerts|

## PROVIDER_CONNECT_USERS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| PROVIDERID| tbc |  Int 64| |NO|
| FIRSTNAME| tbc | Character| 260|YES|
| LASTNAME| tbc | Character| 260|YES|
| PHONECOUNTRYCODE| tbc | Character| 20|YES|
| PHONEAREACODE| tbc | Character| 32|YES|
| PHONENUMBER| tbc | Character| 80|YES|
| PHONEEXTENSION| tbc | Character| 60|YES|
| EMAIL| tbc | Character| 1024|YES|
| STATUS| tbc | Character| 200|YES|
| REQUESTSENT| tbc | Date Time| |YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| PROVIDERID| Joins to PROVIDERS_V1_VIEW. | Cardinality is zero-to-many.  A provider has zero-to-many alerts|

## PROVIDER_CONTACTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| PROVIDERID| tbc |  Int 64| |NO|
| FIRSTNAME| tbc | Character| 260|YES|
| LASTNAME| tbc | Character| 260|YES|
| ROLE| tbc | Character| 200|YES|
| PRIMARYCONTACT| tbc | Character| 1|NO|
| PHONECOUNTRYCODE| tbc | Character| 20|YES|
| PHONEAREACODE| tbc | Character| 32|YES|
| PHONENUMBER| tbc | Character| 80|YES|
| PHONEEXTENSION| tbc | Character| 60|YES|
| MOBILEPHONECOUNTRYCODE| tbc | Character| 20|YES|
| MOBILEPHONEAREACODE| tbc | Character| 32|YES|
| MOBILEPHONENUMBER| tbc | Character| 80|YES|
| MOBILEPHONEEXTENSION| tbc | Character| 60|YES|
| EMAILADDRESS| tbc | Character| 256|YES|
| PROVIDERCONTACTLINKID| tbc |  Int 64| |YES|
| PROVIDERCONTACTID| tbc |  Int 64| |YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| PROVIDERID| Joins to PROVIDERS_V1_VIEW. | Cardinality is zero-to-many.  A provider has zero-to-many alerts|

## PROVIDER_IDENTIFICATIONS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| PROVIDERID| tbc |  Int 64| |NO|
| IDENTIFICATIONNUMBER| tbc | Character| 72|NO|
| IDENTIFICATIONTYPE| tbc | Character| 200|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| PROVIDERID| Joins to PROVIDERS_V1_VIEW. | Cardinality is zero-to-many.  A provider has zero-to-many alerts|

## PROVIDER_SERVICE_ADDRESSES_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| PROVIDEROFFERINGID| tbc |  Int 64| |NO|
| STATUS| tbc | Character| 200|YES|
| COUNTRY| tbc | Character| 200|YES|
| ADD1| tbc | Character| 1024|YES|
| ADD2| tbc | Character| 1024|YES|
| ADD3| tbc | Character| 1024|YES|
| CITY| tbc | Character| 100|YES|
| STATE| tbc | Character| 100|YES|
| ZIP| tbc | Character| 30|YES|
| PROVIDERADDRESSID| tbc |  Int 64| |YES|
| ADDRESSID| tbc |  Int 64| |YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| PROVIDERID| Joins to PROVIDERS_V1_VIEW. | Cardinality is zero-to-many.  A provider has zero-to-many alerts|

## PROVIDER_SERVICE_CONTACTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| PROVIDEROFFERINGID| tbc |  Int 64| |NO|
| FIRSTNAME| tbc | Character| 260|YES|
| LASTNAME| tbc | Character| 260|YES|
| ROLE| tbc | Character| 200|YES|
| PRIMARYCONTACT| tbc | Character| 1|NO|
| PHONECOUNTRYCODE| tbc | Character| 20|YES|
| PHONEAREACODE| tbc | Character| 32|YES|
| PHONENUMBER| tbc | Character| 80|YES|
| PHONEEXTENSION| tbc | Character| 60|YES|
| MOBILEPHONECOUNTRYCODE| tbc | Character| 20|YES|
| MOBILEPHONEAREACODE| tbc | Character| 32|YES|
| MOBILEPHONENUMBER| tbc | Character| 80|YES|
| MOBILEPHONEEXTENSION| tbc | Character| 60|YES|
| EMAILADDRESS| tbc | Character| 256|YES|
| PROVIDERCONTACTLINKID| tbc |  Int 64| |YES|
| PROVIDERCONTACTID| tbc |  Int 64| |YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| -| - | -|

## PROVIDER_SERVICE_HISTORIES_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| PROVIDEROFFERINGID| tbc |  Int 64| |NO|
| STATUS| tbc | Character| 100|YES|
| STARTDATETIME| tbc | Date Time| |NO|
| CLOSEDDATE| tbc | Date| |YES|
| RECORDEDBY| tbc | Character| 256|NO|
| REASON| tbc | Character| 2000|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|
| CREATEDBY | joins to USERS_V1_VIEW. | Cardinality is one-to-many. An alert joins to 1 user. |
| CLOSEDBY | Joins to USERS_V1_VIEW.| Cardinality is zero-to-one. An alert joins to 1 user if closed. |
| ALERTID | Joins to ALERT_NOTIFICATIONS_V1_VIEW.| Cardinality is zero-to-many. |

## PROVIDER_SERVICE_RATES_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| PROVIDEROFFERINGID| tbc |  Int 64| |NO|
| RATE| tbc | Decimal fixed-point| 2 decimal places|NO|
| STARTDATE| tbc | Date| |NO|
| ENDDATE| tbc | Date| |YES|
| UNITTYPE| tbc | Character| 100|YES|
| PROVIDEROFFERINGRATEID| tbc |  Int 64| |YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## PROVIDER_SERVICES_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| PROVIDERID| tbc |  Int 64| |NO|
| PROVIDEROFFERINGID| tbc |  Int 64| |NO|
| SERVICEOFFERINGID| tbc |  Int 64| |NO|
| PROVIDEROFFERINGGROUPID| tbc |  Int 64| |NO|
| NAME| tbc | Character| 200|YES|
| GROUPNAME| tbc | Character| 200|YES|
| LANGUAGES| tbc | Character| 500|YES|
| STATUS| tbc | Character| 200|YES|
| CATEGORIES| tbc | Character| 1000|YES|
| CQCLOCATIONID| tbc | Character| 80|YES|
| ADDEDON| tbc | Date Time| |YES|
| ADDEDBY| tbc | Character| 256|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|

## PROVIDER_SHORTLISTED_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| PROVIDEROFFERINGID| tbc |  Int 64| |NO|
| CLIENTREFERENCE| tbc | Character| 200|YES|
| SHORTLISTEDBYUSERNAME| tbc | Character| 256|YES|
| SHORTLISTEDBYEXTERNALUSER| tbc | Character| 400|NO|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|






This section describes data available for services.





## SERVICES_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| SERVICEDELIVERYID| tbc |  Int 64| |NO|
| CLIENTREFERENCE| tbc | Character| 200|YES|
| PROVIDEROFFERINGID| tbc |  Int 64| |YES|
| SERVICEOFFERINGID| tbc |  Int 64| |NO|
| PROVIDERID| tbc |  Int 64| |YES|
| NAME| tbc | Character| 200|YES|
| DESCRIPTION| tbc | Character| 1000|YES|
| STATUS| tbc | Character| 200|YES|
| CATEGORIES| tbc | Character| 1000|YES|
| UNITVALUE| tbc | Character| 32|YES|
| UNITVALUEASNUMBER| tbc | Decimal fixed-point| 2 decimal places|YES|
| UNITTYPE| tbc | Character| 100|YES|
| STARTDATE| tbc | Date| |YES|
| CREATIONDATE| tbc | Date| |NO|
| EXPECTEDENDDATE| tbc | Date| |YES|
| COMPLETIONDATE| tbc | Date| |YES|
| FREQUENCY| tbc | Character| 200|YES|
| UNITCOST| tbc | Decimal fixed-point| 2 decimal places|YES|
| OUTCOME| tbc | Character| 200|YES|
| CREATEDBY| tbc | Character| 256|NO|
| COMPLETEDBY| tbc | Character| 256|YES|
| PAYMENTAUTHSTATUS| tbc | Character| 200|YES|
| AUTHSTATUSUPDATEDON| tbc | Date| |YES|
| AUTHSTATUSUPDATEDBY| tbc | Character| 200|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|
| CREATEDBY | joins to USERS_V1_VIEW. | Cardinality is one-to-many. An alert joins to 1 user. |
| CLOSEDBY | Joins to USERS_V1_VIEW.| Cardinality is zero-to-one. An alert joins to 1 user if closed. |
| ALERTID | Joins to ALERT_NOTIFICATIONS_V1_VIEW.| Cardinality is zero-to-many. |





This section describes data available for team actions.





## TEAMACTION_BARRIERS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| BARRIERID| tbc |  Int 64| |NO|
| ACTIONID| tbc |  Int 64| |NO|
| ACTIONNAME| tbc | Character| 1024|YES|
| BARRIERNAME| tbc | Character| 1024|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|
| CREATEDBY | joins to USERS_V1_VIEW. | Cardinality is one-to-many. An alert joins to 1 user. |
| CLOSEDBY | Joins to USERS_V1_VIEW.| Cardinality is zero-to-one. An alert joins to 1 user if closed. |
| ALERTID | Joins to ALERT_NOTIFICATIONS_V1_VIEW.| Cardinality is zero-to-many. |

## TEAMACTION_PROGRESSCOMMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| PROGRESSID| tbc |  Int 64| |NO|
| ACTIONID| tbc |  Int 64| |NO|
| CREATIONDATE| tbc | Date Time| |NO|
| CREATEDBY| tbc | Character| 256|NO|
| COMMENTS| tbc | Character| 8000|YES|
| PROGRESS| tbc | Character| 256|YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|
| CREATEDBY | joins to USERS_V1_VIEW. | Cardinality is one-to-many. An alert joins to 1 user. |
| CLOSEDBY | Joins to USERS_V1_VIEW.| Cardinality is zero-to-one. An alert joins to 1 user if closed. |
| ALERTID | Joins to ALERT_NOTIFICATIONS_V1_VIEW.| Cardinality is zero-to-many. |

## TEAMACTIONS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| tbc | Character| 200|YES|
| ACTIONID| tbc |  Int 64| |NO|
| ASSIGNEDTO| tbc | Character| 256|YES|
| ASSIGNEDTOFULLNAME| tbc | Character| 524|YES|
| ASSIGNEDTOTEAMROLE| tbc | Character| 200|YES|
| NAME| tbc | Character| 1024|YES|
| CATEGORY| tbc | Character| 100|YES|
| STATUS| tbc | Character| 100|YES|
| ADDEDBY| tbc | Character| 200|NO|
| ADDEDON| tbc | Date| |NO|
| REASON| tbc | Character| 2000|YES|
| STARTDATE| tbc | Date| |NO|
| EXPECTEDENDDATE| tbc | Date| |YES|
| COMPLETEDON| tbc | Date| |YES|
| COMPLETEDBY| tbc | Character| 200|YES|
| OUTCOME| tbc | Character| 100|YES|
| PROGRESS| tbc | Character| 256|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|
| CREATEDBY | joins to USERS_V1_VIEW. | Cardinality is one-to-many. An alert joins to 1 user. |
| CLOSEDBY | Joins to USERS_V1_VIEW.| Cardinality is zero-to-one. An alert joins to 1 user if closed. |
| ALERTID | Joins to ALERT_NOTIFICATIONS_V1_VIEW.| Cardinality is zero-to-many. |




This section describes data available for touchpoints.





## PATIENTS_UNDER_MANAGEMENT_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| MONTHYEAR| tbc | Date| |NO|
| PATIENTID| tbc |  Int 64| |NO|
| MONTH| tbc | Character| 40|NO|
| YEAR| tbc |  Int 32| |NO|
| ACTIVELYMANAGEDDAYS| tbc |  Int 32| |NO|
| RECORDSTATUS| tbc | Character| 40|NO|
| UNIQUEREF| tbc | Character| 200|YES|
| FIRSTNAME| tbc | Character| 200|YES|
| LASTNAME| tbc | Character| 200|YES|
| INGESTIONTIME| tbc | Date Time| |YES|

### Links to other data



| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| -| - | -|



## PROGRAM_BARRIERS_V1_VIEW


| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| BARRIERID| tbc |  Int 64| ---|NO|
| PROGRAMID| tbc |  Int 64|--- |NO|
| PROGRAMNAME| tbc | Character| 75|YES|
| BARRIERNAME| tbc | Character| 1024|YES|
| INGESTIONTIME| tbc | Date Time| ---|YES|

### Links to other data



| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| BARRIERID| BARRIERS_V1_VIEW | Cardinality is one-to-one.  A program is associated with zero-to-many program associated barriers|
| PROGRAMID| PROGRAMS_V1_VIEW | Cardinality is one-to-one.  A program barrier is associated with one program enrollment|

## PROGRAM_CLIENTACTIONS_V1_VIEW


| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| ACTIONID| tbc |  Int 64| ---|NO|
| PROGRAMID| tbc |  Int 64|--- |NO|
| PROGRAMNAME| tbc | Character| 75|YES|
| ACTIONAME| tbc | Character| 1024|YES|
| INGESTIONTIME| tbc | Date Time|--- |YES|

### Links to other data



| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| ACTIONID| BARRIERS_V1_VIEW | Cardinality is one-to-one.  A client action is associated with one program enrolment|
| PROGRAMID| PROGRAMS_V1_VIEW | Cardinality is one-to-one.  A program barrier is associated with one program enrolment|

## PROGRAM_GOALS_V1_VIEW


| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| GOALID| tbc |  Int 64| ---|NO|
| PROGRAMID| tbc |  Int 64|--- |NO|
| PROGRAMNAME| tbc | Character| 75|YES|
| GOALNAME| tbc | Character| 1024|YES|
| INGESTIONTIME| tbc | Date Time| ---|YES|

### Links to other data



| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| GOALID|  BARRIERS_V1_VIEW | Cardinality is one-to-one.  A goal is associated with one program enrolment|
| PROGRAMID| PROGRAMS_V1_VIEW | Cardinality is one-to-one.  A program barrier is associated with one program enrolment|

## PROGRAM_TEAMACTIONS_V1_VIEW


| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| ACTIONID| tbc |  Int 64| ---|NO|
| PROGRAMID| tbc |  Int 64| --- |NO|
| PROGRAMNAME| tbc | Character| 75|YES|
| ACTIONAME| tbc | Character| 1024|YES|
| INGESTIONTIME| tbc | Date Time| --- |YES|

### Links to other data



| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| ACTIONID| BARRIERS_V1_VIEW | Cardinality is one-to-one.  An action is associated with one program enrolment|
| PROGRAMID|PROGRAMS_V1_VIEW | Cardinality is one-to-one.  A program barrier is associated with one program enrolment|

## PROGRAM_TOUCHPOINTS_V1_VIEW


| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| TOUCHPOINTID| tbc |  Int 64| ---|NO|
| CLIENTREFERENCE| tbc | Character| 200|YES|
| PROGRAMID| tbc |  Int 64| ---|YES|
| PROGRAMNAME| tbc | Character| 75|YES|
| TOUCHPOINTSUBJECT| tbc | Character| 500|YES|
| INGESTIONTIME| tbc | Date Time| ---|YES|

### Links to other data



| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| TOUCHPOINTID|BARRIERS_V1_VIEW | Cardinality is one-to-one.  An touchpoint is associated with one program enrolment|
| PROGRAMID|PROGRAMS_V1_VIEW | Cardinality is one-to-one.  A program barrier is associated with one program enrolment|






This section describes data available for goals.

A goal is a measurable target that a client can achieve. Use this data set to identify a client's planned goal.


## GOALS_V1_VIEW

This view groups attributes that relate to to a client's goals such as the goal name, focus area, type, progress and competion details.  


| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| [REFERRALS_V1_VIEW](guides/referral.md)|This view groups attributes that relate to client referral such as the referral date, referral reason, cohort, and organization unit that referred the client, or that the client was referred to.| 22:06|
| [GOALS_V1_VIEW](guides/clinicaldata.md)|This view groups attributes that relate to to a client's goals such as the goal name, type, start date and end date. A goal is a measurable target that a client can achieve. Use this data set to identify a client's planned goal.|22:06|
| GOALID| Identifier for a goal. |  Int 64| ---|NO|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|NO|
| NAME| Name of the goal. | Character| 1024|No|
| FOCUSAREA| Focus area of the goal for reporting purposes. For example, medications, safety, basic needs. | Character| 200|YES|
| TYPE| Goal type, for example, long-term or short term | Character| 100|YES|
| STAGEOFCHANGE| Value that indicates the client's readiness or motivation in relation to the goal. | Character| 100|YES|
| IMPORTANCE| Importance of the goal to the client, on a scale of 1 (low) to 10 (high). | Character| 100|YES|
| CONFIDENCE| Client's confidence about the goal, on a scale of 1 (low) to 10 (high). | Character| 100|YES|
| ADDEDBY| First name and last name of the user who added the goal. | Character| 200|NO|
| ADDEDON| Date the record was added. | Date| ---|NO|
| COMPLETEDBY| First name and last name of the user who completed the item. | Character| 200|YES|
| COMPLETEDON| Date when record was set to completed. | Date|--- |YES|
| SOURCE| Origin of the goal. For example, Care Manager or Program. | Character| 100|YES|
| STARTDATE| Date on which the goal is due to start. | Date|--- |YES|
| TARGETDATE| Date on which the goal is expected to be completed. | Date| ---|YES|
| REASON| Reaon the goal was added to the care plan. | Character| 2000|YES|
| OUTCOME| Outcome of the goal. For example, successful, not successful, or abandoned. | Character| 100|YES|
| PROGRESS|  Latest progress recorded in relation to the record,for example, poor, good, very good, excellent. 256|YES|
| TARGETVALUE| Target value that represents the achievement of the goal. | Character| 100|YES|
| COMPLETIONCOMMENTS| Most recent comment added when the goal was completed. | Character| 8000|YES|
| INGESTIONTIME| Date and Time the record was ingested, supports change data capture. | Date Time| ---|YES|

### Links to other data



| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-many. <br/> A client is assocaited with zero-to-many goals.|
| COMPLETEDBY | USERS_V1_VIEW | Cardinality is one-to-many. <br/> A goal joins to one user. |





This section describes data available for referrals.


Referrals are used to direct a client to the correct organization unit that will meet their care management needs.  


## REFERRALS_V1_VIEW

This view groups attributes that relate to a client's referrals such as cohort name, referral date, referral reason and stats of the referral.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| REFERRALID| Identifier for a record. |  Int 64|--- |NO|
| COHORTNAME| Name of the cohort that referred the client. Only populated when the referral came from an external system. | Character| 500|YES|
| COHORTSOURCE| Indicates where the cohort came from, for example, a facility or an external system. Only populated when the referral came from an external system. The field is not displayed in the Watson Care Manager user interface. | Character| 100|YES|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|NO|
| REFERRALREASON| Reason the client was referred.| Character| 2000|NO|
| REFERREDDATE| Date that the client was referred to the organization. | Date|--- |NO|
| CREATEDBY| First name and last name of the user who created the referral. | Character| 200|NO|
| STATUS| Current status of the referral, open, accepted, or rejected. | Character| 200|YES|
| PRIORITY|Priority of the item, high, medium, low or not set. | Character| 200|YES|
| FROMORGNAME| Name of the organization unit that referred the client.| Character| 500|YES|
| FROMORGEXTERNALREF| Reference number for the organization unit that referred the client. | Character| 400|YES|
| TOORGNAME| Name of the organization unit that the client was referred to. | Character| 500|YES|
| TOORGEXTERNALREF| Reference number for the organization unit that the client was referred to. | Character| 400|YES|
| COMMENTS| Comments entered for the record. | Character| 2000|YES|
| ASSIGNEDTO| First name and last name of the user who is assigned the referral. | Character| 200|YES|
| ASSIGNEDDATE| Date and time that the referral was assigned to a care manager. | Date Time| ---|YES|
| REJECTREASON| Reason for rejecting the referral that was selected from a preconfigured list of reasons. | Character| 200|YES|
| REJECTCOMMENTS| Comments relating to the referral rejection. | Character| 2000|YES|
| REJECTOTHERREASON|  Reason entered for rejecting the referral, if none of the reasons in the preconfigured list were suitable for selection. | Character| 500|YES|
| REJECTEDATE| Date and time that the referral was rejected.| Date Time| ---|YES|
| REJECTEDY| First name and last name of the user who rejected the referral. | Character| 200|YES|
| OTHERREFERRALREASON| Other referral reason. | Character| 2000|YES|
| SOURCE| System in which the data was recorded. | Character| 400|YES|
| ORIGINALSOURCE| System in which the data was recorded for the first time. | Character| 400|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time| ---|YES|

### Links to other data


| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE|CLIENTS_V1_VIEW | Cardinality is one-to-many. <br/>  A client is assocaited with zero-to-many referrals.|
| CREATEDBY | USERS_V1_VIEW | Cardinality is one-to-many. <br/>  A referral joins to one user. |
| ASSIGNEDTO |  USERS_V1_VIEW| Cardinality is zero-to-one. <br/>  A referral joins to one user. |
| REJECTEDY | USERS_V1_VIEW| Cardinality is zero-to-one. <br/> A referral joins to one user. |



## TASK_ROLES_V1_VIEW


| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| TEAMROLEID| Identifier for a record. |  Int 64| ---|NO|
| TEAMROLE| The  team role that is assigned the task. | Character| 200|NO|
| RECORDSTATUS| Status of the record, Actived or Cancelled. | Character| 40|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time| ---|NO|
