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

This version is:  
✅ **Shorter** (no fluff)  
✅ **Easier to scan** (bullet points, tables)  
✅ **Actionable** (clear use cases + examples)  
✅ **Visual** (emoji + formatting for quick reading)  

Let me know if you'd like any tweaks! 🚀
