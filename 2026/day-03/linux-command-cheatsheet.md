## 1. Process Management Commands

- `ps aux` – Displays all running processes with details.
- `top` – Shows real-time CPU and memory usage of processes.
- `htop` – Interactive process viewer (enhanced version of top).
- `kill PID` – Terminates a process using its PID.
- `kill -9 PID` – Forcefully kills a process.
- `nice` – Starts a process with a specific priority.
- `renice` – Changes priority of a running process.
- `uptime` – Shows system running time and load average.
- `free -m` – Displays memory usage in MB.
- `watch command` – Repeats a command at regular intervals.

---

## 2. File System & Disk Commands

- `ls` – Lists files and directories.
- `pwd` – Shows current working directory.
- `cd` – Changes directory.
- `touch file` – Creates an empty file.
- `cp source dest` – Copies files or directories.
- `mv source dest` – Moves or renames files.
- `rm file` – Deletes a file.
- `rm -r dir` – Deletes a directory recursively.
- `df -h` – Shows disk space usage.
- `du -sh file/dir` – Shows size of a file or directory.
- `find /path -name file` – Searches files by name.
- `chmod` – Changes file permissions.
- `chown` – Changes file ownership.

---

## 3. Networking & Troubleshooting Commands

- `ping hostname` – Checks network connectivity.
- `ip addr` – Displays IP addresses and network interfaces.
- `ip route` – Shows routing table.
- `netstat -tuln` – Displays listening ports (older systems).
- `ss -tuln` – Shows active listening ports (modern replacement).
- `curl URL` – Tests API endpoints or downloads data.
- `wget URL` – Downloads files from the internet.
- `dig domain` – Checks DNS records.
- `traceroute host` – Traces network path to a host.

---

## 4. Logs & System Inspection Commands

- `journalctl` – Views systemd logs.
- `journalctl -u service` – Shows logs of a specific service.
- `tail -f file` – Continuously monitors log files.
- `less file` – Reads large files safely.
- `dmesg` – Displays kernel-related messages.

---

## 5. Service Management (systemd)

- `systemctl status service` – Checks service status.
- `systemctl start service` – Starts a service.
- `systemctl stop service` – Stops a service.
- `systemctl restart service` – Restarts a service.
- `systemctl enable service` – Enables service at boot.
- `systemctl disable service` – Disables service at boot.

