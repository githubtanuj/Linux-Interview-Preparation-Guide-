# **🚀 Linux basic Cheat Sheet - Part 1 (DevOps Edition)*

### ✅ ** List of Commands Covered:**


| Category                   | Commands Covered                                                                  |
| -------------------------- | --------------------------------------------------------------------------------- |
| File Navigation / Creation | `ls`, `pwd`, `cd`, `mkdir`, `touch`, `clear`                                      |
| File/Folder Management     | `rm`, `rm -r`, `rmdir`, `cp`, `cp -r`, `mv`                                       |
| Viewing/Editing Content    | `cat`, `echo ... > file`, `head`, `tail`, `tail -f`, `less`, `more`, `cut`, `tee` |
| Links                      | `ln source link`, `ln -s source linkname`                                         |
| Sorting and Diff           | `sort`, `diff`                                                                    |
| Word & Byte Count          | `wc`                                                                              |
| Monitoring & Logs          | `ps`, `top`, `free -h`, `vmstat`, `df -h`, `du`, `nohup`, `head/tail nohup.out`   |

## 🧩 Linux Commands & Concepts (Complete Overview)

### **1. Terminal & Shell Basics**

* **Terminal**: Text-based interface to enter commands.
* **Shell**: Interpreter that executes your commands.

---

### **2. Directory Navigation & File Basics**

* `pwd`: Print working directory (your current directory).
* `cd directory`: Change directory.

  * `cd ..` moves up one level.
* `ls`: List files & directories.

  * `ls -a`: Shows hidden (dot‑) files.
  * `ls -l`: Detailed listing including permissions, owner, etc.
* `mkdir foldername`: Create a new directory.
* `touch filename`: Create an empty file.
* `clear`: Clear the terminal screen.

---

### **3. File & Folder Management**

* `cp source dest`: Copy files or directories.

  * `cp -r source_folder dest_folder`: Recursively copy a folder.
* `mv source dest`: Move or rename a file or directory.
* `rm filename`: Permanently delete a file.
* `rm -r foldername`: Remove a folder and all its contents.
* `rmdir foldername`: Remove an empty folder.

---

### **4. Viewing File Content**

* `cat filename`: Display whole file content.
* `echo "text"`: Print text to terminal.
* `echo "text" > file.txt`: Write text to a file.
* `head filename`: View top lines.
* `tail filename`: View bottom lines.

  * `tail -f filename`: Live-monitor a file (e.g., logs as they update).
* `less filename` / `more filename`: View files page-by-page.

---

### **5. File Analysis & Comparison**

* `wc filename`: Shows lines, words, and byte count.

  * Can be used with multiple files to compare counts.
* `cut -b start-end filename`: Extract specified byte range.
* `tee`: `command | tee file.txt` – outputs to terminal **and** writes to file.
* `sort`: Sort file lines alphabetically.
* `diff file1 file2`: Compare two files to show differences.

---

### **6. Links: Hard vs. Soft**

* **Soft/symbolic link**: `ln -s source linkname`

  * If the source file is deleted, the link breaks.
* **Hard link**: `ln source linkname`

  * Remains valid even if original is removed — both point to the same data.

---

### **7. System Metrics & Monitoring**

* `ps`: Shows processes running in the current shell session.
* `top`: Interactive real-time view of system resources and processes.
* `free -h`: Displays RAM usage in a human-readable format.
* `vmstat`: Virtual memory stats—active/inactive, swap, I/O.
* `df -h`: Disk usage overview of all mounted filesystems.
* `du .`: Disk usage by directory/file under the current folder.

  * `du -h folder/filename` for readability.

---

### **8. Background Tasks & Logs**

* `nohup command > output.log 2>&1 &`: Run a command immune to hangups, saving both output and errors.
* You can then inspect logs using:

  * `head -n 5 nohup.out`
  * `tail -n 5 nohup.out`
* Combine with `head`, `tail`, `wc`, etc., to analyze logs.

---



# **🚀 Linux User management and Permission Part -2 Cheat Sheet - Part 1 (DevOps Edition)*
### **Linux Basics Summary with Examples** 

Simply think of Read (4) + Write (2) + Execute (1) = 7.

777 means Read + Write + Execute permissions for the Owner, Group, and Others.
The first digit represents the Owner,
The second digit represents the Group,
The third digit represents Others.

