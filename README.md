# Analyzing Types of Web Application Attacks

This project provides a comprehensive guide for understanding and simulating web application attacks using tools like **WebGoat**, **Burp Suite**, and **DVWA (Damn Vulnerable Web Application)**. It is aimed at cybersecurity professionals and students looking to strengthen their practical knowledge of web vulnerabilities.

---

## Project Link

Explore project documentation: [Analyzing Types of Web Application Attacks](https://github.com/StephVergil/Analyzing-Types-of-Web-Application-Attacks/blob/main/Analyzing%20Types%20of%20Web%20Application%20Attacks.docx)

---

## Overview

### Topics Covered:
1. **SQL Injection Basics**  
   - Manual exploitation using WebGoat.  
   - Automatic exploitation with SQLmap.  
2. **Using Burp Suite**  
   - Intercepting and manipulating HTTP requests.  
   - Exploiting vulnerabilities like SQL Injection.  
3. **DVWA Setup and Attacks**  
   - Preparing a vulnerable environment.  
   - Extracting sensitive data using SQL Injection.  

### Tools Used:
- **WebGoat**: A deliberately insecure application for learning web security.  
- **Burp Suite**: A powerful platform for testing web application security.  
- **DVWA**: A PHP/MySQL web application designed to be vulnerable.  
- **SQLmap**: An automated SQL Injection tool.

---

## Instructions

### 1. WebGoat for SQL Injection
- **Setup**:
  1. Launch the Kali VM and start the WebGoat Docker container:
     ```bash
     sudo docker run --rm -it webgoat/goatandwolf
     ```
  2. Access WebGoat in the browser:
     ```
     http://172.17.0.2:8080/WebGoat/login
     ```
  3. Register a new user with:
     - **Username**: `guestuser`
     - **Password**: `guestuser`

- **SQL Injection Tasks**:
  - Complete lessons focusing on crafting malicious SQL queries to extract data.  
  - Explore challenges involving multi-field injection.

### 2. Burp Suite
- **Setup**:
  1. Launch Burp Suite and start a **Temporary Project**.  
  2. Enable HTTP request interception and open the WebGoat login page.  

- **Task**:
  - Use the **Repeater** tool to manipulate SQL queries and achieve unauthorized access.  

### 3. DVWA for SQL Injection
- **Setup**:
  1. Start the DVWA server using Docker:
     ```bash
     sudo docker run --rm -it -p 4444:80 vulnerables/web-dvwa
     ```
  2. Access DVWA:
     ```
     http://192.168.0.6:4444
     ```
  3. Log in with:
     - **Username**: `admin`  
     - **Password**: `password`

- **Task**:
  - Use **Burp Suite** to gather information for SQLmap.  
  - Execute SQLmap to dump sensitive data:
    ```bash
    sqlmap -u "http://192.168.0.6:4444/vulnerabilities/sqli/?id=fakeid&Submit=Submit" \
      --cookie "PHPSESSID=tded69hra57jaiha981q516843; security=low" --dump
    ```

---

## Learning Objectives
1. Understand the principles behind SQL Injection attacks.  
2. Gain hands-on experience with security tools like Burp Suite and SQLmap.  
3. Simulate real-world web application vulnerabilities in a controlled environment.  

---

## Resources
- [WebGoat Documentation](https://owasp.org/www-project-webgoat/)
- [Burp Suite Guide](https://portswigger.net/burp/documentation)
- [SQLmap Official Documentation](https://sqlmap.org/)
- [DVWA GitHub Repository](https://github.com/digininja/DVWA)

---

### Disclaimer
This project was conducted in a controlled environment. Unauthorized use of these techniques or tools outside such an environment may violate ethical guidelines and legal regulations.

---

> **Author**: Stephanie Vergil  
