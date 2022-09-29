

This section describes data available for inquiries.

Care team members can create inquiries for services and send them to one or more providers. In the Watson Care Manager Connect Providers application, providers can view and respond to inquiries and make offers to provide services.

These views group attributes relating to inquiries that are sent by the care team to providers to solicit services for their clients. Use these views to create inquiries reports. 

## INQUIRIES_V1_VIEW
This view groups attributes that relate to an inquiry such as the inquiry ID, the service name, expected start date, frequency of the service, and the number of units to be delivered.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:--------------|
| INQUIRYID| Identifier for a record. |  Int 64| ---            | NO            |
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200            | NO            |
| SERVICEOFFERINGID| Identifier for a record. | Int 64| ---          | NO            |
| SERVICENAME| Name of the service for which the inquiry was made. | Character| 500            | YES           |
| REFERENCENUMBER| Reference number assigned to the inquiry by Watson Care Manager after the inquiry was sent. | Int 64| ---            | NO            |
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
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Client reference joins to a client.<br/> A client is associated with zero-to-many inquiries. |
| RECORDEDBY | USERS_V1_VIEW| Updated-by joins to one user.<br/> A user is associated with zero-to-many inquiries.         |
| INQUIRYID | INQUIRY_COMMENTS_V1_VIEW| An inquiry is associated with zero-to-many inquiry comments.                                  |
| INQUIRYID | INQUIRY_RESPONSES_V1_VIEW| An inquiry is associated with zero-to-many inquiry responses.                                 |



## INQUIRY_COMMENTS_V1_VIEW
This view groups attributes that relate to an inquiry comment such as the author, status, and content text for the 
comment. 

| Attribute | Description                                                                                                                                                          | Domain definition |Character size | Nulls allowed |
| :-------------- |:---------------------------------------------------------------------------------------------------------------------------------------------------------------------|:------ |:------ |:--------------|
| INQUIRYID| Identifier for a record.                                                                                                                                             |  Int 64| ---| NO            |
| RECORDEDON| Comments added to the inquiry when it was created.                                                                                                                   |  Date Time| ---| NO            |
| RECORDEDBY| The identity of the user who recorded the record.                                                                                                                    |  Character| 256| NO            |
| COMMENT| Comments added to the inquiry by a care team member. All providers who received the inquiry can see the comment, except for providers who have declined the inquiry. |  Character| 8000| YES           |
| INQUIRYEVENTID| Identifier for a record.                                                                                                                                             |  Int 64| ---| YES           |
| STATUS| Current status of the inquiry comments, draft, open, closed, or cancelled.                                                                                            | Character| 200| YES           |
| INGESTIONTIME| Date and time the record was ingested, supports change data capture.                                                                                                 | Date Time| ---| NO            |

### Links to other data

| Attribute | Joins to | Cardinality                                                                                         |
| :-------------- | :------ |:----------------------------------------------------------------------------------------------------|
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Client reference joins to a client.<br/> A client is associated with zero-to-many inquiry comments. |
| RECORDEDBY | USERS_V1_VIEW| Updated-by joins to one user.<br/> A user is associated with zero-to-many inquiries.                |
| INQUIRYID | INQUIRY_COMMENTS_V1_VIEW| An inquiry is associated with zero-to-many inquiry comments.                                         |

## INQUIRY_RESPONSES_V1_VIEW
This view groups attributes that relate to responses and inquiry response comments by providers to inquiries about their services, such as the responder, status, type, and content text for the comment.

| Attribute | Description                                                                                                                                            | Domain definition |Character size | Nulls allowed |
| :-------------- |:-------------------------------------------------------------------------------------------------------------------------------------------------------|:------ |:------ |:--------------|
| INQUIRYID| Identifier for a record.                                                                                                                               |  Int 64| ---| NO            |
| PROVIDERID| Identifier for a record.                                                                                                                               |  Int 64| ---| NO            |
| SERVICEOFFERINGID| Identifier for a record.                                                                                                                               |  Int 64| ---| NO            |
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
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Client reference joins to a client.<br/> A client is associated with zero-to-many inquiry responses. |
| RECORDEDBY | USERS_V1_VIEW| Updated-by joins to one user.<br/> A user is associated with zero-to-many inquiries.                 |
| INQUIRYID | INQUIRY_RESPONSES_V1_VIEW| An inquiry is associated with zero-to-many inquiry responses.                                         |