412 means Read permission for the Owner, Execute permission for the Group, and Write permission for Others.
again the first digit represents the Owner,
The second digit represents the Group,
The third digit represents Others.
#### **1. Basic Commands**  
- **`date`**: Check current date/time.  
  ```bash
  date  # Output: Fri Dec 15 09:00:00 UTC 2023
  ```  
- **`ls`**: List files/directories.  
  ```bash
  ls -l  # Detailed list (shows permissions)
  ```  
- **`mkdir`**: Create a directory.  
  ```bash
  mkdir deps  # Creates 'deps' folder
  ```  
- **`touch`**: Create an empty file.  
  ```bash
  touch demo.txt  # Creates 'demo.txt'
  ```  
- **`cd`**: Navigate directories.  
  ```bash
  cd deps      # Enter 'deps' folder
  cd ..        # Move up one level
  ```  

#### **2. File Operations**  
- **`echo`**: Print text or write to a file.  
  ```bash
  echo "Hello" > hello.txt  # Writes "Hello" to hello.txt
  ```  
- **`cat`**: View file content.  
  ```bash
  cat demo.txt  # Displays content of demo.txt
  ```  
- **`cp` / `mv`**: Copy or move files.  
  ```bash
  cp file.txt /backup/      # Copies file.txt to /backup/
  mv old.txt new.txt        # Renames old.txt to new.txt
  ```  
- **`rm`**: Delete files/folders.  
  ```bash
  rm file.txt          # Deletes file.txt
  rm -r folder/        # Deletes folder recursively
  ```  

#### **3. Permissions & Ownership**  
- **`chmod`**: Change permissions.  
  ```bash
  chmod 755 script.sh  # Sets rwxr-xr-x (User: rwx, Group/Others: r-x)
  ```  
- **`chown`**: Change owner.  
  ```bash
  sudo chown user:group file.txt  # Changes owner to 'user' and group to 'group'
  ```  

#### **4. User & Group Management**  
- **Create User**:  
  ```bash
  sudo useradd jethalal  # Adds user 'jethalal'
  sudo passwd jethalal   # Sets password for 'jethalal'
  ```  
- **Switch User**:  
  ```bash
  su jethalal  # Log in as 'jethalal'
  ```  
- **Create Group**:  
  ```bash
  sudo groupadd devs  # Creates 'devs' group
  sudo usermod -aG devs jethalal  # Adds 'jethalal' to 'devs' group
  ```  

#### **5. Compression & Archiving**  
- **`tar`**: Archive files.  
  ```bash
  tar -czvf backup.tar.gz /folder  # Compresses '/folder' into backup.tar.gz
  tar -xzvf backup.tar.gz          # Extracts files
  ```  
- **`zip` / `unzip`**:  
  ```bash
  zip archive.zip file.txt        # Creates archive.zip
  unzip archive.zip               # Extracts files
  ```  

#### **6. Networking**  
- **`ssh`**: Connect to a remote server.  
  ```bash
  ssh -i key.pem user@host  # Connects using a private key
  ```  
- **`scp`**: Securely copy files.  
  ```bash
  scp file.txt user@host:/path/  # Copies file.txt to remote server
  ```  

#### **7. System Monitoring**  
- **`df`**: Check disk space.  
  ```bash
  df -h  # Shows disk usage in human-readable format
  ```  
- **`top`**: Monitor processes.  
  ```bash
  top  # Real-time process viewer
  ```  

---  
**Key Takeaways**:  
- Use `sudo` for admin tasks (e.g., `sudo apt install package`).  
- Permissions: `chmod 755` (rwxr-xr-x) for scripts, `644` (rw-r--r--) for files.  
- Archive files with `tar` or `zip`.  
- Remote access: `ssh` for login, `scp` for file transfer.  

Practice these commands to master Linux basics! 🐧





NETWORKING LINUX


Here’s my **optimized version** of your networking commands summary — **simpler, clearer, and more actionable** while keeping all key details intact:

---

# **🚀 Linux Networking Cheat Sheet (DevOps Edition)**  
*Quick commands to debug, monitor, and fix networks.*

---

### **1. `ping` → "Is it alive?"**  
```bash
ping google.com
```  
- **Checks:** Can I reach this server? How fast?  
- **Look for:**  
  - ✅ `Packets: 5 sent, 5 received` → Good!  
  - ❌ `100% packet loss` → Dead connection.  

---

### **2. `netstat` / `ss` → "Who’s connected?"**  
```bash
ss -tuln  # Show open ports (faster than netstat)
```  
- **Checks:** What services (web, SSH, DB) are running?  
- **Key flags:**  
  - `-t` = TCP | `-u` = UDP | `-l` = Listening ports  

