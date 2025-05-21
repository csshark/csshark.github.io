---
layout: default
title: Robert Strzoda
---

# Robert Strzoda

<b>Future Purple Teamer | Cybersecurity Analyst</b>

---

## About Me

<div style="display: flex; align-items: center;">
  <img src="img.png" alt="Robert Strzoda" style="float: left; margin-right: 20px; height: 150px; width: 150px; border-radius: 50%;" />
  <div>
    <p>I’m a <strong>cybersecurity analyst</strong> with a passion for both offensive and defensive security. My expertise spans penetration testing, vulnerability research, and threat detection, as well as log analysis, SIEM management, and incident response. I stay up-to-date on the latest CVEs, attack vectors, and security trends to ensure robust protection for systems and networks. I am constantly practicing by solving CTFs, participating in red and blue team exercises, and deepening my knowledge in line with current cybersecurity trends.</p>
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

### **<span style="color: blue;">Blue</span> Team Skills**
- **Log Analysis & Monitoring**
- **SIEM Management**
- **Analyticlal Thinking**
- **Incident Response & Forensics**
- **Threat Intelligence & Hunting**
- **Endpoint Detection & Response (EDR)**
- **Extended Detection & Response (XDR)**

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

### 3. **PenMate - my personal helper**
   - Developed a Python script to automate API endpoint scanning & fuzzing for web applications.
   - Developed new C drivers for Signal/Network analysis and information gathering.
   - Created MQTT safety verification tool to enhance IoT security.

### 4. **Threat Intelligence Predictions**
   - Developed python program to predict what threat actor might do next.
   - Implemented integration with AI and .json list with common hacking open-source tools.
   - Tools used: IBM Watson, Python, js

---

## Certifications/Certificates

- **IBM Cybersecurity Analyst Professional Certificate**
- **HTB CTPS (in progress)**
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

| **Tool**           | **Purpose**                          |
|:-------------------|:-------------------------------------|
| **<span style="color: blue;">SonarQube</span>** | Security Code Inspection (SAST) |
| **<span style="color: blue;">bearer</span>** | Security Code Inspection Tool (SAST) |
| **<span style="color: blue;">Splunk</span>** | SIEM for log analysis and monitoring |
| **<span style="color: blue;">QRadar</span>** | SIEM for threat detection and response |
| **<span style="color: blue;">Lynis</span>** | Security auditing and compliance tool |
| **<span style="color: blue;">Snort</span>** | Network intrusion detection system   |
| **<span style="color: blue;">OSSEC</span>** | Host-based intrusion detection system |
| **<span style="color: red;">Burp Suite</span>** | Web application security testing     |
| **<span style="color: red;">jwt.io</span>** | JSON Web Token (JWT) Debugger        |
| **<span style="color: red;">Sublist3r</span>** | Reconnaissance in web penetration testing |
| **<span style="color: red;">Wfuzz</span>** | Web application fuzzing              |
| **<span style="color: red;">HashCat</span>** | Password cracking, brute force attacks |
| **<span style="color: red;">John The Ripper</span>** | Password cracking, hybrid attacks    |
| **<span style="color: red;">OWASP ZAP</span>** | Web application security general scanning |
| **<span style="color: red;">Silver C2</span>** | Post-Exploitation framework          |
| **<span style="color: red;">SearchSploit</span>** | Exploit identification                |
| **<span style="color: red;">XSStrike</span>** | XSS vulnerability discovery helper   |
| **<span style="color: red;">RADAR</span>** | DNS footprint-based resource detection |
| **<span style="color: purple;">CyberChef</span>** | Data decoding, encoding, and analysis |
| **<span style="color: purple;">Nmap</span>** | Network scanning                     |
| **<span style="color: purple;">Wireshark</span>** | Network traffic analysis             |
| **<span style="color: purple;">Scapy</span>** | Network packet preparation           |
| **<span style="color: purple;">Nessus</span>** | Vulnerability scanning and assessment |
| **<span style="color: purple;">OpenVAS</span>** | Vulnerability scanning and management |
| **<span style="color: purple;">Atomic Red Team</span>** | Automated attack simulations based on MITRE ATT&CK |
| **<span style="color: purple;">Velociraptor</span>** | Endpoint monitoring and forensic analysis |
| **<span style="color: purple;">Shodan</span>** | Search engine for internet-connected devices |

---

## Code Snippets

Here’s a snippet of a Python script I wrote to automate API endpoint scanning & fuzzing in order to solve CTF:

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
