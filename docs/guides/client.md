

This section describes data available for clients.<br/> <br/>
These views groups attributes that relate to a client's demographic information, address and contact information along with referral and utilization information for the client. It also contains a view that groups clients who actively receive care management from your organization, a view that groups data that relates to tags recorded for clients and a view that groups data that shows who has requested emergency access to a client and when.

## CLIENTS_V1_VIEW


This view groups attributes that relate to a client's demographics data such as their name, marital status, and gender. In addition, this view groups a client's preferred or most recently updated address, phone number, and email address data.


| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|NO|
| PRIORITY| Importance of the client's care, high, medium, low, or not set.| Character| 20|YES|
| PRIORITYSORTORDER| Order that the priority values are shown in the report, 1, 2, 3, or 4. |  Int 32| ---|NO|
| CLIENTSTATUS| Client's status in the application, active or inactive. | Character|20|NO|
| PREFERREDLANGUAGE| Client's preferred language for communications.| Character| 50|YES|
| PREFCOMMMETHOD| Client's preferred method of communication, hard copy, email, data transfer, phone or fax. | Character| 50|YES|
| DATEOFBIRTH| Client's date of birth.| Date Time|--- |YES|
| DATEOFDEATH| Client's date of death.| Date Time| ---|YES|
| MOTHERSBIRTHLASTNAME| Mother's birth last name. | Character| 200|YES|
| BIRTHLASTNAME| Client's birth last name.| Character| 200|YES|
| TYPEOFNAME| Client's type of name, alias, preferred, registered, or stage name. | Character| 50|YES|
| FIRSTNAME| Client's first name.| Character| 200|YES|
| LASTNAME| Client's last name.  | Character| 200|YES|
| SUFFIX| Client's suffix, for example, junior, senior, or esquire | Character| 20|YES|
| MIDDLENAME| Client's middle name. | Character| 200|YES|
| INITIALS| Client's intials.| Character| 50|YES|
| TITLE| Client's title, for example, Mr or Ms. | Character| 20|YES|
| GENDER| Client's gender.| Character| 20|YES|
| MARITALSTATUS| Client's marital status.| Character| 50|YES|
| PREFERREDID| Client's preferred identification number. | Character| 200|YES|
| PREFERREDIDTYPE| Client's preferred identification type, for example, reference number, or employee ID. | Character| 50|YES|
| PHONETYPE| Type of phone number, home, work, mobile, or other. By default, the client's preferred phone number is displayed. If no preferred phone number is recorded, the most recently updated phone number is displayed.| Character| 40|YES|
| PHONECOUNTRYCODE| Phone country code. | Character| 20|YES|
| PHONEAREACODE| Phone area code. | Character| 20|YES|
| PHONENUMBER| Phone number. | Character| 40|YES|
| PHONEEXTENSION| Phone extension number. | Character| 20|YES|
| PHONEPREFERREDIND| Indicates if this is the client's preferred phone number for contact. | Character| 1|YES|
| EMAILADDRESS| Client's email address | Character| 500|YES|
| EMAILADDRESSTYPE| Type of email address, personal, business, or other. By default, the client's preferred email address is displayed. If no preferred email address is recorded, the most recently updated email address is displayed. | Character| 40|YES|
| EMAILPREFERREDIND| Indicates if this is the client's preferred email address for contact. | Character| 1|YES|
| CREATIONDATE| Date and time that the record was created. | Date Time| ---|YES|
| REGISTEREDBYUSER| First name and last name of the user who created the record.| Character| 256|YES|
| ADDRESSTYPE| Type of address, residential, work, or mailing. By default, the client's preferred address is displayed. If no preferred address is recorded, the most recently updated address is displayed.| Character| 40|YES|
| ADDRESSCITY| Address city. | Character| 100|YES|
| ADDRESSSTATE| Address state. | Character| 100|YES|
| ADDRESSZIP| Address zip. | Character| 30|YES|
| ADDRESS1| First line of the client's address. | Character| 1024|YES|
| ADDRESS2| Second line of the client's address. | Character| 1024|YES|
| ADDRESS3| Third line of the client's address.| Character| 1024|YES|
| ADDRESSPREFERREDIND| Indicates if this is the client's preferred address for communications. | Character| 1|YES|
| ADDRESSPHYSICALVISIT| Indicates whether the address is the client's physical visit address. The address shown matches the address that is displayed throughout Merative Integrated Care for the client, for example, in their context pane and search result. | Character| 1|YES|

