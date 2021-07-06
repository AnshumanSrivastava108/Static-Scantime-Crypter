# Static-Scantime-Crypter

The project aims at building a Scan-Time Crypter in C++, that can assist a malware/false-positives in bypassing antivirus software. This Project is coded for Security purpose, it can be used to protect files against Reverse Engineering. The Crypter will open the target file from the disk while creating another output file to the disk. The Crypter will then extract the contents from the malware and obfuscate them using XOR encryption algorithm. 

## Tested On
[![Kali)](https://www.google.com/s2/favicons?domain=https://www.kali.org/)](https://www.kali.org) **Kali Linux - ROLLING EDITION**

[![Windows)](https://www.google.com/s2/favicons?domain=https://www.microsoft.com/en-in/windows/)](https://www.microsoft.com/en-in/windows/) **Windows 10**

## Language and IDE Used
- C++ - General purpose, case-sensitive, free-form programming language that supports object-oriented, procedural and generic programming
- Visual Studio - Integrated development environment from Microsoft. Visual Studio dev tools & services make development easy for C++ language.

### Implementation Summary

1. Creating a Malware: A windows meterpreter payload is crafted using msfvenom. Command used is - msfvenom –p     windows/meterpreter/reverse/tcp to create a reverse tcp meterpreter shell for windows 64bit OS. At the end of this step, an executable file called payload.exe will be created.

2. Encrypting the Malware using File Handling and XOR Encryption:

   **1.**   The file will be read using the function fopen() and mode ‘r’. 

   **2.**   The contents of the file will be retrieved using the fgets() function until it reachs EOF. 

   **3.**   The contents of the file will be XORed.

   **4.**   The encrypted contents will be then written to a new file and the stream will be closed to prevent data leakage.

3. Execution and Deobfuscation: The contents of the file will be deobfuscated when it is executed on the victim’s machine. Deobfuscation will be carried out using the same keys from encryption process.

4. Testing the Cryper: The Crypter will then be tested on services like [www.virustotal.com](http://www.virustotal.com/) and other antivirus software to prove the successful bypassing of Malware from security software.

### Scan Results:

![](/image/scanresult.png)

### Conclusion

- Obfuscating a malware using XOR encryption is better than other algorithms. When we XOR a piece of text, each character undergoes a bitwise operation. The encrypted piece of text can only be decrypted only by someone who has the key. To everyone else, the piece of text is just gibberish. This way, XOR Encryption takes the lead when compared to other algorithms like ROT13 or Base64 encoding. We see that the latter two do not need keys, hence can be easily decrypted and are less secure.

- The XOR encryption algorithm has a time complexity of O(n), which is the same as Base64 Encoding and ROT13, but the latter two have greater space complexities, and hence the encryption and decryption process becomes longer since the number of variables and the execution time is more. 

- In conclusion, the XOR Encryption algorithm is much more compact, reliable and efficient in comparison to other algorithms like Base64 Encoding and ROT13. 

### Author

**Anshuman Srivastava**

* Twitter: [@Anshuman_121](https://twitter.com/Anshuman_121)
* Github: [@AnshumanSrivastava108](https://github.com/AnshumanSrivastava108)
* LinkedIn: [@AnshumanSrivastava108](https://www.linkedin.com/in/anshumansrivastava108)
