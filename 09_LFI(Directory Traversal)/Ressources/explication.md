# 09_LFI(Directory Traversal)

# *How to find it*

We know that the pages are generated throught the url 'page=...';
We try to add '../' to see if we can find something in server;
We get many pop-ups with different messages make us to think to do with this technic;
We used add multiple '../' and 'etc/passwd' at the end.

- http://10.12.100.35/?page=../../../../../../../etc/passwd

# *How should secure it*

To avoid LFI and many other vulnerabilities, never trust user input. 
If you need to include local files in your website or web application code, 
use a whitelist of allowed file names and locations. 
Make sure that none of these files can be replaced by the attacker using file upload functions.



