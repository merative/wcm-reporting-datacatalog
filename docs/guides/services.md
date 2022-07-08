

This section describes data available for services.


## SERVICE_GOALS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| GOALID| Identifier for a goal record.  |Int 64| --|NO|
| SERVICEID| Identifier for a service record.  |Int 64| --|NO|
| GOALNAME| The goal name for a client. | Character| 500|YES|
| SERVICENAME| Name of the service provided to the client. | Character| 200|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|---  |NO|

### Links to other data


| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| GOALID| Joins to GOALS_V1_VIEW. | Cardinality is one-to-one.  A goal is linked to one goal record.|
| SERVICEID | joins to SERVICE_V1_VIEW. | Cardinality is one-to-one. A service is linked to one service provider record. |




## SERVICE_BARRIERS_V1_VIEW


| Attribute | Description | Domain definition |Size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| BARRIERID| Identifier for a barrier record.  |Int 64| --|NO|
| SERVICEID| Identifier for a service record.  |Int 64| --|NO|
| GOALNAME| The goal name for a client. | Character| 500|YES|
| SERVICENAME| Name of the service provided to the client. | Character| 200|YES|
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time|---  |NO|

### Links to other data


| Attribute | Description |Cardinality |
| :-------------- | :------ |:------ |
| BARRIERID| Joins to BARRIERS_V1_VIEW. | Cardinality is one-to-one.  A barrier is linked to one barrier record.|
| SERVICEID | joins to SERVICE_V1_VIEW. | Cardinality is one-to-one. A service is linked to one service provider record. |