---

### **3. `traceroute` → "Where’s the blockage?"**  
```bash
traceroute google.com
```  
- **Shows:** Every "hop" (router) your data takes to reach Google.  
- **Use case:** Slow website? Find which hop is lagging.  

---

### **4. `mtr` → "Ping + Traceroute (live view)"**  
```bash
mtr google.com
```  
- **Live updates:** Combines `ping` + `traceroute` in one.  
- **Pro tip:** Press `q` to quit.  

---

### **5. `dig` / `nslookup` → "DNS Detective"**  
```bash
dig google.com  # Better output than nslookup
```  
- **Answers:** What’s the IP of `google.com`?  
- **Extra:**  
  ```bash
  dig MX google.com  # Check email servers
  ```  

---

### **6. `telnet` → "Is port 80/443 open?"**  
```bash
telnet google.com 80
```  
- **If it connects:** Port is open (great for web servers).  
- **If stuck/timeout:** Port is blocked.  

---

### **7. `ifconfig` / `ip` → "What’s my IP?"**  
```bash
ip a  # Modern replacement for ifconfig
```  
- **Shows:** Your IP, MAC address, and network interfaces.  

---

### **8. `arp` → "Who’s on my WiFi?"**  
```bash
arp -a
```  
- **Lists:** All devices on your local network + their MAC addresses.  

---

### **9. `curl` / `wget` → "Download or Test APIs"**  
```bash
curl -I https://google.com  # Check HTTP headers
wget https://example.com/file.zip  # Download files
```  

---

### **10. `watch` → "Auto-refresh any command"**  
```bash
watch -n 2 'netstat -tuln'  # Updates every 2 secs
```  
- **Great for:** Monitoring logs, connections, or server stats.  

---

### **11. `nmap` → "Port Scanner"**  
```bash
nmap -sT google.com  # Safe scan
```  
- **Finds:** Open ports (e.g., 22=SSH, 80=HTTP, 443=HTTPS).  
- **Warning:** Don’t scan networks without permission!  

---

### **12. `route` → "How does traffic exit?"**  
```bash
ip route  # Show routing table
```  
- **Tells you:** "Is my traffic going through VPN/WiFi/Ethernet?"  

---

### **💡 Pro Tips:**  
1. **Install missing tools:**  
   ```bash
   sudo apt install traceroute mtr nmap  # Debian/Ubuntu
   ```  
2. **Need prettier output?** Pipe to `jq` (for JSON) or `grep`:  
   ```bash
   curl api.example.com | jq  # Colorful JSON
   ```  
3. **Stuck?** Check manual pages:  
   ```bash
   man ping  # Press 'q' to exit
   ```  

---

### **🎯 When to Use What?**  
| **Problem**               | **Command**          |
|---------------------------|----------------------|
| "Is the server up?"       | `ping`               |
| "Why is the site slow?"   | `mtr`                |
| "What ports are open?"    | `nmap` / `netstat`   |
| "Is DNS working?"         | `dig`                |
| "Can I reach port 443?"   | `telnet`             |
| "What’s my IP?"          | `ip a`               |

---
# **🚀 Linux Advance command Cheat Sheet (awk, sed, grep – Easy to Remember!)**





1. grep – The Pattern Finder
When to Use:

Need to find lines containing a word/pattern (e.g., errors in logs).

Quickly filter output (e.g., ps aux | grep nginx).

Why to Use:

Fastest way to search entire files or command output.

Supports case-insensitive (-i), count matches (-c), and more.

What It Shows:

All lines matching the pattern.

Example:

bash
grep -i "error" /var/log/syslog   # Find all "error" lines (ignore case)










2. sed – The Text Replacer
When to Use:

Replace text in files (e.g., change IPs in configs).

Delete lines (e.g., remove debug logs).

Why to Use:

Edit files without opening them (great for automation).

Handle bulk replacements in seconds.

What It Shows:

Modified text (use -i to save changes to the file).

Example:

bash
sed 's/old_ip/new_ip/g' config.txt  # Replace all "old_ip" with "new_ip"
















3. awk – The Data Extractor
When to Use:

Extract specific columns (e.g., timestamps from logs).

Do calculations (e.g., sum values in a CSV).

Why to Use:

Works like a mini programming language for text.

Perfect for structured data (logs, CSVs).

What It Shows:

Filtered columns, calculated results, or reformatted data.

