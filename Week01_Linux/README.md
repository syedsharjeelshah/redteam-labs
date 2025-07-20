_**Week 1 is all about becoming a detective, finding weaknesses by learning about the system, the users, and the power you may already have.**_

                                                        # WEEK 1:

**📚 Goal:** **Learn how to collect basic system and user info after gaining initial access to a Linux machine (post-exploitation step 1).**

**🔹 Step 1:** **Identify Yourself & the System**

   _Understand what user you are, what machine you're on, and its OS._

   **🔧 Commands:**
   
whoami 

**# Shows your current username**

id

**# Shows UID, GID, and group info**

hostname

**# Name of the machine**

uname -a

**# Kernel version and architecture**

cat /etc/os-release

**# OS distribution and version info**



**🧠 Why?**

    You need to know if you are root or a limited user.
    OS and kernel version help in finding exploits.
___________________________________________________________________________________________
**🔹 Step 2: List Users on the System**
   
  _Now discover who else exists on the system. Admins, other users, etc._

  **🔧 Commands:**  
  
cat /etc/passwd          

**# Lists all users**

cut -d: -f1 /etc/passwd 

**# Just show usernames**

getent passwd           

**# Another way to list users (uses system libraries)**


**🧠 Why?**

    See if there's any interesting user (admin, backup, developer)
    Can help in lateral movement or password reuse attacks
___________________________________________________________________________________________
**🔹 Step 3: Group Memberships & Sudo Rights**

  _Check your privileges — can you become root using sudo?_

   **🔧 Commands:**
   
groups     

**# Shows what groups you're part of**

sudo -l    

**# Lists c ommands you can run with sudo (if any)**

**🧠 Why?**

    If sudo is allowed for programs like less, vi, nano, you can escalate to root
    Important for privilege escalation paths
___________________________________________________________________________________________
**🔹 Step 4: Find SUID Binaries**

  _These are files that run as root even if you are a normal user._

  **🔧 Commands:**
  
find / -perm -4000 -type f 2>/dev/null

**🧠 Why?**

    Some programs with SUID bit can be abused (like /bin/bash, /usr/bin/nmap)
    Check GTFOBins for exploits
___________________________________________________________________________________________
**🔹 Step 5: Check for Writable Folders & Files**

  _You might be able to modify scripts or binaries if they’re writable._

 **🔧 Commands:**
 
find / -writable -type d 2>/dev/null   

**# Writable directories**

find / -type f -name "*.sh"        

**# Look for script files**

**🧠 Why?**

    If root is running a script that you can edit, it’s a privilege escalation vector.
___________________________________________________________________________________________
**🔹 Step 6: Investigate Cron Jobs**

  _Cron jobs are scheduled tasks — sometimes they run scripts every minute/hour._

 **🔧 Commands:**
 
cat /etc/crontab

ls -la /etc/cron*

ps aux | grep cron

**🧠 Why?**

    If a cron job is run as root and you can write to its script = root access!
    Common post-exploitation trick
___________________________________________________________________________________________
**🔹 Step 7: Run LinPEAS or pspy (Optional Tools)**

   _Use automated scripts to save time and detect common misconfiguration._

 **🔧 Commands:**
 
- wget https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh
- 
- chmod +x linpeas.sh
- 
- ./linpeas.sh

 **For process monitoring:**
 
./pspy64      

**# You’ll see scheduled cron jobs in real-time**

**🧠 Why?**

    Tools like linPEAS automatically list SUID, crons, passwords, services, etc.
___________________________________________________________________________________________


