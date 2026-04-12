
- Identify different hash types
- Crack Windows and Linux authentication hashes
- Extract and crack hashes from protected files
- Understand password weaknesses and attack methods

---

## Hash Identification

Before cracking, it is important to identify the hash type to use the correct format.

![Hash Identification](screenshots/identifying-hashes.png)

---

## Cracking Windows Hashes (NTLM)

Used John the Ripper to crack Windows authentication hashes.

```bash
john --format=nt --wordlist=rockyou.txt hash.txt

Cracking MD5 Hash
john --format=raw-md5 --wordlist=rockyou.txt hash.txt

Cracking /etc/shadow Hashes

Combined passwd and shadow files, then cracked the hash.

unshadow passwd.txt shadow.txt > combined.txt
john combined.txt --wordlist=rockyou.txt




Cracking ZIP Files

Extracted hash using zip2john and cracked password.

zip2john file.zip > zip.hash
john zip.hash --wordlist=rockyou.txt






Cracking RAR Files
rar2john file.rar > rar.hash
john rar.hash --wordlist=rockyou.txt






Cracking SSH Keys
ssh2john id_rsa > ssh.hash
john ssh.hash --wordlist=rockyou.txt




Key Takeaways
Weak passwords can be cracked quickly using common wordlists
Proper hash identification is critical before attempting to crack
Different file types require preprocessing tools before cracking
Password security is essential to prevent unauthorized access
Lessons Learned
Gained hands-on experience using John the Ripper across multiple scenarios
Improved understanding of Linux command-line tools
Learned how attackers exploit weak password practices
Strengthened troubleshooting and problem-solving skills
Challenges
Identifying correct hash formats initially
Understanding preprocessing steps for different file types
Managing multiple tools and commands during the process
Conclusion

This lab provided practical experience in password cracking techniques and reinforced the importance of strong password policies. The skills developed here are directly applicable to cybersecurity and IT support roles, particularly in understanding system vulnerabilities and user security practices.
