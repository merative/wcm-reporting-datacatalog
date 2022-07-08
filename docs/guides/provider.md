

This section describes data available for providers.

A provider is an organization or individual who provides services, such as healthcare or community services, to individuals under care management.

These views group attributes that relate to providers details such as the provider name, status, contact details and the team member who created the provider.

## PROVIDERS_V1_VIEW

This view groups attributes that relate to the provider such as the provider id, type and status.

| Attribute | Description | Domain definition | Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| PROVIDERID|  Identifier for a record.  |  Int 64|--- |NO|
| NAME| The name of the provider | Character| 500|YES|
| DESCRIPTION| The description of a provider. | Character| 2000|YES|
| PHONECOUNTRYCODE|  Phone country code.  | Character|20 |YES|
| PHONEAREACODE| Phone area code. | Character| 32|YES|
| PHONENUMBER| Phone number| Character|80 |YES|
| PHONEEXTENSION| Phone extension. | Character| 60|YES|
| EMAILADDRESS| Email address. | Character| 256|YES|
| WEBSITE| Website.| Character | 400|YES|
| STATUS| The status of a provider | Character|200 |YES|
| REGISTRATIONDATE|The date the provider was registered. | Date| ---|NO|
| REGISTEREDBY| The identity of the user who registered the provider. | Character| 256|NO|
| CQCPROVIDERID| The provider's CQC provider identification number in the format 1-1XXXXXXXX. The CQC Provider ID applies only in the UK and the option is available in the UK only. | Character| 80|YES|
| PAYPALSIGNUP| The status of whether the provider's PayPal sign-up is complete, Y or N.  | Character| 1|NO|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|---  |YES|

### Links to other data


| Attribute | Joins to|Cardinality |
| :-------------- | :------ |:------ |
| REGISTEREDBY | USERS_V1_VIEW | Created-by joins to a user.<br /> A user is associated with zero-to-many providers. |
