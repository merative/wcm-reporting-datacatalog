

This section describes data available for providers.

A provider is an organization or individual who provides services, such as healthcare or community services, to individuals under care management.

These views group attributes that relate to provider's details such as the provider name, status, contact details, address, identification and the team member who created the provider. These views also group attributes that relate to the provider's service such as address, contacts, rates and status history of the service.

## PROVIDERS_V1_VIEW

This view groups attributes that relate to the provider such as the provider id, type and status.

| Attribute        | Description                                                                                                                                                         | Domain definition | Character size | Nulls allowed |
|:-----------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------|:------------------|:---------------|:--------------|
| PROVIDERID       | Identifier for a provider record.                                                                                                                                   | Int 64            | ---            | NO            |
| NAME             | The name of the provider                                                                                                                                            | Character         | 500            | YES           |
| DESCRIPTION      | The description of a provider.                                                                                                                                      | Character         | 2000           | YES           |
| PHONECOUNTRYCODE | Phone country code.                                                                                                                                                 | Character         | 20             | YES           |
| PHONEAREACODE    | Phone area code.                                                                                                                                                    | Character         | 32             | YES           |
| PHONENUMBER      | Phone number                                                                                                                                                        | Character         | 80             | YES           |
| PHONEEXTENSION   | Phone extension.                                                                                                                                                    | Character         | 60             | YES           |
| EMAILADDRESS     | Email address.                                                                                                                                                      | Character         | 256            | YES           |
| WEBSITE          | Website.                                                                                                                                                            | Character         | 400            | YES           |
| STATUS           | The status of a provider                                                                                                                                            | Character         | 200            | YES           |
| REGISTRATIONDATE | The date the provider was registered.                                                                                                                               | Date              | ---            | NO            |
| REGISTEREDBY     | The identity of the user who registered the provider.                                                                                                               | Character         | 256            | NO            |
| CQCPROVIDERID    | The provider's CQC provider identification number in the format 1-1XXXXXXXX. The CQC Provider ID applies only in the UK and the option is available in the UK only. | Character         | 80             | YES           |
| PAYPALSIGNUP     | The status of whether the provider's PayPal sign-up is complete, Y or N.                                                                                            | Character         | 1              | NO            |
| INGESTIONTIME    | Date and time the record was ingested, supports change data capture.                                                                                                | Date Time         | ---            | YES           |

### Links to other data

| Attribute    | Joins to                         | Cardinality                                                                                                        |
|:-------------|:---------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| REGISTEREDBY | USERS_V2_VIEW                    | Cardinality is one-to-one .<br />  A user identifier is associated with one user.                                  |
| PROVIDERID   | INQUIRIES_RESPONSES_V1_VIEW      | Cardinality is zero-to-many. <br/> A provider identifier is associated with zero-to-many inquiry responses.     |
| PROVIDERID   | PROVIDER_CONNECT_USERS_V1_VIEW   | Cardinality is zero-to-many. <br/> A provider identifier is associated with zero-to-many provider connect users.   |
| PROVIDERID   | PROVIDER_SERVICES_V1_VIEW        | Cardinality is zero-to-many. <br/> A provider identifier is associated with zero-to-many provider services.        |
| PROVIDERID   | PROVIDER_CONTACTS_V1_VIEW        | Cardinality is zero-to-many. <br/>  A provider identifier is associated with zero-to-many contact records.         |
| PROVIDERID   | PROVIDER_ADDRESSES_V1_VIEW       | Cardinality is zero-to-many. <br/> A provider identifier is associated with zero-to-many address records.          |
| PROVIDERID   | PROVIDER_IDENTIFICATIONS_V1_VIEW | Cardinality is zero-to-many. <br/>  A provider identifier is associated with zero-to-many  identification records. |
| PROVIDERID   | USERS_V2_VIEW                    | Cardinality is zero-to-many. <br/>  A provider identifier is associated with zero-to-many  users.                         |

## PROVIDER_ADDRESSES_V1_VIEW

