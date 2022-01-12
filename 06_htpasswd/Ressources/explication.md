# 06_htpasswd

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


we go to http://10.12.100.35/whatever/ and download a file called htpasswd,
inside we will find root:8621ffdbc5698829397d97767ac13db3,
so we will decode it in md5 hash to find a word **dragon** (password)
after that we will go to /admin in the url, and type the user & password
to get the flag.

The flag is : d19b4823e0d5600ceed56d5e896ef328d7a2b9e7ac7e80f4fcdb9b10bcb3e7ff.

# *How should secure it*

make sure to delete or protect every file not useful for the website and that can be access.



