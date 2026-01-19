# Suricata IDS SOC Lab – ICMP & HTTP Detection

This project demonstrates a hands-on SOC Analyst workflow using Suricata IDS on Ubuntu.
The lab focuses on custom rule creation, traffic detection, alert validation, and real-world troubleshooting.

---

## Objectives
- Deploy Suricata in IDS mode
- Write and load custom detection rules
- Detect ICMP (Ping) traffic
- Detect HTTP GET requests
- Validate alerts using fast.log and eve.json
- Troubleshoot rule-path and interface issues

---

## Environment
- OS: Ubuntu (VM)
- IDS: Suricata 7.x
- Mode: IDS
- Network Interface: enp0s3
- Log files:
  - /var/log/suricata/fast.log
  - /var/log/suricata/eve.json

---

## Custom Detection Rules

### ICMP Ping Detection
```conf
alert icmp any any -> any any (msg:"SOC Lab ICMP Ping Detected"; sid:1000001; rev:1;)
