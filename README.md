# Phishing-Email-Analysis
A basic phishing email analysis task focused on detecting spoofed senders, identifying malicious links, and verifying email header discrepancies using online tools.

## 📩 Sample Email
**Subject**: High-severity alert: Phish delivered due to tenant or user override  
**From**: Microsoft <microsoft@email-records.com>  
**Received at**: Fri, 22 Jan 2021 4:22 PM  
**Link/Button Shown**: “View alert details”

## 🧪 Phishing Indicators Identified

1. **Spoofed Sender Email Address**  
   - `email-records.com` is **not** an official Microsoft domain.  
   - Official emails come from domains like `@microsoft.com` or `@office365.microsoft.com`.

2. **Suspicious Domain in Return Path**  
   - Return-Path was `alerts@fake-office365.com` — different from the From address.  
   - This mismatch is common in spoofed or relay-based phishing attempts.

3. **Failed Email Authentication Checks**  
   ✅ **SPF: FAIL**  
   ✅ **DKIM: FAIL**  
   ✅ **DMARC: FAIL**  
   - These failures mean the sender was **not authorized** to send this email using that domain.

4. **Urgent & Alarming Language**  
   - "A high-severity alert has been triggered" is designed to create fear and prompt quick clicks.

5. **Suspicious IP Address**  
   - The sending IP `185.212.111.34` is not associated with Microsoft and flagged as suspicious.

6. **Generic & Robotic Format**  
   - No user name is mentioned; poor formatting and incomplete sentences are unprofessional and typical of phishing.

7. **Reply-To Mismatch**  
   - `Reply-To` was set to `security-check@office365-support-mail.com`, another unverified domain — this would intercept responses.

---

## 🛠 Tools Used

- 📬 **Email Header Analyzer**: [MxToolbox Email Header Tool](https://mxtoolbox.com/EmailHeaders.aspx)
- 🔍 **Visual Verification**: From the email image preview
- 🔐 **SPF/DKIM/DMARC Report**: Collected from analysis PDF

---

## 🚨 Conclusion

This email is a clear **phishing attempt**:
- It uses a **spoofed sender domain**,
- Triggers panic using an **urgent alert message**,
- Encourages the user to click a **fake link**, and
- **Fails** all major email authentication checks.

> 🔐 Always inspect sender domains, header data, and avoid clicking on links or attachments in suspicious emails.

---

## 📁 Files Included in GitHub Repo

- `README.md` — This report
- `phishing_mail.png` — Screenshot of phishing email
- `EmailHeaderAnalysis.pdf` — Header analysis result from MxToolbox

