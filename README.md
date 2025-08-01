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
Here's your beautifully formatted Linux commands cheat sheet with emojis and visual blocks for your GitHub repository:

---

# 🐧 **Linux Interview Cheat Sheet**  
*Master Essential Commands for Technical Interviews*  

---

## 📂 **File System Operations**
```diff
+ 🏠 Navigation:
- pwd          # Show current directory
- cd ~         # Go to home
- cd ..        # Move up one level
- ls -la       # List all files (including hidden)

+ 🛠️ Creation/Deletion:
- touch file   # Create empty file
- mkdir dir    # Create directory
- rm -r dir    # Remove directory recursively
```

---

## 📄 **File Management**
```diff
+ 👀 Viewing Content:
- cat file     # Display entire file
- head -n 5    # Show first 5 lines
- tail -f log  # Live-tail log file

+ ✂️ Manipulation:
- cp a b       # Copy file
- mv a b       # Move/rename
- grep "err"   # Search for pattern
```

---

## 🔗 **Links & Comparisons**
```diff
+ 🔗 Linking:
- ln -s src link  # Create symbolic link
- ln src link     # Create hard link

+ 🔍 Differences:
- diff f1 f2    # Compare files
- sort file     # Sort lines
- wc -l file    # Count lines
```

---

## 🖥️ **System Monitoring**
```diff
+ 📊 Resources:
- top          # Live system stats
- free -h      # Memory usage
- df -h        # Disk space

+ 🕵️ Processes:
- ps aux       # All running processes
- vmstat 1     # Virtual memory stats
- nohup cmd &  # Run persistent command
```

---

## 🧩 **Complete Command Table**

| Category               | Key Commands                          |
|------------------------|---------------------------------------|
| **Navigation**         | `pwd`, `cd`, `ls`, `clear`            |
| **File Operations**    | `touch`, `rm`, `cp`, `mv`, `mkdir`    |
| **Viewing Content**    | `cat`, `head`, `tail`, `less`, `more` |
| **Text Processing**    | `grep`, `cut`, `tee`, `sort`, `diff`  |
| **System Monitoring**  | `top`, `free`, `df`, `du`, `nohup`    |

---

## 💡 **Interview Pro Tips**
```diff
! Remember:
1. Use tab for autocomplete
2. Ctrl+C stops any command
3. man command shows manual
4. sudo = "superuser do"
```

---
 

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


Here's your beautifully formatted GitHub README section with emojis and visual blocks:

---

# 🐧 Linux Command Cheat Sheet for Interviews

## 🔍 `grep` – The Pattern Finder
```diff
+ 🎯 When to Use:
- Need to find lines containing a word/pattern (e.g., errors in logs)
- Quickly filter command output (e.g., `ps aux | grep nginx`)

+ 💡 Why to Use:
- Lightning-fast searching through files/output
- Supports powerful options: case-insensitive (-i), count matches (-c), etc.

+ 📊 What It Shows:
- All lines matching your search pattern

+ 🛠️ Example:
```bash
grep -i "error" /var/log/syslog   # Find all ERRORs (case-insensitive)
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

## ✂️ `sed` – The Text Surgeon
```diff
+ 🎯 When to Use:
- Replace text in files (e.g., update configs)
- Delete/modify specific lines (e.g., clean logs)

+ 💡 Why to Use:
- Edit files without opening them (perfect for scripts)
- Perform bulk edits in milliseconds

+ 📊 What It Shows:
- Modified text (add `-i` to save changes to file)

+ 🛠️ Example:
```bash
sed 's/old/new/g' file.txt        # Replace ALL occurrences
sed '/debug/d' app.log           # Delete all debug lines
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

