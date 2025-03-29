## Nmap

``` bash
sudo nmap -p- -sS -sC -sV --min-rate=5000 -n -vvv -Pn 172.18.0.2 -oN ports
```

| -p-             | Scans **all 65,535 ports** (not just the common ones).                              |
| --------------- | ----------------------------------------------------------------------------------- |
| -sS             | Uses **SYN scan** (stealthy, does not complete TCP handshake).                      |
| -sC             | Runs **default Nmap scripts** to detect vulnerabilities                             |
| -sV             | Performs **service version detection** (identifies running services).               |
| --min-rate=5000 | Sets a **minimum scan rate of 5000 packets per second** (speeds up scanning).       |
| -n              | **Disables DNS resolution** (faster scan).                                          |
| -vvv            | **Very verbose mode** (shows detailed output in real-time).                         |
| -Pn             | **Disables host discovery** (assumes the host is online and skips ICMP ping check). |
| 172.18.0.2      | The **target IP address** (often a Docker container or internal network).           |
| -oN ports       | Saves output in **normal format** to a file named `ports`.                          |
![[Pasted image 20250329035258.png]]