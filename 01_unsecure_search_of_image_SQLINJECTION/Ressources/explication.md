# 01_unsecure_search_of_image_SQLINJECTION

# *How to find it*

Unsecure sql request form in the page: http://10.12.100.35/index.php?page=searchimg

go to the page mentioned before, Whenever you are looking for an SQL injection you want to check if the page is injectable. 

You can type an SQL request responding true everytime such like this one:  '1 or 1=1' so it will return ALL rows from the "list_images" table.

Whenever we type this one we realise that this page can be injected. This is a major security problem.

we did these steps :

INFORMATION_SCHEMA provides access to database metadata, information about the MySQL server such as the name of a database or table, the data type of a column, or access privileges. Other terms that are sometimes used for this information are data dictionary and system catalog.

```sql
1 or 1=1 union select null,table_name from information_schema.tables
```
```sql
 1 or 1=1 union select null,group_concat(column_name) from information_schema.columns where table_name=0x6c6973745f696d61676573
```
 0x6c6973745f696d61676573 = list_images (hexadecimal)

```sql
 1 or 1=1 union select title,comment from list_images
```
then decrypt it with md5 and hash to sha256.

the flag is : f2a29020ef3132e01dd61df97fd33ec8d7fcd1388cc9601e7db691d17d4d6188.

# *How should secure it*

- Using ORM (object relationnal mapping) because they use parametrized statements even though they can let you construct the sql statement.
- Sanitize input: Check that supplied fields like email addresses match a regular expression, ensure that numeric or alphanumeric fields do not contain symbol characters, 
  reject (or strip) out whitespace and new line characters where they are not appropriate.

# *SRC*

https://www.hacksplaining.com/prevention/sql-injection