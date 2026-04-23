# 📋 Incident Response Playbooks

> Step-by-step incident response playbooks for
> common security threats in a SOC environment.
> Author: Thumma Lakshmikanth Gari Dinesh
> Role: Junior SOC Analyst

---

## 📋 Playbook Index

| # | Playbook | Threat Type |
|---|----------|------------|
| 1 | Brute Force Attack | Credential Attack |
| 2 | DDoS Attack | Network Attack |
| 3 | Phishing Email | Social Engineering |
| 4 | Malware Detection | Endpoint Threat |

---

# 🔴 Playbook 1 — Brute Force Attack Response

## Trigger:
- 10+ failed login attempts from same IP
- SIEM alert — Multiple Authentication Failures
- EventID 4625 threshold exceeded

## Step by Step Response:

### Step 1 — Detect & Validate
- ✅ Check alert in SIEM (Splunk/Sentinel)
- ✅ Run failed login query (EventID 4625)
- ✅ Identify source IP and target account
- ✅ Confirm True Positive
### Step 2 — Contain
- ✅ Block source IP on firewall immediately
- ✅ Lock targeted user account
- ✅ Reset account password
- ✅ Enable account lockout policy
### Step 3 — Investigate
- ✅ Check if any login succeeded after failures
- ✅ Identify geolocation of attacking IP
- ✅ Check IP reputation on VirusTotal/Cisco Talos
- ✅ Review logs for lateral movement
### Step 4 — Escalate
- ✅ Create ticket in ServiceNow
- ✅ Assign severity — Critical/High/Medium
- ✅ Escalate to L2 if successful login found
- ✅ Notify security team lead
### Step 5 — Document & Close
- ✅ Document all findings in incident report
- ✅ Record IOCs — IP, account, timestamps
- ✅ Update firewall blocklist
- ✅ Close ticket with resolution notes
---

# 🔴 Playbook 2 — DDoS Attack Response

## Trigger:
- Excessive firewall deny connections
- Single IP with 100+ blocked attempts
- Network performance degradation

## Step by Step Response:

### Step 1 — Detect & Validate
- ✅ Check firewall deny alerts in SIEM
- ✅ Run blocked connections query
- ✅ Identify attacking IPs
- ✅ Confirm DDoS pattern
### Step 2 — Contain
- ✅ Block attacking IP on perimeter firewall
- ✅ Enable rate limiting
- ✅ Contact ISP if volumetric attack
- ✅ Activate DDoS protection service
### Step 3 — Investigate
- ✅ Identify attack type — volumetric/protocol
- ✅ Check if internal IPs involved
- ✅ Look for botnet pattern (subnet attack)
- ✅ Check for secondary attack vectors
### Step 4 — Escalate
- ✅ Create high priority ticket in ServiceNow
- ✅ Notify network team immediately
- ✅ Escalate to L2/L3 for large scale attacks
- ✅ Contact management if business impacted
### Step 5 — Document & Close
- ✅ Document attack timeline
- ✅ Record all attacking IPs
- ✅ Update DDoS runbook
- ✅ Implement permanent blocks
---

# 🟡 Playbook 3 — Phishing Email Response

## Trigger:
- User reports suspicious email
- Email security alert fires
- Malicious link/attachment detected

## Step by Step Response:

### Step 1 — Detect & Validate
- ✅ Collect suspicious email from user
- ✅ Analyze email headers using MXToolbox
- ✅ Check sender domain reputation
- ✅ Scan links using VirusTotal
### Step 2 — Contain
- ✅ Delete email from all mailboxes
- ✅ Block sender domain on email gateway
- ✅ Block malicious URLs on proxy
- ✅ Isolate machine if link was clicked
### Step 3 — Investigate
- ✅ Check if other users received same email
- ✅ Analyze email headers for spoofing
- ✅ Extract all IOCs — URLs, IPs, domains
- ✅ Check if credentials were entered
### Step 4 — Escalate
- ✅ Create ticket in ServiceNow
- ✅ Notify affected users
- ✅ Escalate if credentials compromised
- ✅ Report to email security team
### Step 5 — Document & Close
- ✅ Document phishing indicators
- ✅ Add IOCs to threat intelligence
- ✅ Update email filters
- ✅ Send awareness alert to all users
---

# 🟡 Playbook 4 — Malware Detection Response

## Trigger:
- Antivirus alert fires
- EDR detects suspicious process
- SIEM correlates malware indicators

## Step by Step Response:

### Step 1 — Detect & Validate
- ✅ Review malware alert in SIEM/EDR
- ✅ Identify affected machine and user
- ✅ Check file hash on VirusTotal
- ✅ Confirm True Positive
### Step 2 — Contain
- ✅ Isolate affected machine from network
- ✅ Disable user account temporarily
- ✅ Block malicious hash on EDR
- ✅ Prevent lateral movement
### Step 3 — Investigate
- ✅ Analyze malware behavior
- ✅ Check for persistence mechanisms
- ✅ Review network connections from machine
- ✅ Look for data exfiltration attempts
### Step 4 — Escalate
- ✅ Create critical ticket in ServiceNow
- ✅ Escalate to L2 for malware analysis
- ✅ Notify management if data breach risk
- ✅ Contact threat intelligence team
### Step 5 — Document & Close
- ✅ Document full malware analysis
- ✅ Record all IOCs
- ✅ Reimage affected machine if needed
- ✅ Update detection rules to prevent recurrence
---

## 🛠️ Tools Referenced
- Splunk Enterprise Security
- Microsoft Sentinel
- ServiceNow (Ticketing)
- VirusTotal, Cisco Talos, MXToolbox
- EDR Tools
- Firewall Management Console

## 📫 Connect With Me
- LinkedIn: linkedin.com/in/dineshtl
- GitHub: github.com/Dineshtl
- Email: dineshtl821@gmail.com
