## **Wrong Spooky Season**

This was the first forensics challenge. We are given a network traffic capture that we have to analyze. By opening it in Wireshark, we can see a lot of HTTP packets. We can just click on any of them, then click follow TCP stream and use the arrows at the bottom to skim through the various streams. It looks like some sort of Java based application got compromised.

![WrongSpookySeason](/Screenshots/FORENSICS_1.png)

In the last stream (14th), along with some suspicious activities going on, we can see what looks like a reversed base64 encoded string thrown into the void by the attacker.

![WrongSpookySeason](/Screenshots/FORENSICS_1.1.png)

Now we can simply use Cyberchef or `echo "ENCODED_STRING" | rev | base64 -d` to get the flag.

#### HTB{j4v4_5pr1ng_just_b3c4m3_j4v4_sp00ky!!}