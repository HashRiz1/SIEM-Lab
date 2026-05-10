# Linux Endpoint Monitoring Overview

## Objective

This section documents the Linux/Ubuntu phase of my Wazuh SIEM/SOC lab.

The goal is to monitor an Ubuntu endpoint using Wazuh and simulate realistic SOC workflows, including endpoint data collection, alert integration, and malware detection.

## Implemented Capabilities
- File Integrity Monitoring
- VirusTotal enrichment
- Rootcheck testing
- ClamAV malware detection
- ClamAV on-access blocking/prevention
- ClamAV log collection into Wazuh
- Vulnerability Detection
- Syscollector inventory collection
- Security Configuration Assessment

## Sections
- [ClamAV Integration](clamav-integration/) - Local Linux malware detection, on-access prevention, and Wazuh alerting using ClamAV logs.
