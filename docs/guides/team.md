

This section describes data available for teams, team members and users.  

These views groups attributes that relate to a users details, such as their login id,  which workspaces they have access to, what team role they are assigned, when they last logged in to the application and whether they are a member of a client's team.  


## TEAM_MEMBERS_V2_VIEW

<br/> ```TEAM_MEMBERS_V1_VIEW``` is deprecated so use this view instead. The attribute previously named ```ROLENAME``` has been renamed to ```DEFAULTWORKSPACE``` .

This view groups attributes that relate to a client's team members and their role on the team. If additional roles are added for a team member who is already on the client's team, their previous role is end dated and a new instance of that role is created with a new start date. External users that have no email address will be automatically given the following email address to be stored as their login ID: <first 6 chararcters from the username column>.\<full name>@protectedapi.com.
<br/>Uniqueness is guaranteed by teamID and loginID. Team identifier could be repeated in the view, and user login identifier could be repeated in the view.


| Attribute               | Description                                                                                                                            | Domain definition     | Character size | Nulls allowed |
|:------------------------|:---------------------------------------------------------------------------------------------------------------------------------------|:----------------------|:---------------|:--------------|
| TEAMID                  | Identifier for a team record.                                                                                                          | Int 64                | ---            | NO            |
| LOGINID                 | A unique identifier for a user record. Typically an email address.                                                                     | Character             | 256            | NO            |
| TEAMMEMBERID            | Identifier for a team member.                                                                                                          | Int 64                | ---            | YES           |
| TEAMMEMBERSTARTDATE     | Date the team member was added to the team.                                                                                            | Date                  | ---            | YES           |
| TEAMMEMBERENDDATE       | Date the team member was removed from the team.                                                                                        | Date                  | ---            | YES           |
| FIRSTNAME               | User's given name.                                                                                                                     | Character             | 260            | YES           |
| SURNAME                 | User's last name.                                                                                                                      | Character             | 260            | YES           |
| TITLE                   | User's title. For example, Mr or Ms.                                                                                                   | Character             | 60             | YES           |
| FULLNAME                | User's first name and last name.                                                                                                       | Character             | 524            | YES           |
| USERSTATUS              | The status of the user's account. The status can be active, suspended, or closed.                                                      | Character             | 1850           | NO            |
| ACCOUNTENABLED          | Shows if the account is active or suspended. Users whose accounts are suspended cannot sign in to Merative Integrated Care.             | Character             | 1              | NO            |
| CREATIONDATE            | Date the user's account was created.                                                                                                   | Date                  | ---            | NO            |
| LASTSUCCESSLOGIN        | Date on which the user last logged in successfully.                                                                                    | Date Time             | ---            | YES           |
| DEFAULTWORKSPACE        | User's default workspace, for example, Care Team, Administrator, and so on.                                                            | Character             | 200            | NO            |
| CORE                    | Indicates if the user is a member of the core care team.                                                                               | Character             | 1              | YES           |
| FREQUENCY               | Frequency of the visits or meetings that the care team member has with the client.                                                     | Character             | 40             | YES           |
| DISTANCE                | Frequency of the visits or meetings that the care team member has with the client.                                                     | Double floating-point | ---            | YES           |
| DISTANCETYPE            | Distance type, in kilometers or miles.                                                                                                 | Character             | 40             | YES           |
| COMMENTS                | Comments about the care team member.                                                                                                   | Character             | 8000           | YES           |
| TEAMMEMBERTYPE          | Used to show only users who are care team members in dashboards and reports.                                                           | Character             | 100            | YES           |
| TEAMROLE                | Role of the care team member on the team. For example, care manager, nutritionist.                                                     | Character             | 100            | YES           |
| PRIMARYROLEIND          | Indicates if the care team member is responsible for the client’s care plan and programs.                                              | Character             | 1              | YES           |
| CAPACITY                | Maximum number of clients the care team member can safely and effectively manage when they have the primary role on the team.          | Int 32                | ---            | YES           |
| ISUSER                  | Can this care team member login to the application, values are Y or N.                                                                 | Character             | 1              | NO            |
| EXTERNALROLENAME        | Displays the user's external role, if configured.                                                                                      | Character             | 1024           | YES           |
| SECURITYROLE            | Displays a comma separated list of the user's assigned security roles, for example, Care Team Standard Access, Full Access, and so on. | Character             | 1024           | NO            |
| INGESTIONTIME           | Date and time the record was ingested, supports change data capture.                                                                   | Date Time             | ---            | NO            |
| TEAMMEMBERROLESTARTDATE | Care team member’s role start date.                                                                                                    | Date                  | ---            | YES           |
| TEAMMEMBERROLEENDDATE   | Care team member’s role end date.                                                                                                      | Date                  | ---            | YES           |

