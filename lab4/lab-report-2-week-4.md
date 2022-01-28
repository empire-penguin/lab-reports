[Main Page](https://empire-penguin.github.io/empire-penguin/)

***

Lab Report 2
============

Incremental Programming and Debugging & When Tests Accumulate. 
------------------------------------

This lab consisted of testing various markdown files to see if our
markdown parser was capable of performing the right interpretation. 

We began by forking the repo found [here](https://github.com/ucsd-cse15l-w22/markdown-parse) and testing to see if our 
test file is successfully parsed.

The inital fork contained the following java and text files:
![testfiles](./images/inital.png)

And successfully created the output 
```
[https://something.com, some-page.html]
```
We then created the following test files:

![testfiles](./images/test-files.png)

After attempting to parse [test2-file.md](https://github.com/empire-penguin/markdown-parse/blob/ea4c83fbd96a476233b95048aa12cb38e3113395/test2-file.md) we recieved the following symptom:
```
Exception in thread "main" java.lang.OutOfMemoryError: Java heap space
        at java.base/java.lang.StringLatin1.newString(StringLatin1.java:769)
        at java.base/java.lang.String.substring(String.java:2709)
        at MarkdownParse.getLinks(MarkdownParse.java:17)
        at MarkdownParse.main(MarkdownParse.java:25)
```

This symptom was most probabily caused by an infinite loop in light of the out of memory error and 
that the output took a substancial amount of time before throwing the error.

![first-fix](./images/first-fix.png)