This view groups attributes that relate to the provider's address such as the address details, the address status, and whether the address is the provider's primary address.
<br/>Uniqueness is guaranteed by providerID and provideraddressID. Provider identifier could be repeated in the view, and provider address identifier could be repeated in the view.
<br/>

| Attribute         | Description                                                               | Domain definition | Character size | Nulls allowed |
|:------------------|:--------------------------------------------------------------------------|:------------------|:---------------|:--------------|
| PROVIDERADDRESSID | Identifier for a provider address record.                                 | Int 64            | ---            | YES           |
| PROVIDERID        | Identifier for a provider record.                                         | Int 64            | ---            | NO            |
| STATUS            | Current status of the address record, active or cancelled.                | Character         | 200            | YES           |
| PRIMARYADDRESS    | Indicates if this is the provider's preferred address for communications. | Character         | 1              | NO            |
| COUNTRY           | Country of the provider's address.                                        | Character         | 200            | YES           |
| ADD1              | Line 1 of the provider's address.                                         | Character         | 1024           | YES           |
| ADD2              | Line 2 of the provider's address.                                         | Character         | 1024           | YES           |
| ADD3              | Line 3 of the provider's address.                                         | Character         | 1024           | YES           |
| CITY              | City of the provider's address.                                           | Character         | 100            | YES           |
| STATE             | State of the provider's address.                                          | Character         | 100            | YES           |
| ZIP               | Zip of the provider's address.                                            | Character         | 30             | YES           |
| INGESTIONTIME     | Date and time the record was ingested, supports change data capture.      | Date Time         | ---            | YES           |

### Links to other data

| Attribute         | Joins to                            | Cardinality                                                                                                      |
|:------------------|:------------------------------------|:-----------------------------------------------------------------------------------------------------------------|
| PROVIDERADDRESSID | PROVIDER_SERVICE_ADDRESSES_V1_VIEW  | Cardinality is one-to-one. A provider address identifier is associated with one provider service address record. |
| PROVIDERID        | PROVIDERS_V1_VIEW                   | Cardinality is one-to-one. A provider identifier is associated with one provider record.                         |


## PROVIDER_CONNECT_USERS_V1_VIEW

This view groups attributes that relate to users of the Connect Provider application. For example, the user's name, phone number, email address, and status. Use this view to identify providers who have users onboarded to the Connect application.


| Attribute        | Description                                                          | Domain definition | Character size | Nulls allowed |
|:-----------------|:---------------------------------------------------------------------|:------------------|:---------------|:--------------|
| PROVIDERID       | Identifier for a provider record.                                    | Int 64            | ---            | NO            |
| FIRSTNAME        | The first name of a connect provider web application user.           | Character         | 260            | YES           |
| LASTNAME         | The last name of a connect provider web application user.            | Character         | 260            | YES           |
| PHONECOUNTRYCODE | Phone country code.                                                  | Character         | 20             | YES           |
| PHONEAREACODE    | Phone area code.                                                     | Character         | 32             | YES           |
| PHONENUMBER      | Phone number.                                                        | Character         | 80             | YES           |
| PHONEEXTENSION   | Phone extension.                                                     | Character         | 60             | YES           |
| EMAIL            | Email address.                                                       | Character         | 1024           | YES           |
| STATUS           | The status of a provider.                                            | Character         | 200            | YES           |
| REQUESTSENT      | Date and time the request was sent.                                  | Date Time         | ---            | YES           |
| INGESTIONTIME    | Date and time the record was ingested, supports change data capture. | Date Time         | ---            | YES           |

### Links to other data

| Attribute  | Joins to           | Cardinality                                                                                     |
|:-----------|:-------------------|:------------------------------------------------------------------------------------------------|
| PROVIDERID | INQUIRIES_V1_VIEW  | Cardinality is one-to-one. <br/> A inquiry identifier is associated with one inquiry record.    |
| PROVIDERID | PROVIDERS_V1_VIEW  | Cardinality is one-to-one. </br>  A provider identifier is associated with one provider record. |

