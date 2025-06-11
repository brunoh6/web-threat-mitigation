# web-threat-mitigation
Hands-on lab on detecting and mitigating web app threats using OWASP ZAP, Burp Suite, and ModSecurity WAF (with OWASP CRS). Case study: Spring4Shell (CVE-2022-22965). Local Docker-based setup.

# Web Threat Mitigation Lab – OWASP ZAP, ModSecurity & CVE Exploitation

This repository documents a lab focused on simulating, analyzing, and mitigating common web application threats. It includes installation of vulnerable targets, scanning tools, deployment of a WAF (ModSecurity with OWASP CRS), and a live exploitation of CVE-2022-22965 (Spring4Shell).

## Lab Objectives

- Deploy a vulnerable web application (WebGoat) using Docker
- Perform vulnerability scanning using OWASP ZAP and Burp Suite
- Setup a reverse proxy using Nginx + ModSecurity + OWASP CRS 4.9.0
- Analyze results before and after WAF implementation
- Exploit Spring4Shell and verify WAF effectiveness

## Tools Used

- Docker + Docker Compose
- OWASP ZAP and Burp Suite
- ModSecurity (via libnginx-mod-http-modsecurity)
- OWASP Core Rule Set (CRS 4.9.0)
- Kali Linux with Metasploit Framework
- CentOS 9 Stream & Debian 12

## Lab Workflow

1. **WebGoat Deployment** on CentOS using Docker, exposed on port 8080.
2. **Initial Scanning** from Kali Linux using OWASP ZAP:
   - High-risk alerts: SQL Injection, Spring4Shell
   - Medium: Missing CSP, CSRF Tokens, Parameter Tampering
   - Info: Version leaks, potential XSS, session issues
3. **Reverse Proxy Deployment** on Debian 12 using nginx.
4. **WAF Setup** with OWASP CRS and rules loaded from:
   ```
   /etc/nginx/coreruleset-4.9.0/crs-setup.conf
   /etc/nginx/coreruleset-4.9.0/rules/*.conf
   ```
   Rules were tested and enabled by checking ModSecurity logs.
5. **Post-WAF Scanning** using OWASP ZAP showed:
   - Reduced alerts (blocked or masked responses)
   - Confirmation of WAF protection in place
6. **Exploit Testing** using Metasploit against Spring4Shell:
   - Without WAF: RCE successful (reverse shell payload)
   - With WAF: Exploit blocked due to CRS detection

## Conclusion

The lab shows the importance of layered security:
- A vulnerable app can be exposed easily without protection
- ZAP/Burp help identify and categorize vulnerabilities
- ModSecurity and OWASP CRS effectively reduce attack surface
- WAFs can block real-world CVEs like Spring4Shell with proper tuning

## Structure

web-threat-mitigation-lab/
├── README.md
├── lab_summary_en.md
├── lab_summary_es.md
└── screenshots/
