# Packet Analysis Report - Elevate Labs Task 5

## Task Overview

- **Objective**: Capture and analyze network traffic for Day 5 of the Elevate Labs Cybersecurity Internship (June 30, 2025).
- **Tool Used**: Wireshark on Ubuntu.
- **Interface**: `wlp1s0`
- **Goal**: Capture packets, identify at least three protocols, filter by protocol, and export as `.pcap`.

## Packet Capture Process

1. **Installed Wireshark**:

   ```bash
   sudo apt update
   sudo apt install wireshark
   ```
2. **Identified Interface**:

   ```bash
   ip link show
   ```
   - Selected `wlp1s0`.
3. **Captured Traffic**:
   - Started Wireshark: `sudo wireshark`
   - Captured on `wlp1s0` for \~60 seconds.
   - Generated traffic:

     ```bash
     firefox https://cursor.com
     ping -c 5 google.com
     curl https://www.curson.com
     ```
4. **Stopped Capture**: Clicked **Stop** in Wireshark.
5. **Filtered Packets**:
   - Applied filters: `dns`, `tcp`.
   - Screenshot: `Screenshots/wireshark_dns.png`.
   - Screenshot: `Screenshots/wireshark_icmp.png
6. **Exported Capture**:
   - Saved as `wireshark_capture.pcap`.

## Identified Protocols

1. **DNS**:
   - **Details**: Query for `cursor.com` (A record), response with IP `192.168.55.213`.
   - **Filter**: `dns`.
   - **Observation**: UDP-based, resolved domains for browsing and ping.
2. **ICMP**:
   - **Details**: 5 echo requests/replies to `google.com`
   - **Filter**: `icmp`.
   - **Observation**: Used for ping, confirmed network reachability.

## Summary

- **Capture Duration**: \~60 seconds, \~500 packets.
- **Key Findings**:
  - DNS queries resolved domains for browsing and ping operations.
  - ICMP confirmed connectivity to external servers.
- **Wireshark Decryption**: Wireshark can decrypt TLS if provided with private keys or session keys (e.g., SSLKEYLOGFILE), but metadata like IPs and ports remain visible.

## Learnings

- **Packet Analysis**: Wireshark reveals protocol interactions, aiding troubleshooting and security analysis.
- **Protocols**: HTTP, DNS, and ICMP are foundational for web and network connectivity.
- **Next Steps**: Explore TLS decryption and advanced filters (e.g., by IP or payload).

## Files Included

- `wireshark_capture.pcap`: Packet capture file.
- `Screenshots/wireshark_filters.png`: Screenshot of filtered packets.
- `packet_analysis_report.md`: This report.
- `README.md`: Task overview.
- `notes.md`: Wireshark setup commands.

## Portfolio

This task is part of my Elevate Labs internship portfolio: Elevate-Labs-Internship-Tasks.
