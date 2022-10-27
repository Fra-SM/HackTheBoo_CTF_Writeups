## **Evaluation Deck**

This was the first web challenge. Taking a look at the provided source code, we can see that the `routes.py` file contains a vulnerability that results from the lines in the picture.

![EvaluationDeck](/Screenshots/WEB_1.png)

This basically allows code injection through the “operator” parameter passed in the POST requests to the *api/get_health* API endpoint. Using Burp Repeater to speed up the testing process, we need to forward a request to this endpoint and set all the 3 parameters: we can assign 1 to *current_health* and *attack_power*, while *operator* will contain our payload. The crafted payload looks like: `\nimport subprocess as sp\nresult=sp.getoutput('cat ../flag.txt')\ny =`. The \n characters are there for indentation reasons. Since we are assigning the command output to the result variable, which is embedded in the response, we can see the flag inside the response body.

![EvaluationDeck](/Screenshots/WEB_1.1.png)

A cool alternative (but overkill) solution could have been to use a reverse shell.

#### HTB{c0d3_1nj3ct10ns_4r3_Gr3at!!}