---
layout: default
title: Robert Strzoda
---

# Robert Strzoda

<b>Future Purple Teamer | Security Engineer</b>

---

## About Me

<div style="display: flex; align-items: center;">
  <img src="img.png" alt="Robert Strzoda" style="float: left; margin-right: 20px; height: 150px; width: 150px; border-radius: 50%;" />
  <div>
    <p>I’m a <strong>cybersecurity engineer</strong> with a passion for both offensive and defensive security. My expertise spans penetration testing, vulnerability research, and threat detection, as well as log analysis, SIEM management, and incident response. I stay up-to-date on the latest CVEs, attack vectors, and security trends to ensure robust protection for systems and networks. I am constantly practicing by solving CTFs, participating in red and blue team exercises, and deepening my knowledge in line with current cybersecurity trends.</p>
  </div>
</div>

---

## Skills

### **<span style="color: red;">Red</span> Team Skills**
- **Web Application Penetration Testing**
- **Network Security Assessments**
- **Vulnerability Research & Exploitation**
- **Automation with Python & Bash**
- **LLM Penetration Testing**
- **PoC/Reporting**
- **Scripting (Python,bash)**
- **Payload Development (Ruby)**

### **<span style="color: blue;">Blue</span> Team Skills**
- **Log Analysis & Monitoring**
- **SIEM Management**
- **Analyticlal Thinking**
- **Incident Response & Forensics**
- **Threat Intelligence & Hunting**
- **Endpoint Detection & Response (EDR)**
- **Extended Detection & Response (XDR)**
- **Identity and Access Management(IAM)**
- **Governance, Risk, and Compliance (GRC)**

---

## Projects

