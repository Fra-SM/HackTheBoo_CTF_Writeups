## **Spookifier**

Second web challenge. Looking once again at the source code of the application, we can see that it leverages [Mako](https://www.makotemplates.org/), a python-based engine, to set up templates for displaying pages. Also, we can easily identify the code responsible for the vulnerability.

![Spookifier](/Screenshots/WEB_2.png)
![Spookifier](/Screenshots/WEB_2.1.png)

Entering `${7 * 7}` in the input text field (common way to test for SSTIs) confirms there is indeed a template injection vulnerability. At this point, we can go to [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings) to look for a possible payload and find the following: `${self.module.cache.util.os.system("id")}` which we can modify into `${self.module.cache.util.os.popen("cat ../flag.txt").read()}` to capture the output of the command and retrieve the flag.

![Spookifier](/Screenshots/WEB_2.2.png)

#### HTB{t3mpl4t3_1nj3ct10n_1s_$p00ky!!}