## 📊 `awk` – The Data Wizard
```diff
+ 🎯 When to Use:
- Extract columns (e.g., timestamps from logs)
- Perform calculations (sums, averages) on data
- Format/report on structured data

+ 💡 Why to Use:
- Like a programming language for text processing
- Handles CSVs, logs, and structured data perfectly

+ 📊 What It Shows:
- Selected columns, processed data, or calculations

+ 🛠️ Examples:
```bash
awk '{print $1,$3}' access.log    # Show 1st & 3rd columns
awk '{sum+=$1} END{print sum}' data.txt  # Sum first column
```
| Task                  | Command Example                          | Explanation                     |
|-----------------------|------------------------------------------|---------------------------------|
| Print columns         | `awk '{print $1, $3}' file.log`         | Print 1st and 3rd columns       |
| Filter lines          | `awk '/ERROR/ {print}' file.log`        | Print lines containing "ERROR"  |
| Count matches         | `awk '/WARN/ {count++} END {print count}' file.log` | Count "WARN" lines |
| Field separator       | `awk -F',' '{print $2}' data.csv`       | Use `,` as delimiter (for CSV)  |
| Math operations       | `awk '{sum+=$1} END {print sum}' nums.txt` | Sum values in 1st column    |

---
---

### 🧠 Interview Pro Tip:
```diff
! Remember the 3 S's:
1. Search → grep
2. Substitute → sed 
3. Slice → awk
```

---

### 🚀 How to Use This Cheat Sheet:
1. Bookmark this page 📌
2. Star the repo ⭐ (to save for later)
3. Practice daily for 1 week 🏋️
4. Ace your Linux interview! 🎉

---

This format:
- Uses eye-catching emojis and color blocks
- Clearly separates concepts
- Highlights key information
- Makes examples stand out
- Includes memorable mnemonics

Would you like me to add any additional commands or sections? 😊


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



---
# **🚀 Linux *AWS EBS Volumes & LVM Management Guide** 
# * 
*A practical tutorial on attaching, mounting, and resizing storage in AWS EC2*  

---

## **1. Core Concepts**  
- **EBS Volume**: Virtual hard disk for AWS EC2 (like `C:`/`D:` drives).  
- **LVM (Logical Volume Manager)**:  
  - **PV (Physical Volume)**: Raw disk (`/dev/xvdf`).  
  - **VG (Volume Group)**: Pool of PVs (e.g., `22GB = 10GB + 12GB`).  
  - **LV (Logical Volume)**: Flexible partition from a VG (e.g., `10GB`).  

---

## **2. Steps Summary**  

### **Step 1: Create & Attach EBS Volumes**  
1. **Create 3 Volumes** in AWS Console:  
   - `10GB`, `12GB`, `14GB` (same AZ as EC2).  
2. **Attach to EC2**:  
   - Device names: `/dev/sdf`, `/dev/sdg`, `/dev/sdh`.  

### **Step 2: Initialize Volumes**  
```bash
lsblk                  # List attached disks  
sudo su                # Switch to root  
```

### **Step 3: LVM Setup**  
1. **Create Physical Volumes (PVs)**:  
   ```bash
   pvcreate /dev/xvdf /dev/xvdg  
   ```  
2. **Create Volume Group (VG)**:  
   ```bash
   vgcreate TWA_vg /dev/xvdf /dev/xvdg  
   ```  
3. **Create Logical Volume (LV)**:  
   ```bash
   lvcreate -L 10G -n TWA_lv TWA_vg  
   ```  

### **Step 4: Mount the LV**  
1. **Format & Mount**:  
   ```bash
   mkfs.ext4 /dev/TWA_vg/TWA_lv  
   mkdir /mnt/TWA_lv_mount  
   mount /dev/TWA_vg/TWA_lv /mnt/TWA_lv_mount  
   ```  
2. **Verify**:  
   ```bash
   df -h  # Check mounted storage  
   ```  

### **Step 5: Direct Mount (Non-LVM)**  
For `/dev/xvdh` (14GB volume):  
```bash
mkfs.xfs /dev/xvdh  
mkdir /mnt/TWA_disk_mount  
mount /dev/xvdh /mnt/TWA_disk_mount  
```

### **Step 6: Extend an LV**  
Add `5GB` to `TWA_lv`:  
```bash
lvextend -L +5G /dev/TWA_vg/TWA_lv  
resize2fs /dev/TWA_vg/TWA_lv  # Resize filesystem  
df -h  # Confirm new size  
```

---

## **3. Key Commands Cheatsheet**  
| Command | Description |  
|---------|-------------|  
| `lsblk` | List block devices |  
| `pvcreate` | Initialize PV |  
| `vgcreate` | Create VG |  
| `lvcreate` | Create LV |  
| `mount` | Mount a filesystem |  
| `lvextend` | Resize LV |  

---

## **4. Pro Tips**  
✅ **Always**:  
- Use `/dev/sdf`+ for non-root volumes.  
- Match AZ for EBS-EC2 attachment.  
- Use `df -h` and `lsblk` for debugging.  

⚠️ **Avoid**:  
- Using `/dev/sda`/`/dev/sdb` (reserved for root).  

---

## **5. Why This Matters**  
- **Scalability**: Dynamically resize storage without downtime.  
- **Cost-Efficiency**: Pay only for what you use.  
- **Flexibility**: Combine disks seamlessly with LVM.  

--- 
