## **Juggling Facts**

Fourth web challenge. We are presented with a page that shows different kinds of "facts". By clicking on *Secret Facts* we can see that only admin has access to those.

![JugglingFacts](/Screenshots/WEB_4.png)

Once again, we can use Burp Proxy to intercept the requests and notice that there's only one parameter called *type* which gets passed in the request body. This is the type of facts we ask for.
Now, we can either spend hours and hours staring at the source code *(ehm...)* looking for SQL injections, file inclusions or whatever, or we can just notice the following lines.

![JugglingFacts](/Screenshots/WEB_4.1.png)
![JugglingFacts](/Screenshots/WEB_4.2.png)

With a bit of research, we can discover that PHP has a feature called *type juggling*, which can cause vulnerabilities, and guess that's what we're dealing with in this case, as suggested from the title of the challenge. We can then exploit the loose comparisons of the switch statement and send something different (a true boolean value in this case) as a payload in order to obtain our flag.

![JugglingFacts](/Screenshots/WEB_4.3.png)

#### HTB{sw1tch_stat3m3nts_4r3_vuln3r4bl3!!!}