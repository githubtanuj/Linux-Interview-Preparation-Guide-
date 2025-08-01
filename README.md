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
