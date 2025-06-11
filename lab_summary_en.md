# Lab Summary (EN)

This lab focused on deploying and protecting a vulnerable web application using open-source tools. The process included:
- Deploying WebGoat on CentOS with Docker
- Scanning with OWASP ZAP and Burp Suite
- Configuring a reverse proxy (nginx) on Debian
- Enabling ModSecurity with OWASP CRS 4.9.0
- Comparing scan results before and after WAF
- Launching the Spring4Shell exploit via Metasploit

With no protection, the application was vulnerable to SQLi, XSS, Spring4Shell, and more. After WAF deployment, most attacks were blocked, including the exploit. This demonstrates effective web application hardening using ModSecurity and open-source tools.
