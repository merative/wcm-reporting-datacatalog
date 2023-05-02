

This section describes data available for tasks.

A task is an item of work that team members and supervisors must complete that relate to a client or a general item of work.

These views groups attributes hat relate to a tasks details such as the task name, priority, category and whether it's assigned to a role or a user.

## TASKS_V1_VIEW
This view groups attributes that relate to a task such as the task name, start time, and priority.

| Attribute | Description | Domain definition | Character size | Nulls allowed |
| :-------------- | :------ |:------ |:---------------|:--------------|
| TASKID| Identifier for a record. |  Int 64| ---            | NO            |
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200            | NO            |
| NAME| The name of the task. | Character| 1000           | NO            |
| DUEDATE| Date that the task is due to be completed. | Date| ---            | YES           |
| STARTTIME| Time that the task is due to start. The start time is populated only when the task due date and time is recorded in Merative Integrated Care. | Date Time| ---            | YES           |
| ENDTIME| Time that the task is due to end. The end time is populated only when the task due date and time is recorded in Merative Integrated Care. | Date Time| ---             | YES           |
| DESCRIPTION| Description of the record. | Character| 1200           | YES           |
| UPDATEDBY| First name and last name of the user who updated the record. | Character| 256            | YES           |
| UPDATEDDATETIME| Date and time that the record was updated. | Date Time| ---             | YES           |
| CREATEDBY| First name and last name of the user who created the record. | Character| 256            | NO            |
| CREATEDDATETIME| Date and time that the record was created. | Date Time| ---             | NO            |
| CATEGORY| Category that best describes the nature of the item. For example, Clinical or Admin. | Character| 1850           | YES           |
| PRIORITY| Priority of the item, High, Medium, or Low or Not Set.  | Character| 1850           | YES           |
| CLOSUREREASON| Reason that the record was closed. | Character| 1850           | YES           |
| TASKSTATUS| Current status of the task, Open, Closed, Overdue, Canceled. | Character| 1850           | YES           |
| ASSIGNEDTO| Email address of the user who was assigned the task. | Character| 256            | YES           |
| ASSIGNEDTOFULLNAME| First name and last name of the user who was assigned the task. | Character| 524            | YES           |
| ASSIGNEDTOROLE| Role of the user who was assigned the task. | Character| 200            | YES           |
| ASSIGNEDDATE| Date and time the task was assigned. | Date Time| ---             | YES           |
| ASSIGNMENTSTATUS| Scheduled status of the task. | Character| 100            | YES           |
| SCHEDULED| Indicates if the task is scheduled. | Character| 1              | YES           |
| ROLEASSIGNED| The care team role that is assigned the task. | Character| 1              | YES           |
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time| ---             | NO            |

### Links to other data


| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br /> A client identifier is associated with one client.|
| CREATEDBY | USERS_V2_VIEW | Cardinality is one-to-one.<br /> A user identifier is associated with one user.|
| UPDATEDBY | USERS_V2_VIEW| Cardinality is one-to-one.<br /> A user identifier is associated with one user.|
| ASSIGNEDTO | USERS_V2_VIEW| Cardinality is one-to-one.<br /> A user identifier is associated with one user.|
| TASKID | TASK_PROGRAMS_V1_VIEW| Cardinality is one-to-many.<br /> A task is associated with zero-to-many programs. |
| TASKID | TASK_ROLE_V1_VIEW| Cardinality is one-to-one.<br /> A task is associated with zero-to-one roles. |



## TASK_PROGRAMS_V1_VIEW
This view groups attributes by their associated program. Use this view to identify specific tasks associated with a client's programs.
<br/>Uniqueness is guaranteed by taskID and programID. Task identifier could be repeated in the view, and program identifier could be repeated in the view.


| Attribute | Description | Domain definition |Character size | Nulls allowed |
| :-------------- | :------ |:------ |:------ |:--------------|
| TASKRELATEDLINKID| Identifier for a record. |  Int 64| ---| NO            |
| TASKID| Identifier for a record. |  Int 64| ---| NO            |
| PROGRAMID|Identifier for a record. |  Int 64| ---| NO            |
| CLIENTREFERENCE| Unique reference number that identifies the client in the application. | Character| 200| NO            |
| INGESTIONTIME| Date and time the record was ingested, supports change data capture. | Date Time| ---| NO            |

### Links to other data

| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one.<br /> A client identifier is associated with one client.|
| TASKID | TASK_V1_VIEW| Cardinality is one-to-one. <br /> A task is associated with one task. |
| PROGRAMID | PROGRAMS_V1_VIEW| Cardinality is one-to-one.<br /> A program is associated with one program. |


© Merative US L.P. 2016, 2023.  Merative is a trademark of Merative US L.P. in the United States and other countries.