Example:

bash
awk '{print $1, $3}' access.log   # Print 1st and 3rd columns (e.g., IP + status code)


Here's a **structured cheat sheet** for `awk`, `sed`, and `grep` with syntax and examples:

---




















# **Linux Text Processing Cheat Sheet**  
*(awk, sed, grep)*  

---

## **1. `awk` – Column-Based Text Processing**  
**Syntax:**  
```bash
awk 'pattern {action}' file
```

### **Key Features & Examples**  
| Task                  | Command Example                          | Explanation                     |
|-----------------------|------------------------------------------|---------------------------------|
| Print columns         | `awk '{print $1, $3}' file.log`         | Print 1st and 3rd columns       |
| Filter lines          | `awk '/ERROR/ {print}' file.log`        | Print lines containing "ERROR"  |
| Count matches         | `awk '/WARN/ {count++} END {print count}' file.log` | Count "WARN" lines |
| Field separator       | `awk -F',' '{print $2}' data.csv`       | Use `,` as delimiter (for CSV)  |
| Math operations       | `awk '{sum+=$1} END {print sum}' nums.txt` | Sum values in 1st column    |

---

## **2. `sed` – Stream Editor (Find/Replace)**  
**Syntax:**  
```bash
sed 's/find/replace/flags' file
```

### **Key Features & Examples**  
| Task                  | Command Example                          | Explanation                     |
|-----------------------|------------------------------------------|---------------------------------|
| Replace first match   | `sed 's/old/new/' file.txt`             | Replace first "old" per line    |
| Replace all matches   | `sed 's/old/new/g' file.txt`            | Replace **all** "old" (global)  |
| Delete lines          | `sed '/pattern/d' file.txt`             | Delete lines with "pattern"     |
| Edit file in-place    | `sed -i 's/old/new/g' file.txt`         | Save changes to file (`-i`)     |
| Print line numbers    | `sed -n '/pattern/=' file.txt`          | Show line numbers of matches    |

---

## **3. `grep` – Pattern Search**  
**Syntax:**  
```bash
grep [options] "pattern" file
```

### **Key Features & Examples**  
| Task                  | Command Example                          | Explanation                     |
|-----------------------|------------------------------------------|---------------------------------|
| Basic search          | `grep "error" file.log`                 | Case-sensitive search           |
| Case-insensitive      | `grep -i "Error" file.log`              | Ignore case (`-i`)              |
| Count matches         | `grep -c "WARN" file.log`               | Count occurrences (`-c`)        |
| Search recursively    | `grep -r "config" /etc/`                | Search in directories (`-r`)    |
| Inverse match         | `grep -v "success" file.log`            | Exclude lines with "success"    |
| Show line numbers     | `grep -n "fail" file.log`               | Print line numbers (`-n`)       |

---

## **Combined Workflow Examples**  
1. **Extract IPs from logs, count unique:**  
   ```bash
   awk '{print $1}' access.log | sort | uniq -c
   ```

2. **Replace "localhost" with "127.0.0.1" in config:**  
   ```bash
   sed -i 's/localhost/127.0.0.1/g' /etc/nginx.conf
   ```

3. **Find all Java processes using high CPU:**  
   ```bash
   ps aux | grep java | awk '$3 > 80 {print $2}'
   ```

---

## **Quick Reference Table**  
| Command | Best For                     | Structure                    |  
|---------|------------------------------|------------------------------|  
| `awk`   | Column extraction, math      | `awk 'pattern {action}' file`|  
| `sed`   | Find/replace, line edits     | `sed 's/find/replace/g' file`|  
| `grep`  | Fast pattern matching        | `grep [options] "pattern" file` |  

---

### **When to Use Which?**  
- **`grep`**: Quick searches (e.g., "Find all errors in logs").  
- **`sed`**: Bulk edits (e.g., "Replace all old IPs with new ones").  
- **`awk`**: Data extraction (e.g., "Sum values in column 2 of a CSV").  

---

**Pro Tip:** Pipe commands together! Example:  
```bash
grep "ERROR" app.log | awk '{print $5}' | sort | uniq -c
```  
→ *Count unique error codes in logs.*  

Save this cheat sheet for quick reference! 🚀


Quick Comparison
Command	When to Use	Why to Use	What It Shows
grep	Find lines matching a word	Fastest search tool	Matching lines
sed	Replace/delete text	Edit files without manual work	Modified text
awk	Extract columns or do math	Handles structured data perfectly	Selected data/calculations

