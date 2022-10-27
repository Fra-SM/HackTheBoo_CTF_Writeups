## **Downgrade**

Fifth forensics challenge. This time we are provided with some logs that we have to analyze in order to answer some questions. The ideal tool to solve this challenge would be Windows Event Viewer, but we can just use something online like [Gigasheet](https://www.gigasheet.com/) and upload our files there. The first question asked to find the log that contained login/logoff events, and *Security* is the answer to that.

![Downgrade](/Screenshots/FORENSICS_5.png)

The next 2 questions can be answered by researching the web.

![Downgrade](/Screenshots/FORENSICS_5.1.png)
![Downgrade](/Screenshots/FORENSICS_5.2.png)

The fourth question asked to identify the unusual authentication package among the logon events. We can build a filter for rows with EventID = 4624 and then group them by authentication package. We can see that NTLM stands out among the others, so that's the answer we're looking for.

![Downgrade](/Screenshots/FORENSICS_5.3.png)
![Downgrade](/Screenshots/FORENSICS_5.5.png)

Finally, the last question asked for the timestamp of the suspicious login event. We can filter for rows with EventID = 4624 and EventData/AuthenticationPackage = NTLM. Notice that there was a successful login as *Administrator* from a workstation named *kali*. At this point we just have to copy the value of the timestamp field, enter that (taking care of the format) as the answer and get greeted with the flag.

![Downgrade](/Screenshots/FORENSICS_5.6.png)
![Downgrade](/Screenshots/FORENSICS_5.4.png)

#### HTB{4n0th3r_d4y_4n0th3r_d0wngr4d3...}