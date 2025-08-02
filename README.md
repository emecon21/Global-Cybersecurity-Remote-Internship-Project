# Web Application Security: OWASP Top 10 & Secure SDLC

> **Internship Project | Global Cybersecurity Remote Internship** 

## Author

**Emmanuel Olowoyo**  
Intern @ Wilses Cybersecurity  
(https://github.com/emecon21)

## Project Overview

This project involved the practical identification, exploitation, and documentation of the OWASP Top 10 web application vulnerabilities using the intentionally vulnerable **OWASP Juice Shop** application. It also demonstrates how secure coding principles and the NIST SP 800-64 Secure SDLC framework can be applied to mitigate these issues.


## Tools & Technologies Used

- **OWASP Juice Shop** (Web Browser Deployment)
- **Developer Tools (Chrome DevTools)**
- **Snyk** (Vulnerability Intelligence)
- **Heroku** (Original hosting platform, now deprecated)
- **Git & GitHub** (Version control and collaboration)


## OWASP Top 10 Vulnerabilities Identified

| # | Vulnerability | Description | Evidence | Suggested Mitigation |
|---|---------------|-------------|----------|-----------------------|
| 1 | Broken Access Control | Unauthorized users could access restricted admin functions via direct URL manipulation. | Forced browsing to `/admin` | Enforce access checks at the server side. |
| 2 | Cryptographic Failures | Sensitive data like passwords were not encrypted in transmission. | Interception using browser tools | Use HTTPS/TLS and encrypt sensitive data at rest. |
| 3 | Injection | SQL Injection vulnerability in login input. | Login with `' OR 1=1--` | Use parameterized queries and input validation. |
| 4 | Insecure Design | Default admin accounts with no forced password change. | Accessed admin with known credentials | Enforce secure onboarding and password policies. |
| 5 | Security Misconfiguration | Admin page and developer logs were exposed by default. | Found `/ftp` and `/logs` folders | Remove unused endpoints and disable debug mode. |
| 6 | Vulnerable & Outdated Components | jQuery 2.2.4 used, known to be vulnerable. | `console.log($.fn.jquery)` | Upgrade to the latest jQuery version. |
| 7 | Identification & Authentication Failures | Weak password policy allowed short, guessable passwords. | Created weak password account | Enforce strong password requirements. |
| 8 | Software & Data Integrity Failures | Client-side JS could be tampered with. | Modified vendor.js to inject custom behavior | Use SRI (Subresource Integrity) and digital signatures. |
| 9 | Security Logging & Monitoring Failures | No logging of failed login attempts or alerting. | Bruteforce detection absent | Implement security logging and alerting systems. |
|10 | SSRF / Improper Input Validation | Image upload field accepted external URLs. | Uploaded file with external image URL | Sanitize file inputs and validate content types. |


## Secure Development Lifecycle Alignment

This project referenced **NIST SP 800-64 Rev. 2** and implemented the following phases:

1. **Initiation** Identified risks based on OWASP Top 10.
2. **Development/Acquisition** Used OWASP Juice Shop to simulate real-world app security issues.
3. **Implementation/Assessment** Exploited vulnerabilities using browser tools.
4. **Operations/Maintenance** Documented vulnerabilities and proposed mitigation.
5. **Disposition** Recommendations for secure coding and system hardening.

