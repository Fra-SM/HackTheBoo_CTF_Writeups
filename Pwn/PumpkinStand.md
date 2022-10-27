## **Pumpkin Stand**

This was the first pwn challenge. We are given a binary that we can execute and interact with.

![PumpkinStand](/Screenshots/PWN_1.png)

Our goal is to buy a laser, but we don't have enough coins. If we take a closer look at the code (we can view it with a decompiler like Ghidra), we can see that there's a line which causes an integer overflow vulnerability. This happens, as per CWE-190, *"when the logic assumes that the resulting value will always be larger than the original value"*. In these cases, the value will "wrap-around", causing an unexpected behavior of the program.

![PumpkinStand](/Screenshots/PWN_1.1.png)

We can then try to send a big enough number as input to successfully buy the laser and obtain the flag.

![PumpkinStand](/Screenshots/PWN_1.2.png)

#### HTB{1nt3g3R_0v3rfl0w_101_0r_0v3R_9000!}