### Links to other data

The attribute CLIENTREFERENCE is the primary key to this table, and can be used to join to any other table if CLIENTREFERENCE is present.


| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| REGISTEREDBYUSER| USERS_V2_VIEW | Cardinality is one-to-one. <br/> A user identifier is associated with one user. <br/> A user is associated with zero-to-many clients.|
| CLIENTREFERENCE| EMERGENCYACCESS_V1_VIEW | Cardinality is one-to-many. <br/> A client is associated with zero-to-many emergency access requests.|
| CLIENTREFERENCE| CLIENT_ADDRESSES_V1_VIEW| Cardinality is one-to-many.  <br/> A client is associated with zero-to-many addresses|
| CLIENTREFERENCE| CLIENT_EMAILS_V1_VIEW | Cardinality is one-to-many. <br/> A client is associated with zero-to-many email addresses.|
| CLIENTREFERENCE| CLIENT_IDENTIFICATIONS_V1_VIEW | Client reference joins to a client.<br /> A client is associated with zero-to-many identifications.|
| CLIENTREFERENCE| CLIENT_PHONES_V1_VIEW | Cardinality is one-to-many. <br/> A client is associated with zero-to-many phone numbers.|
| CLIENTREFERENCE| REFERRALS_V1_VIEW | Cardinality is one-to-many.<br /> A client is associated with zero-to-many referrals.|
| CLIENTREFERENCE| TAGS_V1_VIEW | Cardinality is one-to-many. <br/>  A client is associated with zero-to-many tags.|
| CLIENTREFERENCE| UTILIZATIONS_V1_VIEW | Client reference joins to a client.<br /> A client is associated with zero-to-many utilizations.|
| CLIENTREFERENCE| CLIENT_NAME_HISTORIES_V1_VIEW | Cardinality is one-to-many.<br /> A client is associated with zero-to-many name history records.|
| CLIENTREFERENCE| CLIENT_EMAIL_HISTORIES_V1_VIEW | Cardinality is one-to-many.<br /> A client is associated with zero-to-many email history records.|
| CLIENTREFERENCE| CLIENT_BIRTHDEATH_HISTORIES_V1_VIEW | Cardinality is one-to-many. <br /> A client is associated with zero-to-many birth and death history records.|
| CLIENTREFERENCE| CLIENT_PHONE_HISTORIES_V1_VIEW | Cardinality is one-to-many. <br /> A client is associated with zero-to-many phone number history records.|
| CLIENTREFERENCE| CLIENT_IDENTIFICATION_HISTORIES_V1_VIEW | Cardinality is one-to-many. <br /> A client is associated with zero-to-many identifications history records.|
| CLIENTREFERENCE| CLIENT_ADDRESS_HISTORIES_V1_VIEW | Cardinality is one-to-many.<br /> A client is associated with zero-to-many address history records.|
| CLIENTREFERENCE| CLIENT_GENDER_HISTORIES_V1_VIEW | Cardinality is one-to-many.<br /> A client is associated with zero-to-many gender history records.|
| CLIENTREFERENCE| CLIENT_MARITALSTATUS_HISTORIES_V1_VIEW | Cardinality is one-to-many.<br /> A client is associated with zero-to-many marital status history records.|
| CLIENTREFERENCE| CLIENT_STATUS_HISTORIES_V1_VIEW | Cardinality is one-to-many.<br /> A client is associated with zero-to-many status historyrecords.|
| CLIENTREFERENCE| CLIENT_RECEIVINGCARE_V1_VIEW | Cardinality is zero-to-many.<br /> A client is associated with zero-to-many under care records.|


## CLIENT_RECEIVINGCARE_V1_VIEW

This view groups attributes that relate to clients who actively receive care management from your organization. A client actively receives care management when their status is active and they have a care team with one or more care team members for 1 or more days in a calendar month. Group clients by month and year to see all of your organization's active clients receiving care for that period.

