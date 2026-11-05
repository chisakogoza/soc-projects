# Case: 

## Executive Summary
Investigated a sophisticated phishing email that bypassed email filters and led to credential harvesting for 3 user accounts. Attack was contained within 2 hours of initial detection.

## Timeline
- **09:15 AM:** 
- **09:47 AM:** 
- **10:02 AM:** 
- **11:30 AM:** 

## Investigation Steps
1. Analyzed email headers - identified spoofed sender domain
2. Examined URL - fake Office 365 login page hosted on attacker infrastructure
3. Reviewed proxy logs - confirmed 3 users submitted credentials
4. Checked authentication logs - detected logins from attacker IP
5. Traced attacker activity post-compromise - attempted mailbox access

## Indicators of Compromise (IOCs)
| Type | Value | Description |
|------|-------|-------------|
| Domain | secure-office365-login[.]com | Fake login page |
| IP Address | 185.220.101.X | Attacker infrastructure |
| File Hash | a3f2e1... | Malicious attachment (if applicable) |

## MITRE ATT&CK Mapping
- **T1566.002:** Phishing - Spearphishing Link
- **T1078:** Valid Accounts (compromised credentials)
- **T1114:** Email Collection (attempted)

## Containment Actions
- Blocked malicious domain at web proxy
- Reset passwords for 3 affected accounts
- Enabled MFA enforcement
- Quarantined remaining phishing emails

## Lessons Learned
- Email filters missed this due to new domain registration
- User security awareness training needed
- Faster detection possible with behavioral analytics

## Recommendations
1. Implement DMARC/SPF/DKIM enforcement
2. Deploy URL sandboxing for links
3. Conduct phishing simulation exercises