### Links to other data


| Attribute | Joins to      | Cardinality                                                                  |
|:----------|:--------------|:-----------------------------------------------------------------------------|
| TEAMID    | TEAMS_V1_VIEW | Cardinality is one-to-one. <br/> A team member is associated with one team.  |
| LOGINID   | USERS_V2_VIEW | Cardinality is one-to-many. <br/> A team member is associated with one user. |


## TEAM_MEMBERS_V1_VIEW
 
This view is deprecated and will be removed in a future release. Please use ```TEAM_MEMBERS_V2_VIEW```. The attribute ```ROLENAME``` has been renamed to ```DEFAULTWORKSPACE```.

This view groups attributes that relate to a client's team members and their role on the team. If additional roles are added for a team member who is already on the client's team, their previous role is end dated and a new instance of that role is created with a new start date.
<br/>Uniqueness is guaranteed by teamID and loginID. Team identifier could be repeated in the view, and user login identifier could be repeated in the view.


| Attribute               | Description                                                                                                                            | Domain definition     | Character size | Nulls allowed |
|:------------------------|:---------------------------------------------------------------------------------------------------------------------------------------|:----------------------|:---------------|:--------------|
| TEAMID                  | Identifier for a team record.                                                                                                          | Int 64                | ---            | NO            |
| LOGINID                 | A unique identifier for a user record. Typically an email address.                                                                     | Character             | 256            | NO            |
| TEAMMEMBERID            | Identifier for a team member.                                                                                                          | Int 64                | ---            | YES           |
| TEAMMEMBERSTARTDATE     | Date the team member was added to the team.                                                                                            | Date                  | ---            | YES           |
| TEAMMEMBERENDDATE       | Date the team member was removed from the team.                                                                                        | Date                  | ---            | YES           |
| FIRSTNAME               | User's given name.                                                                                                                     | Character             | 260            | YES           |
| SURNAME                 | User's last name.                                                                                                                      | Character             | 260            | YES           |
| TITLE                   | User's title. For example, Mr or Ms.                                                                                                   | Character             | 60             | YES           |
| FULLNAME                | User's first name and last name.                                                                                                       | Character             | 524            | YES           |
| USERSTATUS              | The status of the user's account. The status can be active, suspended, or closed.                                                      | Character             | 1850           | NO            |
| ACCOUNTENABLED          | Shows if the account is active or suspended. Users whose accounts are suspended cannot sign in to Merative Integrated Care.             | Character             | 1              | NO            |
| CREATIONDATE            | Date the user's account was created.                                                                                                   | Date                  | ---            | NO            |
| LASTSUCCESSLOGIN        | Date on which the user last logged in successfully.                                                                                    | Date Time             | ---            | YES           |
| ROLENAME                | User's security role, for example, Care Team,  Administrator, and so on.                                                               | Character             | 200            | NO            |
| CORE                    | Indicates if the user is a member of the core care team.                                                                               | Character             | 1              | YES           |
| FREQUENCY               | Frequency of the visits or meetings that the care team member has with the client.                                                     | Character             | 40             | YES           |
| DISTANCE                | Frequency of the visits or meetings that the care team member has with the client.                                                     | Double floating-point | ---            | YES           |
| DISTANCETYPE            | Distance type, in kilometers or miles.                                                                                                 | Character             | 40             | YES           |
| COMMENTS                | Comments about the care team member.                                                                                                   | Character             | 8000           | YES           |
| TEAMMEMBERTYPE          | Used to show only users who are care team members in dashboards and reports.                                                           | Character             | 100            | YES           |
| TEAMROLE                | Role of the care team member on the team. For example, care manager, nutritionist.                                                     | Character             | 100            | YES           |
| PRIMARYROLEIND          | Indicates if the care team member is responsible for the client’s care plan and programs.                                              | Character             | 1              | YES           |
| CAPACITY                | Maximum number of clients the care team member can safely and effectively manage when they have the primary role on the team.          | Int 32                | ---            | YES           |
| ISUSER                  | Can this care team member login to the application, values are Y or N.                                                                 | Character             | 1              | NO            |
| EXTERNALROLENAME        | Displays the user's external role, if configured.                                                                                      | Character             | 1024           | YES           |
| SECURITYROLE            | Displays a comma separated list of the user's assigned security roles, for example, Care Team Standard Access, Full Access, and so on. | Character             | 1024           | NO            |
| INGESTIONTIME           | Date and time the record was ingested, supports change data capture.                                                                   | Date Time             | ---            | NO            |
| TEAMMEMBERROLESTARTDATE | Care team member’s role start date.                                                                                                    | Date                  | ---            | YES           |
| TEAMMEMBERROLEENDDATE   | Care team member’s role end date.                                                                                                      | Date                  | ---            | YES           |

