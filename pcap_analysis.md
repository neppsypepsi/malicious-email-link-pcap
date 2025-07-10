# 🧪 PCAP Analysis – Wireshark Review

This file documents the suspicious traffic observed when opening the flagged email link in a sandboxed environment.

## ✅ What We Found:

- DNS queries to unknown subdomains
- TCP handshakes with suspicious IPs
- HTTP GET requests that resolved to obfuscated redirectors
- Delay-triggered popup activity consistent with scareware patterns

## 📎 Notes:

- Original article appeared legitimate
- Malicious behavior triggered only after scroll + idle time
- Screenshots and packet info to be added Monday
