

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
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br /> A client identifier is associated with one client.|
| ASSESSMENTINSTANCEID | ASSESSMENTS_V1_VIEW | Cardinality is one-to-many.<br /> A questionnaire is associated with one-to-many assessment instances. |
| STARTEDBY | USERS_V2_VIEW | Cardinality is one-to-one.<br /> A user identifier is associated with one user. |
| COMPLETEDBY | USERS_V2_VIEW| Cardinality is one-to-one.<br /> A user identifier is associated with one user. |
| ASSESSMENTINSTANCEID| PROGRAM_ASSESSMENTS_V1_VIEW |Cardinality is one-to-one.<br /> An assessment instance identifier is associated with a assessment instance.|

<br />
<br />

An assessment is a custom or industry-standard set of questions which produces a result that can be used to assess a client's needs. You can run an assessment by completing questions.

The following views group attributes that relate to client assessments such as questions, answer types for each question, answer provided by the client, measure, classification and score for completed assessments along with note and note comments views that allow you to identify notes and note comments associated with the assessment.  

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
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br /> A client identifier is associated with one client.|
| STARTEDBY | USERS_V2_VIEW | Cardinality is one-to-one.<br /> A user identifier is associated with one user. |
| COMPLETEDBY | USERS_V2_VIEW| Cardinality is one-to-one.<br /> A user identifier is associated with one user. |
| ASSESSMENTINSTANCEID| ASSESSMENT_MEASURES_V1_VIEW |Cardinality is one-to-many. <br />An assessment is associated with one-to-many measures.|
| ASSESSMENTINSTANCEID| PROGRAM_ASSESSMENTS_V1_VIEW |Cardinality is one-to-one. <br /> An assessment instance identifier is associated with a assessment instance.|
| ASSESSMENTINSTANCEID| ASSESSMENT_NOTES_V1_VIEW |Cardinality is one-to-many. <br /> An assessment instance identifier is associated with zero-to-many assessment note records.|

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
| ASSESSMENTINSTANCEID| ASSESSMENTS_V1_VIEW |Cardinality is one-to-one. <br /> An assessment instance identifier is associated with a assessment instance.|
| ASSESSMENTINSTANCEID| PROGRAM_ASSESSMENTS_V1_VIEW |Cardinality is one-to-one. <br /> An assessment instance identifier is associated with a assessment instance.|


## ASSESSMENT_NOTES_V1_VIEW
This view groups assessments by their associated notes. Use this view to identify specific assessments associated with a note.
<br/><br/>Uniqueness is guaranteed by assessmentID and noteID. Assessment identifier could be repeated in the view, and note identifier could be repeated in the view.
<br/>

| Attribute     | Description                                                                                                                                                            | Domain definition | Character size | Nulls allowed |
|:--------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|:------------------|:-----|:--------------|
| ASSESSMENTINSTANCEID     | Identifier for a barrier record.                                                                                                                                       | Int 64            | ---   | NO            |
| NOTEID     | Identifier for a note record.                                                                                                                                          | Int 64            | ---   | NO            |
| NOTETEXT                  | The text of the note.                                                                                                                                                  | Character| 32592| YES  |
| STATUS                | Current status of the note, Draft, Ready for Review, Final, Discarded, or Canceled. When a Draft or Ready for Review note is deleted, its status changes to Discarded. | Character| 20| YES  |
| INGESTIONTIME | Date and time the record was ingested, supports change data capture.                                                                                                   | Date Time         | ---  | NO            |


### Links to other data


| Attribute | Joins to            | Cardinality                                                                                                  |
|:----------|:--------------------|:-------------------------------------------------------------------------------------------------------------|
| NOTEID    | NOTES_V1_VIEW       | Cardinality is one-to-one.  <br/> A note identifier is associated with one note record.                      |
| NOTEID    | ASSESSMENT_NOTE_COMMENTS_V1_VIEW | Cardinality is one-to-many.  <br/> A note identifier is associated with zero-to many note comments. |
| ASSESSMENTINSTANCEID | ASSESSMENTS_V1_VIEW | Cardinality is one-to-one. <br/>  A assessment instance identifier is associated with one assessment record. |


## ASSESSMENT_NOTE_COMMENTS_V1_VIEW

This view groups attributes that relate to comments recorded for the assessments' note.

| Attribute     | Description | Domain definition |Character size | Nulls allowed |
|:--------------| :------ |:------ |:------ |:------ |
| NOTEID        | Identifier for a record. |  Int 64|---  |NO|
| POSITION      | The index or sequence number of the comment when multiple comments exist. | Int 32|---  |NO|
| COMMENT       | Comment entered for the record. | Character| 32592|NO|
| STATUS        | Current status of the note, Draft, Ready for Review, Final, Discarded, or Canceled. When a Draft or Ready for Review note is deleted, its status changes to Discarded. | Character| 20| YES  |
| INGESTIONTIME | Date and time the record was ingested, supports change data capture. | Date Time|---  |NO|

### Links to other data


| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| NOTEID           | NOTE_V1_VIEW         | Cardinality is zero-to-many. <br/> A note is associated with zero-to-many comments.   |


© Merative US L.P. 2016, 2023. 
Merative is a trademark of Merative US L.P. in the United States and other countries.
