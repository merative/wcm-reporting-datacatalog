

This section describes data available for notes.

Notes can be recorded about clients in different places of the application to address different aspects of client care. If note types are configured to be editable by the care team, you can save a note that you want to return to later as a draft or ready for review version, or as the final version.

## NOTES_V1_VIEW
This view groups attributes that relate to a note such as the priority, subject, status and content text for
the note. Use this view to create notes reports.

| Attribute        | Description                                                                                                                                                            | Domain definition | Character size | Nulls allowed |
|:-----------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|:------------------|:---------------|:--------------|
| CLIENTREFERENCE  | Unique reference number that identifies the client in the application.                                                                                                 | Character         | 200            | YES           |
| NOTEID           | Identifier for a record.                                                                                                                                               | Int 64            | ---            | NO            |
| SUBJECT          | Subject of the note.                                                                                                                                                   | Character         | 480            | YES           |
| NOTECONTEXT      | Context that indicates were the note was added from, for example,  general, assessment, barrier or service.                                                            | Character         | 20             | YES           |
| STATUS           | Current status of the note, Draft, Ready for Review, Final, Discarded, or Canceled. When a Draft or Ready for Review note is deleted, its status changes to Discarded. | Character         | 20             | YES           |
| NOTETYPE         | The note type describes the nature of the note for example, general, private or care plan update.                                                                      | Character         | 50             | YES           |
| DURATION         | How long in minutes the activity took.                                                                                                                                 | Int 32            | ---            | YES           |
| NOTE             | The text of the note.                                                                                                                                                  | Character         | 32592          | YES           |
| SENSITIVE        | Indicates whether the note contains sensitive information.                                                                                                             | Character         | 1              | YES           |
| ADDEDBY          | The identity of user who created the note.                                                                                                                             | Character         | 256            | NO            |
| ADDEDBYFULLNAME  | First name and last name of the user who created the note.                                                                                                             | Character         | 524            | YES           |
| ADDEDBYROLE      | Role of the user who created the note.                                                                                                                                 | Character         | 200            | YES           |
| CREATEDDATETIME  | Date and time that the note was created.                                                                                                                               | Date Time         | ---            | YES           |
| DELETIONREASON   | Reason for deleting a Draft or Ready for Review note.                                                                                                                  | Character         | 512            | YES           |
| MODIFIEDBY       | The identity of user who last modified the note.                                                                                                                       | Character         | 524            | YES           |
| MODIFIEDDATETIME | Date and time the note was last updated.                                                                                                                               | Date Time         | ---            | YES           |
| INGESTIONTIME    | Date and time the record was ingested, supports change data capture.                                                                                                   | Date Time         | ---            | NO            |

### Links to other data

| Attribute        | Joins to              | Cardinality                                                                        |
|:-----------------|:----------------------|:-----------------------------------------------------------------------------------|
| CLIENTREFERENCE  | CLIENTS_V1_VIEW       | Cardinality is one-to-many. <br/> A client is associated with zero-to-many notes.  |
| STATUSEUPDATEDBY | USERS_V2_VIEW         | Cardinality is one-to-many.  <br/>  A user is associated with zero-to-many  notes. |
| MODIFIEDBY       | USERS_V2_VIEW         | Cardinality is one-to-many. <br/> A user is associated with zero-to-many notes.    |
| NOTEID           | NOTE_COMMENTS_V1_VIEW | Cardinality is one-to-many. <br/> A note is associated with zero-to-many comments. |

## NOTE_COMMENTS_V1_VIEW
This view groups attributes that relate to a note comment such as the author, status and content text for
the comment. Use this view to create note comments reports.

| Attribute     | Description                                                                                        | Domain definition | Character size | Nulls allowed |
|:--------------|:---------------------------------------------------------------------------------------------------|:------------------|:---------------|:--------------|
| NOTEID        | Identifier for a record.                                                                           | Int 64            | ---            | NO            |
| NOTETYPE      | The note type describes the nature of the note, for example, general, private or care plan update. | Character         | 50             | YES           |
| POSITION      | Order that the comments were added to the note, for example, I, 2, 3, 4.                           | Character         | 512            | NO            |
| CREATEDBY     | The first name and last name of the user who created the comment.                                  | Character         | 524            | NO            |
| CONTENT       | Note comment text.                                                                                 | Character         | 1              | YES           |
| CREATIONDATE  | Date and time that the comment was added to the note.                                              | Date Time         | ---            | NO            |
| INGESTIONTIME | Date and time the record was ingested, supports change data capture.                               | Date Time         | ---            | NO            |

### Links to other data

| Attribute | Joins to      | Cardinality                                                                       |
|:----------|:--------------|:----------------------------------------------------------------------------------|
| NOTEID    | NOTE_V1_VIEW  | Cardinality is one-to-one. <br/> A note identifieris associated with one note.    |
| CREATEDBY | USERS_V2_VIEW | Cardinality is one-to-one.  <br/>  A user identifier is associated with one user. |


© Merative US L.P. 2016, 2023.  Merative is a trademark of Merative US L.P. in the United States and other countries.
