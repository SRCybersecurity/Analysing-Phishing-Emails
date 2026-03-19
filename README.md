# Analyse a Phishing Email Sample. </br>
**Key Concepts :** Phishing, email spoofing, header analysis, social engineering, threat detection. </br>

## 🎯 Objective
Identify phishing characteristics in a suspicious email sample. 

## 🛠️ Tools
MX Lookup </br>
VirusTotal

## 📌 Steps

### 1.Obtain a sample phishing email (many free samples online).
Email Body Summary:
- A fake job alert pretending to be a recruiter
-	Urging: To apply for new job role by giving a limited time to become a talented top applicant.
-	No phishing alert was triggered.
-	Message was sent by "Unknown".
-	Urging the user to send CV "To Apply". 
---
### 2.Examine sender's email address for spoofing.
  - Not found
---  
### 3.Check email headers for discrepancies (using online MX Lookup). 

**Deliverables :** A report listing phishing indicators found<br>

•	Full email id of sender?<br>
    - 194.25.134.82 <br>

•	What domain is used to send this mail? (Return path/ From)?<br>
    -	wilfrid-adam@t-online.de <br>

•	Sender IP address blacklisted or not? (VirusTotal, MX Lookup)?
   - IP address is not flagged or blacklisted yet.
 
•	What is the status of SPF Authentication Result?

---
| SPF Status | Description |
|------------|-------------|
| **pass**       | The sending IP is authorized by the domain's SPF record. This is a successful SPF check. |
| **fail**       | The sending IP is not authorized to send on behalf of the domain. Usually triggers rejection or spam filtering. |
| **softfail**   | The IP is probably not authorized. The domain's SPF record includes a `~all` mechanism (soft fail). Treated as suspicious, but usually not rejected outright. |
| **neutral**    | No explicit authorization result. The domain's SPF record uses `?all`. Mail may still be accepted. |
| **none**       | The domain has no SPF record. No authentication was possible. |
| **permerror**  | Permanent error in the SPF record (e.g. syntax error). SPF cannot be evaluated. |
| **temperror**  | Temporary error (e.g. DNS lookup failure). SPF check could not complete. Retry may succeed later. |

---

SPF (Sender Policy Framework) to authenticate sender mail exchange server Ip address to avoid spam. If the result is pass then it has designated client id or they might have used new legitimate email id and hasn’t been blacklisted yet.

•	Is anything suspicious found in the email?
  -	Yes
  -	Dkim Signature Error: No DKIM-Signature header found.
  -	Dkim Signature Error: There must be at least one aligned DKIM-Signature for the message to be considered aligned.
---
### 4.Identify suspicious links or attachments.
  - Not Found
---
### 5.Look for urgent or threatening language in the email body.
  - Yes, urging to apply for new job role by giving a limited time to become a talented top applicant.
---
### 6.Note any mismatched URLs (hover to see real link).
  - No
---
### 7.Verify presence of spelling or grammar errors.
  - Not many grammatical mistakes, but lacks authenticity of the job recruiter’s id.<br></br>
---
### 8.Summarize phishing traits found in the email.
 - Using legitimate new email id that hasn’t been blacklisted to avoid getting blocked or filtered.
 - No Personalization, no name, user ID, or specific reference is used shows it's a mass-mailed phishing attempt.</br>

### Conclusion :
This email shows clear signs of phishing:
- Not an authenticated sender identity
- Urgent content.
- Misleading content to gain personal information.
- Lack of personalization
- Signature failure (DKIM)
---
### Action Recommended:
   - Do NOT send your personal information (CV) in the given id in the email.
   - Report the email to your IT/Security team or email provider.
   - Mark it as "Phishing" or "Spam" in your email client.
---
### END

### Thank You
---