### Links to other data


| Attribute | Joins to      | Cardinality                                                                  |
|:----------|:--------------|:-----------------------------------------------------------------------------|
| TEAMID    | TEAMS_V1_VIEW | Cardinality is one-to-one. <br/> A team member is associated with one team.  |
| LOGINID   | USERS_V1_VIEW | Cardinality is one-to-many. <br/> A team member is associated with one user. |



## TEAMS_V1_VIEW
This view groups attributes that relate to a client and their teams. Use this view to identify which teams are associated with which clients.

| Attribute       | Description                                                            | Domain definition | Character size | Nulls allowed |
|:----------------|:-----------------------------------------------------------------------|:------------------|:---------------|:--------------|
| TEAMID          | Identifier for a record.                                               | Int 64            | ---            | NO            |
| CLIENTREFERENCE | Unique reference number that identifies the client in the application. | Character         | 200            | YES           |
| STATUS          | Status of the record, open or closed.                                  | Character         | 40             | NO            |
| INGESTIONTIME   | Date and time the record was ingested, supports change data capture.   | Date Time         | ---            | NO            |

### Links to other data

| Attribute | Joins to |Cardinality |
| :-------------- | :------ |:------ |
| CLIENTREFERENCE| CLIENTS_V1_VIEW | Cardinality is one-to-one. <br/>  A client identifier is associated with one client.|
| TEAMID| TEAM_MEMBERS_V2_VIEW | Cardinality is one-to-many. <br/> A team has zero-to-many team members.|


## USERS_V2_VIEW

<br/> ```USERS_V1_VIEW``` is deprecated so use this view instead. The attribute previously named ```ROLENAME``` has been renamed to ```DEFAULTWORKSPACE``` .

This view groups attributes that relate to users in Merative Integrated Care, for example, user's name, status, workspaces, and security roles. Users that are members of a provider organization will have a provider ID. External users that have no email address will be automatically given the following email address to be stored as their login ID: <first 6 characters from the username column>.\<full name>@protectedapi.com.

| Attribute        | Description                                                                                                                            | Domain definition | Character size | Nulls allowed |
|:-----------------|:---------------------------------------------------------------------------------------------------------------------------------------|:------------------|:---------------|:--------------|
| LOGINID          | A unique identifier for a user record. Typically an email address.                                                                     | Character         | 256            | NO            |
| FIRSTNAME        | User's given name.                                                                                                                     | Character         | 260            | YES           |
| SURNAME          | User's last name.                                                                                                                      | Character         | 260            | YES           |
| TITLE            | User's title. For example, Mr or Ms.                                                                                                   | Character         | 60             | YES           |
| FULLNAME         | User's first name and last name.                                                                                                       | Character         | 524            | YES           |
| USERSTATUS       | The status of the user's account. The status can be Active, Suspended, or Closed.                                                      | Character         | 100            | NO            |
| ACCOUNTENABLED   | Shows if the account is active or suspended. Users whose accounts are suspended cannot sign in to Merative Integrated Care.             | Character         | 1              | NO            |
| CREATIONDATE     | Date the user's account was created.                                                                                                   | Date              | ---            | NO            |
| LASTSUCCESSLOGIN | Date on which the user last logged in successfully.                                                                                    | Date Time         | ---            | YES           |
| DEFAULTWORKSPACE | User's default workspace, for example, Care Team, Administrator, and so on.                                                            | Character         | 200            | NO            |
| CAPACITY         | Maximum number of clients the team member can safely and effectively manage when they have the primary role on the team.               | Int 32            | ---            | YES           |
| WORKSPACES       | Displays a comma-separated list of the user's assigned workspaces.                                                                     | Character         | 1024           | YES           |
| EXTERNALROLENAME | Displays the user's external role, if configured.                                                                                      | Character         | 1024           | YES           |
| SECURITYROLE     | Displays a comma separated list of the user's assigned security roles, for example, Care Team Standard Access, Full Access, and so on. | Character         | 1024           | NO            |
| INGESTIONTIME    | Date and time the record was ingested, supports change data capture.                                                                   | Date Time         | ---            | NO            |
| PROVIDERID       | Identifier for a provider user. NULL if user is not a provider user.                                                                   | Int 64            | ---            | YES           |