## PROVIDER_CONTACTS_V1_VIEW

This view groups attributes that relate to the provider's contacts such as the name, phone number, email, role of the contact, and whether the contact is the provider's primary contact.
<br/>Uniqueness is guaranteed by providerID and providercontactID. Provider identifier could be repeated in the view, and provider contact identifier could be repeated in the view.
<br/>


| Attribute              | Description                                                                                         | Domain definition | Character Size | Nulls allowed |
|:-----------------------|:----------------------------------------------------------------------------------------------------|:------------------|:---------------|:--------------|
| PROVIDERCONTACTID      | Identifier for the provider contact record.                                                         | Int 64            | ---            | YES           |
| PROVIDERID             | Identifier for a provider record.                                                                   | Int 64            | ---            | NO            |
| FIRSTNAME              | Provider contact's first name.                                                                      | Character         | 260            | YES           |
| LASTNAME               | Provider contact's last name.                                                                       | Character         | 260            | YES           |
| ROLE                   | Role of the provider contact.                                                                       | Character         | 200            | YES           |
| PRIMARYCONTACT         | Indicates if this is the provider's primary contact. A provider can have multiple primary contacts. | Character         | 1              | NO            |
| PHONECOUNTRYCODE       | The international dialing code for the provider contact's phone number.                             | Character         | 20             | YES           |
| PHONEAREACODE          | Phone area code.                                                                                    | Character         | 32             | YES           |
| PHONENUMBER            | Phone number.                                                                                       | Character         | 80             | YES           |
| PHONEEXTENSION         | The phone number extension.                                                                         | Character         | 60             | YES           |
| MOBILEPHONECOUNTRYCODE | The international dialing code for the provider contact's mobile phone number.                      | Character         | 20             | YES           |
| MOBILEPHONEAREACODE    | Mobile phone area code.                                                                             | Character         | 32             | YES           |
| MOBILEPHONENUMBER      | Mobile phone number.                                                                                | Character         | 80             | YES           |
| MOBILEPHONEEXTENSION   | The mobile phone number extension.                                                                  | Character         | 60             | YES           |
| EMAILADDRESS           | The email address of the provider contact.                                                          | Character         | 256            | YES           |
| INGESTIONTIME          | Date and time the record was ingested, supports change data capture.                                | Date Time         | ---            | YES           |

### Links to other data

| Attribute         | Joins to                          | Cardinality                                                                                                   |
|:------------------|:----------------------------------|:--------------------------------------------------------------------------------------------------------------|
| PROVIDERCONTACTID | PROVIDER_SERVICE_CONTACTS_V1_VIEW | Cardinality is one-to-many. </br> A provider contact is associated with one-to-many provider service contacts. |
| PROVIDERID        | PROVIDERS_V1_VIEW                 | Cardinality is one-to-one. </br> A provider identifier is associated with one provider record.                |


## PROVIDER_IDENTIFICATIONS_V1_VIEW

This view groups attributes that relate to providers's identification types such as their company number.
<br/>Uniqueness is guaranteed by providerID and identificationnumber. Provider identifier could be repeated in the view, and identification number could be repeated in the view.
<br/>

| Attribute            | Description                                                          | Domain definition | Character Size | Nulls allowed |
|:---------------------|:---------------------------------------------------------------------|:------------------|:---------------|:--------------|
| PROVIDERID           | Identifier for a provider record.                                    | Int 64            | ---            | NO            |
| IDENTIFICATIONNUMBER | Identifier for the identification record.                                        | Character         | 72             | NO            |
| IDENTIFICATIONTYPE   | Type of identification.                                              | Character         | 200            | YES           |
| INGESTIONTIME        | Date and time the record was ingested, supports change data capture. | Date Time         | ---            | YES           |

### Links to other data

| Attribute  | Joins to          | Cardinality                                                                                   |
|:-----------|:------------------|:----------------------------------------------------------------------------------------------|
| PROVIDERID | PROVIDERS_V1_VIEW | Cardinality is one-to-one. </br> A provider identifier is associated with one provider record. |

