

This section describes data available for inquiries.

Care team members can create inquiries for services and send them to one or more providers. In the Merative Integrated Care Connect Providers application, providers can view and respond to inquiries and make offers to provide services.

These views group attributes relating to inquiries that are sent by the care team to providers to solicit services for their clients. Use these views to create inquiries reports.

## INQUIRIES_V1_VIEW
This view groups attributes that relate to an inquiry such as the inquiry ID, the service name, expected start date, frequency of the service, and the number of units to be delivered.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:--------------|
| INQUIRYID| Identifier for an inquiry record. |  Int 64| ---            | NO            |
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200            | NO            |
| SERVICEOFFERINGID| Identifier for a service offering record. | Int 64| ---          | NO            |
| SERVICENAME| Name of the service for which the inquiry was made. | Character| 500            | YES           |
| REFERENCENUMBER| Reference number assigned to the inquiry by Merative Integrated Care after the inquiry was sent. | Int 64| ---         | NO            |
| RECORDEDON| Date on which the inquiry was sent to the provider of the service. | Date Time| ---             | NO            |
| RECORDEDBY| The identity of the user who recorded the record. | Character| 256           | NO            |
| RESPONSEREQUIREDBY| Date by which a response to the inquiry is required. | Date| ---            | YES           |
| UNITTYPE| Unit of measure that is needed. For example, hours, meals, or sessions. | Character| 200             | YES           |
| UNITVALUE| Number of units that are needed. | Character| 50            | YES           |
| EXPECTEDSTARTDATE| Expected start date for the service. The start date is on or after the response required by date. | Date| ---             | YES           |
| EXPECTEDENDDATE| Expected end date for the service. | Date| ---           | YES           |
| FREQUENCY| Required frequency for the service. | Character| 200           | YES           |
| STATUS| Current status of the inquiry, open or closed. | Character| 200           | YES           |
| DAYS| Day(s) of the week that the service is required. | Character| 500           | YES           |
| REASON| Reason the inquiry was closed. | Character| 200            | YES           |
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time| ---             | NO            |

### Links to other data


| Attribute | Joins to | Cardinality                                                                                  |
| :-------------- | :------ |:---------------------------------------------------------------------------------------------|
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one <br/> A client identifier is associated with one client.  |
| RECORDEDBY | USERS_V2_VIEW| Cardinality is one-to-one.  <br/>  A user identifier is associated with one user.           |
| SERVICEOFFERINGID | PROVIDERS_V1_VIEW| Cardinality is one-to-one. <br/> A provider identifier is associated with one provider.       |   
| INQUIRYID | INQUIRY_COMMENTS_V1_VIEW| Cardinality is one-to-many. <br/>  An inquiry is associated with zero-to-many inquiry comments.     |                            
| INQUIRYID | INQUIRY_RESPONSES_V1_VIEW| Cardinality is one-to-many. <br/> An inquiry is associated with zero-to-many inquiry responses.      |                           
                       



## INQUIRY_COMMENTS_V1_VIEW
This view groups attributes that relate to an inquiry comment such as the author, status, and content text for the
comment.

| Attribute | Description                                                                                                                                                          | Domain definition |Character size | Nulls allowed |
| :-------------- |:---------------------------------------------------------------------------------------------------------------------------------------------------------------------|:------ |:------ |:--------------|
| INQUIRYID| Identifier for an inquiry record.                                                                                                                                             |  Int 64| ---| NO            |
| RECORDEDON| Comments added to the inquiry when it was created.                                                                                                                   |  Date Time| ---| NO            |
| RECORDEDBY| The identity of the user who recorded the record.                                                                                                                    |  Character| 256| NO            |
| COMMENT| Comments added to the inquiry by a care team member. All providers who received the inquiry can see the comment, except for providers who have declined the inquiry. |  Character| 8000| YES           |
| INQUIRYEVENTID| Identifier for a record.                                                                                                                                             |  Int 64| ---| YES           |
| STATUS| Current status of the inquiry comments, draft, open, closed, or cancelled.                                                                                            | Character| 200| YES           |
| INGESTIONTIME| Date and time the record was ingested, supports change data capture.                                                                                                 | Date Time| ---| NO            |

### Links to other data

| Attribute | Joins to | Cardinality                                                                                         |
| :-------------- | :------ |:----------------------------------------------------------------------------------------------------|
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one <br/> A client identifier is associated with one client. |
| RECORDEDBY | USERS_V2_VIEW| Cardinality is one-to-one.  <br/>  A user identifier is associated with one user.          |
| INQUIRYID | INQUIRIES_V1_VIEW | Cardinality is one-to-one.<br/>  An inquiry identifier is associated with one inquiry record.   |                               


