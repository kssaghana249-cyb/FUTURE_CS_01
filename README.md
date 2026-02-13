# Vulnerability Assessment Report – Task 1

Intern Name: Saghana K S  
Track: Cybersecurity  
Task Code: FUTURE_CS_01  
Internship Program: Future Interns  
Date: 31-01-2026  

---

## Project Overview

This project presents a basic vulnerability assessment conducted on a publicly accessible web application as part of a cybersecurity internship task.

The objective of this assessment was to identify common security misconfigurations using passive and manual observation techniques without performing exploitation or intrusive testing.

Target Website: http://testphp.vulnweb.com

---

## Scope of Assessment

The assessment was limited to publicly accessible components of the target website.

The focus areas included:

- Missing HTTP security headers  
- Use of insecure communication protocol (HTTP instead of HTTPS)  
- Server and application information disclosure  

No automated scanning tools, exploitation, or intrusive techniques were used.

---

## Tools Used

- Web Browser Developer Tools  
- Manual observation and inspection  
- HTTP response header analysis  

---

## Assessment Methodology

The assessment was conducted using a passive and manual testing approach:

1. Inspected HTTP response headers using browser developer tools  
2. Verified absence of HTTPS through browser address bar  
3. Reviewed page source for information disclosure  
4. Documented all observations without interacting with or modifying the system  

All findings were based solely on publicly available information.

---

## Findings Summary

### Finding 1: Missing HTTP Security Headers

**Risk Level:** Medium  

**Description:**  
The website does not implement recommended HTTP security headers such as:

- X-Frame-Options  
- X-Content-Type-Options  
- Content-Security-Policy  

**Impact:**  
May increase risk of clickjacking, XSS, and content-type sniffing attacks.

**Recommended Remediation:**

- Implement X-Frame-Options  
- Implement X-Content-Type-Options  
- Configure Content-Security-Policy  
- Enable Strict-Transport-Security  

---

### Finding 2: Unencrypted Communication (Missing HTTPS)

**Risk Level:** High  

**Description:**  
The application is accessible via HTTP and does not enforce HTTPS.

**Impact:**

- Man-in-the-Middle (MITM) attacks  
- Exposure of login credentials  
- Session data interception  
- Browser “Not Secure” warnings  

**Recommended Remediation:**

- Implement HTTPS using valid SSL/TLS certificate  
- Redirect HTTP to HTTPS  
- Enable HSTS  
- Monitor certificate validity regularly  

---

### Finding 3: Information Disclosure via Client-Side Code

**Risk Level:** Low  

**Description:**  
The page source reveals technical details including:

- HTML 4.01 Transitional document type  
- Character encoding (iso-8859-2)  
- JavaScript functions and external scripts  
- PHP-based application references  
- Comments indicating test application  

**Impact:**

- Assists attackers in fingerprinting technologies  
- Helps identify potential vulnerabilities  
- Exposes unnecessary internal details  

**Recommended Remediation:**

- Remove unnecessary comments  
- Avoid exposing implementation details  
- Use modern secure configurations  
- Regularly review publicly accessible content  

---

## Risk Classification Overview

| Risk Level | Description |
|------------|------------|
| Low | Minimal security impact but may assist attackers |
| Medium | Moderate security risk requiring remediation |
| High | Critical security issue that should be addressed immediately |

---

## Ethical Considerations

This vulnerability assessment was conducted strictly for educational purposes as part of the Future Interns Cybersecurity Internship program.

No exploitation, intrusive testing, automated scanning, or system manipulation was performed.

All observations were limited to publicly accessible information to ensure the confidentiality, integrity, and availability of the target system were not impacted.

---

## Repository Contents

- Vulnerability Assessment Report (PDF)
- Evidence screenshots (inside Evidence folder)
- Documentation of methodology

---

## Disclaimer

This project was completed for academic and internship evaluation purposes only.

The assessment was conducted using passive observation techniques without exploiting or harming the target system.

The target website used in this report is a publicly available test environment intended for security practice and learning.

This repository is intended solely for educational demonstration of cybersecurity concepts.

