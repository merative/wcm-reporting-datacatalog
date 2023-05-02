

This section describes data available for services.

A service is a plan activity that represents the delivery of care or goods to an individual. A service is typically delivered by a provider at a cost per unit. For example, a home care agency can deliver 2 hours of care at an hourly rate, or an equipment provider can deliver a hearing aid at a specified price.

These views group attributes that relate to services details such as the service name, description, status, start date and the team member who created the service along with goal, barrier,note and note comments views that allow you to identify goals, barriers, notes and note comments associated with the service.

## SERVICES_V1_VIEW

This view groups attributes that relate to the service such as the service name, service start date, frequency and the number of units to be delivered.


| Attribute           | Description                                                                                                              | Domain definition | Character size | Nulls allowed |
|:--------------------|:-------------------------------------------------------------------------------------------------------------------------|:------------------|:-----|:--------------|
| SERVICEID   | Identifier for a service record.                                                                                         | Int 64            | ---   | NO            |
| CLIENTREFERENCE     | Unique reference number that identifies the client in the application.                                                   | Character         | 200  | YES           |
| PROVIDEROFFERINGID  | Identifier for a provider offering record.                                                                               | Int 64            | ---   | YES           |
| SERVICEOFFERINGID   | Identifier for a service offering record.                                                                                | Int 64            | ---   | NO            |
| PROVIDERID          | Identifier for a provider record.                                                                                         | Int 64            | ---   | YES           |
| NAME                | Name of the service provided to the client.                                                                               | Character         | 200  | YES           |
| DESCRIPTION         | Description of the service.                                                                                               | Character         | 1000 | YES           |
| STATUS              | Current status for the service; open, canceled or deleted.                                                                                                | Character         | 200  | YES           |
| CATEGORIES          | Category that best describes the nature of the service.                                                                  | Character         | 1000 | YES           |
| UNITVALUE           | Value that represents the number of units of the service to be delivered, in string format.                              | Character         | 32   | YES           |
| UNITVALUEASANUMBER  | Number of units of the service to be delivered, as a numeric value. You can use this value for comparisons or arithmetic | Decimal           | 20   | YES           |
| UNITTYPE            | Units in which the service is delivered to the client, for example, hours, meals, sessions.                               | Character         | 100  | YES           |
| STARTDATE           | Start date of the service.                                                                                                | Date              | ---   | YES           |
| CREATIONDATE        | Creation date of the service record.                                                                                     | Date              | ---   | NO            |
| EXPECTEDENDDATE     | Expected end date for the service.                                                                                        | Date              | ---   | YES           |
| COMPLETIONDATE      | Date the service was completed.                                                                                            | Date              | ---   | YES           |
| FREQUENCY           | Frequency of the service, for example, weekly, every 2 weeks.                                                            | Character         | 200  | YES           |
| UNITCOST            | Cost per unit for the service based on the provider rate. Populated only if a provider is associated with the service.   | Decimal           | ---   | YES           |
| OUTCOME             | Outcome of the service; Successful, Not Successful, Abandoned.   | Character         | 200  | YES           |
| CREATEDBY           | The identity of user who created the service.                                 | Character         | 256  | YES           |
| COMPLETEDBY         | The identity of user who completed the service.                               | Character         | 256  | YES           |
| PAYMENTAUTHSTATUS   | Current authorization status of the payment, Payment Complete, Cancelled, Not Authorised, or Final Payment Authorized.   | Character         | 200  | YES           |
| AUTHSTATUSUPDATEDON | Date that the payment authorization status was updated.                             | Date              | ---  | YES           |
| AUTHSTATUSUPDATEDBY | The identity of the user who updated the authorization status.                 | Character         | 256  | YES           |
| INGESTIONTIME       | Date and time the record was ingested, supports change data capture.           | Timestamp         | ---  | YES           |

### Links to other data


| Attribute         | Joins to                      | Cardinality                                                                                   |
|:------------------|:------------------------------------|:----------------------------------------------------------------------------------------------|
| CLIENTREFERENCE| CLIENTS_V1_VIEW         | Cardinality is one-to-one. <br/>A client identifier is associated with one client. |
| CREATEDBY  | USERS_V2_VIEW           | Cardinality is one-to-one. <br/> A user identifier is associated with one user.          |
| COMPLETEDBY  | USERS_V2_VIEW           | Cardinality is one-to-one. <br/> A user identifier is associated with one user.         |  
| SERVICEID | SERVICE_GOALS_V1_VIEW    | Cardinality is one-to-many. <br/> A service is associated with zero-to-many goals. |
| SERVICEID | SERVICE_BARRIERS_V1_VIEW | Cardinality is one-to-many. <br/> A service is associated with zero-to-many barriers.  |  
| SERVICEID | SERVICE_NOTE_V1_VIEW | Cardinality is one-to-many. <br/> A service is associated with zero-to-many notes.  |  
| SERVICEID | SERVICE_NOTE_COMMENTS_V1_VIEW | Cardinality is one-to-many. <br/> A service is associated with zero-to-many note comments.  |  
| PROVIDEROFFERINGID| SHORTLISTED_PROVIDERS_V1_VIEW| Cardinality is one-to-one. <br/> A provider offering identifier is associated with one provider offering identifier.  |  



