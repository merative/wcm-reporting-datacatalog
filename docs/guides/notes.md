

This section describes data available for notes.

## NOTES_V1_VIEW
This view groups attributes that relate to a note such as the priority, subject, status and content text for
the note. Use this view to create notes reports.

| Attribute      | Description    | Domain definition | Character size | Nulls allowed |
| :-------------- |:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|:------ |:------ |:--------------|
| NOTEID| Identifier for a record.       |  Int 64| | NO   |
| ADDEDBY| The identity of user who created the note.     | Character| 256| NO   |
| ADDEDBYFULLNAME| First name and last name of the user who created the note.       | Character| 524| YES  |
| ADDEDBYROLE| Role of the user who created the note. | Character| 200| YES  |
| PRIORITY| Priority of the note. | Character| 20| YES  |
| SUBJECT| Subject of the note.  | Character| 480| YES  |
| NOTECONTEXT| Context that indicates were the note was added, General, Assessment.    | Character| 20| YES  |
| STATUS| Current status of the note, Draft, Ready for Review, Final, Discarded, or Canceled. When a Draft or Ready for Review note is deleted, its status changes to Discarded. | Character| 20| YES  |
| NOTETYPE| Type of the note.     | Character| 50| YES  |
| DURATION| Duration of the note, in minutes.     |  Int 32| | YES  |
| MODIFIEDDATETIME| Date and time the note was last updated.       | Date Time| | YES  |
| CLIENTREFERENCE| Unique reference number that identifies the client in the application.  | Character| 200| YES  |
| NOTE| Note text.   | Character| 32592| YES  |
| DISCARDREASON| Reason for deleting a Draft or Ready for Review note.   | Character| 512| YES  |
| MODIFIEDBY| The identity of user who last modify the note. | Character| 524| YES  |
| SENSITIVE| Indicates whether the note contains sensitive client information.| Character| 1| YES  |
| CREATEDDATETIME| Date and time that the note was created.       | Date Time| | YES  |
| INGESTIONTIME| Date and time the record was ingested, supports change data capture.    | Date Time| | NO   |

### Links to other data



| Attribute        | Joins to     | Cardinality |
|:-----------------|:----------------------|:-----------------------------------------------------------------------------------------|
| CLIENTREFERENCE  | CLIENTS_V1_VIEW.      | Client reference joins to a client.<br/> A client is associated with zero-to-many notes. |
| ADDEDBY | USERS_V1_VIEW.        | Added-by joins to a user.<br/> A user is associated with zero-to-many notes.    |
| MODIFIEDBY       | USERS_V1_VIEW.        | Modified-by joins to one user.<br/> A user is associated with zero-to-many notes|
| NOTEID  | NOTE_COMMENTS_V1_VIEW | A note is associated with zero-to-many comments.       |
