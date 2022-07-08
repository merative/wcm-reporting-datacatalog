

This section describes data available for barriers.

A barrier is an issue that your client has that can stop them from achieving their care plan goals and actions.

## BARRIERS_V1_VIEW
This view groups attributes that relate to a barrier such as the name, category, status and notes recorded for the 
barrier. Use this view to create barriers reports.

| Attribute      | Description                                                                                 | Domain definition | Character size | Nulls allowed |
|:---------------|:--------------------------------------------------------------------------------------------|:------ |:---------------|:--------------|
| BARRIERID      | Identifier for a record.                                                                    |  Int 64|--- | NO            |
| CLIENTREFERENCE| Unique reference number that identifies the client in the application.                      | Character| 200| NO            |
| NAME           | The name of the barrier.                                                                    | Character| 1024| YES           |
| CATEGORY       | Category that best describes the nature of the barrier. For example, Education or Mobility. | Character| 100| YES           |
| STATUS         | Current status of the barrier, Open, Resolved, or Canceled.                                 | Character| 100| YES           |
| ADDEDBY        | The identity of user who created the barrier.                                               | Character| 200| NO            |
| ADDEDON        | The date on which the barrier was created.                                                  | Date Time|--- | NO            |
| RESOLVEDBY     | The identity of user who resloved the barrier.                                              | Character| 200| YES           |
| RESOLVEDON     | The date on which the barrier was resolved.                                                 | Date| ---| YES           |
| NOTEID         | Identifier for note record.                                                                 |  Int 64| ---| YES           |
| NOTETEXT       | Note text for the barrier.                                                                  | Character| 1024| YES           |
| INGESTIONTIME  | Date and time the record was ingested, supports change data capture.                        | Date Time| ---| NO            |
### Links to other data


| Attribute | Joins to                | Cardinality                                                                                 |
| :-------------- |:------------------------|:--------------------------------------------------------------------------------------------|
| CLIENTREFERENCE| CLIENTS_V1_VIEW         | Client reference joins to a client.<br/> A client is associated with zero-to-many barriers. |
| ADDEDBY | USERS_V1_VIEW           | Created-by joins to a user.<br/> A user is associated with zero-to-many barriers.           |
| RESOLVEDBY | USERS_V1_VIEW           | Updated-by joins to one user.<br/> A user is associated with zero-to-many barriers.         |     
| BARRIERID | GOAL_BARRIERS_V1_VIEW       | A barrier is associated with zero-to-one goals.                                             |
