# password-cracking-lab-john-the-ripper
🔹 Title
Password Cracking Lab – John the Ripper
🔹 Overview

This project demonstrates hands-on experience using John the Ripper to crack various types of password-protected data across Windows and Linux environments.

The lab includes cracking authentication hashes, encrypted archives, and SSH keys while highlighting security risks associated with weak password practices.

Objectives

Understand password cracking techniques
Identify hash types
Use John the Ripper with different formats
Analyze security weaknesses in password systems
Tools Used

John the Ripper
RockYou Wordlist
zip2john / rar2john / ssh2john
unshadow

Linux (Ubuntu AttackBox)
Methodology

1. Hash Identification
Identified hash types using tools and external resources
Used correct formats for John the Ripper

📸 (Insert Screenshot Here: hash identification)

2. Cracking Basic Hashes

Used wordlists to crack MD5, SHA1, SHA256, and Whirlpool hashes
john --format=raw-md5 --wordlist=rockyou.txt hash1.txt

📸 (Insert Screenshot Here: successful crack)

🔸 3. Windows Authentication Hashes
Cracked NTLM hashes
john --format=nt --wordlist=rockyou.txt ntlm.txt

📸 (Insert Screenshot Here)

🔸 4. Linux /etc/shadow Hashes
Combined passwd + shadow using unshadow
Cracked SHA512 hashes

📸 (Insert Screenshot Here)

🔸 5. Cracking ZIP & RAR Files
Converted files to hashes using zip2john / rar2john
Cracked using wordlist

📸 (Insert Screenshot Here)

🔸 6. Cracking SSH Keys
Used ssh2john to extract hash
Cracked password using John

📸 (Insert Screenshot Here)

🔹 Findings
Weak passwords were successfully cracked using common wordlists
Hash format identification is critical for successful cracking
Different file types require specific preprocessing tools
🔹 Challenges
Identifying correct hash formats
File path and syntax errors
Understanding preprocessing tools (zip2john, ssh2john)
🔹 Lessons Learned
Importance of strong password policies
Risks of weak encryption and reused passwords
Value of proper hash identification and tool usage
