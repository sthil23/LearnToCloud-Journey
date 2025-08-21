# Linux Commands

### Navigation & File Exploration
- **pwd** - Show your current folder (Print Working Directory)
- **cd** - Move between folders (Change Directory)
- **ls** - List files in a folder
- **ls -a** - Show all files, including hidden ones
- **ls -la** - Detailed list of all files, including hidden
- **cat filename** - Displyas contents of a file
- **find . -name "pattern"** - Search for files matching a name pattern
- **locate filename** - Quickly find files using a pre-built index

### File Size & Disk Usage
- **ls -lh** - List files with readable sizes (e.g., KB, MB)
- **du -h** - Show disk usage of files/folders
- **sort -h** - Sort output by human-readable sizes
- **find /path -type f -size +1M** - Find files larger than 1MB

### User & Permission Investigation
- **id username** - Show user ID and group info
- **cat /etc/passwd** - List all user accounts
- **getent passwd UID** - Get user info by UID
- **ls -l /home/** - List home directories with permissions
- **stat filename** - Show detailed file info (owner, size, etc.)
- **find / -perm 777** - Find files with full permissions (rwx for all)
- **chmod 600 filename** - Set secure permissions (read/write for owner only)

### Network & Service Analysis
- **netstat -tuln** - Show listening ports (TCP/UDP)
- **ss -tuln** - Modern version of netstat
- **lsof -i** - List open network connections
- **curl localhost:port** - Test if a web service is running
- **nc -zv host port** - Check if a port is open on a host

### SSH & Key Management
- **ls -la ~/.ssh/** - List SSH config files
- **find ~/.ssh -type f** - Find SSH-related files
- **ssh-keygen** - Generate SSH key pairs
- **chmod 600 ~/.ssh/id_rsa** - Secure your private key file

### Text Search & Encoding
- **grep -r "text" /path** - Search for text inside files recursively
- **base64** - Encode or decode text in base64 format
- **echo -n "text"** - Print text without a newline

### Miscellaneous & Troubleshooting
- **man command** - Open the manual page for a command
- **history** - Show your past commands
- **scp** - Securely copy files between machines