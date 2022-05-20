

This section describes data available for assessments and questionnaries.


A questionnaire  is a custom or industry-standard set of questions that can be used to gather information about a client. You can run a questionnaire by completing questions.


## QUESTIONNAIRE_V1_VIEW

This view groups attributes that relate to client questionnaires, for example, the questionnaire name, questions, and answers provided when filling out the questionnaire.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:--------------|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200| NO            |
| ASSESSMENTINSTANCEID| Identifier for a record.  |  Int 64| ---| NO            |
| ASSESSMENTSTATUS| Status of the assessment, in progress or complete. | Character| 40| NO            |
| STARTEDBY| Full name of the user who added the assessment. | Character| 256| NO            |
| STARTEDDATE| Date and time that the asssessment was started. | Date Time| ---| NO            |
| COMPLETEDBY| First and last name of the user who completed the assessment. | Character| 256| YES           |
| COMPLETEDDATE| Date and time that the assessment was completed. | Date Time| ---| YES           |
| ASSESSMENTNAME| The name of the assessment. | Character| 500| NO            |
| QUESTION| Question asked in the assessment.  | Character| 4000| NO            |
| POSITION| Order that the question numbers are shown in the report, for example, I, 2, 3, 4. |  Int 32| ---| YES           |
| ANSWER| Client's answer to the question, in string or text format. | Character| 4000| YES           |
| DOUBLEVALUE| If the base data type of the answer to the question is a float or a decimal, this field displays a numeric double value that you can use for comparisons or arithmetic. Otherwise, this field is blank. | Double floating-point| ---| YES           |
| LONGVALUE| If the base data type of the answer to the question is an integer, this field displays a number that you can use for comparisons or arithmetic. Otherwise, this field is blank. |  Int 64| ---| YES           |
| DATEVALUE| If the base data type of the answer to the question is a date, time, or timestamp, this field displays a date value that you can use for comparisons or arithmetic. Otherwise, this field is blank. | Date Time| ---| YES           |
| SCORE| Score associated with the client's answer to the question. | Decimal floating-point| ---| YES           |
| INGESTIONTIME| Date and time the record was ingested, supports changed data capture. | Date Time| ---| NO            |

### Links to other data

| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Client reference joins to a client.<br /> A client is associated with zero-to-many questionnaires.|
| ASSESSMENTINSTANCEID | ASSESSMENTS_V1_VIEW | A questionnaire is associated with one-to-many assessment instances. |
| STARTEDBY | USERS_V1_VIEW | Created-by joins to a user.<br /> A user is associated with zero-to-many questionnaires. |
| COMPLETEDBY | USERS_V1_VIEW| Updated-by joins to one user.<br /> A user is associated with zero-to-many completed questionnaires. |
| ASSESSMENTINSTANCEID| PROGRAM_ASSESSMENTS_V1_VIEW | An assessment instance is associated with a program.|

<br />
<br />

An assessment is a custom or industry-standard set of questions which produces a result that can be used to assess a client's needs. You can run an assessment by completing questions.

The following views group attributes that relate to client assessments such as questions, answer types for each question, answer provided by the client, measure, classification and score for completed assessments.  

## ASSESSMENTS_V1_VIEW

This view groups attributes that relate to client assessments, for example, the assessment name, answers, status and score.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:--------------|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200| NO            |
| ASSESSMENTINSTANCEID| Identifier for a record.  |  Int 64|--- | NO            |
| ASSESSMENTSTATUS| Status of the assessment, in progress or complete. | Character| 40| NO            |
| STARTEDBY| Full name of the user who added the assessment. | Character| 256| NO            |
| STARTEDDATE| Date and time that the asssessment was started. | Date Time| ---| NO            |
| COMPLETEDBY| First and last name of the user who completed the assessment. | Character| 256| YES           |
| COMPLETEDDATE| Date and time that the assessment was completed. | Date Time| ---| YES           |
| SCOREONLYIND| Indicates if an assessment score only was captured.  | Character| 1| NO            |
| SCOREONLYDATE| Date that the assessment was conducted when only an assessment score was captured.  | Date| ---| YES           |
| SCOREONLYSOURCE| Source of the assessment when only an assessment score was captured. For example, Payer, Self Reported.  | Character| 100| YES           |
| ASSESSMENTNAME| The name of the assessment. | Character| 500| YES           |
| QUESTION| Question asked in the assessment.  | Character| 4000| NO            |
| POSITION| Order that the question numbers are shown in the report, for example, I, 2, 3, 4. |  Int 32| ---| YES           |
| ANSWER| Client's answer to the question, in string or text format. | Character| 4000| YES           |
| DOUBLEVALUE| If the base data type of the answer to the question is a float or a decimal, this field displays a numeric double value that you can use for comparisons or arithmetic. Otherwise, this field is blank. | Double floating-point| ---| YES           |
| LONGVALUE| If the base data type of the answer to the question is an integer, this field displays a number that you can use for comparisons or arithmetic. Otherwise, this field is blank. |  Int 64| ---| YES           |
| DATEVALUE| If the base data type of the answer to the question is a date, time, or timestamp, this field displays a date value that you can use for comparisons or arithmetic. Otherwise, this field is blank. | Date Time| ---| YES           |
| SCORE| Score associated with the client's answer to the question. | Decimal floating-point| ---| YES           |
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time| ---| NO            |

### Links to other data

| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Client reference joins to a client.<br /> A client is associated with zero-to-many assessments.|
| STARTEDBY | USERS_V1_VIEW | Created-by joins to a user.<br /> A user is associated with zero-to-many assessments. |
| COMPLETEDBY | USERS_V1_VIEW| Updated-by joins to one user.<br /> A user is associated with zero-to-many completed assessments. |
| ASSESSMENTINSTANCEID| ASSESSMENT_MEASURES_V1_VIEW | An assessment is associated with one-to-many measures.|
| ASSESSMENTINSTANCEID| PROGRAM_ASSESSMENTS_V1_VIEW | An assessment instance is associated with a program.|


## ASSESSMENT_MEASURES_V1_VIEW

This view groups attributes that relate to assessment measures such as the measure, classification and the score achieved for a completed assessment.


| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| ASSESSMENTINSTANCEID| Identifier for a record.  |  Int 64| ---|NO|
| MEASURE| Measure that was assessed. | Character| 100|YES|
| SCORE| Score achieved by the client for the measure that was assessed. | Decimal fixed-point| ---|YES|
| CLASSIFICATION| Measure classification that the client is placed in, based on their score. For example, mild, moderate, severe. | Character| 100|YES|
| INGESTIONTIME| Date and Time the record was ingested, supports change data capture. | Date Time| ---|NO|

### Links to other data

| Attribute | Joins to  |Cardinality |
| :-------------- | :------ |:------ |
| ASSESSMENTINSTANCEID| ASSESSMENTS_V1_VIEW | An assessment is associated with one-to-many measure instances.|
| ASSESSMENTINSTANCEID| PROGRAM_ASSESSMENTS_V1_VIEW | An assessment instance is associated with a program.|
