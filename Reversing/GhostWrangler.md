## **Ghost Wrangler**

Third reversing challenge. This time the usual commands like `strings` or `strace` didn't work. We could see that something is written on the screen but `ltrace` only provided a partial output of the flag. After opening the ELF in GDB, we can use the command `catch syscall write`, run the program and notice that the flag gets loaded inside the RSI register.

![GhostWrangler](/Screenshots/REV_3.png)

We can then examine memory using the command `x/50x $rsi` to get the bytes of our flag (last 2  bytes in the red rectangle are excluded).

![GhostWrangler](/Screenshots/REV_3.1.png)

After copying them and doing some formatting, we can use Cyberchef to swap the endianness and unhex them to obtain the flag.

#### HTB{h4unt3d_by_th3_gh0st5_0f_ctf5_p45t!}