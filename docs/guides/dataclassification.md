

## Domain definitions

The following table describes the domain definitions or data types for Merative Integrated Care data.   

Every attribute in every view has a data type. The domain definition or data type influences the range of values that the column can have and the set of operators and functions that apply to it.

The data types are required to consume data through your BI tool, database federation or client download program.


| Domain definition | Description |
| :-------------- | :------ |
| Character| Varying-length character strings with a maximum length of N|
| Int 16 | Small integers|
| Int 32 | Large integers|
| Int 64 | Big integers|
| Date | A date only, for example 12 March 2022 in UTC|
| Date Time | A date and time in UTC|
| Decimal fixed-point | A decimal number with fixed decimal places.|
| Double floating-point| A double-precision floating-point number.|
| Decimal floating-point| A large decimal number with decimal places.|

## Cardinality and joining to other data
Cardinality defines the possible number of occurrences in one entity which is associated with the number of occurrences in another. For example, ONE client has MANY program enrollments. The entity client and program enrollments are inter-connected with a one-to-many relationship.

The three common cardinal relationships are one-to-one, one-to-many, and many-to-many.


| Generic cardinality | Description |  subtypes  |
| :-------------- | :------ |:------ |
| one-to-one| The one-to-one (1:1) relationship defines the fact that one row in a table relates to exactly one row in a second table. | one-to-one, one-to-[zero-or-one] |
| one-to-many | The one-to-many relationship means that one row in a database table relates to many rows in a second table. It is also known as a Primary Key-Foreign Key relationship because it uses primary keys and foreign keys to enforce this relationship. | one-to-many, one-to-[zero-or-many]|
| many-to-many | A many-to-many relationship refers to the relationship between two entities X and Y in which X may be linked to many instances of Y and vice versa. Note that a many-to-many relationship is split into a pair of one-to-many relationships in a physical design. | Cardinality is one-to-many. An alert joins to 1 user. |




## Data types for retrieval from table columns

The following table summarizes the mappings of domain definitions above to Java data types for ResultSet.getXXX methods in JDBC programs.

This table is given as an example for clients who craft a client download program to copy data into a clients local datastore.  The Java programming language is used in this example, however clients can use their local preferring programming language.

The following table summarizes the mappings of data types to Java data types for ResultSet.getXXX methods in JDBC programs.


| Domain definition | Recommended Java data type or Java object type | Other|
| :-------------- | :------ |:------ |
| Character| String |Varying-length character strings with a maximum length of N|
| Int 16 | 	short   | 	short, byte, long, float, double, java.math.BigDecimal, boolean, java.lang.String|
| Int 32 |  	int   |	short, byte, long, float, double, java.math.BigDecimal, boolean, java.lang.String|
| Int 64 | long 	  | int, short, byte, float, double, java.math.BigDecimal, boolean, java.lang.String|
| Date   |  java.sql.Date| 	java.sql.String, java.sql.Date, java.sql.Time, java.sql.Timestamp|
| Date Time | java.sql.Timestamp| 	java.sql.String, java.sql.Date, java.sql.Time, java.sql.Timestamp|
| Decimal fixed-point   | java.math.BigDecimal |	 float, double, java.math.BigDecimal|
| Double floating-point | double |	 float, java.math.BigDecimal|
| Decimal floating-point| java.math.BigDecimal |	 float, double, java.math.BigDecimal|


© Merative US L.P. 2016, 2023.  Merative is a trademark of Merative US L.P. in the United States and other countries.
