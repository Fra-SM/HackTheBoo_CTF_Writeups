## **Cult Meeting**

This was the first reversing challenge. Simply run `strings` against the file we are provided with and scroll through the output to find a password.

![CultMeeting](/Screenshots/REV_1.png)

At this point, just spawn the docker instance, connect to it using `nc IP PORT` and enter the password to get the flag.

#### HTB{1nf1ltr4t1ng_4_cul7_0f_str1ng5}