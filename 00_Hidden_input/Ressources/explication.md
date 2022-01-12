# 00_unsecure_email

# *How to find it*

go to this page http://10.12.100.35/?page=recover#
after that you can inspect element and find an element which contains email, 
modify it respecting the max length. submit a request and you will find the flag.

# *How should secure it*

- Return a consistent message for both existent and non-existent accounts.
- Implement protections against automated submissions such as CAPTCHA, rate-limiting or other controls.
- Employ normal security measures, such as SQL Injection Prevention methods and Input Validation.

# *SRC*

https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html
https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html