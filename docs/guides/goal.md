
This section describes data available for goals. <br/> <br/>

Goals are plan items that represents a measurable target that a client can complete on their plan. Multiple barriers, client actions or team actions can be associated with a goal. <br/>


## GOALS_V1_VIEW

This views groups attributes that relate to goals such as the goal name, importance, outcome and reason for the goal. Use this view in reports to report on client's goals.



| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| GOALID| Identifier for a goal record. |  Int 64| ---|NO|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|YES|
| NAME| Name of the goal. | Character| 1024|YES|
| FOCUSAREA| Focus area of the goal for reporting purposes. For example, medications, safety, basic needs. | Character| 200|YES|
| TYPE| Type of the goal, long-term or short-term.| Character| 100|YES|
| STAGEOFCHANGE| Value that indicates the client's readiness or motivation in relation to the goal. | Character| 100|YES|
| IMPORTANCE| Importance of the goal to the client, on a scale of 1 (low) to 10 (high). | Character| 100|YES|
| CONFIDENCE| Client's confidence about the goal, on a scale of 1 (low) to 10 (high). | Character| 100|YES|
| ADDEDBY| First name and last name of the user who added the goal. | Character| 256|YES|
| ADDEDON| Date when the goal was added. | Date|---|NO|
| COMPLETEDBY| First name and last name of the user who completed the goal. | Character| 256|YES|
| COMPLETEDON| Date when the goal was completed. | Date|---|YES|
| SOURCE| Origin of the goal. For example, Care Manager or Program. | Character| 100|YES|
| STARTDATE| Date on which the goal is due to start. | Date|---|YES|
| TARGETDATE| Date on which the goal is expected to be completed.| Date|---|YES|
| REASON| Reason the goal was added to the care plan.| Character| 2000|YES|
| OUTCOME| Outcome of the goal. For example, successful, not successful, or abandoned. | Character| 100|YES|
| PROGRESS| Progress in relation to the goal. For example, poor, good, excellent.| Character| 256|YES|
| TARGETVALUE| Target value that represents the achievement of the goal. | Character| 100|YES|
| COMPLETIONCOMMENTS| Most recent comment added when the goal was completed. | Character| 8000|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|--- |YES|

### Links to other data

| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Client reference joins to a client.<br /> A client is associated with zero-to-many goals.|
| ADDEDBY | USERS_V1_VIEW | ADDED-by joins to a user.<br /> A user is associated with zero-to-many goals. |
| COMPLETEDBY | USERS_V1_VIEW | Completed-by joins to a user.<br /> A user is associated with zero-to-many goals. |
| GOALID| GOAL_BARRIERS_V1_VIEW| Cardinality is zero-to-many. <br/> A goal is associated with zero-to-many barriers.|
| GOALID| GOAL_CLIENTACTIONS_V1_VIEW | Cardinality is zero-to-many. <br/> A goal is associated with zero-to-many clientactions.|
| GOALID| GOAL_TEAMACTIONS_V1_VIEW| Cardinality is zero-to-many. <br/> A goal is associated with zero-to-many teamactions.|
| GOALID| GOAL_PROGRESSCOMMENTS_V1_VIEW | Cardinality is zero-to-many.<br/>  A goal is associagted with zero-to-many progresscomments.|



## GOAL_BARRIERS_V1_VIEW

This view groups attributes that will allow you to identify barriers associated with client goals. Use this view in reports to report on barriers associated with a client's goals.


| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| BARRIERID| Identifier for a barrier record.  |  Int 64| ---|NO|
| GOALID| Identifier for a goal record.  |  Int 64|--- |NO|
| GOALNAME| Name of the goal that is associated with the barrier. | Character| 1024|YES|
| BARRIERNAME| Name of the barrier that is associated with the goal. | Character| 1024|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|--- |YES|

### Links to other data

| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| GOALID| GOALS_V1_VIEW | Cardinality is zero-to-many. <br/> A barrier is associated with zero-to-many goals.|
| BARRIERID |BARRIERS_V1_VIEW | Cardinality is one-to-one. <br/> A goal barrier is associated with one barrier. |
