### Definition of SQL
1) It is language used to manipulate data in relational databases

### SQL Statement Classes or Types of SQL
1) SQL Schema statements or DDL(Data Definition lang) : 
	 This is used to define the data in the database
2) SQL data Staements or DML (Data manipulation lang) :
	 This is used to manipulate the data
3) SQL transaction statements or DQL (Data Query Language)

### Data Definition Language:

CREATE :

This is used to create the table

```sql
CREATE TABLE corporation (
corp_id SAMLLINT,
name varchar(30)
CONSTRAINT pk_corporation PRIMARY KEY (corp_id)
)
```

INSERT :
This is used to add the data to the table

```sql
INSERT INTO corporation(corp_id, name) VALUES (27, "Danaher")
```