| Attribute | Description | Domain definition |Character Size | Nulls allowed |
| :-------------- | :------ |:------ |:---------- |:------ |
| UNIQUEREF| Unique reference number that identifies the client in the application. | Character| 200|NO|
| FIRSTNAME| Client's first name.| Character| 200|NO|
| LASTNAME| Client's last name.  | Character| 200|NO|
| MONTH| The full month name, for example, January, February. | Character| 40|NO|
| YEAR| The year, for example, 2022. |  Int 32| ---|NO|
| FIRSTDAYOFMONTH| A date value representing the month in which the client is receiving care, for example, 01/01/2022. | Date Time|--- |NO|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|--- |NO|



### Links to other data



| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client. A client is associated with zero-to-many management records.|


## EMERGENCYACCESS_V1_VIEW

This view groups attributes that relate to emergency access requests. Use this view to identify users who have requested emergency access to a client.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| EMERGENCYACCESSID| Identifier for a record. |  Int 64|--- |NO|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|NO|
| REQUESTEDBY| The identity of the user who requested emergency access. The identifier value is an email address. | Character| 256|YES|
| REQUESTEDBYFULLNAME| First name and last name of the user who requested emergency access | Character| 524|YES|
| REQUESTEDBYROLE| Role of the user who requested emergency access | Character| 200|YES|
| STATUS| Status of access, active or expired. | Character| 50|YES|
| STARTDATETIME| Date and time when emergency access started. | Date Time| ---|YES|
| LASTACCESSEDDATETIME| Date and time the user last accessed the individual's plan. | Date Time|--- |YES|
| SECURITYROLE| The security role of the user who requested emergency access. | Character| 1024|YES|
| INGESTIONTIME| Date and Time the record was ingested, supports change data capture. | Date Time|--- |YES|

### Links to other data

| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|
| REQUESTEDBY |USERS_V2_VIEW| Cardinality is one-to-one. <br/>  A user identifier is associated with one user.  |



## CLIENT_ADDRESSES_V1_VIEW
This view groups attributes that relate to a client's address such as the address details, address type, and whether the address is the client's preferred address.  The most recent record of each address type is listed.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|NO|
| ADDRESSTYPE| Type of address, residential, work, mailing.| Character| 40|NO|
| PREFERREDIND| Indicates if this is the client's preferred address for communication. | Character| 1|NO|
| COMMENTS| Comments entered for the record. | Character| 1024|YES|
| CITY| City .| Character| 100|YES|
| STATE| State. | Character| 100|YES|
| ZIP| ZIP code. | Character| 30|YES|
| ADD1| First line of the client's address. | Character| 1024|YES|
| ADD2| Second line of the client's address.| Character| 1024|YES|
| ADD3| Third line of the client's address.| Character| 1024|YES|
| PRIORITY| Priority of the item, high, medium, low, or not set. |  Int 32|--- |YES|
| PHYSICALVISIT| Indicates whether the address is the client's physical visit address. | Character| 1|YES|
| FROMDATE| Date on which the address is valid from.| Date| ---|YES|
| ENDDATE| Date on which the address is valid to.| Date| ---|YES|
| LASTWRITTEN| Date and time the record was changed.| Date Time| ---|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture.| Date Time| ---|YES|

### Links to other data


| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|


## CLIENT_EMAILS_V1_VIEW
This view groups attributes that relate to a client's email address such as the email address details, email address type, and whether the email address is the client's preferred email address. The most recent record of each email type is listed.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|NO|
| EMAILADDRESS| Client's email address. | Character| 500|YES|
| EMAILADDRESSTYPE| Type of email address, personal, business, or other. For each type, only the email address with the most recent start date is displayed. If two email addresses of the same type share the most recent start date, the email address which was modified most recently is displayed. | Character.| 40|YES|
| PREFERREDIND| Indicates if this is the client's preferred email address for communications. | Character| 1|NO|
| COMMENTS| Comments entered for the record.| Character| 1024|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture.| Date Time|--- |YES|

### Links to other data


| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|




## CLIENT_IDENTIFICATIONS_V1_VIEW
This view groups attributes that relate to client's identification types such as their Employee ID or passport, and the number associated with the identification type.  The most recent record of each identification type is listed.

