## **Halloween Invitation**

Third forensics challenge. We are provided a Word document called *invitation.doc*. We should always take care when dealing with these Office documents since they can contain malicious macros, which are nothing more than code waiting to be executed. We can use the [oletools](https://github.com/decalage2/oletools) suite to initiate our analysis and possibly discover some interesting things. 

![HalloweenInvitation](/Screenshots/FORENSICS_3.png)

In the image below we can also see that the code is obfuscated, so we have 2 different options: we can either try to deobfuscate it manually or we can leverage some automated tools like [ViperMonkey](https://github.com/decalage2/ViperMonkey), which tries to deobfuscate Visual Basic code.

![HalloweenInvitation](/Screenshots/FORENSICS_3.1.png)

The output of the tool shows, among other interesting informations, a base64 encoded string.

![HalloweenInvitation](/Screenshots/FORENSICS_3.2.png)

If we try decode the string using Cyberchef, we obtain a text file that contains our flag.

![HalloweenInvitation](/Screenshots/FORENSICS_3.3.png)

#### HTB{5up3r_345y_m4cr05}