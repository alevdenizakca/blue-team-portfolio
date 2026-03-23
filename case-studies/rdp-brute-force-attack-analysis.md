# 🛡️ RDP Brute Force Attack Analysis

## 📌 Scenario
A potential brute force attack was detected targeting a system over Remote Desktop Protocol (RDP). The objective of this analysis is to investigate the suspicious activity and determine whether a security incident has occurred.

---

## 🔍 Investigation

Log management analysis revealed multiple failed login attempts originating from IP address **218.92.0.56** targeting **172.16.17.148** over port **3389 (RDP)**.

Key observations:
- High number of failed login attempts using invalid usernames
- Repeated authentication attempts from a single source IP
- One successful login event following multiple failures

---

## 📊 Log Evidence

- Source IP: **218.92.0.56**
- Destination IP: **172.16.17.148**
- Port: **3389 (RDP)**

### Authentication Events:
- Multiple failed login attempts (invalid usernames)
- Successful login:
  - Username: **matthew**
  - Logon Type: **RemoteInteractive**

---

## 🧠 Analysis

The observed activity is consistent with a **brute force attack** pattern:

- The attacker attempts multiple username/password combinations
- After repeated failures, a successful login is achieved
- This indicates a potential **account compromise**

The successful login using **RemoteInteractive** confirms that access was gained via RDP.

Additionally, threat intelligence analysis using VirusTotal indicates that the source IP address (**218.92.0.56**) is flagged as **malicious by multiple security vendors**, further supporting the likelihood of malicious activity.

---

## 🗺️ MITRE ATT&CK Mapping

- **T1110 – Brute Force**
- **T1021.001 – Remote Services: RDP**

---

## 🚨 Conclusion

This activity represents a **successful brute force attack**, resulting in unauthorized access to the target system.

Immediate action is required to mitigate further risk and prevent lateral movement within the network.

---

## 🛡️ Recommendations

- Block the source IP address (**218.92.0.56**)
- Reset the password for the compromised account (**matthew**)
- Enable Multi-Factor Authentication (MFA)
- Restrict RDP access (VPN / IP whitelist)
- Conduct further investigation on the affected system

---

## 💡 What I Learned

- Brute force attacks can lead to successful compromise if not mitigated
- Logon Type analysis is critical in identifying access methods
- Threat intelligence sources help validate suspicious activity
