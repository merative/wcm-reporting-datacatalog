

This section describes data available for custom entities (custom data type).

Custom entities are configurable records that are defined by the organisation.  A custom data type represents the logical grouping of related attributes about which the organization wants to record information in respect of a client.



## CUSTOM_ENTITIES_V1_VIEW

This view groups attributes that relate to information captured in respect of a custom client data type, such as the custom data type name, attribute name, position, attribute value, effective from date, and effective version number. It is best practice to create reports based on the attribute name and not the position. The position indicates the order that your Administrator added the attribute to the custom client data type and updates in reports if the attribute is later removed.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| ENTITYID|  Identifier for a record.  |  Int 64|--- |NO|
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200|NO|
| UPDATEDBY | The identifier for a user record. The identifier value is an email address.| Character|256| NO|
| DATATYPENAME| The name of the custom client data type. | Character| 200|YES|
| CATEGORY| Category that the custom client data type is grouped into. For example, contact, demographic, clinical. | Character| 100|NO|
| CLUSTER| Name of a cluster that is configured for a custom client data type that contains attributes. This is populated only when the custom client data type contains attributes. | Character| 200|YES|
| POSITION| Order that the attribute  are shown on the custom client data type.|  Int 64| ---|NO|
| ATTRIBUTE| The name of the attribute within the custom client data type. | Character| 120|NO|
| VALUE| Value that was entered for the attribute, in string format. | Character| 2000|YES|
| DOUBLEVALUE|  If the base data type of the attribute is a float or decimal, this field displays a numeric double value that you can use for comparisons or arithmetic. Otherwise, this field is blank. | Double floating-point| ---|YES|
| LONGVALUE|  If the base data type of the attribute is an integer, this field displays a number that you can use for comparisons or arithmetic. Otherwise, this field is blank. |  Int 64| ---|YES|
| DATEVALUE| Date and time the custom client data record was created or last updated by a user in the Care Team application. | Date Time| ---|YES|
| EVIDENCETYPEVERSIONDEFID| Identifier for the version of metadata used to create this evidence record.|  Int 64|--- |YES|
| RELATEDPERSON| The unique reference number that identifies the person related to the client in the application.|  Int 64| ---|YES|
| EFFECTIVEVERSION| The version number of the custom client data type that applies to a particular effective date. The version number for the very first instance of a custom client data type is 0. Version numbers restart when a version is effective from a new date. |  Int 64|--- |YES|
| EFFECTIVEFROM| The date from when the custom client data type version became effective. Each version of a client data type is effective from a particular date, and remains effective until the next version is created. | Date| ---|YES|
| STATUS| Status of the custom client data version, active or canceled. | Character| 200|NO|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|---  |NO|


### Links to other data

| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW| Cardinality is one-to-one. <br/> A client identifier is associated with one client.|
| UPDATEDBY | USERS_V2_VIEW| Cardinality is one-to-one. <br/>  A user identifier is associated with one user. |


© Merative US L.P. 2016, 2023.  Merative is a trademark of Merative US L.P. in the United States and other countries.