## PROVIDER_SERVICES_V1_VIEW

This view groups attributes that relate to the provider's service such as the service name, the group name if the provider service is part of a service group, available languages, the status, and the category of the provider service.
<br/>Uniqueness is guaranteed by providerID and serviceofferingID. Provider identifier could be repeated in the view, and service offering identifier could be repeated in the view.
<br/>

| Attribute               | Description                                                          | Domain definition | Character Size | Nulls allowed |
|:------------------------|:---------------------------------------------------------------------|:------------------|:---------------|:--------------|
| PROVIDERID              | Identifier for a provider record.                                    | Int 64            | ---            | NO            |
| PROVIDEROFFERINGID      | Identifier for a provider offering record.                           | Int 64            | ---            | NO            |
| SERVICEOFFERINGID       | Identifier for a service offering record.                            | Int 64            | ---            | NO            |
| NAME                    | The name of the service offered by the provider.                     | Character         | 200            | YES           |
| GROUPNAME               | Service group associated with the provider service.                  | Character         | 200            | YES           |
| LANGUAGES               | Common languages for the provider service.                           | Character         | 500            | YES           |
| STATUS                  | Status of the provider service.                                      | Character         | 200            | YES           |
| CATEGORIES              | Category that best describes the nature of the provider service.     | Character         | 1000           | YES           |
| ADDEDON                 | Date that the service was associated with the provider.              | Date Time         | ---            | YES           |
| ADDEDBY                 | The user who associated the service with the provider.               | Character         | 256            | YES           |
| INGESTIONTIME           | Date and time the record was ingested, supports change data capture. | Date Time         | ---            | YES           |

### Links to other data

| Attribute          | Joins to                           | Cardinality                                                                                                       |
|:-------------------|:-----------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------|
| PROVIDERID         | PROVIDERS_V1_VIEW                  | Cardinality is one-to-one. </br> A provider identifier is associated with one provider record.                                         |
| PROVIDEROFFERINGID | PROVIDER_SERVICE_ADDRESSES_V1_VIEW | Cardinality is zero-to-many. </br> A provider offering identifier is associated with zero-to-many provider service address records.  |
| SERVICEOFFERINGID  | SERVICES_V1_VIEW                   | Cardinality is zero-to-many. </br> A service is associated with zero-to-many provider services.                                         |
| PROVIDEROFFERINGID | PROVIDER_SERVICES_CONTACTS_V1_VIEW | Cardinality is zero-to-many. </br>  A provider offering identifier is associated with zero-to-many provider service contact records.  |
| PROVIDEROFFERINGID | PROVIDER_SERVICES_HISTORY_V1_VIEW  | Cardinality is one-to-many. </br>  A provider offering identifier is associated with one-to-many provider service history records.  |
| PROVIDEROFFERINGID | PROVIDER_SERVICES_RATES_V1_VIEW    | Cardinality is zero-to-many. </br>  A provider offering identifier is associated with zero-to-many provider service rate records.     |

## PROVIDER_SERVICE_ADDRESSES_V1_VIEW

This view groups attributes that relate to the provider's service address such as the address details and the address status.
<br/>Uniqueness is guaranteed by provideraddressID and providerofferingID. Provider address identifier could be repeated in the view, and provider offering identifier could be repeated in the view.
<br/>


| Attribute          | Description                                                          | Domain definition | Character Size | Nulls allowed |
|:-------------------|:---------------------------------------------------------------------|:------------------|:---------------|:--------------|
| PROVIDERADDRESSID  | Identifier for a provider address record.                            | Int 64            | ---            | YES           |
| PROVIDEROFFERINGID | Identifier for a provider offering record.                           | Int 64            | ---            | NO            |
| STATUS             | The status of a provider.                                            | Character         | 200            | YES           |
| COUNTRY            | Country of the provider's service address.                           | Character         | 200            | YES           |
| ADD1               | Line 1 of the provider's service address.                            | Character         | 1024           | YES           |
| ADD2               | Line 2 of the provider's service address.                            | Character         | 1024           | YES           |
| ADD3               | Line 3 of the provider's service address.                            | Character         | 1024           | YES           |
| CITY               | City of the provider's service address.                              | Character         | 100            | YES           |
| STATE              | State of the provider's service address.                             | Character         | 100            | YES           |
| ZIP                | Zip of the provider's service address.                               | Character         | 30             | YES           |
| INGESTIONTIME      | Date and time the record was ingested, supports change data capture. | Date Time         | ---            | YES           |

