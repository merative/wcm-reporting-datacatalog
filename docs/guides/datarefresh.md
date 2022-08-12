

This view shows the date and time of the last data refresh. Describes the age and status of the data refresh. Data captured after this date is not available. <br/> <br/>



## DATAREFRESH_V1_VIEW
This view groups attributes that relate to when data was last refreshed such as the date and time of the last refresh and the status of the refresh. Use the attributes in the Data Refresh view to understand when data was last copied from the application to the reporting warehouse.

| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:------ |
| LASTREFRESHDATE| The date and time of the last data refresh. Describes the age of the data. Data captured after this date is not available. |  Date Time|--- |NO|
| LASTREFRESHSTATUS| Describes the status of the last data refresh, Complete or In Progress. | Character| 200|NO|
