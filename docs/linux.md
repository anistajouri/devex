# essential Linux commands:

## 1. System Information

```bash
uptime     # System up time and load average
# result: 15:23:52 up 7 days, 3:42, 2 users, load average: 0.52, 0.65, 0.43

# 15:23:52              # Current time
# up 7 days, 3:42       # System has been running for 7 days and 3 hours, 42 minutes
# 2 users               # Number of users currently logged in
# load average: 0.52, 0.65, 0.43   # Load averages for past 1, 5, and 15 minutes 
```

```bash
free       # Memory usage
# result:
#              total        used        free      shared  buff/cache   available
# Mem:        16367436     1234567     9876543       12345     2345678     8765432
# Swap:       2097148           0     2097148

df -h      # Disk space usage
# result:
# Filesystem      Size  Used Avail Use% Mounted on
# /dev/sda1        50G   20G   30G  40% /
# tmpfs           7.8G  1.2M  7.8G   1% /dev/shm

top        # System monitoring
# result: (interactive display of system processes)

uname -a   # System/kernel information
# result: Linux hostname 5.4.0-42-generic #46-Ubuntu SMP Fri Jul 10 00:24:02 UTC 2020 x86_64 x86_64 x86_64 GNU/Linux

lscpu      # CPU information
# result:
# Architecture:        x86_64
# CPU op-mode(s):      32-bit, 64-bit
# Byte Order:          Little Endian
# CPU(s):              8
# On-line CPU(s) list: 0-7
# Thread(s) per core:  2
# Core(s) per socket:  4
# Socket(s):           1
# Vendor ID:           GenuineIntel
# CPU family:          6
# Model:               158
# Model name:          Intel(R) Core(TM) i7-7700HQ CPU @ 2.80GHz
# Stepping:            9
# CPU MHz:             2808.004
# BogoMIPS:            5616.00
# Virtualization:      VT-x
# L1d cache:           32K
# L1i cache:           32K
# L2 cache:            256K
# L3 cache:            6144K
```

## 2. File Operations

```bash
ls         # List files
# result: file1.txt  file2.txt  dir1  dir2

pwd        # Current directory
# result: /home/user

cd /path/to/directory  # Change directory

cp source.txt destination.txt  # Copy
mv oldname.txt newname.txt     # Move/rename
rm file.txt                    # Remove
mkdir newdir                   # Create directory
touch newfile.txt              # Create/update file
find /path -name "file.txt"    # Search files
grep "search_term" file.txt    # Search content
```

```bash
du -sh /path/to/directory   # Show only total size of directory
# result: 1.5G    /path/to/directory

du -h --max-depth=1 /path/to/directory   # Show only one level deep
# result:
# 500M    /path/to/directory/subdir1
# 1.0G    /path/to/directory/subdir2
# 1.5G    /path/to/directory

du -h --threshold=100M /path/to/directory   # Show only items larger than 100MB
# result:
# 500M    /path/to/directory/subdir1
# 1.0G    /path/to/directory/subdir2
```

## 3. File Viewing/Editing

```bash
cat file.txt        # Display file content
# result: (contents of file.txt)

less file.txt       # Page through file
# result: (interactive display of file contents)

head -n 10 file.txt # Show first 10 lines
# result: (first 10 lines of file.txt)

tail -n 10 file.txt # Show last 10 lines
# result: (last 10 lines of file.txt)

vim file.txt        # Edit file with vim
nano file.txt       # Edit file with nano
```

## 4. Process Management

```bash
ps         # Show processes
# result:
#   PID TTY          TIME CMD
#  1234 pts/0    00:00:00 bash
#  5678 pts/0    00:00:00 ps

kill 1234  # Terminate by PID
killall process_name  # Terminate by name

systemctl status service_name  # Manage services
# result: (status of the service)
```

## 5. Network Commands

```bash
ip a       # Network config
# result: (network interface details)

ping google.com  # Test connectivity
# result:
# PING google.com (172.217.14.206) 56(84) bytes of data.
# 64 bytes from 172.217.14.206: icmp_seq=1 ttl=54 time=10.3 ms

ss -tuln   # Socket statistics
# result: (list of listening sockets)

curl http://example.com  # Transfer data
# result: (HTML content of the page)
wget http://example.com  # Transfer data
# result: (downloaded file)
```

## 6. User Management

```bash
sudo command       # Run as superuser
chmod 755 file.txt # Change permissions
chown user:group file.txt  # Change ownership
passwd             # Change password
```

## 7. Package Management

```bash
# Debian/Ubuntu
apt update
# result: (updates package lists)

apt install package_name
# result: (installs the package)

# RHEL/CentOS
yum install package_name
# result: (installs the package)

dnf update
# result: (updates packages)
```

## 8. Archive/Compression

```bash
tar -cvf archive.tar file1 file2  # Archive files
# result: (creates archive.tar containing file1 and file2)

gzip file.txt  # Compress files
# result: (creates file.txt.gz)

zip archive.zip file1 file2  # Zip operations
# result: (creates archive.zip containing file1 and file2)

unzip archive.zip  # Unzip operations
# result: (extracts files from archive.zip)
```