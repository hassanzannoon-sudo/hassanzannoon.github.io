# Incident Report: Recon & Brute-force Activity

**Project:** Network Attack Simulation (Kali + Suricata)
**Author:** Hassan Zannoon
**Date:** 2025-12-09

## Summary
Observed port scanning followed by password-guessing attempts against SSH. Suricata alerts captured scanning signatures and anomalies in network traffic.

## Timeline
- 2025-12-01 09:10 IST — Nmap scan detected.
- 2025-12-01 09:12 IST — Multiple SSH connection attempts (hydra) observed.
- 2025-12-01 09:15 IST — Suricata produced multiple alerts (SUSPICIOUS_SCAN).

## Detection
- Suricata logs: eve.json and fast.log
- PCAPs captured for timeframe

## Investigation Steps
1. Review Suricata eve.json alerts and map to source IPs.
2. Extract PCAP and analyze with Wireshark for patterns.
3. Correlate with host logs for any successful connections.
4. Prepare IOC list (IPs, domains, hashes).

## Findings
- Scanning followed by brute-force behavior from 198.51.100.23.
- No successful exploitation achieved in lab environment.

## Containment & Remediation
- Block offending IP at perimeter and update IDS rules.
- Harden SSH and reduce service exposure.
- Retain PCAPs for further analysis.

## Recommendations
- Use anomaly detection for repeated scanning across multiple hosts.
- Automate containment for high-confidence malicious scanning.

## Evidence Files
- pcaps/scan-session.pcap
- suricata/eve.json
- fast.log
- attack-timeline.md
