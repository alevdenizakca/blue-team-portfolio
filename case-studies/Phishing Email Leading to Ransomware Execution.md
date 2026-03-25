# 🛡️ Phishing Email Leading to Ransomware Execution

## 📌 Scenario
A suspicious email was received by a user, leading to the execution of a malicious file and potential ransomware infection.

---

## 🔍 Investigation

On April 4, 2021, at 11:00 PM, user **mark@letsdefend.io** received a suspicious email from **lethuyan852@gmail.com**.

Key findings:
- Email contained a suspicious URL: http://nuangaybantiep.xyz
- URL was identified as malicious via NordVPN Link Checker
- User accessed the malicious link

---

## 📊 Log / Endpoint Evidence

- **User:** mark@letsdefend.io  
- **Sender:** lethuyan852@gmail.com  
- **Suspicious URL:** http://nuangaybantiep.xyz  

### Process Activity:
- Outlook.exe executed
- Suspicious process **ab.exe** launched afterward

### Additional Findings:
- Browser activity not directly available (no SIEM agent)
- Log Management confirmed access to the malicious URL

### Malware Analysis:
- File: **ab.exe**
- MD5 Hash: 0b486fe0503524cfe4726a4022fa6a68
- VirusTotal Result: Flagged as **ransomware**

---

## 🧠 Analysis

The observed behavior indicates a **phishing attack leading to malware execution**:

- User receives and interacts with a malicious email
- Malicious link is accessed
- Payload is executed on the system
- File identified as ransomware via threat intelligence

This confirms a **successful compromise with ransomware infection**.

---

## 🗺️ MITRE ATT&CK Mapping

- **T1566 – Phishing**
- **T1204 – User Execution**
- **T1059 – Command Execution**
- **T1486 – Data Encrypted for Impact (Ransomware)**

---

## 🚨 Conclusion

This incident represents a **successful phishing attack resulting in ransomware execution**.

Immediate action is required to contain the threat and prevent further damage.

---

## 🛡️ Recommendations

- Isolate the infected system
- Terminate malicious process (**ab.exe**)
- Perform full endpoint scan
- Reset user credentials
- Block malicious URL and indicators
- Monitor for lateral movement

---

## 💡 What I Learned

- Phishing attacks often lead to full compromise if user interaction occurs  
- Email + URL + process correlation is critical in SOC analysis  
- Threat intelligence (VirusTotal) plays a key role in confirming malware type  
