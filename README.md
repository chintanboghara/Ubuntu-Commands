## File System Navigation

- `pwd` - Print the current working directory.
- `ls` - List files and directories in the current directory.
  - `ls -l` - List in long format.
  - `ls -a` - List all files, including hidden files.
- `cd <directory>` - Change to the specified directory.
  - `cd ..` - Move up one directory level.
  - `cd ~` - Change to the home directory.
- `mkdir <directory>` - Create a new directory.
- `rmdir <directory>` - Remove an empty directory.
- `touch <file>` - Create an empty file or update the timestamp of an existing file.
- `cp <source> <destination>` - Copy files or directories.
- `mv <source> <destination>` - Move or rename files or directories.
- `rm <file>` - Remove a file.
  - `rm -r <directory>` - Remove a directory and its contents recursively.

## File Viewing and Editing

- `cat <file>` - Display the contents of a file.
- `less <file>` - View file contents one page at a time.
- `head <file>` - Display the first 10 lines of a file.
  - `head -n <number> <file>` - Display the first `n` lines.
- `tail <file>` - Display the last 10 lines of a file.
  - `tail -n <number> <file>` - Display the last `n` lines.
- `nano <file>` - Open a file in the Nano text editor.
- `vim <file>` - Open a file in the Vim text editor.

## System Information

- `uname -a` - Display system information.
- `df -h` - Display disk space usage in a human-readable format.
- `du -sh <directory>` - Display the size of a directory.
- `free -h` - Display memory usage in a human-readable format.
- `top` - Display real-time system statistics and running processes.
- `htop` - Interactive process viewer (may need to be installed).

## Package Management

- `sudo apt update` - Update the package list.
- `sudo apt upgrade` - Upgrade installed packages.
- `sudo apt install <package>` - Install a package.
- `sudo apt remove <package>` - Remove a package.
- `sudo apt autoremove` - Remove unused packages.
- `sudo apt search <keyword>` - Search for a package.
- `sudo apt show <package>` - Display information about a package.

## User Management

- `sudo adduser <username>` - Add a new user.
- `sudo deluser <username>` - Delete a user.
- `sudo passwd <username>` - Change a user's password.
- `whoami` - Display the current username.
- `who` - Display logged-in users.
- `sudo usermod -aG <group> <username>` - Add a user to a group.

## Permissions

- `chmod <permissions> <file>` - Change file permissions.
  - Example: `chmod 755 script.sh` - Give read, write, and execute permissions to the owner, and read and execute permissions to others.
- `chown <user>:<group> <file>` - Change file ownership.
  - Example: `chown user:group file.txt` - Change the owner and group of `file.txt`.


## Networking

- `ifconfig` - Display network interface information.
- `ping <host>` - Test connectivity to a host.
- `ssh <user>@<host>` - Connect to a remote host via SSH.
- `scp <file> <user>@<host>:<destination>` - Copy files to a remote host.
- `wget <url>` - Download a file from the internet.
- `curl <url>` - Transfer data from or to a server.

## Process Management

- `ps` - Display currently running processes.
  - `ps aux` - Display all running processes.
- `kill <PID>` - Terminate a process by its Process ID.
  - `kill -9 <PID>` - Forcefully terminate a process.
- `bg` - Resume a suspended job in the background.
- `fg` - Bring a background job to the foreground.

## Intermediate Commands

### File Compression and Archiving
- `tar -cvf archive.tar <files>` - Create a tar archive.
- `tar -xvf archive.tar` - Extract a tar archive.
- `tar -czvf archive.tar.gz <files>` - Create a compressed tar archive (gzip).
- `tar -xzvf archive.tar.gz` - Extract a compressed tar archive (gzip).
- `zip archive.zip <files>` - Create a zip archive.
- `unzip archive.zip` - Extract a zip archive.

### File Searching
- `find <directory> -name <filename>` - Search for files by name.
  - Example: `find /home -name "*.txt"` - Find all `.txt` files in `/home`.
- `grep <pattern> <file>` - Search for a pattern in a file.
  - Example: `grep "error" log.txt` - Find lines containing "error" in `log.txt`.
  - `grep -r <pattern> <directory>` - Recursively search for a pattern in a directory.

### Disk Usage Analysis
- `ncdu` - Interactive disk usage analyzer (may need to be installed).
- `df -h` - Display disk space usage in a human-readable format.
- `du -sh *` - Display the size of all files and directories in the current directory.

### System Monitoring
- `uptime` - Display system uptime and load averages.
- `vmstat` - Display system performance statistics.
- `iostat` - Display CPU and I/O statistics.

### Environment Variables
- `printenv` - Display all environment variables.
- `export <variable>=<value>` - Set an environment variable.
  - Example: `export PATH=$PATH:/new/path` - Add `/new/path` to the `PATH` variable.
