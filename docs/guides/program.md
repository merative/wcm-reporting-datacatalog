

This section describes data available for programs.

A program is a care delivery strategy that is designed to deliver a specific client outcome.

These views group attributes that relate to a client’s programs such as the program name, status and the date and time from which a program is in a status. They also contains views that groups data for plan activies and items that can be associated with a program such as assessments, goals, client actions, team actions, barriers, touchpoints and utilizations.  



## PROGRAMS_V1_VIEW
This view groups attributes that relate to a client’s programs such as the program name, program enrollment status, and the completion date.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| PROGRAMID| Identifier for a record. |  Int 64|--- |NO|
| NAME| The name of a program. | Character| 75|YES|
| PROGRAMENROLLMENTSTATUS| The current program enrollement status, assigned, pending, enrolled, not enrolled, disenrolled or completed. | Character| 50|NO|
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
| CLIENTREFERENCE|  CLIENTS_V1_VIEW |  Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|
| STATUSEUPDATEDBY|  USERS_V2_VIEW | Cardinality is one-to-one.  <br/>  A user identifier is associated with one user.                               |
| PROGRAMID| PROGRAM_ASSESSMENTS_V1_VIEW | Cardinality is one-to-many. <br/> A program enrollment is associated with zero-to-many assessment records.|
| PROGRAMID| PROGRAM_UTILIZATIONS_V1_VIEW | Cardinality is one-to-many. <br/> A program enrollment is associated with zero-to-many utilization records.|
| PROGRAMID| PROGRAM_TOUCHPOINTS_V1_VIEW | Cardinality is one-to-many. <br/> A program enrollment is associated with zero-to-many touchpoint records.|
| PROGRAMID| PROGRAM_BARRIERS_V1_VIEW | Cardinality is one-to-many. <br/> A program enrollment is associated with zero-to-many barrier records.|
| PROGRAMID| PROGRAM_CLIENTACTIONS_V1_VIEW | Cardinality is one-to-many. <br/> A program enrollment is associated with zero-to-many client action records.|
| PROGRAMID| PROGRAM_GOALS_V1_VIEW | Cardinality is one-to-many. <br/> A program enrollment is associated with zero-to-many goal records.|
| PROGRAMID| PROGRAM_TEAMACTIONS_V1_VIEW | Cardinality is one-to-many. <br/> A program enrollment is associated with zero-to-many team action records.|
| PROGRAMID| TASK_PROGRAMS_V1_VIEW | Cardinality is one-to-many. <br/> A program enrollment is associated with zero-to-many task records.|


## PROGRAM_ASSESSMENTS_V1_VIEW


This view groups assessments by their associated programs. Use this data set to identify specific assessments associated with a client's program.
<br/>Uniqueness is guaranteed by programID and assessmentinstanceID. Program identifier could be repeated in the view, and assessment instance identifier could be repeated in the view.

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
| ASSESSMENTINSTANCEID| ASSESSMENTS_V1_VIEW | Cardinality is one-to-one. <br/>  An assessment instance identifier is associated with one assessment instance record.|
| PROGRAMID| PROGRAMS_V1_VIEW | Cardinality is one-to-one.<br/>  A program identifier is associated with one program record. |




## PROGRAM_UTILIZATIONS_V1_VIEW

This view groups programs by their utilization type. Use this data set to identify specific utilizations associated with a client's program.
<br/>Uniqueness is guaranteed by programID and utilizationID. Program identifier could be repeated in the view, and utilization identifier could be repeated in the view.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| UTILIZATIONID| The identifier for a utilization record.  |  Int 64|--- |NO|
| PROGRAMID| The identifier for a program enrollment record.  |  Int 64| ---|NO|
| PROGRAMNAME| The name of this program. | Character| 75|YES|
| UTILIZATIONTYPE| Utilization type that is associated with the program. | Character| 200|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|--- |NO|

### Links to other data

| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| UTILIZATIONID| UTILIZATIONS_V1_VIEW | Cardinality is one-to-one. <br/> A utilization identifier is associated with one utilization record.|
| PROGRAMID| PROGRAMS_V1_VIEW | Cardinality is one-to-one.<br/>  A program identifier is associated with one program record. |



## PROGRAM_TOUCHPOINTS_V1_VIEW
This view groups touchpoints by their associated program. Use this view to identify specific touchpoints associated with a client's programs.
<br/>Uniqueness is guaranteed by programID and touchpointID. Program identifier could be repeated in the view, and touchpoint identifier could be repeated in the view.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| TOUCHPOINTID| The identifier for a touchpoint record. |  Int 64| ---|NO|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application.| Character| 200|YES|
| PROGRAMID| The identifier for a program enrollment record.  |  Int 64| ---|YES|
| PROGRAMNAME| The name of this program. | Character| 75|YES|
| TOUCHPOINTSUBJECT| Subject of the touchpoint. | Character| 500|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time| ---|NO|

### Links to other data



| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE|  CLIENTS_V1_VIEW | Cardinality is one-to-many. <br/> A client is associated with zero-to-many programs.|
| TOUCHPOINTID|TOUCHPOINTS_V1_VIEW | Cardinality is one-to-one. <br/> A touchpoint identifier is associated with one touchpoint record.|
| PROGRAMID| PROGRAMS_V1_VIEW | Cardinality is one-to-one.<br/>  A program identifier is associated with one program record. |



## PROGRAM_BARRIERS_V1_VIEW
This view groups barriers by their associated program. Use this view to identify specific barriers associated with a client's programs.
<br/>Uniqueness is guaranteed by programID and barrierID. Program identifier could be repeated in the view, and barrier identifier could be repeated in the view.

| Attribute | Description                                                          | Domain definition |Character size | Nulls allowed |
| :-------------- |:---------------------------------------------------------------------|:------ |:------ |:--------------|
| BARRIERID| The identifier for a barrier.                                        |  Int 64| ---| NO            |
| PROGRAMID| The identifier for a program enrollment record.                      |  Int 64|--- | NO            |
| PROGRAMNAME| The name of this program.                                              | Character| 75| YES           |
| BARRIERNAME| The name of the barrier.                                               | Character| 1024| YES           |
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time| ---| NO            |

### Links to other data



| Attribute | Joins to | Cardinality                                                                                        |
| :-------------- | :------ |:---------------------------------------------------------------------------------------------------|
| BARRIERID| BARRIERS_V1_VIEW | Cardinality is one-to-one.<br/>  A barrier identifier is associated with one barrier record. |
| PROGRAMID| PROGRAMS_V1_VIEW | Cardinality is one-to-one.<br/>  A program identifier is associated with one program record. |

## PROGRAM_CLIENTACTIONS_V1_VIEW
This view groups client actions by their associated program. Use this view to identify specific client actions associated with a client's programs.
<br/>Uniqueness is guaranteed by programID and actionID. Program identifier could be repeated in the view, and action identifier could be repeated in the view.

| Attribute | Description                                                          | Domain definition |Character size | Nulls allowed |
| :-------------- |:---------------------------------------------------------------------|:------ |:------ |:--------------|
| ACTIONID| The identifier for a action.                                         |  Int 64| ---| NO            |
| PROGRAMID| The identifier for a program enrollment record.                      |  Int 64|--- | NO            |
| PROGRAMNAME| The name of this program.                                            | Character| 75| YES           |
| ACTIONAME| The name of the action.                                              | Character| 1024| YES           |
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|--- | NO            |

### Links to other data



| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| ACTIONID| CLIENTACTIONS_V1_VIEW | Cardinality is one-to-one. <br/> A client action is associated with one action record.|
| PROGRAMID| PROGRAMS_V1_VIEW | Cardinality is one-to-one.<br/>  A program identifier is associated with one program record. |

## PROGRAM_GOALS_V1_VIEW
This view groups goals by their associated program. Use this view to identify specific goals associated with a client's programs.
<br/>Uniqueness is guaranteed by programID and goalID. Program identifier could be repeated in the view, and goal identifier could be repeated in the view.

| Attribute | Description                                                          | Domain definition |Character size | Nulls allowed |
| :-------------- |:---------------------------------------------------------------------|:------ |:------ |:--------------|
| GOALID| The identifier for a goal.                                           |  Int 64| ---| NO            |
| PROGRAMID| The identifier for a program enrollment record.                      |  Int 64|--- | NO            |
| PROGRAMNAME| The name of this program.                                         | Character| 75| YES           |
| GOALNAME| The name of the goal.                                                | Character| 1024| YES           |
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time| ---| NO            |

### Links to other data



| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| GOALID|  GOALS_V1_VIEW | Cardinality is one-to-one. <br/> A goal is associated with one program enrollment.|
| PROGRAMID| PROGRAMS_V1_VIEW | Cardinality is one-to-one.<br/>  A program identifier is associated with one program record. |

## PROGRAM_TEAMACTIONS_V1_VIEW
This view groups team actions by their associated program. Use this view to identify specific team actions associated with a client's programs.
<br/>Uniqueness is guaranteed by programID and actionID. Program identifier could be repeated in the view, and action identifier could be repeated in the view.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| ACTIONID| The identifier for an action record. |  Int 64| ---|NO|
| PROGRAMID| The identifier for a program enrollment record.  |  Int 64| --- |NO|
| PROGRAMNAME| The name of this program. | Character| 75|YES|
| ACTIONAME| The name of an action that is associated with the program. | Character| 1024|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture.  | Date Time| --- |YES|

### Links to other data



| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| ACTIONID| TEAMACTIONS_V1_VIEW | Cardinality is one-to-one. <br/> A team action is associated with one team action record.|
| PROGRAMID| PROGRAMS_V1_VIEW | Cardinality is one-to-one.<br/>  A program identifier is associated with one program record. |


© Merative US L.P. 2016, 2023.  Merative is a trademark of Merative US L.P. in the United States and other countries.
