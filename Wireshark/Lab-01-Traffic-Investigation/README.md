# Wireshark Lab 1 – Traffic Investigation

## Objective

Analyze network traffic using Wireshark and identify protocols, hostnames, encryption, and browser activity.

---

## Tools Used

- Kali Linux
- Wireshark
- PCAP Analysis

---

## Investigation 1: TLS Traffic

### Findings

- Protocol: TLS 1.2
- Destination Port: 443
- Encryption: Enabled
- SNI (Server Name Indication): Present

### Hostname Discovered

firefox-settings-attachments.cdn.mozilla.net

### Questions Answered

| Question | Answer |
|-----------|-----------|
| Protocol used on port 443 | HTTPS |
| What translates hostnames to IPs | DNS |
| Meaning of SNI | Server Name Indication |
| Hostname discovered | firefox-settings-attachments.cdn.mozilla.net |

### Assessment

The traffic appears legitimate because it originates from Mozilla Firefox infrastructure.

---

## Investigation 2: HTTP Traffic

### Findings

- Destination IP: 34.107.221.82
- Destination Port: 80
- Protocol: HTTP
- Encryption: None

### Host Header

detectportal.firefox.com

### User-Agent

Mozilla/5.0 (X11; Linux x86_64; rv:140.0) Gecko/20100101 Firefox/140.0

### Why Host and User-Agent Were Visible

HTTP traffic is transmitted in plaintext, allowing headers to be viewed directly. In HTTPS/TLS traffic, application-layer data is encrypted.

---

## Security Concepts Learned

- DNS hostname resolution
- HTTP vs HTTPS
- TLS encryption
- Server Name Indication (SNI)
- User-Agent analysis
- Packet inspection
- Browser traffic identification

---

## Conclusion

This investigation demonstrated how Wireshark can be used to identify protocols, hostnames, browser activity, and encrypted versus unencrypted traffic. The observed traffic was determined to be legitimate Mozilla Firefox traffic.

