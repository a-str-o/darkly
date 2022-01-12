# 03_unsecure_admin_cookie

Unsecure sql request form in the page: http://10.12.100.35

# *How to find it*

Go on the page mentionned before. Inspect element and find the cookies I_am_admin. 

We can see his md5 value which corresponds to false.

I_am_admin= **false** -> 68934a3e9455fa72420237eb05902327

# *how to get the flag*

We are just going to look with my md5 for the value of true in md5.

**true** -> ft_md5 -> b326b5062b2f0e69046810717534cb09

Then we can refresh the browser which will create an alert and print:

Good job! Flag : df2eb4ba34ed059a1e3e89ff4dfc13445f104a1a52295214def1c4fb1693a5c3

And here we are now we are admin on the website.

# *How should secure it*

do not put critical information in cookies, or crypt it very well with good hash.