| Attribute       | Description | Domain definition |Character size | Nulls allowed |
|:----------------| :------ |:------ |:------ |:------ |
| CLIENTREFERENCE | Unique reference number that identifies the client in the application. | Character| 200|NO|
| ALTERNATEIDTYPE | Client identification type, for example, reference number, or passport number. The type can be the client's unique system reference number or a configured identification type.  | Character| 50|NO|
| ALTERNATEID     | Client identification number. | Character| 200|NO|
| PREFERREDIND    | Indicates if this is the client's preferred identification number for communications. | Character| 1|NO|
| COMMENTS        | Comments entered for the record. | Character| 50|YES|
| UPDATEDON       | Date and time the record was changed. | Date Time| ---|NO|
| FROMDATE        | Date on which the record is valid from. | Date| ---|YES|
| ENDDATE         |Date on which the record is valid to. | Date| ---|YES|

### Links to other data

| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|





## CLIENT_PHONES_V1_VIEW
This view groups attributes that relate to a client's phone number such as the phone number, phone type, and whether the phone number is the client's preferred phone number for calls and texts. The most recent record of each phone type is listed.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|NO|
| PHONECOUNTRYCODE| Phone country code. | Character| 20|YES|
| PHONEAREACODE| Phone area code.  | Character| 20|YES|
| PHONENUMBER| Phone number. | Character| 40|YES|
| PHONEEXTENSION| Phone extension. | Character| 20|YES|
| PHONETYPE| Type of phone number, home, work, mobile, or other.| Character| 40|YES|
| PREFERREDIND| Indicates if this is the client's preferred phone number for contact. | Character| 1|NO|
| COMMENTS| Comments entered for the record.  | Character| 1024|YES|
| PREFERREDFORTEXT| Indicates if this is the client's preferred phone number for texts. | Character| 1|YES|
| FROMDATE| Date on which the record is valid from.| Date| ---|YES|
| ENDDATE| Date on which the record is valid to. | Date| ---|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time| ---|YES|

### Links to other data


| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|


## REFERRALS_V1_VIEW

Referrals are used to direct a client to the correct organization unit that will meet their care management needs.

This view groups data items that relate to a client's referrals such as cohort name, referral date, referral reason and status of the referral.



| Attribute | Description | Domain definition | Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| REFERRALID|  Identifier for a referral record.  |  Int 64|--- |NO|
| COHORTNAME| Name of the cohort that referred the client. Only populated when the referral came from an external source. | Character| 500|YES|
| COHORTSOURCE| Indicates where the cohort came from, for example, a facility or an external system. Only populated when the referral came from an external system. The field is not displayed in the Merative Integrated Care user interface.  | Character| 100 |YES|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|NO|
| REFERRALREASON| Reason the client was referred selected from a preconfigured list of reasons.| Character| 2000|NO|
| OTHERREFERRALREASON| Reason entered for the referral, if none of the reasons in the preconfigured list were suitable for selection. | Character| 2000|YES|
| REFERRALDATE| Date that the client was referred to the organization. | Date| ---|NO|
| CREATEDBY| 	First name and last name of the user who created the referral. | Character| 256|YES|
| STATUS| Current status of the referral, open, accepted, or rejected.| Character| 200|YES|
| PRIORITY| Indicates how urgently the client requires care, Low, Medium, High, or Not Set. | Character|200 |YES|
| FROMORGNAME| Name of the organization unit that referred the client.  | Character| 500|YES|
| FROMORGEXTERNALREF| Reference number for the organization unit that referred the client. | Character| 400|YES|
| TOORGNAME| Name of the organization unit that the client was referred to. | Character| 500|YES|
| TOORGEXTERNALREF| Reference number for the organization unit that the client was referred to. | Character| 400|YES|
| COMMENTS| Comments entered for the record.| Character| 2000|YES|
| ASSIGNEDTO| First name and last name of the user who is assigned the referral. | Character| 256|YES|
| ASSIGNEDDATE| Date and time that the referral was assigned. | Date Time| ---|YES|
| REJECTREASON| Reason for rejecting the referral that was selected from a preconfigured list of reasons. | Character| 200|YES|
| REJECTCOMMENTS| Comments relating to the referral rejection. | Character| 2000|YES|
| REJECTOTHERREASON|  Reason entered for rejecting the referral, if none of the reasons in the preconfigured list were suitable for selection. | Character| 500|YES|
| REJECTEDDATE| Date and time that the referral was rejected. | Character| 200|YES|
| REJECTEDBY| First name and last name of the user who rejected the referral. | Date Time| ---|YES|
| SOURCE| System in which the data was recorded. | Character| 400|YES|
| ORIGINALSOURCE| System in which the data was recorded for the first time. | Character| 400|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time| ---|YES|



