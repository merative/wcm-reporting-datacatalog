

This section describes data available for touchpoints.

A touchpoint is a record of a contact or attempted contact made with or received from a client another individual in relation to a client.

These views group attributes that relate to a touchpoint such as the subject, who the contact was with, the contact method, status, content text for the touchpoint and comments recorded for the touchpoint.


## TOUCHPOINTS_V1_VIEW

This view groups attributes that relate to a touchpoint such as the subject, status and content text for the touchpoint. Use this view to create touchpoint reports.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| TOUCHPOINTID|  Identifier for a record.  |  Int 64|--- |NO|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|NO|
| ADDEDBY| The identity of the user who created the record.  | Character| 256|NO|
| ADDEDBYFULLNAME| First name and last name of the user who created the item.  | Character| 524|YES|
| ADDEDBYROLE| The role name of the user who created this item. | Character| 200|YES|
| ADDEDDATE| Date that the touchpoint was added. | Date Time| ---|YES|
| CONTACTWITH| Type of person who was contacted in the touchpoint. | Character| 50|YES|
| CONTACTMETHOD| Method of contact used for the touchpoint. | Character| 50|YES|
| CONTACTDIRECTION| Direction of the contact, inbound or outbound. | Character| 50|YES|
| CONTACTOUTCOME| Indicates whether the contact attempt was successful or unsuccessful. | Character| 50|YES|
| CONTACTDATETIME| Contact date for the touchpoint. | Date Time| ---|NO|
| CONTACTDURATION| Time in minutes of the touchpoint. | Decimal fixed-point| 2 decimal places|YES|
| VALIDATEDIDENTITYIND| Indicates whether the identity of the person who was contacted was validated. | Character| 1|NO|
| SUBJECTTEXT| Subject of the touchpoint. | Character| 480|YES|
| NOTETEXT| Note text. | Character| 32592|YES|
| SENSITIVE| Indicates whether the note contains sensitive client information. | Character| 1|YES|
| STATUS| Status of the record, open or closed. | Character| 50|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. |  Date Time|--- |NO|

### Links to other data


| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|
| ADDEDBY | USERS_V2_VIEW | Cardinality is one-to-one. <br/> A user identifier is associated with one user. |
| TOUCHPONTID | PROGRAM_TOUCHPOINTS_V1_VIEW| Cardinality is one-to-many. <br/> A touchpoint is associated with zero-to-many programs. |
| TOUCHPONTID | TOUCHPOINT_COMMENTS_V1_VIEW| Cardinality is one-to-many. <br/> A touchpoint is associated with zero-to-many touchpoint comments. |

## TOUCHPOINT_COMMENTS_V1_VIEW

This view groups attributes that relate to a touchpoint comment such as the author, status and content text for the comment. Use this view to create touchpoint comments reports.


| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| TOUCHPOINTID|  Identifier for a touchpoint record.  |  Int 64|--- |NO|
| CREATEDBY| The first name and last name of the user who created the comment. | Character| 100|YES|
| CONTENT| Touchpoint comment text. | Character| 32592|YES|
| CREATIONDATE| Date and time the comment was added. | Date Time| ---|YES|
| POSITION| Order that the comments were added to the touchpoint, for example, I, 2, 3, 4.  |  Int 32| ---|NO|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. |  Date Time|--- |NO|

### Links to other data


| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| TOUCHPOINTID| TOUCHPOINTS_V1_VIEW | Cardinality is one-to-one. <br/> A touchpoint identifier is associated with one touchpoint.|
| CREATEDBY | USERS_V2_VIEW | Cardinality is one-to-one. <br/> A user identifier is associated with one user. |


© Merative US L.P. 2016, 2023.  Merative is a trademark of Merative US L.P. in the United States and other countries.
