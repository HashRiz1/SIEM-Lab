# Threat Hunting

## Purpose

Threat Hunting is used to search for and investigate any security events from the Ubuntu endpoint.

This focuses on specifics, such as alerts and documented investigation notes, that may be useful in the future for other investigations.

**Below are examples of what Threat hunting searches for**

- Malware detection alerts from ClamAV
- File activity events from Wazuh File Integrity Monitoring
- Rootcheck detection alerts
- Events from the Ubuntu endpoint agent

## Investigation: SCA AppArmor Status Change

An event was created in the threat hunting event category, the event was an SCA finding related to AppArmor

![image](screenshots/image.png)

**Investigation Steps:**

I reviewed the event details in Wazuh and determined that the event showed that a CIS Ubuntu benchmark check which changed from passing to to failed. This means the endpoint's hardening stance has changed and now requires review.

**Validation**

After identifying the event in Wazuh, I validated the AppArmor state directly on the Ubuntu endpoint.

I reviewed the AppArmor profile with ``sudo aa-status`` which I got 

![image](screenshots/imag
