

This section describes data available for content records. <br/> <br/>

Client consent represents a client's permission for their data to be captured and used to improve their care. <br/> <br/>

These views groups attributes that relate to a client's consent records such as the consent type, status, the date consent was received, attachments provided to support the clients's consent and the history of the consent record.


## CONSENTS_V1_VIEW
This view groups attributes that relate to the client's consent, such as the consent type, status, expiry and description of the consent record.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CONSENTID| Identifier for a record. |  Int 64|--- |NO|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|NO|
| TEAMMEMBERID| Team member identity of a representative on the care team who can provide consent on behalf of a client who is incapable of giving consent themselves. |  Int 64| ---|YES|
| CONSENTTYPES| One or more values that describe the nature of the consent documents that the client can provide. For example, Lab results or Mental health information. | Character| 4000|YES|
| TYPE| Category of the client consent record, by type. Consent types are configured by your organization. | Character| 200|YES|
| RECEIVEDDATE| Date that the client's consent to share details of their personal health with the care team was received. | Date|--- |YES|
| RECEIVEDBY| The identifier for a user record. The identifier value is an email address. | Character| 256|YES|
| EXPIRYDATE| Expiry date for the consent document. | Date|--- |YES|
| STATUS| Current status of the consent record, Received, Expired, Withdrawn, or Canceled. | Character| 200|YES|
| DESCRIPTION| Additional detail that was captured about the consent. | Character| 8000|YES|
| WITHDRAWNDATE| Date and time that the consent was withdrawn. | Date| ---|YES|
| WITHDRAWNBY| The identifier for a user record. The identifier value is an email address. | Character| 256|YES|
| ISCOMMUNITYCONSENT| Is this a community consent or individual consent record, Y or N. | Date Time| ---|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|---  |NO|

### Links to other data

| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW| Cardinality is one-to-one. <br/> A client identifier is associated with one client.|
| RECEIVEDBY | USERS_V2_VIEW| Cardinality is one-to-one. <br/>  A user identifier is associated with one user. |
| WITHDRAWNBY | USERS_V2_VIEW| Cardinality is one-to-one. <br/>  A user identifier  is associated with one user. |
| TEAMMEMBERID | TEAMMEMBERS_V1_VIEW| Cardinality is one-to-one. <br/>  A team member identifier is associated with one team member. |
| CONSENTID| CONSENT_ATTACHMENTS_V1_VIEW | Cardinality is one-to-many. <br/>  A consent is associated with zero-to-many attachments.|
| CONSENTID| CONSENT_HISTORIES_V1_VIEW | Cardinality is one-to-many. <br/>  A consent is associated with zero-to-many consent history records.|



## CONSENT_ATTACHMENTS_V1_VIEW

This view groups attributes that relate to attachments provided to support the client's consent, such as the attachment type, status, when the attachment was added, and who added it.  


| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CONSENTID| Identifier for a record. |  Int 64|--- |NO|
| ADDEDBY| The identifier for a user record. The identifier value is an email address. | Character| 256|YES|
| ADDEDBYFULLNAME| First name and last name of the user who added the record.  | Character| 524|YES|
| ADDEDBYROLE| The role of the user who added the record. | Character| 200|YES|
| ATTACHMENTNAME| The name of the attachment. | Character| 1024|YES|
| STATUS| The status of the attachment. | Character| 200|YES|
| RECEIPTDATE| The date the attachment was entered. | Date Time| ---|YES|
| ISCOMMUNITYCONSENT| Is this a community consent record. | Date Time|--- |YES|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|NO|
| ATTACHMENTID| Identifier for a attachment record. |  Int 64|--- |NO|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|---  |NO|

### Links to other data
| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CONSENTID| CONSENTS_V1_VIEW| Cardinality is one-to-one. <br/>  A consent identifier is associated with one consent .|
| ADDEDBY | USERS_V2_VIEW| Cardinality is one-to-one. <br/>  A user identifier is associated with one user. |
| CLIENTREFERENCE| CLIENTS_V1_VIEW| Cardinality is one-to-one. <br/> A client identifer is associated with one client.|

## CONSENT_HISTORIES_V1_VIEW

This view groups attributes that relate to consent history, such as when the consent record was updated, the status of the record and who updated the record.


| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CONSENTHISTORYID| Identifier for a record. |  Int 64| ---|YES|
| UPDATEDBY| The identifier for a user record. The identifier value is an email address. | Character| 256|YES|
| UPDATEDDATE| The date the record was updated. | Date| ---|YES|
| STATUS| The status of the consent. | Character| 200|YES|
| CONSENTID| Identifier for a record. |  Int 64|--- |NO|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|---  |NO|

### Links to other data
| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CONSENTID| CONSENTS_V1_VIEW| Cardinality is one-to-one. <br/> A client identifier is associated with one client.|
| UPDATEDBY | USERS_V2_VIEW| Cardinality is one-to-one.<br/> A user identifier is associated with one user. |


© Merative US L.P. 2016, 2023. 
Merative is a trademark of Merative US L.P. in the United States and other countries.