### Links to other data


| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|
| CREATEDBY | USERS_V2_VIEW | Cardinality is one-to-one. <br/> A user identifier is associated with one user. |
| ASSIGNEDTO | USERS_V2_VIEW | Cardinality is one-to-one. <br/> A user identifier is associated with one user. |
| REJECTEDBY | USERS_V2_VIEW | Cardinality is one-to-one. <br/> A user identifier is associated with one user. |
| REFERRALID  | REFERRAL_HISTORIES_V1_VIEW | Cardinality is one-to-many. <br/> A referral is associated with zero-to-many history records.       |

## REFERRAL_HISTORIES_V1_VIEW


This view groups data items that relate to a client's referral status change histories such as referral status,  change date, reasons and comments.



| Attribute | Description | Domain definition | Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| REFERRALHISTORYID|  Identifier for a referral history record.  |  Int 64|--- |NO|
| REFERRALID|  Identifier for a referral record.  |  Int 64|--- |NO|
| ASSIGNEDTO| 	Login ID of the user who was assigned the referral. | Character| 256|YES|
| CREATEDBY| 	Login ID of the user who created the referral. | Character| 256|YES|
| COMMENTS| Comments entered for the record.| Character| 6000|YES|
| FROMSTATUS| Previous status of the referral, open, accepted, or rejected.| Character| 1850|YES|
| TOSTATUS| Changed status of the referral, open, accepted, or rejected.| Character| 1850|YES|
| REASON          | Reason for changing referral status.                                     |  Character| 1850             | YES           |
| OTHERREASON     | Other reason for changing referral status.                               | Character| 800            | YES           |
| CREATEDON| Date that the referral was created. | Date| ---|NO|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time| ---|YES|


### Links to other data


| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| REFERRALID| REFERRALS_V1_VIEW | Cardinality is one-to-one.<br /> A referral history identifier is associated with one referral.|
| CREATEDBY        |  USERS_V2_VIEW       | Cardinality is one-to-one.  <br/>  A user identifier is associated with one user.|
| ASSIGNEDTO        |  USERS_V2_VIEW       | Cardinality is one-to-one.  <br/>  A user identifier is associated with one user.|






## TAGS_V1_VIEW
Tags are used to describe additional information about the client like whether they are a member of an organization or group, for example, student, football team. This view groups attributes that relate to a client's tags, such as the tag name, status, when it was added and which users added the tag.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| TAGID| Identifier for a record. |  Int 64| ---|NO|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|YES|
| TAGNAME| The name of the tag. | Character| 512|YES|
| ADDEDBY| The identity of the user who created the record.  | Character| 256|NO|
| ADDEDON| Date on which the record was added.| Date Time| ---|YES|
| STATUS| The tag status, Active or Canceled. | Character| 200|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture.| Date Time| ---|YES|

### Links to other data



| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|
| ADDEDBY |  USERS_V2_VIEW | Cardinality is one-to-one. <br/> A user identifier is associated with one user. |

## UTILIZATIONS_V1_VIEW

A utilization records the clinical services that clients visit so that the organization can understand the types of services that clients use, and service usage and outcome patterns.

This view groups attributes that relate to the utilization such as the utilization id, type and the client's reference.

