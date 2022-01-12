# 08_Redirection

on all pages there is links of social media like this :

http://10.12.100.35/index.php?page=redirect&site=instagram

# *How to find it*

We will try to spoof the header function in order to get the proper redirection for the admin page :

http://10.12.100.35/index.php?page=redirect&site=admin // or anything

# *How should secure it*

- Sanitize data input in an HTTP request before reflecting it back, ensuring all data is validated, 
  filtered or escaped before echoing anything back to the user, such as the values of query parameters during searches.
- Use strong antivirus protection.

