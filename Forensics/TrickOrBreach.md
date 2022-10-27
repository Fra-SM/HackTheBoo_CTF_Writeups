## **Trick Or Breach**

Second forensics challenge. We have another packet capture to analyze. This time we only see DNS queries to strange looking subdomain strings. This is an indicator for DNS exfiltration attacks.

![TrickOrBreach](/Screenshots/FORENSICS_2.png)

We can use *tshark* (Wireshark CLI tool) to extract all the aforementioned strings from the responses, by using the following command:
`tshark -r capture2.pcap -Y "dns.flags.response == 0" -T fields -e "dns.qry.name" | uniq | cut -d . -f 1 | tr -d "\n"`

We can then copy the output and head over to Cyberchef. By first unhexing and then unzipping the string, we obtain a bunch of XML files. Inspecting the *xl/sharedStrings.xml* one we find the flag.

![TrickOrBreach](/Screenshots/FORENSICS_2.1.png)

#### HTB{M4g1c_c4nn0t_pr3v3nt_d4t4_br34ch}