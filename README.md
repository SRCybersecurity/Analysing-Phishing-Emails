# 🎣 Phishing Email Analysis & Investigation

A practical email threat analysis exercise focused on phishing detection, sender authentication, email header investigation, domain reputation, and social engineering indicators.

This project documents the analysis of a suspicious job-recruitment email investigated in a simulated Security Operations Center (SOC) environment. The investigation examines sender information, email authentication results, message content, and potential indicators of credential harvesting or personal information theft.

The objective is to identify phishing characteristics, assess the email's risk, document relevant indicators of compromise (IOCs), and recommend appropriate defensive actions.

Security Notice: This investigation is based on the available sample and reported analysis results. An individual indicator, such as a missing DKIM signature or an unflagged IP address, is not sufficient on its own to prove malicious activity. Findings should be correlated with complete email headers, message content, URL analysis, and available threat intelligence.

### 📌 Table of Contents

```

Project Overview
Objectives
Tools and Technologies
Investigation Scenario
Email Sample Summary
Investigation Methodology
Email Header and Sender Analysis
SPF Authentication Analysis
DKIM Authentication Analysis
Domain and IP Reputation Analysis
Social Engineering Indicators
Indicators of Compromise
Screenshots and Evidence
Findings and Risk Assessment
Recommended Mitigations
Conclusion
Lessons Learned
Responsible Use

```

### 🎯 Project Overview

Phishing is a social engineering technique in which an attacker impersonates a trusted person, organization, or service to manipulate recipients into disclosing sensitive information, opening malicious attachments, or visiting deceptive websites.

This investigation examines a suspicious job-opportunity email that attempts to persuade the recipient to submit a CV within a limited period.

The analysis focuses on identifying potential warning signs, including:

Suspicious or unverified sender identity.
Incomplete email authentication evidence.
Urgency-based social engineering.
Generic, non-personalized messaging.
Potential collection of personal information.
Insufficient evidence of legitimate recruitment activity.

The investigation follows a structured email triage process similar to the initial analysis performed by SOC analysts and incident responders.

### 🎯 Objectives
The primary objectives of this investigation are to:

```
Identify characteristics associated with phishing emails.
Examine sender information and available email headers.
Review SPF and DKIM authentication evidence.
Assess sender IP and domain reputation using available security tools.
Identify social engineering techniques used in the email body.
Document available indicators of compromise.
Determine an appropriate risk assessment and response.
Recommend actions to prevent potential data exposure.

```

### 🛠️ Tools and Technologies

