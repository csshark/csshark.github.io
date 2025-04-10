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

---

## Projects

### 1. **SDR-CAP**
   - Migrated OpenWifi image to grant full support from Analog Devices.
   - Customized build instruction to allow everyone develop his own solution.
   - Developed sniffer driver and compiled it into FPGA board.
   - Tools used: Vivado, gcc, bash

### 2. **PenMate - my personal helper**
   - Developed a Python script to automate API endpoint scanning & fuzzing for web applications.
   - Developed new C drivers for Signal/Network analysis and information gathering.
   - [View on GitHub](https://github.com/csshark/pen-mate).

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

---

## Code Snippets

Here’s a snippet of a Python script I wrote to automate API endpoint scanning & fuzzing:

```python
async def discover_api_endpoints(session, url):
    print(f"Discovering API endpoints on {url}...")
    endpoints = set()
    try:
        async with session.get(url, timeout=TIMEOUT) as response:
            text = await response.text()
            soup = BeautifulSoup(text, "html.parser")
            # Find all links
            for link in soup.find_all("a", href=True):
                href = link["href"]
                full_url = urljoin(url, normalize_path(href))
                endpoints.add(full_url)
            # Find all forms
            for form in soup.find_all("form"):
                action = form.get("action")
                method = form.get("method", "GET").upper()  # set default to GET if method is not specified
                inputs = [input_tag.get("name") for input_tag in form.find_all("input")]
                if action:
                    full_url = urljoin(url, normalize_path(action))
                    endpoints.add((full_url, method, inputs))  # Store form details
            # Find all API endpoints (e.g., Swagger/OpenAPI)
            swagger_url = urljoin(url, "/api-docs/v1/openapi.json")
            swagger_data = await check_swagger_docs(session, swagger_url)
            if swagger_data:
                swagger_endpoints = parse_swagger_docs(swagger_data, url)
                endpoints.update(swagger_endpoints)
    except Exception as e:
        print(f"Error discovering endpoints: {e}")
    return list(endpoints)
```