| Attribute | Description | Domain definition | Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| UTILIZATIONID|  Identifier for a record.  |  Int 64|--- |NO|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|YES|
| VISITDATE| The date on which the client was admitted to a service, or completed their visit.  | Date|--- |YES|
| ADMITTEDIND| The check box to confirm that the client was admitted. | Character| 1|YES|
| DISCHARGEDDATE| The discharge or end date of a service lasted longer than one day.| Date|--- |YES|
| SOURCE| The source that indicates who is providing the information about the service that a client used. For example, a caregiver, or a hospital. The Source list also contains a value of Other.| Character| 200|YES|
| OTHERSOURCE| Source system where the record originated (if configured). | Character| 500|YES|
| ADDEDBY| The identity of the user who added the utilization.  | Character| 256|YES|
| ADDEDON| Date and time that the record was added. | Date Time|---  |YES|
| TYPE| The name of the type that indicates the service that a client visited for clinical care, for example, an Emergency Room or acute hospital. The type list also contains a value of Other. | Character| 200|YES|
| OTHERTYPE| 	The specific service type when Other is selected as the type. | Character| 200|YES|
| DISPOSITION| The type of disposition that indicates the outcome for a client after they availed of clinical services. For example, after a stay in a hospital, a client might return home or go to a skilled nursing facility (SNF). The Disposition list also contains a value of Other. | Character| 200|YES|
| OTHERDISPOSITION| The specific disposition when Other is selected as the disposition type. | Character|500 |YES|
| LOCATION| The name of the facility where a client availed of health services, for example, the name of a hospital, hospice, or rehabilitation center. | Character| 200|YES|
| OTHERLOCATION| The facility name where the client received health services when Other is selected as the location.| Character| 500|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Character| 200|YES|

### Links to other data


| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|
| ADDEDBY | USERS_V2_VIEW | Cardinality is one-to-one. <br/> A user identifier is associated with one user.|
| UTILIZATIONID | PROGRAM_UTILIZATIONS_V1_VIEW | Cardinality is one-to-one <br />A utilization identifier is associated with one utilization record. |

## CLIENT_NAME_HISTORIES_V1_VIEW

This view groups attributes that relate to a client's name change history such as when and who created or updated the client's name. Use this view with the clients view to identify when changes were made and by who to a client's name.


| Attribute       | Description | Domain definition |Character size | Nulls allowed |
|:----------------| :------ |:------ |:------ |:------ |
| CLIENTREFERENCE | Unique reference number that identifies the client in the application. | Character| 200|NO|
| NAMEID| Identifier for a record. |  Int 64|--- |NO|
| CORRECTIONID| Identifier linking edits to a name record. |  Int 64|--- |NO|
| ACTION | Action carried out on the record such as create, update, or delete. | Character| 200|NO|
| UPDATEDBYFULLNAME| First name and last name of the user who updated the record. | Character| 524|NO|
| UPDATEDON        | Date and time the record was changed. | Date Time| ---|NO|
| TYPEOFNAME| Client's type of name, alias, preferred, registered, or stage name. | Character| 50|YES|
| FIRSTNAME| Client's first name.| Character| 200|YES|
| LASTNAME| Client's last name.  | Character| 200|YES|
| SUFFIX| Client's suffix, for example, junior, senior, or esquire. | Character| 20|YES|
| MIDDLENAME| Client's middle name. | Character| 200|YES|
| INITIALS| Client's intials.| Character| 50|YES|
| COMMENTS| Comments entered for the record.| Character| 8000|YES|
| TITLE| Client's title, for example, Mr or Ms. | Character| 20|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|--- |YES|

### Links to other data

| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|


## CLIENT_EMAIL_HISTORIES_V1_VIEW

This view groups attributes that relate to a client's email change history such as when and who created or updated the client's email address. Use this view with the clients view to identify when changes were made and by who to a client's email.

| Attribute       | Description | Domain definition |Character size | Nulls allowed |
|:----------------| :------ |:------ |:------ |:------ |
| CLIENTREFERENCE | Unique reference number that identifies the client in the application. | Character| 200|NO|
| EMAILID| Identifier for a record. |  Int 64|--- |NO|
| CORRECTIONID| Identifier linking edits to an email record. |  Int 64|--- |NO|
| ACTION | Action carried out on the record such as create, update, or delete. | Character| 200|NO|
| UPDATEDBYFULLNAME| First name and last name of the user who updated the record. | Character| 524|NO|
| UPDATEDON        | Date and time the record was changed. | Date Time| ---|NO|
| EMAILTYPE| Client's type of name, alias, preferred, registered, or stage name. | Character| 40|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|--- |YES|

### Links to other data

| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|



## CLIENT_BIRTHDEATH_HISTORIES_V1_VIEW

This view groups attributes that relate to a client's birth and death change history such as when and who created or updated the client's date of birth or death. Use this view with the clients view to identify when changes were made and by who to a client's birth and death details.

