# Analyzing Types of Web Application Attacks

This project offers an in-depth exploration of web application vulnerabilities, attack simulation, and defensive techniques. It uses tools such as **WebGoat**, **Burp Suite**, **DVWA (Damn Vulnerable Web Application)**, and **SQLmap**, providing cybersecurity practitioners and learners with actionable insights into identifying and exploiting security weaknesses.

---

## Project Link

Explore project documentation: [Analyzing Types of Web Application Attacks](https://github.com/StephVergil/Analyzing-Types-of-Web-Application-Attacks/blob/main/Analyzing%20Types%20of%20Web%20Application%20Attacks.docx)

---

## Overview

### Topics Covered:
1. **SQL Injection Fundamentals**  
   - Principles of SQL Injection, vulnerabilities, and exploitation techniques.  
   - Using both manual methods (WebGoat) and automated tools (SQLmap) for attack execution.
2. **Burp Suite for Security Testing**  
   - Intercepting, modifying, and replaying HTTP requests.  
   - Simulating attacks to identify application weaknesses, including SQL Injection.  
3. **DVWA Setup and Practical Attacks**  
   - Configuring a deliberately insecure environment.  
   - Conducting targeted attacks to extract sensitive data and evaluate defense mechanisms.  
4. **Advanced Analysis and Mitigation**  
   - Understanding vulnerabilities from a development and operational perspective.  
   - Implementing best practices to mitigate risks associated with common attacks.

### Tools Used:
- **WebGoat**: OWASP's interactive and insecure web application for learning web vulnerabilities.  
- **Burp Suite**: A comprehensive platform for web application security assessment.  
- **DVWA**: A PHP/MySQL-based application designed for testing security tools and learning common exploits.  
- **SQLmap**: A specialized tool for automating the detection and exploitation of SQL Injection flaws.  

---

## Instructions

### 1. WebGoat for SQL Injection

#### Setup:
1. Launch the WebGoat Docker container:
   ```bash
   sudo docker run --rm -it webgoat/goatandwolf
   ```
2. Access the application:
   ```
   http://172.17.0.2:8080/WebGoat/login
   ```
3. Register a user:
   - **Username**: `guestuser`  
   - **Password**: `guestuser`  

#### Tasks:
- Complete lessons on SQL Injection to understand how malicious queries can exploit vulnerabilities.  
- Experiment with multi-field injections to extract comprehensive datasets.
- Explore scenarios like bypassing authentication mechanisms.

---

### 2. Burp Suite for HTTP Request Analysis

#### Setup:
1. Open Burp Suite and start a **Temporary Project**.  
2. Configure the browser to use Burp Suite as a proxy.  
3. Enable interception and access WebGoat or other applications.

#### Tasks:
- Use the **Repeater** module to manipulate and resend SQL queries.
- Analyze responses to identify weaknesses and demonstrate unauthorized access.
- Generate proof-of-concept exploits based on observed vulnerabilities.

---

### 3. DVWA for Hands-On Attacks

#### Setup:
1. Start DVWA using Docker:
   ```bash
   sudo docker run --rm -it -p 4444:80 vulnerables/web-dvwa
   ```
2. Access DVWA:
   ```
   http://192.168.0.6:4444
   ```
3. Log in with credentials:
   - **Username**: `admin`  
   - **Password**: `password`  

#### Tasks:
- Evaluate low, medium, and high-security levels within DVWA.
- Perform SQL Injection attacks manually and automate them using SQLmap:
   ```bash
   sqlmap -u "http://192.168.0.6:4444/vulnerabilities/sqli/?id=fakeid&Submit=Submit" \
     --cookie "PHPSESSID=tded69hra57jaiha981q516843; security=low" --dump
   ```
- Extract database contents to understand the severity of vulnerabilities.

---

## Learning Objectives

1. **Attack Mechanics**: Grasp how attackers exploit SQL Injection vulnerabilities to retrieve or manipulate data.
2. **Tool Mastery**: Gain expertise in using tools like Burp Suite and SQLmap to conduct security testing.
3. **Controlled Environments**: Learn to configure and test insecure applications safely, avoiding ethical and legal risks.
4. **Mitigation Strategies**: Identify effective coding practices and security configurations to prevent exploitation.

---

## Resources

- [WebGoat Documentation](https://owasp.org/www-project-webgoat/): Step-by-step guides for leveraging WebGoat effectively.  
- [Burp Suite Guide](https://portswigger.net/burp/documentation): Comprehensive documentation for all Burp Suite features.  
- [SQLmap Official Documentation](https://sqlmap.org/): Advanced usage examples and parameters for SQLmap.  
- [DVWA GitHub Repository](https://github.com/digininja/DVWA): Source code and setup instructions for DVWA.  
- [OWASP Top Ten](https://owasp.org/www-project-top-ten/): An essential reference for understanding the most critical web application vulnerabilities.

---

### Disclaimer
This project was conducted in a controlled environment. Unauthorized use of these techniques or tools outside such an environment may violate ethical guidelines and legal regulations.

---

> **Author**: Stephanie Vergil

