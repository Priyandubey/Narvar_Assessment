# Narvar_Assessment
Design and build a URL shortener service that can be used to shorten hundreds of millions of URLs - assume this will support a company like Narvar that provides tracking of packages to a few hundred top retailers. The service returns a short URL, given a longer URL; and similarly redirects to the longer URL when given the short URL. As part of your solution, provide a brief technical document that outlines some of your design decisions such as storage choices, choice of language, length of the short URL, rate limits etc. Extra points for providing your solution in docker / kubernetes setup.

Please have a look at the details and feel free to write/ call back in case of any queries?

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

Our System should be able to generate a unique url which is shorten form of the input url.

Lets say, we want to shorten the url "https://corp.narvar.com/" we would get some output like "https://shorturl/pQG12a".
In the above example "https://shorturl/" will always fixed and is called the base URL. So our main work here will be to generate the part "pQG12a"from the           input url i.e "https://corp.narvar.com/".
If we add both the base and the required String we will get the shorten URL. Lets give a template to the output as "base_url/<hash_value>"

We may have to shorten hundreds of millions of URLs lets say a billion of url. So we should be able to generate billions of the unique <hash_value>. If we use
62 characters(uppercase and lowercase alphabets and digits) to generate all possible <hash_value> of length 5, we would be able to generate 62^5 i.e 0.9 billion <hash_value> which is quite close to our expectation. 

Lets say this <hash_value> is always of fixed length i.e 5. We can randomly generate this <hash_value> and store it in the form of <ID,URL> in a list. Where ID will be the randomly generated <hash_value>. So when the user input the URL we generate the <hash_value> as the ID and store it in the list. While when we are typing the shorten_url in our browser we can search for the <hash_value> in the list and redirect to the URL.

A problem in the approach is we might generate same <hash_value> for different URL.
To overcome this hurdle we may store it in the database in the following way:-

```
lknefl
```

