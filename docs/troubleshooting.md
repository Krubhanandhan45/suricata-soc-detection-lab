# Suricata Troubleshooting Notes

## Issue 1: HTTP alerts not triggering
**Cause:**
- Incorrect rule keywords
- Missing http.request_method
- Suricata running in IDS mode without proper interface

**Fix:**
- Used correct rule syntax:
  http.request_method;
  content:"GET";
- Verified rule load using:
  suricata -T -c /etc/suricata/suricata.yaml
- Restarted Suricata service

---

## Issue 2: fast.log empty
**Cause:**
- Logs not flushed
- Wrong interface monitored

**Fix:**
- Truncated log:
  truncate -s 0 /var/log/suricata/fast.log
- Restarted Suricata

---

## Validation Commands
```bash
ping 8.8.8.8
curl http://example.com
tail -f /var/log/suricata/fast.log
