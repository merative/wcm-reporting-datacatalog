

This section describes data available for client actions.

Client actions are actions that clients can complete to help them to achieve a goal.

These views groups attributes that relate to a client actions such as the client action name, category, status and reason for the client action.

## CLIENTACTIONS_V1_VIEW

The client actions view groups attributes relating to actions by their assigned client. Use this view to create client action reports.


| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| ACTIONID|Identifier for a record.|  Int 64| ---|NO|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|NO|
| NAME| The name of the client action. | Character| 1024|YES|
| CATEGORY| Category that best describes the nature of the action. For example, education, appointment. | Character| 100|YES|
| STATUS| Current status of the action, planned, current, overdue, or completed. | Character| 100|NO|
| ADDEDBY| First name and last name of the user who added the record. | Character| 256|NO|
| ADDEDON| Date on which the record was added. | Date|  ---|NO|
| REASON| Reason that the record was added. | Character| 2000|YES|
| STARTDATE| Date on which the action is due to start. | Date| ---|NO|
| EXPECTEDENDDATE| Date on which the action is expected to be completed. | Date| ---|YES|
| COMPLETEDON| Date on which the action was completed. | Date| ---|YES|
| COMPLETEDBY| First name and last name of the user who completed the action. | Character| 256|YES|
| OUTCOME| Outcome of the item, successful, not successful or abandoned. | Character| 100|YES|
| PROGRESS| Latest progress recorded in relation to the record, poor, good, very good, excellent. | Character| 256|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture.  | Date Time| ---|NO|

### Links to other data


| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Client reference joins to a client.<br /> A client is associated with zero-to-many client actions.|
| ADDEDBY | USERS_V1_VIEW | Added-by joins to a user. <br /> A user is associated with zero-to-many client actions.|
| COMPLETEDBY | USERS_V1_VIEW | Completed-by joins to a user. <br /> A user is associated with zero-to-many client actions. |
| ACTIONID | CLIENTACTION_BARRIERS_V1_VIEW| A client action is associated with zero-to-many barriers. |
| ACTIONID | CLIENTACTION_PROGRESSCOMMENTS_V1_VIEW| A client action is associated with zero-to-many progress comments. |
| ACTIONID |PROGRAM_CLIENTACTION_V1_VIEW| A client action is associated with zero-to-many programs. |
| ACTIONID | GOALS_CLIENTACTIONS_V1_VIEW| A client action is associated with zero-to-many goals. |


## CLIENTACTION_BARRIERS_V1_VIEW

This view groups attributes that will allow you to identify barriers associated with client actions. Use this view in reports to report on barriers associated with a client's actions.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| BARRIERID|Identifier for a record. |  Int 64| ---|NO|
| ACTIONID| Identifier for a record. |  Int 64| ---|NO|
| ACTIONNAME| The name of the client action. | Character| 1024|YES|
| BARRIERNAME| The name of the client barrier.  | Character| 1024|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture.  | Date Time| ---|NO|

### Links to other data

| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| BARRIERID| BARRIERS_V1_VIEW | Barrierid joins to an barrier.<br/> A client action is associated with zero-to-many barriers.|
| ACTIONID | CLIENTACTIONS_V1_VIEW | Actionid joins to an action.<br/> A client action is associated with zero-to-many barriers. |


## CLIENTACTION_PROGRESSCOMMENTS_V1_VIEW

This view groups attributes that relate to comments recorded when progress is updated for a client action, such as the progress comment, the name of the user who added the comment, and the date when the comment was added.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| PROGRESSID| Identifier for a record.  |  Int 64| ---|NO|
| ACTIONID| Identifier for a record.  |  Int 64| ---|NO|
| CREATIONDATE| Date and time that the record was created. | Date Time|---|NO|
| CREATEDBY| First name and last name of the user who created the comment.| Character| 256|NO|
| COMMENTS| Comments entered for the record. | Character| 8000|YES|
| PROGRESS| Progress recorded in relation to the item, poor, good, very good, excellent. | Character| 256|YES|

### Links to other data

| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| ACTIONID| CLIENTACTIONS_V1_VIEW | Actionid joins to an action.<br/> A client action is associated with zero-to-many progress comments.|
| CREATEDBY | USERS_V1_VIEW |  Created-by joins to a user. <br /> A user is associated with zero-to-many progress comments. |
