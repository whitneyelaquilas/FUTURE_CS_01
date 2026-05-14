# Vulnerability Assessment Report – Google Gruyere

**Author**: [Whitney El Aquilas]  
**Date**: May 2026  
**Tools used**: Nmap, OWASP ZAP (passive mode), Browser DevTools, Canva  

## Target
- **URL**: `https://google-gruyere.appspot.com/`
- **Type**: Deliberately vulnerable web application (authorized for security testing)

## Objective
Perform a passive vulnerability assessment as required by the assignment:
- Identify common web vulnerabilities
- Classify risk levels (Low / Medium / High)
- Explain issues in simple business language
- Provide clear remediation steps
- Deliver a professionally designed report (Canva) and publish it on GitHub.

## Methodology
1. **Nmap** – Port scanning and service detection (`-sV -sC` on initial target `demo.owasp-juice.shop`).
2. **OWASP ZAP (passive mode)** – Browsed the application while ZAP recorded alerts.
3. **Browser DevTools** – Manually inspected HTTP headers, cookies, and HTML comments.
4. **Canva** – Designed the final report (PDF).

## Key Findings

| Vulnerability | Risk Level | Quick Fix |
|---------------|------------|------------|
| Missing `X-Frame-Options` header | Medium | Add `X-Frame-Options: SAMEORIGIN` |
| Missing `Strict-Transport-Security` (HSTS) | Medium | Add `Strict-Transport-Security: max-age=31536000` |
| Session cookie without `Secure` flag | Low | Add `Secure; HttpOnly; SameSite=Lax` |
| Internal comments in HTML | Low | Remove debug comments from production |

## Report
The full vulnerability assessment report is available here:  
📄 [Vulnerability_Assessment_Report.pdf](./Vulnerability_Assessment_Report.pdf)

*(Make sure the PDF file is uploaded to the same repository with the exact filename above.)*

## Repository structure
