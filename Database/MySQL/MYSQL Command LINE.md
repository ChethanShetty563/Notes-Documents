
### 1) How to go to Mysql prompt?

	Press Windows button and search for Mysql

### 2) Looging in using root account

```sql
mysql -u root -p;
```

After it will ask for the password.

### 3) List the databases that are present

```sql
show databses;
```

### 4) Selecting database or specifying that DB that you want to use
```sql
use sakila;

or you can specify while logging in as well

mysql -u root -p sakila;
This will save you from having to type `use sakila;`
```

### 5) Get the current time and date;
```sql
SELECT now();
```
now() is builtin function that return current date and time