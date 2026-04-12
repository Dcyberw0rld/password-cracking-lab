# Password Cracking Lab – John the Ripper

## Overview
The goal of this lab was to gain hands-on experience using John the Ripper to crack various types of password hashes and protected files. This included working with Windows and Linux authentication hashes as well as password-protected ZIP, RAR, and SSH files.

This lab demonstrates practical understanding of password security, hash identification, and common attack techniques used in cybersecurity.

---

## Lab Source
This project was completed as part of a TryHackMe learning module. All work reflects hands-on execution, analysis, and documentation of the lab.

---

## Tools Used
- John the Ripper
- RockYou Wordlist
- zip2john
- rar2john
- ssh2john
- Linux (Kali/Ubuntu)
- Hashes.com

---

## Objectives
- Identify different hash types
- Crack Windows and Linux authentication hashes
- Extract and crack hashes from protected files
- Understand password weaknesses and attack methods

---

## Hash Identification

Before cracking, it is important to identify the hash type to use the correct format.

![Hash Identification](screenshots/Identifying-hashes.png)

---

## Cracking Basic Hashes (MD5)

Used wordlists to crack MD5 hash

[Command]  john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash1.txt  
 
![Cracking Basic Hashes (MD5)](screenshots/md5-crack.png)

## Cracking Windows Hashes (NTLM)

Used John the Ripper to crack Windows authentication hashes.

[Command] john --format=nt --wordlist=/usr/share/wordlists/rockyou.txt ntlm.txt

![Cracking Windows Hashes (NTLM)](screenshots/ntlm-crack.png)

## Linux /etc/shadow Hashes
Combined passwd + shadow using unshadow
Cracked SHA512 hashes

[Command] unshadow local_passwd local_shadow > unshadowed.txt

![Linux /etc/shadow Hashes](screenshots/shadow-crack-1.png)

[Command] john --wordlist=/usr/share/wordlists/rockyou.txt --format=sha512crypt unshadowed.txt

![Linux /etc/shadow Hashes](screenshots/shadow-crack-2.png)


## Cracking ZIP & RAR Files
Converted files to hashes using zip2john / rar2john
Cracked using wordlist

[command] zip2john secure.zip > zip_hash.txt

![Cracking ZIP](screenshots/zip-crack-1.png)

john zip.hash --wordlist=rockyou.txt

[command] john –wordlist=/user/share/wordlists/rockyou.txt zip_hash.txt

![Cracking ZIP](screenshots/zip-crack-2.png)

opened the contents of the zip file to read the hidden flag

![Cracking ZIP](screenshots/zip-crack-3.png)

rar2john file.rar > rar.hash

john rar.hash --wordlist=rockyou.txt

![Hash Identification](screenshots/rar-crack-1.png)

![Hash Identification](screenshots/rar-crack-2.png)

![Hash Identification](screenshots/rar-crack-3.png)

## Cracking SSH Keys
Used ssh2john to extract hash
Cracked password using John

![Hash Identification](screenshots/ssh-crack-1.png)

![Hash Identification](screenshots/ssh-crack-2.png)

## Findings

Weak passwords were successfully cracked using common wordlists

Hash format identification is critical for successful cracking

Different file types require specific preprocessing tools

## Challenges

Identifying correct hash formats

File path and syntax errors

Understanding preprocessing tools (zip2john, ssh2john)

## Lessons Learned

Importance of strong password policies

Risks of weak encryption and reused passwords

Value of proper hash identification and tool usage


