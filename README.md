# Wireshark-Incident-Analysis
Network forensic investigation using Wireshark to analyze Trickbot malware infection within the Stormtheory domain. Includes technical report and executive summary.

# 🛡️ Trickbot Network Forensics – Wireshark-Based Incident Analysis

This repository documents a forensic investigation of a Trickbot malware infection targeting the `stormtheory.info` enterprise domain. The analysis is based on PCAP traffic examined in Wireshark and alert data generated from Suricata.

---

## 📁 Files in This Repository

| File Name                                      | Description                                                   |
|-----------------------------------------------|---------------------------------------------------------------|
| `Wireshark Evidence Analysis - Stormtheory.DC.pdf` | Full report including detailed traffic analysis, malware behavior, and attack timeline |
| `2019-02-23-traffic-analysis-exercise-alerts.txt` | Suricata IDS alert logs generated from PCAP analysis |
| `2019-02-23-traffic-analysis-exercise-alerts.jpg` | Visual snapshot of IDS alerts showing malicious traffic patterns |

---

## 📌 Incident Summary

- Victim Host: `10.2.23.231` (FERGUSON-WIN-PC)
- Domain Controller: `10.2.23.2`
- Infection Vector: GET request for `troll1.jpg` from malicious IP `209.141.55.226`
- Malware: Trickbot/TrickLoader
- C2 Infrastructure:
  - Domains: `dicarkadar[.]com`, `cranetisti[.]com`, `superhaps[.]pw`
  - IPs: `190.146.112.216`, `213.226.68.112`, `85.143.218.7`, and others
- Exfiltrated Data:
  - Outlook credentials
  - Billing/card information
  - Domain and system information

---

## 🔍 Suricata Alert Highlights

- 🚨 Evil EXE download from `209.141.55.226` pretending to be a JPEG
- 📦 WebSocket request to `87.236.22.142`
- 🔓 EternalBlue SMB exploit probe from infected host to domain controller
- 📤 Trickbot data exfiltration to `190.146.112.216`

> See full details in the `.txt` and `.jpg` alert files.

---

## 🔬 Methodology

- PCAP analyzed in Wireshark and correlated with Suricata IDS alerts
- Malicious files identified and hashed
- IOCs cross-referenced with VirusTotal, AbuseIPDB, and CrowdSec CTI
- Traffic anomalies and evasion techniques documented in full report

---

## 🧪 Obfuscation Techniques Observed

- Malware hidden in `.jpg`, `.png`, `.exe` formats
- WebSocket-based persistence
- TLS encryption to evade detection
- JA3 fingerprint reuse to link malicious infrastructure
- Anonymous SMB probing of IPC$, Netlogon, SAMR shares

---

## 👤 Author

Sriram  
Graduate Student – Digital Forensics & Cybersecurity  
February 2025

---

## 📄 License

This work is licensed under the  
Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0)

📌 *You may view and share this work with proper credit, but you may not modify it or use it for commercial purposes.

🔗 [View License Terms](https://creativecommons.org/licenses/by-nc-nd/4.0/)