### Links to other data

| Attribute          | Joins to                   | Cardinality                                                                                                              |
|:-------------------|:---------------------------|:-------------------------------------------------------------------------------------------------------------------------|
| PROVIDERADDRESSID  | PROVIDER_ADDRESSES_V1_VIEW | Cardinality is one-to-one. </br>  A provider address identifier is associated with one provider address record. |
| PROVIDEROFFERINGID | SERVICES_V1_VIEW           | Cardinality is one-to-one. </br>  A provider offering identifier is associated with one service record.                  |
| PROVIDEROFFERINGID | PROVIDER_SERVICES_V1_VIEW  | Cardinality is one-to-one. </br>  A provider offering identifier is associated with one provider service record.         |

## PROVIDER_SERVICE_CONTACTS_V1_VIEW

This view groups attributes that relate to the provider's contacts such as the name, phone number, email, role of the contact, and whether the contact is the provider's primary contact.
<br/>Uniqueness is guaranteed by providercontactID and providerofferingID. Provider contact identifier could be repeated in the view, and provider offering identifier could be repeated in the view.
<br/>


| Attribute              | Description                                                                   | Domain definition | Character Size | Nulls allowed |
|:-----------------------|:------------------------------------------------------------------------------|:------------------|:---------------|:--------------|
| PROVIDERCONTACTID      | Identifier for the provider contact record.                                   | Int 64            | ---            | YES           |
| PROVIDEROFFERINGID     | Identifier for a provider offering record.                                    | Int 64            | ---            | NO            |
| FIRSTNAME              | First name of the contact associated with the provider service.               | Character         | 260            | YES           |
| LASTNAME               | Last name of the contact associated with the provider service.                | Character         | 260            | YES           |
| ROLE                   | Role of the contact associated with the provider service.                     | Character         | 200            | YES           |
| PRIMARYCONTACT         | Indicates if this is the primary contact associated with the provider service.| Character         | 1              | NO            |
| PHONECOUNTRYCODE       | International dialing code for the provider service contact's phone number.   | Character         | 20             | YES           |
| PHONEAREACODE          | Area code for the provider service contact's phone number.                    | Character         | 32             | YES           |
| PHONENUMBER            | Provider service contact's phone number.                                      | Character         | 80             | YES           |
| PHONEEXTENSION         | The phone number extension.                                                   | Character         | 60             | YES           |
| MOBILEPHONECOUNTRYCODE | International dialing code for the provider service contact's mobile phone number. | Character         | 20             | YES           |
| MOBILEPHONEAREACODE    | Area code for the provider service contact's mobile phone number.             | Character         | 32             | YES           |
| MOBILEPHONENUMBER      | Provider service contact's mobile phone number.                               | Character         | 80             | YES           |
| MOBILEPHONEEXTENSION   | The mobile phone number extension.                                            | Character         | 60             | YES           |
| EMAILADDRESS           | The email address for the provider service contact.                           | Character         | 256            | YES           |
| INGESTIONTIME          | Date and time the record was ingested, supports change data capture.          | Date Time         | ---            | YES           |

### Links to other data

| Attribute          | Joins to                  | Cardinality                                                                                                             |
|:-------------------|:--------------------------|:------------------------------------------------------------------------------------------------------------------------|
| PROVIDERCONTACTID  | PROVIDER_CONTACTS_V1_VIEW | Cardinality is one-to-one. </br> A provider contact identifier is associated with one provider contact record. |
| PROVIDEROFFERINGID | PROVIDER_SERVICES_V1_VIEW | Cardinality is one-to-one. </br>  A provider offering identifier is associated with one provider services record.       |
| PROVIDEROFFERINGID | SERVICES_V1_VIEW          | Cardinality is one-to-one. </br>  A provider offering identifier is associated with one services record.                |

