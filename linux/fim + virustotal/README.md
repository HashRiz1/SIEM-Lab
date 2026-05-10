# FIM and VirusTotal Integration

## Summary

For this part of the lab, I configured Wazuh File Integrity Monitoring on the Ubuntu endpoint and integrated VirusTotal enrichment on the Wazuh manager.

File Integrity Monitoring was used to detect any creation, modification, or deletion of files on the endpoint. VirusTotal added more context to file integrity events, helping show how endpoint data can be reviewed during SOC alerts.

## What I Configured

- Wazuh File Integrity Monitoring for monitored endpoint paths
- VirusTotal integration on the Wazuh manager
- VirusTotal enrichment for syscheck events
- Wazuh Dashboard searches for FIM and VirusTotal-related alerts

## Configuration

The VirusTotal integration was configured on the Wazuh manager in:

```text
/var/ossec/etc/ossec.conf

<integration>
  <name>virustotal</name>
  <api_key>REDACTED</api_key>
  <group>syscheck</group>
  <alert_format>json</alert_format>
</integration>
```

## Testing

I tested FIM in various ways, including creating, deleting, and modifying files inside the endpoint. 
These changes then create a syscheck event on Wazuh through the FIM Events category. 

![Event](screenshots/image.png)
We can see that Wazuh generated a syscheck log that gives us the time, which agent was involved, the path, which in this case was for test.txt, and the event that occurred, which is `Integrity checksum changed`.

We can further check the modifications by opening the document details log.

![Event](screenshots/1image.png)

Upon opening the document details, we can view what was changed through the syscheck.diff row. The `> hello` means the text "hello" was added to the file. 

If it were < it would mean it was removed from the file
