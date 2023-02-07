
### 1) List all the databases available
```mongodb
show dbs;
```

### 2) Create a new database / Switch the database
```mongodb
use Banking;
```
It will create a database and switch to it

Note : The new db won't get displayed in "show dbs" command untill the data gets added

```monogdb
db
```
The above command will display the db that we are currently working

### 3) Drop the databases

Goto the database that you want to drop by "use banking;" and follow the below command

```mongo
db.dropDatabase()
```


