

This section describes data available for programs.

A program is a care delivery strategy that is designed to deliver a specific client outcome.

These views group attributes that relate to a client’s programs such as the program name, status,  assessments that are assigned to the program and the date and time from which a program is in a status.



## PROGRAMS_V1_VIEW
This view groups attributes that relate to a client’s programs such as the program name, program enrollment status, and the completion date.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| PROGRAMID| Identifier for a record. |  Int 64|--- |NO|
| NAME| The name of a program. | Character| 75|YES|
| DESCRIPTION| The current program enrollement status, assigned, pending, enrolled, not enrolled, disenrolled or completed. | Character| 50|NO|
| STARTDATE| Date on which a program is in the program enrollment status. | Date|--- |NO|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character | 200|NO|
| GRADUATIONDATE| The date a client graduated from the program.| Date|---|YES|
| PROGRAMSTATUS| The current status of the program, not started, in progress or complete. | Character| 11|YES|
| ASSIGNEDDATETIME| Date and Time from which a program is in the assigned status. | Date Time| ---|YES|
| PENDINGDATETIME| Date and Time from which a program is in the pending status. | Date Time | ---|YES|
| ENROLLEDDATETIME| Date and Time from which a program is in the enrolled status. | Date Time| ---|YES|
| COMPLETEDDATETIME| Date and Time from which a program is in the completed status.  | Date Time|--- |YES|
| DISENROLLEDDATETIME| Date and Time from which a program is in the disenrolled status. | Date Time |--- |YES|
| NOTENROLLEDDATETIME| Date and Time from which a program is in the not enrolled status. | Date Time|--- |YES|
| REASON| The most recent reason for a client's program status change. | Character| 50|YES|
| STATUSEUPDATEDBY| The identifier for a user record who updated the program enrollment status. The identifier value is an email address. | Character| 256|YES|
| STATUSEUPDATEDBYFULLNAME| First name and last name of the user who updated the program enrollment status. | Character| 524|YES|
| STATUSEUPDATEDBYROLE| Role of the user who updated the program enrollment status. | Character| 200|YES|
| OTHERREASON|  The most recent other reason entered by a team member for a client's program status change.  | Character| 1200|YES|
| COMMENT| Comment entered for the record. | Character| 900|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|--- |NO|

### Links to other data

| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE|  CLIENTS_V1_VIEW | Cardinality is one-to-many. <br/> A client is associated with zero-to-many programs.|
| STATUSEUPDATEDBY|  USERS_V1_VIEW | Cardinality is one-to-one.  <br/>  A status is associated with 1 user.|

## PROGRAM_ASSESSMENTS_V1_VIEW


This view groups assessments by their associated programs. Use this data set to identify specific assessments associated with a client's program.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| ASSESSMENTINSTANCEID| Identifier for a record.  |  Int 64|--- |NO|
| ASSESSMENTNAME| Name of a program that relates to the assessment.  | Character| 500|NO|
| PROGRAMID| Identifier for a program record. |  Int 64| ---|NO|
| PROGRAMNAME| The name of a program. | Character| 75|NO|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|--- |NO|

### Links to other data


| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| PROGRAMID|PROGRAMS_V1_VIEW | Cardinality is one-to-one. <br/>  An assessment instance is associated with one program enrolment.|
| ASSESSMENTS_V1_VIEW| ASSESSMENTS_V1_VIEW | Cardinality is one-to-one. <br/>  An assessment instance is associated with one program enrolment.|