| Attribute       | Description | Domain definition |Character size | Nulls allowed |
|:----------------| :------ |:------ |:------ |:------ |
| CLIENTREFERENCE | Unique reference number that identifies the client in the application. | Character| 200|NO|
| BIRTHDEATHID| Identifier for a record. |  Int 64|--- |NO|
| CORRECTIONID| Identifier linking edits to a client birth and death record. |  Int 64|--- |NO|
| ACTION | Action carried out on the record such as create, update, or delete. | Character| 200|NO|
| UPDATEDBYFULLNAME| First name and last name of the user who updated the record. | Character| 524|NO|
| UPDATEDON        | Date and time the record was changed. | Date Time| ---|NO|
| EMAILTYPE| Client's type of name, alias, preferred, registered, or stage name. | Character| 40|YES|
| DATEOFBIRTH| Client's date of birth.| Date Time|--- |YES|
| DATEOFDEATH| Client's date of death.| Date Time| ---|YES|
| MOTHERSBIRTHLASTNAME| Mother's birth last name. | Character| 200|YES|
| BIRTHLASTNAME| Client's birth last name.| Character| 200|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|--- |YES|

### Links to other data

| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|


## CLIENT_PHONE_HISTORIES_V1_VIEW

This view groups attributes that relate to a client's phone change history such as when and who created or updated the client's phone number. Use this view with the clients view to identify when changes were made and by who to a client's phone number.

| Attribute       | Description | Domain definition |Character size | Nulls allowed |
|:----------------| :------ |:------ |:------ |:------ |
| CLIENTREFERENCE | Unique reference number that identifies the client in the application. | Character| 200|NO|
| PHONEID| Identifier for a record. |  Int 64|--- |NO|
| CORRECTIONID| Identifier linking edits to a phone record. |  Int 64|--- |NO|
| ACTION |Action carried out on the record such as create, update, or delete. | Character| 200|NO|
| UPDATEDBYFULLNAME| First name and last name of the user who updated the record. | Character| 524|NO|
| UPDATEDON        | Date and time the record was changed. | Date Time| ---|NO|
| PHONETYPE| Client's type of phone such as home or preferred. | Character| 40|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|--- |YES|

### Links to other data

| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|



## CLIENT_IDENTIFICATION_HISTORIES_V1_VIEW

This view groups attributes that relate to a client's identification change history such as when and who created or updated the client's identification details.  Use this view with the clients view to identify when changes were made and by who to a client's identification details.

| Attribute       | Description | Domain definition |Character size | Nulls allowed |
|:----------------| :------ |:------ |:------ |:------ |
| CLIENTREFERENCE | Unique reference number that identifies the client in the application. | Character| 200|NO|
| EMAILID| Identifier for a record. |  Int 64|--- |NO|
| CORRECTIONID| Identifier linking edits to an identification record. |  Int 64|--- |NO|
| ACTION | Action carried out on the record such as create, update, or delete. | Character| 200|NO|
| UPDATEDBYFULLNAME| First name and last name of the user who updated the record. | Character| 524|NO|
| UPDATEDON        | Date and time the record was changed. | Date Time| ---|NO|
| IDENTIFICATIONTYPE| Client's type of identification, for example, SSN. | Character| 40|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|--- |YES|

### Links to other data

| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|


## CLIENT_ADDRESS_HISTORIES_V1_VIEW

This view groups attributes that relate to a client's address change history such as when and who created or updated the client's address. Use this view with the clients view to identify when changes were made and by who to a client's address details.

| Attribute       | Description | Domain definition |Character size | Nulls allowed |
|:----------------| :------ |:------ |:------ |:------ |
| CLIENTREFERENCE | Unique reference number that identifies the client in the application. | Character| 200|NO|
| ADDRESSID| Identifier for a record. |  Int 64|--- |NO|
| CORRECTIONID| Identifier linking edits to an address record. |  Int 64|--- |NO|
| ACTION | Action carried out on the record such as create, update, or delete. | Character| 200|NO|
| UPDATEDBYFULLNAME| First name and last name of the user who updated the record. | Character| 524|NO|
| UPDATEDON        | Date and time the record was changed. | Date Time| ---|NO|
| ADDRESSTYPE| Client's type of address, for example, home or work. | Character| 40|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|--- |YES|

### Links to other data

| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|




