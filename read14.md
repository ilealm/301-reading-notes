#  Database Normalization Explained in Simple English  

> Database normalization is a process used to organize a database into tables and columns.  

* The main idea with this is that a table should be about a specific topic and only supporting topics included. 
* Having the table serve many purposes introduces many of the challenges; namely, data duplication, data update issues, and increased effort to query data.
* As tables satisfy each successive database normalization form, they become less prone to database modification anomalies and more focused toward a sole purpose or topic.

## Reasons for Database Normalization
1. To minimize duplicate data (1st | 1NF)
1. The second is to minimize or avoid data modification issues (2nd | 1NF)
1. To simplify queries (3rd | 3NF)

## Data Duplication and Modification Anomalies( 1st | 1NF)
* The information is stored in a relational table with each column containing atomic values. There are no repeating groups of columns.
* Duplicated information presents two problems:

1. It increases storage and decrease performance.
1. It becomes more difficult to maintain data changes.
* These situations are **_modification_** anomalies. Database normalization fixes them. 

#### There are three modification anomalies that can occur: (2nd | 1NF)
* The table is in first normal form and all the columns depend on the table’s primary key.

_Insert Anomaly_
* There are facts we cannot record until we know information for the entire row.  
* In order to create the record, we need provide a primary key. 

_Update Anomaly_
* In this case we have the same information in several rows, then there are multiple updates that need to be made. 

_Deletion Anomaly_
* Deletion of a row causes removal of more than one set of facts. 

## Search and Sort Issues (3rd | 3NF)

* The last reason we’ll consider normalization is making it easier to search and sort data. 
* The table is in second normal form and all of its columns are not transitively dependent on the primary key