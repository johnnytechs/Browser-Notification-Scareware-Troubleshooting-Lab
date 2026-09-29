# Browser Notification Scareware Troubleshooting Lab

**Scenario:** I investigated repeated fake antivirus notifications appearing on a Windows computer. The alerts claimed that virus protection had expired and that multiple threats were detected. I identified that the notifications were being delivered through Microsoft Edge rather than Windows Security, then blocked and removed the suspicious browser notification source. Then Notifications stopped Completly 

**1. Identify the Fake Antivirus Notifications**

Multiple antivirus-style alerts appeared on the desktop claiming that the system had expired virus protection, malware, and potential viruses.

The notifications referenced antivirus brands such as Norton and McAfee and attempted to convince the user to click buttons such as `Protect`, `Activate protection`, and `Delete viruses`.

I noticed that the notifications were being delivered through Microsoft Edge, which indicated that the alerts were likely browser notifications rather than verified Windows Security detections.

<img width="274" height="753" alt="01-fake-antivirus-notifications" src="https://github.com/user-attachments/assets/5bc45e79-d808-4295-8466-c7f3bee139f2" />

**2. Identify and Block the Suspicious Notification Source**

I opened Microsoft Edge notification permissions and reviewed the websites associated with browser notifications.

I identified the suspicious domain shown in the original alerts:

`datljgps66ac738de10.retuio.co.in`

I blocked the site from sending additional browser notifications to prevent the fake antivirus alerts from continuing.

<img width="1448" height="1086" alt="02-blocked-malicious-browser-notification" src="https://github.com/user-attachments/assets/d0688de7-9be3-4fb0-aa10-922b65513579" />

**Note:** This screenshot was reconstructed after remediation to document the suspicious domain that was observed during the incident.

**3. Verify the Suspicious Notification Permission Was Removed**

After blocking the suspicious site, I removed the notification permission and reviewed the Microsoft Edge notification settings again.

The notification permission lists showed that no suspicious websites were currently allowed or blocked, confirming that the unwanted browser notification entry had been removed.

<img width="945" height="944" alt="03- Malaware Notification Removed" src="https://github.com/user-attachments/assets/7c5a01b7-d5f0-42af-941e-7053e1830af7" />


**4. Verify the System with Windows Security**

I opened Windows Security and checked the system for current threats.

Windows Security showed no current threats, which helped confirm that the original warnings were scareware-style browser notifications rather than active threat detections from Windows Security.


<img width="945" height="944" alt="04-windows-security-no-current-threats" src="https://github.com/user-attachments/assets/5942c467-125b-4c7c-8303-baae34732d98" />


**Tools used:** Microsoft Edge • Windows Security • Site Permissions • Browser Notification Settings • Windows 11

**Result:** Successfully identified the source of repeated fake antivirus notifications, blocked and removed the suspicious browser notification permission, and verified the system status using Windows Security.

## What I Learned

I learned how browser notification permissions can be abused by deceptive websites to display convincing antivirus and malware warnings directly on the Windows desktop.

During the troubleshooting process, I identified that the alerts were being delivered through Microsoft Edge instead of Windows Security. This helped narrow the issue down to browser notification permissions rather than immediately assuming the computer was infected with malware.

I also learned the importance of verifying the source of a security warning before interacting with it. Instead of clicking the alert, I reviewed the browser permissions, identified the suspicious domain, removed its access, and verified the system through Windows Security.

This lab reinforced the importance of identifying the source of an alert, isolating the cause, applying the appropriate fix, and validating the system afterward.

**Identify → Investigate → Block → Remove → Verify**