- `unset <variable>` - Remove an environment variable.

### Cron Jobs
- `crontab -e` - Edit the current user's cron jobs.
- `crontab -l` - List the current user's cron jobs.
- `crontab -r` - Remove the current user's cron jobs.

### Networking Tools
- `netstat -tuln` - Display listening ports and connections.
- `nmap <host>` - Scan a host for open ports (may need to be installed).
- `traceroute <host>` - Trace the route packets take to a host.
- `dig <domain>` - Query DNS information for a domain.

### System Logs
- `tail -f /var/log/syslog` - Monitor system logs in real-time.
- `journalctl` - Query and display systemd logs.
  - `journalctl -xe` - Display detailed logs with explanations.

## Advanced Commands

### Kernel and System Management
- `uname -r` - Display the current kernel version.
- `sudo apt install linux-headers-$(uname -r)` - Install kernel headers for the current kernel.
- `sudo sysctl -w <parameter>=<value>` - Modify kernel parameters at runtime.
  - Example: `sudo sysctl -w net.ipv4.ip_forward=1` - Enable IP forwarding.
- `sudo sysctl -p` - Apply changes from `/etc/sysctl.conf`.

### Advanced File System Management
- `sudo fdisk -l` - List all disk partitions.
- `sudo mkfs.ext4 /dev/sdX1` - Format a partition with the ext4 file system.
- `sudo mount /dev/sdX1 /mnt` - Mount a partition to a directory.
- `sudo umount /mnt` - Unmount a partition.
- `sudo blkid` - Display block device attributes.
- `sudo fsck /dev/sdX1` - Check and repair a file system.

### Advanced Networking
- `iptables` - Configure firewall rules.
  - Example: `sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT` - Allow SSH traffic.
- `ufw` - Uncomplicated Firewall (UFW) management.
  - `sudo ufw enable` - Enable UFW.
  - `sudo ufw allow 22/tcp` - Allow SSH traffic.
- `tcpdump` - Capture network traffic.
  - Example: `sudo tcpdump -i eth0` - Capture traffic on the `eth0` interface.
- `ss` - Display socket statistics.
  - Example: `ss -tuln` - Display listening ports.

### Advanced Process Management
- `nice -n <priority> <command>` - Run a command with a specific priority.
  - Example: `nice -n 10 ./script.sh` - Run `script.sh` with a low priority.
- `renice <priority> -p <PID>` - Change the priority of a running process.
- `strace <command>` - Trace system calls and signals.
  - Example: `strace ls` - Trace the `ls` command.
- `lsof` - List open files and processes using them.
  - Example: `lsof -i :22` - List processes using port 22.

### Advanced Package Management
- `dpkg -i <package.deb>` - Install a `.deb` package.
- `dpkg -r <package>` - Remove a `.deb` package.
- `dpkg -l` - List all installed packages.
- `apt-cache search <keyword>` - Search for packages in the cache.
- `apt-get source <package>` - Download the source code of a package.

### Virtualization and Containers
- `virsh` - Manage virtual machines (requires libvirt).
  - Example: `virsh list --all` - List all virtual machines.
- `docker` - Manage Docker containers.
  - Example: `docker ps -a` - List all containers.
- `lxc` - Manage LXC containers.
  - Example: `lxc list` - List all LXC containers.

### Advanced Log Analysis
- `logrotate` - Manage log rotation.
  - Example: `sudo logrotate -f /etc/logrotate.conf` - Force log rotation.
- `awk` - Advanced text processing.
  - Example: `awk '{print $1}' file.txt` - Print the first column of `file.txt`.
- `sed` - Stream editor for text manipulation.
  - Example: `sed 's/foo/bar/g' file.txt` - Replace "foo" with "bar" in `file.txt`.

### System Recovery and Rescue
- `fsck` - Check and repair a file system.
- `chroot` - Change the root directory for a command.
  - Example: `sudo chroot /mnt /bin/bash` - Run a shell in a different root.
- `grub-rescue` - Repair GRUB bootloader.
- `dd` - Low-level disk operations.
  - Example: `dd if=/dev/sdX of=backup.img` - Create a disk image.

## Miscellaneous

- `clear` - Clear the terminal screen.
- `history` - Display command history.
- `man <command>` - Display the manual page for a command.
- `sudo <command>` - Execute a command with superuser privileges.
- `exit` - Close the terminal session.

## Tips

- Use `Tab` for auto-completion of commands and file names.
- Use `Ctrl + C` to interrupt a running command.
- Use `Ctrl + Z` to suspend a running command.
- Use `Ctrl + D` to log out of the current shell.
