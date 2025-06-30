# Wireshark Setup Notes
- Installed Wireshark: `sudo apt install wireshark`.
- Identified interface: `ip link show`.
- Captured on `wlan0`: `sudo wireshark`.
- Generated traffic: `firefox http://cursor.com`, `ping -c 4 google.com`, `curl https://www.cursor.com`.
- Filtered: `dns`, `icmp`.
- Saved capture: `wireshark_capture.pcap`.
