# 🔥 XSSRock - Automated XSS Scanner  
### 🚀 Advanced XSS Detection Suite by RockSec  

###Set Up a Virtual Environment (Optional but Recommended)**
```sh
sudo apt install python3-venv -y  # Install virtualenv if not installed
python3 -m venv env  # Create a virtual environment
source env/bin/activate  # Activate the environment
```

**Before use you need to collect query parameters so use below tool to collect**

```sh
 git clone https://github.com/0xKayala/ParamSpider
 cd ParamSpider
 pip3 install -r requirements.txt
```
After install use below one liner to collect all query parameters

```sh
python3 paramspider.py --domain bugcrowd.com --exclude woff,css,js,png,svg,php,jpg --output params.txt && cat params.txt | httpx-toolkit > paramlive.txt
```
Use this query parameters to test find the xss vulnerability

*Here are the **Linux terminal** steps to install the necessary dependencies and set up your environment:*

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

### **Step 3: Install Required Python Packages**
```sh
pip install argparse requests selenium
```
> **Note:** The other modules like `random`, `time`, `json`, `base64`, `os`, `re`, `queue`, and `threading` are built-in and don’t require installation.

---

### **Step 4: Install Chrome & ChromeDriver**
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
### **Step 5: You're Ready to Go!**

   ```bash
 git clone https://github.com/rocksec00/xssrock/
 cd xssrock
   ```


1. Make the script executable:
   ```bash
   chmod +x xssrock
   ```
   
2. If you want to Run Globally Move or Copy the script to `/usr/local/bin`:
   
   For Move
   
   ```bash
   mv xssrock /usr/local/bin
   ```
   For Copy
   
      ```bash
   cp xssrock /usr/local/bin
   ```
   
3. Help
   ```bash
   xssrock -h

Once everything is installed, run XSSRock using the following commands: 

Note: If you enable golbal access ignore **Python3**

### 🔍 **Scan a Single URL**
```bash
python3 xssrock -u "http://testphp.vulnweb.com/admin/?C=FUZZ"
```

### 📜 **Scan Multiple URLs from a File**
```bash
python3 xssrock -f urls.txt
```

### 🎯 **Use Custom Payloads** **(File or directory)**
```bash
python3 xssrock -p payloads.txt
```

### 🎯 **Use Proxy** 

```bash
python3 xssrock --proxy path/to/proxylist
```

### 🔄 **Enable Slack Notifications**
```bash
python3 xssrock -u "http://testphp.vulnweb.com/admin/?C=FUZZ" -w "https://hooks.slack.com/services/YOUR/WEBHOOK/URL"
```
Test webhook site - https://webhook.site/

---

## 📄 **Example Report Output (`xss_report_YYYYMMDD_HHMMSS.json`)**
```json
{
    "timestamp": "20250225_123456",
    "url": "http://testphp.vulnweb.com/admin/?C=FUZZ",
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

🔥 **Happy Hacking! Stay Safe!** 🚀  

---







cron job 

```bash
* * * * * /bin/bash -c 'source /home/ubuntu/.venv/bin/activate && python3 path/to/xss.py -u http://testphp.vulnweb.com/search.php?test=12 -p /path/to/payload/file or-directory/  -w webhookurl  -t 20 >> path/to/saved/xss_$(date +\%Y-\%m-\%d_\%H-\%M-\%S).log 2>&1'
```

