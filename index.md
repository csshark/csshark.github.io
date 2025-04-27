---
layout: default
title: Robert Strzoda
---

# Robert Strzoda

<b>Penetration Tester | Ethical Hacker</b>

---

## About Me

<div style="display: flex; align-items: center;">
  <img src="img.png" alt="Robert Strzoda" style="float: left; margin-right: 20px; height: 150px; width: 150px; border-radius: 50%;" />
  <div>
    <p>I’m a <strong>penetration tester</strong> and <strong>ethical hacker</strong> with a passion for uncovering vulnerabilities and securing systems. I stay up-to-date on the latest CVEs, attack vectors, and security trends to ensure robust protection for web applications, networks, and source code. I am constantly practicing by solving CTFs and deepening my knowledge, and consolidating practices in line with current cyber security trends.</p>
  </div>
</div>

---

## Skills

Here are some of the skills I bring to the table:

- **Web Application Penetration Testing**
- **Source Code Security Audits**
- **Network Security Assessments**
- **Vulnerability Research & Exploitation**
- **Automation with Python & Bash**
- **Over 2 years experience with Linux OS family** 
- **LLM Penetration Testing**
---

## Projects

### 1. **AIpocalypse**
   - Stored most of known AI payloads in a .json file.
   - Created Python program that iterates trough payloads and sends them as an input to AI models.
   - The number of payloads successfully completed (ERROR or leakage of confidential data) so far: 56
   - [View on Github](https://github.com/csshark/AIpocalypse).

### 2. **SDR-CAP**
   - Migrated OpenWifi image to grant full support from Analog Devices.
   - Customized build instruction to allow everyone develop his own solution.
   - Developed sniffer driver and compiled it into FPGA board.
   - Tools used: Vivado, gcc, bash

### 3. **PenMate - my personal helper**
   - Developed a Python script to automate API endpoint scanning & fuzzing for web applications.
   - Developed new C drivers for Signal/Network analysis and information gathering.
   - Created MQTT safety verification tool to enchance IoT secuirty.

---

## Certifications/Certificates

- **IBM Cybersecurity Analyst Professional Certificate**
- **HTB CTPS (in progress)**
- **OSCP (in progress)**

---

## Contact Me

Let’s connect and discuss how I can help by discovering vulnerabilities in your infrastructure!

- **Email**: [rstrzoda@zohomail.eu](mailto:rstrzoda@zohomail.eu)
- **GitHub**: [csshark](https://github.com/csshark)
- **LinkedIn**: [Robert Strzoda](https://www.linkedin.com/in/robertstrzoda)

---

## Tools I Use

Here’s a list of tools I frequently use:

| Tool           | Purpose                          |
|:---------------|:---------------------------------|
| **Burp Suite** | Web application security testing |
| **Sublist3r**  | Reconnaissance in web application penetration testing | 
| **Wfuzz**      | Web application fuzzing |
| **CyberChef**  | Data decoding, encoding, and analysis tool | 
| **HashCat**    | Password cracking, brute force attacks | 
| **John The Ripper** | Pasword cracking, hybrid attacks |
| **OWASP ZAP**  | Web application security general scanning |
| **Metasploit** | Exploitation framework           |
| **Nmap**       | Network scanning                 |
| **Wireshark**  | Network traffic analysis         |
| **Scapy**      | Network packet preparation |
| **Nikto**      | Web server vulnerability scanning |
| **SonarQube**  | Security Code Inspection | 
| **XSStrike**   | My personal best XSS vulnerability discovery helper | 
| **RADAR**      | Recon tool developed to detect resources by DNS footprint |  

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
