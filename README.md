# Security Automation Script

This script automates several security testing tools for comprehensive vulnerability assessment of web applications.

### Steps:

1. **Nmap Scan:**
   ```bash
   nmap -sV -A -p- --script vuln <target_ip>

Replace <target_ip> with the IP address of the target you want to scan.
Performs a service version detection and vulnerability scan using Nmap.
Nikto Scan:

bash
Copy code
nikto -h <target_url> -Tuning 9 -maxtime 2h
Replace <target_url> with the URL of the target you want to scan.
Executes Nikto with aggressive tuning and a maximum runtime of 2 hours for detailed vulnerability checks.
WPScan:

bash
Copy code
wpscan --url <target_url> --enumerate ap,at,tt,cb,dbe,u,m --random-user-agent
Replace <target_url> with the URL of the target WordPress site.
Performs enumeration of plugins, themes, users, and more using WPScan with randomized user-agent.
SQLMap:

bash
Copy code
sqlmap -u <target_url> --dbs --risk=3 --level=5 --tamper=space2comment,charencode --batch --random-agent --threads=10
Replace <target_url> with the URL vulnerable to SQL injection.
Conducts SQLMap with high risk and level settings, tampering options, and multi-threaded execution.
Dirb (Directory Brute-force):

bash
Copy code
dirb <target_url> -X .php,.asp,.aspx,.jsp,.html,.js
Replace <target_url> with the base URL to be bruteforced.
Utilizes Dirb to discover hidden files and directories with specified extensions.
Instructions:
Ensure you have the necessary tools (nmap, nikto, wpscan, sqlmap, dirb) installed and properly configured on your system.
Replace placeholders (<target_ip>, <target_url>) with actual target details before running each command.
Run these commands sequentially in a terminal or command prompt for thorough security testing of web applications.
