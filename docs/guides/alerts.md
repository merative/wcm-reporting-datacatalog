

This section describes data available for alerts.

Alerts are used to highlight some aspect of the client's care that needs action or attention from the team.

These views group attributes that relate to a client's alert details such as the alert name, priority, names of teams members who are notified about the alert, and the team member who created the alert.

## ALERTS_V1_VIEW

This view groups attributes that relate to the alert such as the alert name, priority and the client's reference.

| Attribute | Description | Domain definition | Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| ALERTID|  Identifier for a record.  |  Int 64|--- |NO|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|NO|
| ALERTNAME| The name of the alert. | Character| 512|NO|
| PRIORITY| Priority of the alert, critical, high, medium, or low. | Character| 40|NO|
| NOTETEXT| Note that was entered for the record. | Character| 32592|YES|
| SOURCE| Source system where the record originated (if configured). | Character| 512|YES|
| ORIGNALSOURCE| Original source system where the record was recorded for the very first time (if configured). | Character| 512|YES|
| CREATEDBY| The identity of the user who created the record.  | Character| 256|NO|
| CREATIONDATETIME| Date and time that the record was created. | Date Time|---  |NO|
| CLOSEDBY|The identity of the user who closed the alert.  | Character| 256|YES|
| CLOSUREDATETIME| Date and time that the record was closed. | Date Time|---  |YES|
| STATUS| Status of the record, Open or Closed.| Character| 40|NO|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|---  |NO|

### Links to other data


| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br /> A client identifier is associated with one client.|
| CREATEDBY | USERS_V2_VIEW | Cardinality is one-to-one.<br /> A user identifier is associated with one user. |
| CLOSEDBY | USERS_V2_VIEW| Cardinality is one-to-one.<br /> A user identifier is associated with one user. |
| ALERTID | ALERT_NOTIFICATIONS_V1_VIEW| Cardinality is one-to-many. <br/> An alert is associated with zero-to-many notifications. |
| ALERTID | ALERT_COMMENTS_V1_VIEW| Cardinality is one-to-many. <br/> An alert is associated with zero-to-many comments. |





## ALERT_NOTIFICATIONS_V1_VIEW

This view groups attributes that relate to who is notified of an alert, such as the alert name and the names of the team members who are notified of the alert.

| Attribute | Description | Domain definition |Character size  | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| ALERTID|  Identifier for a record. |  Int 64|---  |NO|
| ALERTNAME|The name of the alert. | Character| 512|NO|
| TEAMMEMBERNAME|Names of the team members who are notified of the alert. | Character| 524|NO|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|---  |NO|

### Links to other data


| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| ALERTID | ALERTS_V1_VIEW| Cardinality is one-to-one. <br/>An alert identifier is associated with one alert. |






## ALERT_COMMENTS_V1_VIEW

This view groups attributes that relate to comments recorded for an alert, such as the comment, who created it and when it was created.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| ALERTID| Identifier for a record. |  Int 64|---  |NO|
| COMMENT| Comment entered for the record. | Character| 32592|NO|
| CREATEDBY| The first name and last name of the user who created the comment. | Character| 100|NO|
| POSITION| The index or sequence number of the comment when multiple comments exist. | Int 32|---  |NO|
| CREATIONDATE| Date and time that the record was created. | Date Time|---  |NO|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|---  |NO|

### Links to other data


| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| ALERTID | ALERTS_V1_VIEW| Cardinality is one-to-one. <br/> An alert identifier is associated with one alert. |


© Merative US L.P. 2016, 2023. 
Merative is a trademark of Merative US L.P. in the United States and other countries.