### 1. **AIpocalypse**
   - Stored most known AI payloads in a .json file.
   - Created Python program that iterates through payloads and sends them as input to AI models.
   - The number of payloads successfully completed (ERROR or leakage of confidential data) so far: 56
   - [View on Github](https://github.com/csshark/AIpocalypse).

### 2. **SDR-CAP**
   - Migrated OpenWifi image to grant full support from Analog Devices.
   - Customized build instruction to allow everyone to develop their own solution.
   - Developed sniffer driver and compiled it into FPGA board.
   - Tools used: Vivado, gcc, bash

### 3. **FormPoison - Form Inputs Fuzzer**
   - Created payloads file and separated them into categories.
   - Devoloped python script to find web frameworks, bad headers and support cookie verification.
   - Tools used: python, python-requests.

### 4. **Threat Intelligence Predictions**
   - Developed python program to predict what threat actor might do next.
   - Implemented integration with AI and .json list with common hacking open-source tools.
   - Tools used: IBM Watson, Python, js

---

## ☁️ Cloud Environments I worked with

<p align="left">
  <a href="https://aws.amazon.com/" target="_blank">
    <img src="https://www.logo.wine/a/logo/Amazon_Web_Services/Amazon_Web_Services-Logo.wine.svg" alt="AWS" width="50" height="50"/>
  </a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://azure.microsoft.com/" target="_blank">
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/azure/azure-original.svg" alt="Azure" width="50" height="50"/>
  </a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://cloud.google.com/" target="_blank">
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/googlecloud/googlecloud-original.svg" alt="Google Cloud" width="50" height="50"/>
  </a>
</p>

## Certifications/Certificates

- **IBM Cybersecurity Analyst Professional Certificate**
- **BurpSuite Certified Practicioner (in progress)**
- **CPTAv2 (in progress)**
- **CompTIA Security+ (planned)**

---

## Contact Me

Let’s connect and discuss how I can help secure your infrastructure!

- **Email**: [rstrzoda@zohomail.eu](mailto:rstrzoda@zohomail.eu)
- **GitHub**: [csshark](https://github.com/csshark)
- **LinkedIn**: [Robert Strzoda](https://www.linkedin.com/in/robertstrzoda)

---

## My Tools

Here’s a list of tools I frequently use:

| **Tool**           | **Purpose**                         |
|:-------------------|:-------------------------------------|
| 🔵 **SonarQube**        | Security Code Inspection (SAST)     |
| 🔵 **ELK Stack**   | Log analytics, document search, security information and event management (SIEM) |  
| 🔵 **bearer**           | Security Code Inspection Tool (SAST) |
| 🔵 **Fortify**          | Static Code Analyzer                 |
| 🔵 **Splunk**           | SIEM for log analysis and monitoring |
| 🔵 **QRadar**           | SIEM for threat detection and response |
| 🔵 **Lynis**            | Security auditing and compliance tool |
| 🔵 **Snort**            | Network intrusion detection system   |
| 🔵 **OSSEC**            | Host-based intrusion detection system |
| 🔴 **Burp Suite**       | Web application security testing     |
| 🔴 **jwt.io**           | JSON Web Token (JWT) Debugger        |
| 🔴 **Sublist3r**        | Reconnaissance in web penetration testing |
| 🔴 **Wfuzz**            | Web application fuzzing              |
| 🔴 **HashCat**          | Password cracking, brute force attacks |
| 🔴 **John The Ripper**  | Password cracking, hybrid attacks    |
| 🔴 **OWASP ZAP**        | Web application security general scanning |
| 🔴 **Silver C2**        | Post-Exploitation framework          |
| 🔴 **SearchSploit**     | Exploit identification                |
| 🔴 **XSStrike**         | XSS vulnerability discovery helper   |
| 🔴 **RADAR**            | DNS footprint-based resource detection |
| 🔴 **DeepSeek AI**      | Exploit research, offensive security tasks, payloads |
| 🟣 **CyberChef**        | Data decoding, encoding, and analysis |
| 🟣 **Nmap**             | Network scanning                     |
| 🟣 **Wireshark**        | Network traffic analysis             |
| 🟣 **Scapy**            | Network packet preparation           |
| 🟣 **Nessus**           | Vulnerability scanning and assessment |
| 🟣 **OpenVAS**          | Vulnerability scanning and management |
| 🟣 **Atomic Red Team**  | Automated attack simulations based on MITRE ATT&CK |
| 🟣 **Velociraptor**     | Endpoint monitoring and forensic analysis |
| 🟣 **Shodan**           | Search engine for internet-connected devices |

---

## Code Snippets

Here’s a snippet of a Python script I wrote to automate API endpoint scanning & fuzzing in order to solve CTF (usually my scripts are Python+requests library):

```python

async def fuzz_endpoint(session, endpoint, extended_scan=False):
    vulnerabilities = []

    # Skip non-form endpoints
    if not isinstance(endpoint, tuple) or len(endpoint) != 3:
        return vulnerabilities

    url, method, inputs = endpoint

    # Skip the Werkzeug debugger console
    if "console" in url:
        return vulnerabilities

    for payload in get_fuzz_payloads(extended_scan):
        try:
            # Prepare data for POST or GET
            data = {input_name: payload for input_name in inputs} if inputs else {"input": payload}

            # Send request based on form method
            if method == "POST":
                await asyncio.sleep(REQUEST_DELAY)
                async with session.post(url, data=data, timeout=TIMEOUT) as response:
                    text = await response.text()
                    if response.status == 200 and len(text) > 0:
                        vulnerabilities.append(f"Potential vulnerability at {url} with payload: {payload}")
            else:  # Default to GET
                await asyncio.sleep(REQUEST_DELAY)
                async with session.get(url, params=data, timeout=TIMEOUT) as response:
                    text = await response.text()
                    if response.status == 200 and len(text) > 0:
                        vulnerabilities.append(f"Potential vulnerability at {url} with payload: {payload}")

        except Exception as e:
            print(f"Error fuzzing {url}: {e}")

    return vulnerabilities

    except Exception as e:
        print(f"Error discovering endpoints: {e}")
    return list(endpoints)
```
