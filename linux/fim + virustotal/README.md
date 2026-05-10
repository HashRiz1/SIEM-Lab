# FIM and VirusTotal Integration

## Overview

For this part of the lab, I used Wazuh's File Integrity Monitoring to detect file activity on the Ubuntu endpoint. I also configured VirusTotal so Wazuh could check a file's reputation, and when needed, file integrity events were generated.

## Validation

The EICAR test file was used as a safe test artifact.

Wazuh detected the file activity through File Integrity Monitoring, and the VirusTotal integration generated an alert.
