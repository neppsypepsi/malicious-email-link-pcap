# 🎯 PCAP Analysis – Fireworks Phishing Investigation

## 📝 What happened?

## 📌 What Happened

On Wednesday, June 25, 2025, at 12:02:43 PM, SentinelOne flagged a suspicious email that was sent internally. The email appeared to promote fireworks safety, linking to the site `mysafela[.]org/fireworks`. At first glance, the site looked legitimate and displayed normal public content. There were no immediate red flags in the page when it was initially loaded.

However, after normal use on the page, there was a sudden behavior change. A fake security pop-up appeared, claiming the user's PC was infected. Along with this pop-up, scareware-style audio played to simulate urgency. The page then redirected to a phishing site designed to impersonate Microsoft Defender, prompting users to call a fake support line or input credentials.

Our team believed that this was a **delayed JavaScript-based redirect**, allowing the initial link to pass casual inspection or sandboxing if not monitored long enough. This would essentially be a form of **social engineering**, aiming to scare the user into taking further action.

---

## 🧪 How I Investigated It

To better understand the network behavior behind this redirect, I downloaded the PCAP file generated during the Any.run sandbox session. Since the traffic reflects interaction with a public site in an isolated environment (not internal systems), I’ve made the redacted PCAP file available in this repository for reference under `/pcap`.

### 🔎 Initial Packet Review
Using Wireshark I first reviewed all **HTTP GET and POST requests**, but they didn’t reveal anything meaningful — likely because the site switched over to encrypted traffic soon after the page loaded. The HTTP traffic looked relatively normal and didn't show any immediate signs of injection or unusual parameters.

However, when I examined the **TLS traffic**, I found much more activity and a longer list of external domains. This included suspicious certificate exchanges and encrypted sessions that were established shortly after the pop-up appeared.

---

## 🌐 Domain Discovery via TLS Traffic

I extracted a list of domains and IPs observed during the TLS sessions. These appeared in **Server Name Indication (SNI)** fields, certificate metadata, or were contacted as part of redirects.

**Screenshots of the relevant Wireshark traffic** have been added in `/evidence/tls_domains/`.

Here is the list of domains I identified:
