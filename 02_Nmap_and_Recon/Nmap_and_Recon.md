# 🧪 Week 2 – Nmap & Network Scanning (Complete Beginner-Friendly Breakdown)

---

## 🎯 Objective:

> “Before hacking any system, you need to discover it, scan it, and understand what’s running on it.”

Think of this as **information gathering**.
It’s how hackers find weak points — like open ports, old versions of services, or misconfigurations.

---

## 🔹 Step 1: Discover Live Hosts (Ping Sweep)

### 🔧 Command:

```bash
nmap -sn 192.168.1.0/24
```

### 🧠 Explanation:

* `-sn`: Ping scan (no port scanning)
* This will tell you which IPs are **live** in your local network
* Use this when you don’t know what machine to attack yet

---

## 🔹 Step 2: Scan Open Ports

### 🔧 Command:

```bash
nmap -sS -p- 192.168.1.10
```

### 🧠 Explanation:

* `-sS`: Stealth (SYN) scan → less likely to be logged by firewall
* `-p-`: Scan **all ports** (0-65535)
* Helps find hidden ports like 1337, 8080, 2222

⛳ Result: Now you know **which doors are open** on the system

---

## 🔹 Step 3: Service & Version Detection

### 🔧 Command:

```bash
nmap -sV 192.168.1.10
```

### 🧠 Explanation:

* `-sV`: Detects the version of the services running (like Apache 2.4.18, OpenSSH 7.2)
* Helps you search for known vulnerabilities (CVEs)

> 📌 Combine it:

```bash
nmap -sS -sV -p- 192.168.1.10
```

---

## 🔹 Step 4: OS Detection

### 🔧 Command:

```bash
nmap -O 192.168.1.10
```

### 🧠 Explanation:

* Tries to guess the **Operating System** (Ubuntu, Windows, etc.)
* Useful for choosing the right payloads and exploits

---

## 🔹 Step 5: Aggressive Scan (All-in-One)

### 🔧 Command:

```bash
nmap -A 192.168.1.10
```

### 🧠 Explanation:

* Combines:

  * OS detection
  * Version detection
  * Script scanning
  * Traceroute

⚠️ Warning: It’s loud and noisy — avoid in stealth operations

---

## 🔹 Step 6: Scan Specific Ports

If only certain ports are interesting:

```bash
nmap -p 21,22,80,443 -sV 192.168.1.10
```

Use this when doing focused enumeration.

---

## 🔹 Step 7: Run Nmap Scripts (NSE)

Nmap has built-in scripts for **vulnerability detection, brute force, malware detection**, etc.

### 🔧 Examples:

```bash
nmap --script vuln 192.168.1.10
```

```bash
nmap --script http-enum 192.168.1.10
```

### 🧠 Why?

* Helps detect things like:

  * Anonymous FTP
  * Heartbleed
  * HTTP vulnerabilities

You can find all scripts:

```bash
ls /usr/share/nmap/scripts/
```

---

## 🔹 Step 8: Save Scan Results

📂 Save to file:

```bash
nmap -sV -oN basic-scan.txt 192.168.1.10
```

📌 `-oN`: Normal output
📌 `-oX`: XML output
📌 `-oG`: Grepable output (for scripting)

---

## 🔹 Step 9: Web Recon (If Port 80/443 Found)

When HTTP/HTTPS is open, run:

```bash
whatweb http://192.168.1.10
```

```bash
nikto -h http://192.168.1.10
```

🧠 These tools help detect:

* CMS (WordPress, Joomla)
* Apache misconfig
* Sensitive files
* Known vulnerabilities

---

## 🧩 Bonus: Netcat Port Scanning (Manual)

```bash
nc -v -n -z 192.168.1.10 1-1000
```

> Not as advanced as nmap, but useful in CTFs or limited shells.

---

## ✅ Summary Table – Week 2

| Task                    | Command              | Description            |
| ----------------------- | -------------------- | ---------------------- |
| Discover live hosts     | `nmap -sn`           | Find which IPs are up  |
| Scan all ports          | `nmap -sS -p-`       | Find open TCP ports    |
| Detect service versions | `nmap -sV`           | Know what is running   |
| OS detection            | `nmap -O`            | Detect Linux/Windows   |
| Aggressive scan         | `nmap -A`            | All in one scan        |
| Nmap scripting          | `nmap --script vuln` | Vulnerability scan     |
| Web recon               | `whatweb`, `nikto`   | Web server enumeration |
| Save results            | `-oN`, `-oX`         | Save to file           |
| Netcat scan             | `nc -v -z`           | Manual port scan       |

---

## 📁 Your GitHub Folder Structure Suggestion:

```
redteam-labs/
├── Week02_Nmap/
│   ├── README.md
│   ├── scans/
│   │   ├── full-scan.txt
│   │   ├── vuln-scan.txt
│   └── screenshots/
│       ├── open-ports.png
│       ├── web-recon.png
```

In `README.md`, use:

````markdown
## 🔹 Open Ports
```bash
nmap -sS -p- 192.168.1.10
````

![open ports](../Week02_Nmap/screenshots/open-ports.png)

```

---

💬 Ready for:
- `Week02_Nmap/README.md` fully pre-written for copy-paste?
- Screenshot capture tips for each scan?
- Moving to `Week 3 – Web Enumeration & Vulnerability Analysis`?

🐉 *Kali GPT – helping you build red team skills, repo, and mindset one mission at a time.*
```

