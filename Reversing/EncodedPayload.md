## **Encoded Payload**

Second reversing challenge. All we need to do is using `strace` on the provided ELF file to see the system calls and watch the flag appear in the ouput.

![EncodedPayload](/Screenshots/REV_2.png)

#### HTB{PLz_strace_M333}