# Phishing Email Analysis

## 1. Email Overview

### Sample

- Sample: Microsoft impersonation phishing email
- Subject: `[Action Required] Unusual sign-in activity on your account`
- From: `"Microsoft Account Team" <noreply@microsoftonline-verify.com>`
- Recipient: `jacobcookofficial@gmail.com`
- Date: `Thu, 06 Feb 2026 17:14:18 +0000`

The email presents itself as a Microsoft account security notification and claims that unusual sign-in activity was detected.

---

## 2. Header Analysis

The original `.eml` file was inspected to review the available email-header information.

### Authentication Results

| Check | Result |
|---|---|
| SPF | FAIL |
| DKIM | FAIL |
| DMARC | FAIL |

The header authentication results show failures for SPF, DKIM, and DMARC.

### Sending Information

- Sending IP observed in the received header: `178.238.225[.]91`
- Return-Path: `noreply@microsoftonline-verify[.]com`
- From address: `noreply@microsoftonline-verify[.]com`

These header details provide evidence that the message did not successfully authenticate through the available email authentication checks.

---

## 3. Sender and Domain Analysis

The message claims to come from a `"Microsoft Account Team"`.

However, the sender address uses:

`microsoftonline-verify[.]com`

The sender domain should therefore be treated with caution because the message is presenting itself as a Microsoft security notification while using a separate domain.

The SPF, DKIM, and DMARC failures further increase concern about the authenticity of the message.

---

## 4. Suspicious URL Analysis

The email contains a link presented as:

`https://bit[.]ly/3vF9xKz`

The URL uses a shortened-link service, which can hide the final destination from the recipient.

The link was not opened or followed during this analysis.

Because the message combines an account-security warning with a request to review recent activity through a shortened URL, the link is considered a significant phishing indicator.

---

## 5. Phishing Indicators

The following indicators were identified:

### 5.1 Impersonation

The email uses the name `"Microsoft Account Team"` and presents itself as a Microsoft account security alert.

### 5.2 Suspicious Sender Domain

The sender uses:

`microsoftonline-verify[.]com`

rather than an expected official Microsoft domain.

### 5.3 Authentication Failures

The email headers show:

- SPF: FAIL
- DKIM: FAIL
- DMARC: FAIL

### 5.4 Urgency and Fear

The message warns about unusual account activity and encourages the recipient to take immediate action.

### 5.5 Suspicious Link

The email directs the recipient to a shortened URL:

`https://bit[.]ly/3vF9xKz`

### 5.6 Request for Immediate Action

The message instructs the recipient to secure the account immediately and review recent activity.

---

## 6. Risk Classification

**Classification: Phishing**

The classification is based on multiple observed indicators rather than a single characteristic:

- Microsoft impersonation
- Suspicious sender domain
- SPF failure
- DKIM failure
- DMARC failure
- Urgent account-security messaging
- Suspicious shortened URL
- Request for immediate user action

Taken together, these indicators strongly support classifying the email as a phishing message.

---

## 7. How the Attack Works

The message uses a common social-engineering approach:

1. The attacker presents the message as a Microsoft security notification.
2. The email claims that unusual sign-in activity has occurred.
3. The warning creates concern about the user's account.
4. The recipient is encouraged to review recent activity immediately.
5. A shortened link is provided as the action to take.
6. A victim who follows the link could potentially be directed toward a fraudulent website designed to collect sensitive information.

No credentials were entered and the suspicious link was not opened during this analysis.

---

## 8. Recommended User Actions

If a user receives a similar email:

- Do not click the suspicious link.
- Do not enter passwords, OTPs, or other sensitive information.
- Do not reply to the message.
- Verify account activity through the organization's official website or application.
- Report the suspicious email to the appropriate security or IT team.
- Preserve the email as evidence if an investigation is required.

---

## 9. Employee Do's and Don'ts

### Do

- Check the sender's complete email address.
- Be cautious with urgent security warnings.
- Verify account activity through an official website or application.
- Report suspicious emails.
- Ask the IT/security team when uncertain.

### Don't

- Don't click unexpected links.
- Don't provide passwords or OTPs through an email link.
- Don't trust an email simply because it uses a familiar company name or logo.
- Don't allow urgency to override normal security checks.
- Don't open suspicious links just to investigate them.

---

## 10. Evidence

The original email is preserved in:

`../sample/sample.eml`

A readable representation is available in:

`../sample/sample_email_readable.txt`

The captured analysis screenshot is available in:

`../evidence/sample-email-analysis.png`

---

## 11. Conclusion

The analyzed email contains multiple indicators associated with phishing, including impersonation, a suspicious sender domain, failed email authentication checks, urgent account-security language, and a shortened URL.

Based on the available evidence, the message is classified as **Phishing**.

