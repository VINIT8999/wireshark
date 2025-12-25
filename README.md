Network Traffic Analysis using Wireshark (Learning Project)
Overview

This project documents my hands-on learning with Wireshark by capturing and analyzing live Wi-Fi network traffic.
The goal was to understand how encrypted traffic (HTTPS, TLS, QUIC) appears at the packet level and how basic filtering can be used to observe normal network behavior from a security perspective.

This is not a real incident response or threat-hunting case. It is a learning and exploration exercise.

Tool Used

Wireshark

Dataset

Live Wi-Fi network capture

Traffic generated from normal browsing and background system activity

Internal host IP used for analysis: 192.168.1.3

What I Analyzed

The analysis was done using Wireshark display filters to understand different traffic patterns:

1. TCP Traffic

Observed dominant TCP traffic over port 443

Confirmed normal HTTPS communication behavior

2. UDP / QUIC Traffic

Identified UDP traffic on port 443 using QUIC (HTTP/3)

Learned how modern browsers use QUIC for faster encrypted communication

3. Host-Specific Traffic

Isolated traffic related to a single internal system

Focused analysis on inbound and outbound communication of that host

4. TLS Handshake Observation

Identified TLS 1.2 handshake packets (Client Hello, Server Hello, Certificate)

Understood where encryption starts and why payload inspection is limited

5. Public Internet Communication

Confirmed outbound connections to public IP addresses

Validated normal internet access behavior

6. TCP Reset Packets

Observed TCP RST packets on HTTPS connections

Learned how normal session termination can appear in captures

7. SSH Activity Check

Checked for rapid or repeated SSH connections on port 22

No SSH brute-force or automated attack behavior observed during capture

Key Learnings

Encrypted traffic dominates modern networks

Payload inspection is not possible without decryption keys

QUIC traffic looks very different compared to traditional TCP-based HTTPS

Simple filters can quickly rule out obvious suspicious activity, but do not replace deep SOC investigation

Limitations

No attack traffic was intentionally generated

No decryption or advanced threat analysis was performed

No correlation with logs, SIEM, or threat intelligence

Conclusions are based only on packet-level observation

Disclaimer

This project is created for learning purposes only.
It should not be considered a professional SOC investigation, incident response report, or threat-hunting analysis.

Author

Vinit Shankar Raparti
