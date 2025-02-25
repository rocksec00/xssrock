# 🔥 XSSRock - Automated XSS Scanner  
### 🚀 Advanced XSS Detection Suite by RockSec  

<p align="center">
    <img src="https://img.shields.io/badge/Made%20by-RockSec-blue.svg" alt="Made by RockSec">
    <img src="https://img.shields.io/badge/Language-Python%203.7%2B-blue.svg">
    <img src="https://img.shields.io/badge/Status-Active-green.svg">
</p>

## 🚀 Features  
✅ **Covers All XSS Types** (Reflected, Stored, DOM-Based, Blind, CSP Bypass, WAF Bypass)  
✅ **Automated Payload Mutation & WAF Bypass**  
✅ **Proxy & TOR Rotation** (Auto-switch on 403/429 errors)  
✅ **Blind XSS Support** (via `https://xss.report/c/rocksec`)  
✅ **Saves XSS Reports in JSON Format**  

---

## 🛠 **Installation Steps**  

### ✅ **Step 1: Install Python & pip**  
Ensure you have **Python 3.7+** and `pip` installed:  

```bash
python3 --version
pip3 --version
```

If not installed, install them using:  

#### **For Linux (Debian/Ubuntu)**  
```bash
sudo apt update && sudo apt install python3 python3-pip -y
```

#### **For macOS (Using Homebrew)**  
```bash
brew install python
```

#### **For Windows**  
Download and install Python from 👉 [Python.org](https://www.python.org/downloads/).  
Make sure to check **"Add Python to PATH"** during installation.

---

### ✅ **Step 2: Clone the Repository**
```bash
git clone https://github.com/yourusername/XSSRock.git
cd XSSRock
```

---

### ✅ **Step 3: Install Required Dependencies**  

#### **Method 1: Install via `requirements.txt`**
```bash
pip3 install -r requirements.txt
```

#### **Method 2: Install Modules Manually**
```bash
pip3 install requests selenium argparse
```

---

### ✅ **Step 4: Install Google Chrome & ChromeDriver**  
Since the script uses **Selenium** for **DOM-Based XSS detection**, install **Google Chrome** and **ChromeDriver**.

#### **For Linux (Debian/Ubuntu)**  
```bash
sudo apt install google-chrome-stable
wget https://chromedriver.storage.googleapis.com/$(curl -sS chromedriver.storage.googleapis.com/LATEST_RELEASE)/chromedriver-linux64.zip
unzip chromedriver-linux64.zip
sudo mv chromedriver /usr/local/bin/
```

#### **For macOS (Using Homebrew)**
```bash
brew install --cask google-chrome
brew install chromedriver
```

#### **For Windows**
1. Download **Google Chrome** from [here](https://www.google.com/chrome/).
2. Download **ChromeDriver** from 👉 [ChromeDriver Site](https://sites.google.com/chromium.org/driver/).
3. Extract `chromedriver.exe` and place it in `C:\Windows\System32\`.

---

### ✅ **Step 5: (Optional) Install TOR for Proxy Rotation**  
If you want **TOR-based proxy rotation**, install TOR.

#### **For Linux**  
```bash
sudo apt install tor
sudo systemctl start tor
```

#### **For macOS**  
```bash
brew install tor
brew services start tor
```

#### **For Windows**  
Download and install TOR from 👉 [Tor Project](https://www.torproject.org/download/).

---

## 🚀 **Usage**
Once everything is installed, run XSSRock using the following commands:

### 🔍 **Scan a Single URL**
```bash
python3 xssrock.py -u "http://example.com/vuln.php?search=test"
```

### 📜 **Scan Multiple URLs from a File**
```bash
python3 xssrock.py -f urls.txt
```

### 🎯 **Use Custom Payloads**
```bash
python3 xssrock.py -p payloads.txt
```

### 🔄 **Enable Slack Notifications**
```bash
python3 xssrock.py -u "http://example.com" -w "https://hooks.slack.com/services/YOUR/WEBHOOK/URL"
```

---

## 📄 **Example Report Output (`xss_report_YYYYMMDD_HHMMSS.json`)**
```json
{
    "timestamp": "20250225_123456",
    "url": "http://example.com/vuln.php?search=test",
    "parameter": "search",
    "payload": "<script>alert(1)</script>"
}
```

---

## 🛡 **Legal Disclaimer**
This tool is intended for **educational purposes** and **authorized penetration testing** only.  
Do **not** use XSSRock to test applications without **explicit permission**.  
The developers are **not responsible** for any misuse of this tool.  

---

## ❤️ **Contributing**
1. **Fork** the repo  
2. **Create a new branch** (`git checkout -b feature-branch`)  
3. **Commit your changes** (`git commit -m "Added new feature"`)  
4. **Push to the branch** (`git push origin feature-branch`)  
5. **Create a Pull Request**  



🔥 **Happy Hacking! Stay Safe!** 🚀  

---
