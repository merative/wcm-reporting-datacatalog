

This section describes data available for notes.



## TOUCHPOINTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| TOUCHPOINTID|  Identifier for a record.  |  Int 64|--- |NO|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|NO|
| ADDEDBY| The identity of the user who created the record.  | Character| 256|NO|
| ADDEDBYFULLNAME| First name and last name of the user who created the item.  |  |
| ADDEDBYROLE| The role name of the user who created the item. | Character| 200|YES|
| ADDEDDATE| Date that the touchpoint was added. | Date Time| |YES|
| CONTACTWITH| Type of person who was contacted in the touchpoint. | Character| 50|YES|
| CONTACTMETHOD| Method of contact used for the touchpoint. | Character| 50|YES|
| CONTACTDIRECTION| Direction of the contact, Inbound or Outbound. | Character| 50|YES|
| CONTACTOUTCOME| Indicates whether the contact attempt was successful or unsuccessful. | Character| 50|YES|
| CONTACTDATETIME| Contact date for the touchpoint. | Date Time| |NO|
| CONTACTDURATION| Time in minutes of the touchpoint. | Decimal fixed-point| 2 decimal places|YES|
| VALIDATEDIDENTITYIND| Indicates whether the identity of the person who was contacted was validated. | Character| 1|NO|
| SUBJECTTEXT| Subject of the touchpoint. | Character| 480|YES|
| NOTETEXT| Note text. | Character| 32592|YES|
| SENSITIVE| Indicates whether the note contains sensitive client information. | Character| 1|YES|
| STATUS| Status of the record, Open or Closed. | Character| 50|YES|
| INGESTIONTIME| Date and Time the record was ingested, supports change data capture.  |  |

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| Joins to CLIENTS_V1_VIEW. | Cardinality is one-to-many.  A client has zero-to-many alerts|
| ADDEDBY | joins to USERS_V1_VIEW. | Cardinality is one-to-many. An alert joins to 1 user. |


## TOUCHPOINT_COMMENTS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| TOUCHPOINTID|  Identifier for a touchpoint record.  |  Int 64|--- |NO|
| CREATEDBY| The first name and last name of the user who created the comment. | Character| 100|YES|
| CONTENT| Touchpoint comment text. | Character| 32592|YES|
| CREATIONDATE| Date the comment was added. | Date Time| |YES|
| POSITION| The id of the comment, a sequence number starting at 1.  |  Int 32| |NO|

### Links to other data

Please review and amend, just examples below to help your edits.

| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| TOUCHPOINTID| TOUCHPOINTS_V1_VIEW. | Cardinality is zero-to-many.  A touchpoint has zero-to-many comments.|
