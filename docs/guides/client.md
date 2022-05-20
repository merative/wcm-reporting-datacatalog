

This section describes data available for clients.<br/>
These views groups attributes that relate to a client's demographic information, address and contact information. It also contains a view that groups data that relates to tags recorded for clients and a view that groups data that shows who has requested emergency access to a client and when.

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
| DATEOFBIRTH| Clients date of birth.| Date Time|--- |YES|
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
| ADDRESSPHYSICALVISIT| Indicates whether the address is the client's physical visit address. The address shown matches the address that is displayed throughout Watson Care Manager for the client, for example, in their context pane and search result. | Character| 1|YES|

### Links to other data

The attribute CLIENTREFERENCE is the primary key to this table, and can be used to join to any other table if CLIENTREFERENCE is present.


| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| REGISTEREDBYUSER | USERS_V1_VIEW | Registered-by-user joins to a user.<br /> A user is associated with zero-to-many clients. |




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
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-many. <br/> A client is associated with zero-to-many emergency access requests.|
| REQUESTEDBY |USERS_V1_VIEW| Cardinality is one-to-many. <br/> An emergency access request is associated with one user. |



## CLIENT_ADDRESSES_V1_VIEW
This view groups attributes that relate to a client's address such as the address details, address type, and whether the address is the client's preferred address.

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
| ADD2| Second line of the client's address.| 1024|YES|
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
| CLIENTREFERENCE| CLIENTS_V1_VIEW| Cardinality is one-to-many.  <br/> A client is associated with zero-to-many addresses|



## CLIENT_EMAILS_V1_VIEW
This view groups attributes that relate to a client's email address such as the email address details, email address type, and whether the email address is the client's preferred email address.

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
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-many. <br/> A client is associated with zero-to-many email addresses.|




## CLIENT_IDENTIFICATIONS_V1_VIEW
This view groups attributes that relate to client's identification types such as their Employee ID or passport, and the number associated with the identification type.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|NO|
| ALTERNATEIDTYPE| Client identification type, for example, reference number, or passport number. The type can be the client's unique system reference number or a configured identification type.  | Character| 50|NO|
| ALTERNATEID| Client identification number. | Character| 200|NO|
| PREFERREDIND| Indicates if this is the client's preferred identification number for communications. | Character| 1|NO|
| COMMENTS| Comments entered for the record. | Character| 50|YES|
| LASTWRITTEN| Date and time the record was changed. | Date Time| ---|NO|
| FROMDATE| Date on which the record is valid from. | Date| ---|YES|
| ENDDATE|Date on which the record is valid to. | Date| ---|YES|

### Links to other data

| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Client reference joins to a client.<br /> A client is associated with zero-to-many identifications.|





## CLIENT_PHONES_V1_VIEW
This view groups attributes that relate to a client's phone number such as the phone number, phone type, and whether the phone number is the client's preferred phone number for calls and texts.

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
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-many. <br/> A client is associated with zero-to-many phone numbers.|






## TAGS_V1_VIEW
This view groups attributes that relate to a client's tags, such as additional information that describes them like whether they are a member of an organization or group, for example, student, football team.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| TAGID| Identifier for a record. |  Int 64| ---|NO|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|YES|
| TAGNAME| The name of the tag. | Character| 512|YES|
| ADDEDBY| First name and last name of the user who added the record. | Character| 256|YES|
| ADDEDON| Date on which the record was added.| Date Time| ---|YES|
| STATUS| The tag status, Active or Canceled. | Character| 200|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture.| Date Time| |YES|

### Links to other data



| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE|  CLIENTS_V1_VIEW| Cardinality is one-to-many. <br/>  A client is associated with zero-to-many tags.|
| UPDATEDBYUSERNAME |  USERS_V1_VIEW | Cardinality is one-to-many. <br/> A tag is associated with one user. |
