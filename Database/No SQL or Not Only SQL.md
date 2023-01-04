###  Overview
* Untill the emergence of NoSQL, SQL databases were the primary method to store the data in many organisation.
* However, due to some weaknesses in these databases and huge explosion in the unstructured and semi structured data led to the acute need for a new type of databse technology

### Why NoSQL?

Lets take a example and check how NoSQL is different from SQL

Consider a E-commerce company that needs to store its information in database

How would a RDBMS solution look like for above problem?

![[Pasted image 20230103082832.png]]

As  you can see this is how we store the data in RDBMS. Suppose a manager now needs to get the report of profit for a particular product or Order.

Now we should run a query which fetches the data from all these tables using joins. And we get the results in new tabular form where we get the results from 3 different tables

| Order_ID | Name | Category | Sales | Profit |
| --- | --- | --- |---| --- | 
| T-103 | JBL | Tech | 2400 | 500

But as the size of the data increses, joins become computationally expensive

Now lets see how the same data can be stored in NoSQl specifically in Document Based DB
```Mongo
{
"_id : ObjectID("5kvbfkb55dvdf5v)",
"Order_Id": "T-103",
"NAme" : 2400,
"Profit" : 760
}
```

As the above all the information is stored in single record. Its in a denormalized way means everything is availabel in one place. And to fetch the data I don't need to go to multiple place.I can fetch easily from one place which makes the query faster.

Its realy helpfull when we have huge amount of data.


* The structure that you see above is the document structure or JSON structure
* The elements are mapped in the form of "Key: value" pair

### 2 major challenges of SQL are :

*  Necessity of Joins
* Lack of flexible Schema : SQL database require you to maintain all field values explicitly even if you don't need them for a particular record.

### SQL vs NOSQL

|  SQL | NoSQL |
| --- | --- |
| * SQL databases store information in form of tables with fixed schema | * NOSQL databases follow a dynamic schema|
| SQL databases are generally scaled vertically by increasing the CPU and RAM to increase the power of existing database | NOSQL databases are more suitable for Horizontal scaling |
| It is mostly used when there is transactional need | NOSQL supports few of the transactional needs | 
| SQL databases are designed to handle advanced querying requirements | NOSQL databases are utilised to handle complex data and they can be scaled as per requiremnet |

For more details refer : [ https://www.mongodb.com/nosql-explained]

## BASE property of NoSQL

The 3 principles are :
 1) Basic availability
 2) Soft state
 3) Eventual consistency


