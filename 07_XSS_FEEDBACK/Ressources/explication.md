# 07_XSS_FEEDBACK

Here is the located page for having the flag :
http://10.12.100.35/?page=feedback

# *How to find it*
If we inject a script tag in comment it will filter it.
and if we just type the word "script" into one the inputs the flag will appear.

# *How should secure it*

- Filter input on arrival filter as strictly as possible based on what is expected or valid input.
- Encode data on output, encode the output to prevent it from being interpreted as active content.

