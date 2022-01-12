# 05_referer © BornToSec

Here is the located page for having the flag :
http://10.12.100.35/?page=e43ad1fdc54babe674da7c7b8f0127bde61de3fbe01def7d00f151c2fcca6d1c

# *How to find it*

Go on the page mentionned before. Inspect element and then go in the main content and read the commentary! 
You'll find after this one a commentary saying that you have to come from the NASA and from the ft_bornToSec browser. 
We will use this commande :

__curl -s -A 'ft_bornToSec' --referer "https://www.nsa.gov/" "http://10.12.100.35/?page=e43ad1fdc54babe674da7c7b8f0127bde61de3fbe01def7d00f151c2fcca6d1c" > flag.html && cat flag.html | grep flag__

And you will see the result appearing :

The flag is : f2a29020ef3132e01dd61df97fd33ec8d7fcd1388cc9601e7db691d17d4d6188

# *How should secure it*

- Filter input on arrival filter as strictly as possible based on what is expected or valid input.
- Encode data on output, encode the output to prevent it from being interpreted as active content.
- Check the request headers in the server side.