## INQUIRY_RESPONSES_V1_VIEW
This view groups attributes that relate to responses and inquiry response comments by providers to inquiries about their services, such as the responder, status, type, and content text for the comment.
<br/>Uniqueness is guaranteed by inquiryID and providerID. Inquiry identifier could be repeated in the view, and provider identifier could be repeated in the view.


| Attribute | Description                                                                                                                                            | Domain definition |Character size | Nulls allowed |
| :-------------- |:-------------------------------------------------------------------------------------------------------------------------------------------------------|:------ |:------ |:--------------|
| INQUIRYID| Identifier for an inquiry record.                                                                                                                               |  Int 64| ---| NO            |
| PROVIDERID| Identifier for a provider record.                                                                                                                               |  Int 64| ---| NO            |
| SERVICEOFFERINGID| Identifier for a service offering record.                                                                                                               |  Int 64| ---| NO            |
| CLIENTREFERENCE| Unique reference number that identifies the client in the application.                                                                                 | Character| 200            | NO            |
| RESPONDER| Name of the provider contact who responded to the inquiry.                                                                                             | Character | 400| YES            |
| STATUS| Current status of the offer, awaiting offer, offer made, pending acceptance, accepted, withdrawn, rejected, or declined.                               | Character| 200| NO            |
| OFFEREXPIRYDATE| Date on which the provider's offer expires.                                                                                                                     | Date| ---           | YES           |
| OFFEREDUNITS| Number of units of the service offered by the provider.                                                                                                |  Character| 256| YES            |
| OFFEREDRATE| Rate offered by the provider to provide the service for the client.                                                                                    | Decimal| ---           | YES           |
| RECORDEDON| Date and time the offer was last updated.                                                                                                              |  Date Time| ---| NO            |
| RECORDEDBY| The identity of the user who recorded the record.                                                                                                      |  Character| 256| NO            |
| COMMENTS| Comments between a care team member and a specific provider about the inquiry.                                                                         |  Character| 8000| YES|
| ISRESPONSECOMMENT| Indicates whether the comment is an inquiry response.                                                                                                  |  Int 64| ---| NO            |
| TYPE| Type of response, status change, comment, offer update, resource added, or resource removed.                                                            |  Character| 200| YES            |
| INQUIRYLINEITEMEVENTID| Identifier for a record.                                                                                                                               |  Int 64| ---| NO            |
| INGESTIONTIME| Date and time the record was ingested, supports change data capture.                                                                                   | Date Time| ---| NO            |

### Links to other data

| Attribute | Joins to | Cardinality                                                                                          |
| :-------------- | :------ |:-----------------------------------------------------------------------------------------------------|
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one <br/> A client identifier is associated with one client. |
| RECORDEDBY | USERS_V2_VIEW| Cardinality is one-to-one.  <br/>  A user identifier is associated with one user.          |
| INQUIRYID | INQUIRIES_V1_VIEW | Cardinality is one-to-one.<br/>  An inquiry identifier is associated with one inquiry record.     |
| PROVIDERID | PROVIDERS_V1_VIEW| Cardinality is one-to-one. <br/> A provider identifier is associated with one provider.


## SHORTLISTED_PROVIDERS_V1_VIEW

This view groups attributes that relate to shortlisted providers such as the first name and last name of the client or the team member who shortlisted the provider.

| Attribute          | Description                                                            | Domain definition | Character size | Nulls allowed |
|:-------------------|:-----------------------------------------------------------------------|:------------------|:-----|:--------------|
| PROVIDEROFFERINGID | Identifier for a provider offering record.                             | Int 64            |---    | NO            |
| CLIENTREFERENCE    | Unique reference number that identifies the client in the application. | Character         | 200  | YES           |
| ADDEDBY            | The identity of user who shortlisted the record.                       | Character         | 256  | YES           |
| ADDEDBYCLIENT      | First name and last name of the client who shortlisted the record.     | Character         | 400  | NO            |
| INGESTIONTIME      | Date and time the record was ingested, supports change data capture.   | Date Time         |  --- | YES           |

### Links to other data

| Attribute       | Joins to          | Cardinality                                                   |
|:----------------|:--------------------------|:--------------------------------------------------------------|
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one <br/> A client identifier is associated with one client. |
| ADDEDBY | USERS_V2_VIEW |Cardinality is one-to-one. </br> A user is associated with one user record.|
| PROVIDEROFFERINGID | SERVICES_V1_VIEW |Cardinality is one-to-one. </br> A provider offering identifier is associated with one provider offering identifier.|


© Merative US L.P. 2016, 2023.  Merative is a trademark of Merative US L.P. in the United States and other countries.
