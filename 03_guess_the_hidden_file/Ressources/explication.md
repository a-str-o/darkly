# 03_guess_the_hidden_file

we want to find the good README.md which is hiding here in this URL :
http://10.12.100.35/.hidden/

# *How to find it*

we used nmap in this vulnerability 'nmap -v -A 10.12.100.35'
and we get this :

PORT     STATE SERVICE VERSION
80/tcp   open  http    nginx 1.8.0
|_http-server-header: nginx/1.8.0
| http-robots.txt: 2 disallowed entries
|_/whatever /.hidden
|_http-title: BornToSec - Web Section
|_http-favicon: Unknown favicon MD5: E7D08792AE6EC9DBBF3CEBFB48EE4057
| http-methods:
|_  Supported Methods: GET HEAD POST
4242/tcp open  ssh     OpenSSH 5.9p1 Debian 5ubuntu1.7 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey:
|   1024 c1:03:76:40:29:e8:ab:f6:8a:9f:1c:71:6e:23:e0:58 (DSA)
|   2048 89:95:1a:c3:7c:1b:fc:3c:34:1d:76:d5:c9:fa:86:03 (RSA)
|_  256 09:86:1a:be:13:a5:a1:0c:7f:f7:55:50:ac:7a:c7:1a (ECDSA)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

when you go to the page mentionned before. you will see alot of README
hidden, approximately 26^3 = 17576 and only 1 contains the hidden flag.

so we will try to find the flag! with these steps :

__wget -m -r -linf -k -p -q -E -e robots=off http://10.12.100.35/.hidden__

- -m: This option turns on recursion and time-stamping.
- -r: Turn on recursive retrieving.
- -k: Conver Links, After the download is complete, convert the links in the document to make them suitable for local viewing. 
- -p: This option causes Wget to download all the files that are necessary to properly display a given HTML page.
- -E: adjust-extension this option will cause the suffix .html to be appended to the local filename.
- -e: Executes Command, robots=off causes it to ignore robots.txt for that domain
- -l: level option we given it **inf** infinite.

__find . -name "README" -exec cat {} + > res__

__cat res | grep [0-9]__


# *How should secure it*

make sure to delete or protect every file not useful for the website and that can be access.


# *SRC*
https://gist.github.com/Dammmien/4af98e05f9c51c2da007cc70d62bf562
https://stackoverflow.com/questions/27266972/regular-expression-doesnt-start-with-character-a-or-whitespace