## PROVIDER_SERVICE_HISTORIES_V1_VIEW

This view groups attributes that relate to the status changes for a provider's service, such as the provider's service status, draft, active, closed, or cancelled, the reason for the status change, the date when the status was updated, and who updated the status.


| Attribute          | Description                                                                                | Domain definition | Character Size | Nulls allowed |
|:-------------------|:-------------------------------------------------------------------------------------------|:------------------|:---------------|:--------------|
| PROVIDEROFFERINGID | Identifier for a provider offering record.                                                 | Int 64            | ---            | NO            |
| STATUS             | Status of the provider service, active, draft, closed, or cancelled.                        | Character         | 100            | YES           |
| STARTDATETIME      | Date when the status was updated.                                                          | Date Time         | ---            | NO            |
| CLOSEDDATE         | Date when the service was closed.                                                          | Date              | ---            | YES           |
| RECORDEDBY         | User who updated the service status.                                                       | Character         | 256            | NO            |
| REASON             | Reason for updating the service status.                                                    | Character         | 2000           | YES           |
| INGESTIONTIME      | Date and time the record was ingested, supports change data capture.                       | Date Time         | ---            | YES           |


### Links to other data

| Attribute          | Joins to                  | Cardinality                                                                                                       |
|:-------------------|:--------------------------|:------------------------------------------------------------------------------------------------------------------|
| PROVIDEROFFERINGID | PROVIDER_SERVICES_V1_VIEW | Cardinality is one-to-one. </br>  A provider offering identifier is associated with one provider services record. |
| PROVIDEROFFERINGID | SERVICES_V1_VIEW          | Cardinality is one-to-one. </br>  A provider offering identifier is associated with one services record.          |

## PROVIDER_SERVICE_RATES_V1_VIEW

This view groups attributes that relate to the provider's service rates such as the rate value and the dates for which the rate is valid.
<br/>Uniqueness is guaranteed by providerofferingrateID and providerofferingID. Provider offering rate identifier could be repeated in the view, and provider offering identifier could be repeated in the view.
<br/>

| Attribute              | Description                                                          | Domain definition   | Character Size   | Nulls allowed |
|:-----------------------|:---------------------------------------------------------------------|:--------------------|:-----------------|:--------------|
| PROVIDEROFFERINGRATEID | Identifier for a provider offering rate.                             | Int 64              | ---              | YES           |
| PROVIDEROFFERINGID     | Identifier for a provider offering record.                           | Int 64              | ---              | NO            |
| RATE                   | Monetary rate for the provider service.                              | Decimal fixed-point | 2 decimal places | NO            |
| STARTDATE              | Date from when the provider service rate applies.                    | Date                | ---              | NO            |
| ENDDATE                | Date from when the provider service rate is no longer valid.         | Date                | ---              | YES           |
| UNITTYPE               | Unit of measure for the provider service rate.                       | Character           | 100              | YES           |
| INGESTIONTIME          | Date and time the record was ingested, supports change data capture. | Date Time           | ---              | YES           |

### Links to other data

| Attribute          | Joins to                  | Cardinality                                                                                                       |
|:-------------------|:--------------------------|:------------------------------------------------------------------------------------------------------------------|
| PROVIDEROFFERINGID | PROVIDER_SERVICES_V1_VIEW | Cardinality is one-to-one. </br>  A provider offering identifier is associated with one provider services record. |
| PROVIDEROFFERINGID | SERVICES_V1_VIEW          | Cardinality is one-to-one. </br>  A provider offering identifier is associated with one services record.          |


© Merative US L.P. 2016, 2023.  Merative is a trademark of Merative US L.P. in the United States and other countries.