## SERVICE_GOALS_V1_VIEW
This view groups services by their associated goal. Use this view to identify specific services associated with a client's goals.
<br/><br/>Uniqueness is guaranteed by serviceID and goalID. Service identifier could be repeated in the view, and goal identifier could be repeated in the view.

| Attribute     | Description                                                          | Domain definition | Character size | Nulls allowed |
|:--------------|:---------------------------------------------------------------------|:------------------|:-----|:--------------|
| GOALID        | Identifier for a goal record.                                        | Int 64            | ---   | NO            |
| SERVICEID     | Identifier for a service record.                                     | Int 64            | ---   | NO            |
| GOALNAME      | The name of the goal.                                                | Character         | 500  | YES           |
| SERVICENAME   | The name of the service.                                             | Character         | 200  | YES           |
| INGESTIONTIME | Date and time the record was ingested, supports change data capture. | Date Time         | ----  | NO            |

### Links to other data


| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| GOALID|GOALS_V1_VIEW | Cardinality is one-to-one.  <br/> A goal is associated with one goal.|
| SERVICEID | SERVICE_V1_VIEW| Cardinality is one-to-one. <br/>  A service identifier is associated with one service. |




## SERVICE_BARRIERS_V1_VIEW
This view groups services by their associated barrier. Use this view to identify specific services associated with a barrier.
<br/><br/>Uniqueness is guaranteed by serviceID and barrier ID. Service identifier could be repeated in the view, and barrier identifier could be repeated in the view.

| Attribute     | Description                                                          | Domain definition | Character size | Nulls allowed |
|:--------------|:---------------------------------------------------------------------|:------------------|:-----|:--------------|
| BARRIERID     | Identifier for a barrier record.                                     | Int 64            | ---   | NO            |
| SERVICEID     | Identifier for a service record.                                     | Int 64            | ---   | NO            |
| BARRIERNAME   | The name of the barrier.                                             | Character         | 500  | YES           |
| SERVICENAME   | The name of the service.                                             | Character         | 200  | YES           |
| INGESTIONTIME | Date and time the record was ingested, supports change data capture. | Date Time         | ---  | NO            |

### Links to other data


| Attribute | Joins to               | Cardinality                                                                    |
|:----------|:---------------------------|:-------------------------------------------------------------------------------|
| BARRIERID | BARRIERS_V1_VIEW | Cardinality is one-to-one.  <br/> A barrier is associated with one barrier.         |
| SERVICEID | SERVICE_V1_VIEW  | Cardinality is one-to-one. <br/>  A service is associated with one service. |

## SERVICE_NOTES_V1_VIEW
This view groups services by their associated notes. Use this view to identify specific services associated with a note.
<br/><br/>Uniqueness is guaranteed by serviceID and noteID. Service identifier could be repeated in the view, and note identifier could be repeated in the view.



| Attribute     | Description                                                          | Domain definition | Character size | Nulls allowed |
|:--------------|:---------------------------------------------------------------------|:------------------|:-----|:--------------|
| SERVICEID     | Identifier for a service record.                                     | Int 64            | ---   | NO            |
| NOTEID     | Identifier for a note record.                                        | Int 64            | ---   | NO            |
| NOTETEXT                  | The text of the note.   | Character| 32592| YES  |
| STATUS                | Current status of the note, Draft, Ready for Review, Final, Discarded, or Canceled. When a Draft or Ready for Review note is deleted, its status changes to Discarded. | Character| 20| YES  |
| INGESTIONTIME | Date and time the record was ingested, supports change data capture. | Date Time         | ---  | NO            |

### Links to other data


| Attribute | Joins to        | Cardinality                                                                                   |
|:----------|:----------------|:----------------------------------------------------------------------------------------------|
| NOTEID    | NOTES_V1_VIEW   | Cardinality is one-to-one.  <br/> A note identifier is associated with one note record.              |
| NOTEID    | SERVICE_NOTE_COMMENTS_V1_VIEW | Cardinality is one-to-many.<br/> A note identifier is associated with with zero-to-many note comments. |
| SERVICEID | SERVICE_V1_VIEW | Cardinality is one-to-one. <br/> A service identifier is associated with one service. |


## SERVICE_NOTE_COMMENTS_V1_VIEW

This view groups attributes that relate to comments recorded for the services' note.

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
| NOTEID           | NOTE_V1_VIEW         | Cardinality is one-to-one. <br/> A note identifier is associated with one note.   |



© Merative US L.P. 2016, 2023.  Merative is a trademark of Merative US L.P. in the United States and other countries.
