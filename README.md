# 📨 Malicious Email Link PCAP – Redacted Case Study

This repository documents the investigation of a suspicious email sent internally, which triggered a malware alert during my cybersecurity internship. The link appeared to lead to a normal article, but later revealed malicious behavior including scareware pop-ups and suspicious network activity.

> ⚠️ All names, domains, and agency details have been redacted for public release.

---

## 🧪 Incident Summary

- Email sent internally with good intent (public safety warning)
- Link led to a public article site
- Initially appeared safe in sandboxed VM
- After ~1 minute of scrolling, triggered:
  - Fake “Your PC is infected” popup
  - Scareware audio alerts
  - Malicious redirect link embedded in popup

---

## 🌐 Network Traffic

- Full PCAP file captured from visit
- Inspected using **Wireshark**
- Suspicious DNS and TCP traffic observed:
  - Possible IP loggers
  - Cookie trackers
  - Fake Microsoft tech support domains

---

## 🛠️ Tools Used

- Wireshark  
- urlscan.io  
- VirusTotal  
- Sandboxed Virtual Machine  
- Firefox Developer Tools (optional)

---

📁 Screenshots and traffic logs will be added Monday in the `/evidence` folder.
