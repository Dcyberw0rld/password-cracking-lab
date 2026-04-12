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

---

## Objectives
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
