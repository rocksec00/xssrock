# 🔥 XSSRock - Automated XSS Scanner  
### 🚀 Advanced XSS Detection Suite by RockSec  

Here are the **Linux terminal** steps to install the necessary dependencies and set up your environment:

### **Step 1: Update Your System**
Before installing anything, update your package list:
```sh
sudo apt update && sudo apt upgrade -y
```

---

### **Step 2: Install Python and pip**
Check if Python is installed:
```sh
python3 --version
```
If not, install it:
```sh
sudo apt install python3 python3-pip -y
```

---

### **Step 3: Set Up a Virtual Environment (Optional but Recommended)**
```sh
sudo apt install python3-venv -y  # Install virtualenv if not installed
python3 -m venv env  # Create a virtual environment
source env/bin/activate  # Activate the environment
```

---

### **Step 4: Install Required Python Packages**
```sh
pip install argparse requests selenium
```
> **Note:** The other modules like `random`, `time`, `json`, `base64`, `os`, `re`, `queue`, and `threading` are built-in and don’t require installation.

---

### **Step 5: Install Chrome & ChromeDriver**
1. **Install Google Chrome**
   ```sh
   wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
   sudo apt install ./google-chrome-stable_current_amd64.deb -y
   ```
   Verify installation:
   ```sh
   google-chrome --version
   ```

2. **Download and Install ChromeDriver**
   - First, find your **Chrome version**:
     ```sh
     google-chrome --version
     ```
   - Visit the [ChromeDriver download page](https://chromedriver.chromium.org/downloads) and download the version that matches your Chrome version.
   - Extract and move it to `/usr/local/bin`:
     ```sh
     wget https://chromedriver.storage.googleapis.com/<YOUR_VERSION>/chromedriver_linux64.zip
     unzip chromedriver_linux64.zip
     sudo mv chromedriver /usr/local/bin/
     chmod +x /usr/local/bin/chromedriver
     ```
   - Verify installation:
     ```sh
     chromedriver --version
     ```
### **Step 6: You're Ready to Go!**
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







cron job 

```bash
* * * * * /bin/bash -c 'source /home/ubuntu/.venv/bin/activate && python3 path/to/xss.py -u http://testphp.vulnweb.com/search.php?test=12 -p /path/to/payload/file or-directory/  -w webhookurl  -t 20 >> path/to/saved/xss_$(date +\%Y-\%m-\%d_\%H-\%M-\%S).log 2>&1'
```