### Links to other data

Any table with a `LOGINID` can link to this table.  This table can link to any table with a `LOGINID`, one example is included below.  

Please note that other data sets may not always use a field named `LOGINID`  as the key to link to `USERS_V2_VIEW`.  Sometimes more descriptive attribute names are used, for example, `Created By/Updated By/Registered By`,  to link to  `USERS_V2_VIEW.LOGINID`.

| Attribute  | Joins to             | Cardinality                                                                        |
|:-----------|:---------------------|:-----------------------------------------------------------------------------------|
| LOGINID    | TEAM_MEMBERS_V2_VIEW | Cardinality is zero-to-many. <br/> A user is associated with zero to many teams.   |
| PROVIDERID | PROVIDERS_V1_VIEW    | Cardinality is zero-to-one. <br/> A user is associated with zero or one providers. |


## USERS_V1_VIEW

<br/> This view is deprecated and will be removed in a future release. Please use ```USERS_V2_VIEW```. The attribute ```ROLENAME``` has been renamed to ```DEFAULTWORKSPACE```.

This view  groups attributes that relate to users who are not in a client's team, but might have interacted with the client. For example, a user who assigned a program to the client.

| Attribute        | Description                                                                                                                            | Domain definition | Character size | Nulls allowed |
|:-----------------|:---------------------------------------------------------------------------------------------------------------------------------------|:------------------|:---------------|:--------------|
| LOGINID          | A unique identifier for a user record. Typically an email address.                                                                     | Character         | 256            | NO            |
| FIRSTNAME        | User's given name.                                                                                                                     | Character         | 260            | YES           |
| SURNAME          | User's last name.                                                                                                                      | Character         | 260            | YES           |
| TITLE            | User's title. For example, Mr or Ms.                                                                                                   | Character         | 60             | YES           |
| FULLNAME         | User's first name and last name.                                                                                                       | Character         | 524            | YES           |
| USERSTATUS       | The status of the user's account. The status can be Active, Suspended, or Closed.                                                      | Character         | 100            | NO            |
| ACCOUNTENABLED   | Shows if the account is active or suspended. Users whose accounts are suspended cannot sign in to Merative Integrated Care.             | Character         | 1              | NO            |
| CREATIONDATE     | Date the user's account was created.                                                                                                   | Date              | ---            | NO            |
| LASTSUCCESSLOGIN | Date on which the user last logged in successfully.                                                                                    | Date Time         | ---            | YES           |
| ROLENAME         | User's security role, for example, Care Team,  Administrator, and so on.                                                               | Character         | 200            | NO            |
| CAPACITY         | Maximum number of clients the team member can safely and effectively manage when they have the primary role on the team.               | Int 32            | ---            | YES           |
| WORKSPACES       | Displays a comma-separated list of the user's assigned workspaces.                                                                     | Character         | 1024           | YES           |
| EXTERNALROLENAME | Displays the user's external role, if configured.                                                                                      | Character         | 1024           | YES           |
| SECURITYROLE     | Displays a comma separated list of the user's assigned security roles, for example, Care Team Standard Access, Full Access, and so on. | Character         | 1024           | NO            |
| INGESTIONTIME    | Date and time the record was ingested, supports change data capture.                                                                   | Date Time         | ---            | NO            |

### Links to other data

Any table with a `LOGINID` can link to this table.  This table can link to any table with a `LOGINID`, one example is included below.  

Please note that other data sets may not always use a field named `LOGINID`  as the key to link to `USERS_V1_VIEW`.  Sometimes more descriptive attribute names are used, for example, `Created By/Updated By/Registered By`,  to link to  `USERS_V1_VIEW.LOGINID`.

| Attribute | Joins to             | Cardinality                                                                      |
|:----------|:---------------------|:---------------------------------------------------------------------------------|
| LOGINID   | TEAM_MEMBERS_V1_VIEW | Cardinality is zero-to-many. <br/> A user is associated with zero to many teams. |


© Merative US L.P. 2016, 2023.  Merative is a trademark of Merative US L.P. in the United States and other countries.