## CLIENT_GENDER_HISTORIES_V1_VIEW

This view groups attributes that relate to a client's gender change history such as when and who created or updated the client's gender information. Use this view with the clients view to identify when changes were made and by who to a client's gender information.

| Attribute       | Description | Domain definition |Character size | Nulls allowed |
|:----------------| :------ |:------ |:------ |:------ |
| CLIENTREFERENCE | Unique reference number that identifies the client in the application. | Character| 200|NO|
| GENDERID| Identifier for a record. |  Int 64|--- |NO|
| CORRECTIONID| Identifier linking edits to a gender record. |  Int 64|--- |NO|
| ACTION | Action carried out on the record such as create, update, or delete. | Character| 200|NO|
| UPDATEDBYFULLNAME| First name and last name of the user who updated the record. | Character| 524|NO|
| UPDATEDON        | Date and time the record was changed. | Date Time| ---|NO|
| GENDER           | Client's gender.                      | Character| 20 |YES|
| STARTDATE| Date from which the marital status is valid.| Date| ---|YES|
| ENDDATE| Date to which the marital status is valid.| Date| ---|YES|
| COMMENTS| Comments entered for the record.| Character| 1024|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture.| Date Time|--- |YES|

### Links to other data

| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|



## CLIENT_MARITALSTATUS_HISTORIES_V1_VIEW

This view groups attributes that relate to a client's maritial status change history such as when and who created or updated the client's martial status information. Use this view with the clients view to identify when changes were made and by who to a client's martial status information.

| Attribute       | Description | Domain definition |Character size | Nulls allowed |
|:----------------| :------ |:------ |:------ |:------ |
| CLIENTREFERENCE | Unique reference number that identifies the client in the application. | Character| 200|NO|
| MARITIALSTATUSID| Identifier for a record. |  Int 64|--- |NO|
| CORRECTIONID| Identifier linking edits to a maritial status record. |  Int 64|--- |NO|
| ACTION | Action carried out on the record such as create, update, or delete. | Character| 200|NO|
| UPDATEDBYFULLNAME| First name and last name of the user who updated the record. | Character| 524|NO|
| UPDATEDON        | Date and time the record was changed. | Date Time| ---|NO|
| MARITIALSTATUS| Client's type of name, alias, preferred, registered, or stage name. | Character| 40|YES|
| STARTDATE| Date from which the marital status is valid.| Date| ---|YES|
| ENDDATE| Date to which the marital status is valid.| Date| ---|YES|
| COMMENTS| Comments entered for the record.| Character| 1024|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture.| Date Time|--- |YES|

### Links to other data

| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|


## CLIENT_STATUS_HISTORIES_V1_VIEW

This view groups attributes that relate to status changes for a client, such as the client's status, active or inactive, the reason for the client status change, and the date when the status was updated. Use this view with the clients view to identify when changes were made and by who to a client's status information.

| Attribute             | Description                                                            | Domain definition | Character size | Nulls allowed |
|:----------------------|:-----------------------------------------------------------------------|:------ |:---------------|:--------------|
| CLIENTSTATUSHISTORYID | Identifier for a record.                                               |  Int 64| ---            | NO            |
| CLIENTREFERENCE       | Unique reference number that identifies the client in the application. | Character| 200            | NO            |
| STATUS                | Status of the record such as active, inactive, or delete.                     |  Character| 50             | NO            |
| STATUSREASON          | Reason for changing client status.                                     |  Character| 50             | YES           |
| STATUSOTHERREASON     | Other reason for changing client status.                               | Character| 200            | YES           |
| COMMENTS              | Comments entered for the record.                                       | Character| 8000           | YES           |
| UPDATEDBYFULLNAME     | First name and last name of the user who updated the record.           | Character| 524            | NO            |
| UPDATEDBYROLE         | Role of the user who updated the record.                               | Character| 200            | YES           |
| UPDATEDON             | Date and time the record was changed.                                  | Date Time| ---            | NO            |
| INGESTIONTIME         | Date and time the record was ingested, supports change data capture.   | Date Time| ---            | NO            |

### Links to other data

| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br/>  A client identifier is associated with one client.|


© Merative US L.P. 2016, 2023. 
Merative is a trademark of Merative US L.P. in the United States and other countries.
