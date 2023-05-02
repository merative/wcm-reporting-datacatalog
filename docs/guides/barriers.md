

This section describes data available for barriers.

A barrier is an issue that your client has that can stop them from achieving their care plan goals and actions.

## BARRIERS_V1_VIEW
These views group attributes that relate to a barrier such as the name, category and status of the
barrier along with note and note comments views that allow you to identify notes and note comments associated with the barrier. Use these views to create barriers reports.

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
| INGESTIONTIME  | Date and time the record was ingested, supports change data capture.                        | Date Time| ---| NO            |
### Links to other data


| Attribute | Joins to                | Cardinality                                                                                 |
| :-------------- |:------------------------|:--------------------------------------------------------------------------------------------|
| CLIENTREFERENCE| CLIENTS_V1_VIEW         | Cardinality is one-to-one.<br/> A client identifier is associated with one client. |
| ADDEDBY | USERS_V2_VIEW           | Cardinality is one-to-one.<br/> A user identifier is associated with one user.          |
| RESOLVEDBY | USERS_V2_VIEW           | Cardinality is one-to-one.<br/> A user identifier is associated with one user.         |     
| BARRIERID | GOAL_BARRIERS_V1_VIEW       | Cardinality is one-to-many. <br/>A barrier is associated with zero-to-many goals.           |
| BARRIERID | SERVICE_BARRIERS_V1_VIEW       | Cardinality is one-to-many. <br/>A barrier is associated with zero-to-many services.     |
| BARRIERID | PROGRAM_BARRIERS_V1_VIEW       | Cardinality is one-to-many. <br/>A barrier is associated with zero-to-many programs.     |
| BARRIERID | CLIENTACTION_BARRIERS_V1_VIEW      | Cardinality is one-to-many. <br/>A barrier is associated with zero-to-many client actions.     |
| BARRIERID | TEAMACTION_BARRIERS_V1_VIEW      | Cardinality is one-to-many. <br/>A barrier is associated with zero-to-many team actions.     |
| BARRIERID | BARRIER_NOTES_V1_VIEW      | Cardinality is one-to-many. <br/>A barrier is associated with zero-to-many note records.     |

## BARRIER_NOTES_V1_VIEW
This view groups barriers by their associated notes. Use this view to identify specific barriers associated with a note.
<br/>Uniqueness is guaranteed by barrierbID and noteID. Barrier identifier could be repeated in the view, and note identifier could be repeated in the view.

<br/>

| Attribute     | Description                                                                                                                                                            | Domain definition | Character size | Nulls allowed |
|:--------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|:------------------|:-----|:--------------|
| BARRIERID     | Identifier for a barrier record.                                                                                                                                       | Int 64            | ---   | NO            |
| NOTEID     | Identifier for a note record.                                                                                                                                          | Int 64            | ---   | NO            |
| NOTETEXT                  | The text of the note.                                                                                                                                                  | Character| 32592| YES  |
| STATUS                | Current status of the note, Draft, Ready for Review, Final, Discarded, or Canceled. When a Draft or Ready for Review note is deleted, its status changes to Discarded. | Character| 20| YES  |
| INGESTIONTIME | Date and time the record was ingested, supports change data capture.                                                                                                   | Date Time         | ---  | NO            |

### Links to other data


| Attribute | Joins to        | Cardinality                                                                                   |
|:----------|:----------------|:----------------------------------------------------------------------------------------------|
| NOTEID    | NOTES_V1_VIEW   | Cardinality is one-to-one.  <br/> A note identifier is associated with one note record.       |
| NOTEID    | BARRIER_NOTE_COMMENTS_V1_VIEW   |Cardinality is one-to-many.<br/>A note is associated with zero-to many note comments.|
| BARRIERID | BARRIER_V1_VIEW | Cardinality is one-to-one. <br/>  A barrier identifier is associated with one barrier record. |



## BARRIER_NOTE_COMMENTS_V1_VIEW

This view groups attributes that relate to comments recorded for the barriers' note.

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
| NOTEID           | NOTE_V1_VIEW         | Cardinality is one-to-one. <br/> A note identifier is associated with one note record.    |


© Merative US L.P. 2016, 2023. 
Merative is a trademark of Merative US L.P. in the United States and other countries.
