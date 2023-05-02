This section describes data available for care team actions. <br/> <br/>
Team actions are plan activities that team members can complete to help a client to achieve a goal. <br/>  <br/>
These views groups attributes that relate to actions such as the action name, category, status, progress commments
recorded against the care team action and reason for the action.

## TEAMACTIONS_V1_VIEW
The team actions view groups attributes relating to team actions, such as the name, category, status and completion
details for the action. Use this view to create team action reports.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:--------------|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200| NO           |
| ACTIONID| Identifier for a record.    |  Int 64| ---| NO            |
| ASSIGNEDTO| Email address of the user who was assigned the action. | Character| 256| YES           |
| ASSIGNEDTOFULLNAME| First name and last name of the user who was assigned the action. | Character| 524| YES           |
| ASSIGNEDTOTEAMROLE| Role of the user who was assigned the action. | Character| 200| YES           |
| NAME| Name of the action. | Character| 1024| YES           |
| CATEGORY| Category that best describes the nature of the action. For example, education, appointment.| Character| 100| YES           |
| STATUS| Current status of the action; planned, current, overdue, or completed. | Character| 100| YES           |
| ADDEDBY| Login ID of the user who added the record. | Character| 200| NO            |
| ADDEDON| Date on which the record was added. | Date|--- | NO            |
| REASON| Reason that the record was added. | Character| 2000| YES           |
| STARTDATE| Date on which the action is due to start. | Date|--- | NO            |
| EXPECTEDENDDATE| Date on which the action is expected to be completed. | Date|--- | YES           |
| COMPLETEDON| Date on which the action was completed. | Date|--- | YES           |
| COMPLETEDBY| Login ID  of the user who completed the action. | Character| 200| YES           |
| OUTCOME| Outcome of the item; successful, not successful or abandoned. | Character| 100| YES           |
| PROGRESS| Latest progress recorded in relation to the record, for example, poor, good, very good, excellent. | Character| 256| YES           |
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time| ---| NO             |
### Links to other data


| Attribute | Joins to                | Cardinality                                                                                 |
| :-------------- |:------------------------|:--------------------------------------------------------------------------------------------|
| CLIENTREFERENCE| CLIENTS_V1_VIEW         | Cardinality is one-to-one. <br/>  A client identifier is associated with one client. |
| ADDEDBY | USERS_V2_VIEW | Cardinality is one-to-one.<br /> A user identifier is associated with one user.|
| COMPLETEDBY | USERS_V2_VIEW | Cardinality is one-to-one.<br /> A user identifier is associated with one user. |
| ASSIGNEDTO | USERS_V2_VIEW | Cardinality is one-to-one.<br /> A user identifier is associated with one user. |
| ACTIONID | PROGRAM_TEAMACTIONS_V1_VIEW| Cardinality is one-to-many. <br/> A team action is associated with zero-to-many programs. |
| ACTIONID | GOAL_TEAMACTIONS_V1_VIEW| Cardinality is one-to-many. <br/> A team action is associated with zero-to-many goals. |
| ACTIONID | TEAMACTION_BARRIERS_V1_VIEW| Cardinality is one-to-many. <br/> A team action is associated with zero-to-many barriers. |
| ACTIONID | TEAMACTION_PROGRESSCOMMENTS_V1_VIEW| Cardinality is one-to-many. <br/> A team action is associated with zero-to-many progress comments |


## TEAMACTION_BARRIERS_V1_VIEW
This view groups attributes that will allow you to identify barriers associated with team actions. Use this view in
reports to report on barriers associated with a team's actions.
<br/>Uniqueness is guaranteed by barrierID and actionID. Barrier identifier could be repeated in the view, and team action identifier could be repeated in the view.


| Attribute | Description                        | Domain definition |Character size | Nulls allowed |
| :-------------- |:-----------------------------------|:------ |:------ |:--------------|
| BARRIERID| Identifier for a barrier.          |  Int 64|--- | NO            |
| ACTIONID| Identifier for a team action. |  Int 64| ---| NO            |
| ACTIONNAME| The name of the team action.  | Character| 1024| YES           |
| BARRIERNAME| The name of the barrier.           | Character| 1024| YES           |
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time| ---| NO            |

### Links to other data

| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| BARRIERID| BARRIERS_V1_VIEW | Cardinality is one-to-one.<br/> A barrier identifier is associated with one barrier.|
| ACTIONID | TEAMACTIONS_V1_VIEW | Cardinality is one-to-one.<br/> A team action identifier is associated with one team action. |


## TEAMACTION_PROGRESSCOMMENTS_V1_VIEW
This view groups attributes that relate to comments recorded when progress is updated for a team action, such as the
progress comment, the name of the user who added the comment, and the date when the comment was added.
<br/>Uniqueness is guaranteed by actionID and progressID. Team action identifier could be repeated in the view, and progress identifier could be repeated in the view.


| Attribute | Description                          | Domain definition |Character size | Nulls allowed |
| :-------------- |:-------------------------------------|:------ |:------ |:------ |
| PROGRESSID| Identifier for the progress record.         |  Int 64|--- |NO|
| ACTIONID| Identifier for the team action. |  Int 64| ---|NO|
| CREATIONDATE| Date and time that the record was created. | Date Time|---|NO|
| CREATEDBY| First name and last name of the user who created the comment.| Character| 256|NO|
| COMMENTS| Comments entered for the record. | Character| 8000|YES|
| PROGRESS| Progress recorded in relation to the item, for example, poor, good, very good, excellent. | Character| 256|YES|

### Links to other data

| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| ACTIONID| TEAMACTIONS_V1_VIEW | Cardinality is one-to-one.<br/> A team action identifier is associated with one team action. |
| CREATEDBY | USERS_V2_VIEW |  Cardinality is one-to-one.<br /> A user identifier is associated with one user.  |


© Merative US L.P. 2016, 2023.  Merative is a trademark of Merative US L.P. in the United States and other countries.