| Tool | Purpose |
|---|---|
| [MXToolbox](https://mxtoolbox.com/) | Inspect email-related DNS records, authentication configuration, and blacklist information where available. |
| [VirusTotal](https://www.virustotal.com/) | Review IP addresses, domains, and URLs against available threat intelligence sources. |
| Email Header Analyzer | Examine sender routing information and email authentication results, including SPF and DKIM. |
| Email Client | Review message content, sender details, links, and attachments. |

Document findings and investigation evidence

**Tool limitations:** Reputation results depend on the data available at the time of analysis. A clean reputation result does not establish that an IP address, domain, or message is safe.

### 🔎 Investigation Scenario

```
A suspicious email was investigated in a simulated SOC environment. The message appeared to advertise a job opportunity and encouraged the recipient to apply quickly by submitting a CV.

The email did not trigger an automated phishing alert during the reported exercise. This made manual inspection necessary.

The investigation focused on the sender identity, available authentication information, message language, and potential collection of personal information.
```
### Investigation workflow
```
Review the suspicious email and summarize its content.
Examine the sender address and available message headers.
Check the sender IP address and domain reputation.
Review SPF and DKIM authentication evidence.
Inspect links and attachments where available.
Identify social engineering characteristics.
Record findings and recommend appropriate response actions.
```

### 📧 Email Sample Summary
The analyzed email presented itself as a job opportunity from an apparently unknown recruiter.

***Observed characteristics:***

| Attribute | Observation |
|---|---|
| **Email Theme** | Job recruitment or employment opportunity. |
| **Sender Identity** | Reported as unknown; legitimacy remains unverified. |
| **Call to Action** | Submit a CV to apply for the advertised position. |
| **Urgency** | A limited-time opportunity was presented to encourage a quick response. |
| **Personalization** | No recipient name, user ID, or specific reference was identified in the reported review. |
| **Automated Detection** | No phishing alert was triggered during the exercise. |
| **Potential Objective** | Collection of personal information through a potentially deceptive recruitment message. |

The combination of an unverified recruiter identity, urgency-based language, generic messaging, and a request for personal information justified further investigation.

These characteristics are suspicious but are not independently conclusive proof of phishing. Legitimate recruiters may also send generic job announcements, so contextual and technical evidence must be considered.

### 🧪 Investigation Methodology


Step 1: Obtain and Review the Email Sample
```
A sample email was obtained for analysis and reviewed in a controlled investigation environment.

The initial review focused on:
- The sender's displayed identity.
- The email address and domain.
- The subject and message body.
- The request to submit a CV.
- Urgent or manipulative wording.
- The presence of suspicious URLs or attachments.
- The absence of a recognizable recruiter identity.

Observation: The message encouraged the recipient to apply for a job opportunity within a limited time and did not provide sufficient identity context in the reported sample.
```
Step 2: Examine the Sender Address
```
The sender identity was reviewed for inconsistencies and signs of impersonation.

The reported sender information was:  "" wilfrid-adam@t-online.de ""

The investigation did not identify a confirmed spoofing indicator from the available sender-address review.

However, the absence of an obvious spoofing indicator does not establish that the sender is legitimate. A real mailbox can be compromised, and an attacker can send messages from a domain that has not previously been associated with malicious activity.

Assessment: Sender legitimacy remained unverified.
```

Step 3: Analyze Email Headers

Email headers provide information about message routing, sender claims, receiving infrastructure, and authentication results.

***The analysis considered:***
```
From
Return-Path
Received
Authentication-Results
Received-SPF
DKIM-Signature
Sending IP address

The reported investigation identified DKIM-related errors and an IP address associated with the email.

A complete assessment should compare the From domain, envelope sender, sending infrastructure, and authentication results to determine whether the message passed the relevant authentication checks.
```
**Important:** The From header is not proof of sender identity. It can be forged unless the message is validated using appropriate authentication and other contextual evidence.

Step 4: Check Domain and IP Reputation
```
The reported investigation used MX Lookup and VirusTotal to examine sender infrastructure and reputation.
The IP address was reported as not flagged or blacklisted at the time of analysis.
This finding means that no adverse reputation result was identified in the reported checks. It does not prove that the sender or message is trustworthy.
Newly observed malicious infrastructure, compromised legitimate accounts, and low-volume phishing campaigns may not yet have accumulated negative reputation.
```

Step 5: Review Email Authentication
```
The reported results identified DKIM signature errors. The available information did not establish the actual SPF result.

SPF and DKIM must be interpreted separately, and their results should be correlated with DMARC alignment where applicable.
```
Step 6: Inspect URLs and Attachments
```
The reported review did not identify suspicious links or attachments in the sample.

No URL redirect chain or credential-harvesting destination was independently established by the supplied observations.

If URLs are present in the original email, they should be extracted and assessed using an approved analysis environment. Do not open suspicious links directly on a production workstation.
```
Step 7: Assess Social Engineering
```
The email used urgency and a job-opportunity theme to encourage the recipient to submit personal information.

The lack of recipient-specific context and insufficiently verified recruiter identity increased suspicion.
```
Step 8: Document Findings
```
The observations were consolidated into a report covering authentication evidence, sender reputation, social engineering, and recommended defensive actions.
```

### 📬 Email Header and Sender Analysis

**Reported Sender Information**

| Attribute | Observed Value |
|---|---|
| **Reported Sender Email** | `wilfrid-adam@t-online.de` |
| **Reported IP Address** | `194.25.134.82` |
| **Sender Domain** | `t-online.de` |
| **Sender Spoofing** | Not confirmed by the reported address review |
| **IP Reputation** | Reportedly not flagged or blacklisted at the time of analysis |
| **DKIM Result** | Signature-related errors reported; no `DKIM-Signature` header found |
| **SPF Result** | Not established from the available findings |
| **Suspicious Links** | None identified in the reported review |
| **Suspicious Attachments** | None identified in the reported review |

**Evidence qualification:** The available information does not establish that 194.25.134.82 was conclusively the originating sender IP. Email headers can contain multiple IP addresses, and the correct interpretation depends on trusted Received headers and the receiving server's authentication results.

The IP address should therefore be treated as a reported investigation artifact until its role in the message delivery path is verified.```
What to inspect in the headers

| Header | Investigation Purpose |
|---|---|
| `From` | Displays the claimed sender identity. |
| `Return-Path` | Identifies the envelope return address recorded by the receiving system. |
| `Received` | Records message transfer between mail servers. |
| `Authentication-Results` | Reports authentication checks performed by a receiving server. |
| `Received-SPF` | May contain SPF evaluation details. |
| `DKIM-Signature` | Contains a DKIM signature when the message has been signed. |

When reviewing Received headers, begin with the receiving infrastructure you trust. Sender-controlled header values may be forged.

#### 🛡️ SPF Authentication Analysis

```
SPF stands for Sender Policy Framework. It allows a receiving mail server to check whether an IP address is authorized by a domain's SPF policy to send mail using that domain's envelope sender identity.

SPF does not, by itself, prove that the displayed From identity is legitimate.
```
#### SPF Status and Description

| SPF Status | Description |
|---|---|
| `pass` | The connecting IP is authorized by the evaluated SPF policy for the relevant identity. |
| `fail` | The evaluated SPF policy explicitly does not authorize the IP address. |
| `softfail` | The policy indicates that the IP is probably unauthorized, but does not explicitly reject it. |
| `neutral` | The domain's SPF policy does not assert whether the IP address is authorized. |
| `none` | No applicable SPF policy was found for the evaluated identity. |
| `permerror` | A permanent error, such as an invalid SPF record, prevented reliable evaluation. |
| `temperror` | A temporary error, such as a DNS lookup failure, prevented SPF evaluation. |

#### Findings

| Item | Finding |
|---|---|
| SPF Authentication Status | Not established from the available evidence. |
| DKIM Authentication | No `DKIM-Signature` header was found in the reported analysis. |
| Sender IP Reputation | Reportedly not flagged or blacklisted at the time of analysis. |
| Sender Identity | The legitimacy of the sender remains unverified. |
| Social Engineering | Urgency-based language encouraged the recipient to submit a CV. |
| Personalization | No recipient-specific name or reference was identified in the reported review. |
| Suspicious URLs | None identified in the reported review. |
| Attachments | No suspicious attachments were identified in the reported review. |
| Overall Assessment | Suspicious email; further validation is recommended. |

The supplied investigation details did not include a confirmed SPF result.

Therefore, the SPF status should be recorded as Not established from the available evidence, rather than PASS, FAIL, or NONE.

If SPF passes, that indicates authorization under the evaluated SPF policy. It does not guarantee that the message is benign, that the sender mailbox has not been compromised, or that the displayed sender identity is aligned with the authenticated identity.

**ecommended follow-up:** Retrieve the receiving server's original Authentication-Results header and correlate the SPF result with the envelope sender and DMARC evaluation.

#### 🔏 DKIM Authentication Analysis
```
DKIM stands for DomainKeys Identified Mail. It uses a cryptographic signature to allow receiving mail systems to verify that signed portions of a message have not been altered and that the signing domain takes responsibility for the signature.

The reported investigation identified the following errors:

No DKIM-Signature header was found.
No aligned DKIM signature was available according to the reported analysis.
Findings

The absence of a DKIM signature means that DKIM authentication could not be established through a message signature.

It does not, on its own, prove that the email is malicious. Some legitimate senders do not sign messages with DKIM, and mail can authenticate through other mechanisms.

The absence of an aligned DKIM signature can affect DMARC evaluation, but the actual DMARC result cannot be determined from the supplied DKIM observations alone.
```
***Security interpretation***
The DKIM findings increase the need for further validation when considered alongside the unverified sender identity and suspicious message content.

The correct conclusion is that the reported email lacked DKIM signature evidence—not that a DKIM signature was definitively forged.

### 🌐 Domain and IP Reputation Analysis

The investigation reportedly used MX Lookup and VirusTotal to review the sender infrastructure.

**Observed results**
```
Indicator	Reported Result	Interpretation
IP address	194.25.134.82	No flag or blacklist listing reported
Sender domain	t-online.de	Sender domain identified; legitimacy of the specific message remains unverified
IP reputation	No adverse result reported	A clean result does not establish that the message is safe
Domain reputation	No conclusive malicious verdict supplied	Requires independent validation and contextual review
```
**Important considerations**
```
A legitimate email provider's domain can be abused by a compromised account.
An IP address may be new to threat intelligence databases.
Reputation databases can disagree or have incomplete coverage.
An IP address's reputation does not independently authenticate a message.
A legitimate domain does not guarantee that a particular email is legitimate.
```
**Assessment:** The reported reputation checks did not identify a known blacklist indicator. The message still required further investigation based on its content and authentication evidence.

### 🎭 Social Engineering Indicators

Social engineering manipulates a recipient into taking an action that benefits an attacker.

| Indicator | Observation | Security Significance |
|---|---|---|
| **Urgency** | The recipient was encouraged to apply within a limited period. | May pressure users to act before verifying the sender. |
| **Unverified Identity** | The recruiter's identity was not adequately established. | Makes independent sender verification important. |
| **Generic Messaging** | No recipient-specific name, user ID, or reference was reported. | May indicate bulk distribution, although legitimate campaigns can also be generic. |
| **Request for Personal Information** | The recipient was asked to submit a CV. | Could expose contact details, employment history, and other personal data. |
| **Limited Authenticity Cues** | The reported message lacked convincing recruiter context. | Reduces confidence in the claimed recruitment purpose. |
| **Missing DKIM Evidence** | No DKIM signature was reported. | Prevents DKIM-based verification for this message; does not independently prove phishing. |

**Potential attack objective**
```
A fraudulent recruitment email may attempt to collect personal information, redirect victims to a deceptive website, or establish contact for subsequent fraud.

However, the supplied evidence does not establish that a credential-harvesting page or redirect chain was present in this particular sample.

The observed behavior is consistent with suspicious recruitment-themed social engineering, but the precise attacker objective remains unconfirmed.
```
### 🧾 Indicators of Compromise (IOCs)

The following table records the available investigation artifacts. It distinguishes observed values from confirmed malicious indicators.

| Type | Value | Assessment |
|---|---|---|
| Sender Email | `wilfrid-adam@t-online.de` | Suspicious context; maliciousness not independently confirmed. |
| Sender Domain | `t-online.de` | Reported sender domain; not established as malicious. |
| Reported IP | `194.25.134.82` | Reportedly not flagged; originating role requires header verification. |
| Suspicious URL | Not identified | No URL IOC established from the reported findings. |
| File Hash | Not available | No attachment hash established. |
| DKIM Signature | Not found in the reported analysis | DKIM authentication evidence is missing. |
| SPF Result | Not established | Original email authentication results are required. |

**IOC handling note:** These artifacts should not automatically be added to blocklists. The sender domain and IP may belong to legitimate infrastructure. Validate the message context and delivery path before taking infrastructure-level blocking action.

### 📸 Screenshots and Evidence

Screenshots from the investigation can be included here to document the analysis and support reproducibility.

**Evidence integrity** The screenshots are uploaded in the repository.

### 📊 Findings and Risk Assessment

Based on the supplied observations, the message should be treated as suspicious and should not be trusted without independent verification.

| Finding | Severity Assessment | Reason |
|---|---|---|
| Unverified Recruiter Identity | Medium | Sender legitimacy has not been established. |
| Urgency-Based Recruitment Message | Medium | Encourages rapid action before verification. |
| Request to Submit a CV | Medium | May expose personal and professional information. |
| Missing DKIM Signature Evidence | Low to Medium | Reduces available authentication assurance; not proof of maliciousness. |
| IP Not Reported as Blacklisted | Informational | Does not establish sender legitimacy. |
| No Suspicious URL or Attachment Identified | Informational | No URL or file-based indicator was established in the reported review. |
| SPF Result Unavailable | Informational | Authentication status remains undetermined. |

These are preliminary, qualitative assessments for this exercise—not official CVSS scores or verified organizational risk ratings. Severity may change if further evidence identifies credential theft, malicious infrastructure, impersonation, or actual data exposure.

**Overall assessment**

**Disposition:** Suspicious email — further validation required.
```
The combination of an unverified sender identity, urgency-based language, a request for personal information, and missing DKIM signature evidence warrants caution.

The supplied evidence supports treating the message as a potential phishing attempt. It does not independently confirm the presence of a credential-harvesting page, a URL redirect chain, or a compromised sender account.
```
### 🛡️ Recommended Mitigations

***For Email Recipients***
```
Do not send your CV or other personal information to an unverified sender.
Avoid clicking links or opening unexpected attachments.
Verify job opportunities through independently obtained official company contact information.
Report the message to your organization's IT or security team.
Use your email client's phishing-reporting feature where available.
```

***For SOC Analysts***
```
Preserve the original email, including full headers, for investigation.
Review trusted Received headers and the original authentication results.
Establish the actual SPF, DKIM, and DMARC outcomes where available.
Examine extracted URLs and attachments in an approved analysis environment.
Correlate sender and infrastructure artifacts with reliable threat intelligence.
Search for similar messages across organizational mailboxes.
Determine whether any recipient clicked a link or submitted information.
Record evidence, confidence, and investigation limitations in the incident report.
```
***For Email Administrators***
```
Maintain appropriate SPF, DKIM, and DMARC configurations for organizational domains.
Monitor authentication failures and suspicious sending patterns.
Apply phishing detection and reporting controls.
Consider targeted blocking only after validating the maliciousness of relevant indicators.
Provide users with clear guidance for reporting suspicious recruitment messages.
```
***🏁 Conclusion***
```
This investigation examined a suspicious recruitment-themed email that encouraged the recipient to submit a CV within a limited timeframe.

The reported findings included an unverified sender identity, generic messaging, urgency-based language, a request for personal information, and missing DKIM signature evidence. The reported IP reputation checks did not identify a blacklist listing, and no suspicious URL or attachment was identified in the supplied review.

A clean IP reputation result does not establish legitimacy, and missing DKIM evidence alone does not prove phishing. Nevertheless, the combined observations justify treating the email as suspicious and withholding personal information until the sender and opportunity are independently verified.
```
### Final Recommendations
```
Do not submit personal information until the recruiter and job opportunity have been independently verified.
Report the email to the appropriate IT or security team.
Preserve the original message and complete headers for further analysis.
Validate SPF, DKIM, and DMARC results using the receiving server's authentication records.
Investigate links and attachments if they are present in the original sample.
Document the findings and update the assessment if additional evidence becomes available.
```
**Final disposition:** Potential phishing attempt requiring caution and further validation.

### 📚 Lessons Learned
```
This investigation highlights several important email security principles:

A message can be suspicious even when its sending IP is not blacklisted.
Sender display information is not proof of identity.
SPF, DKIM, and DMARC provide different, complementary forms of authentication evidence.
Urgency and requests for personal information are useful social engineering indicators.
Reputation results must be interpreted alongside email content and header evidence.
Investigation reports should clearly distinguish observed facts, analytical conclusions, and unverified hypotheses.
```
Effective phishing analysis requires a combination of technical validation, contextual investigation, and careful evidence handling.

### 🔒 Responsible Use
```
This project is intended for cybersecurity education, defensive email analysis, and authorized security investigations.

Analyze suspicious messages in an approved environment. Avoid opening potentially malicious links or attachments on production systems, and do not publish unredacted personal information from the original sample.

Investigate carefully. Validate the evidence. Protect user information.
```
