#🛡️ Azure Sentinel Honeypot Lab (SIEM Detection Project)

This project demonstrates a self-built cloud honeypot using a publicly exposed Azure VM and Microsoft Sentinel to detect brute-force login attempts from real-world threat actors.

---

##💡 Project Summary

I built a cloud-based detection lab on Azure to simulate unauthorized access attempts and observe brute-force activity. Logs were ingested into Microsoft Sentinel for monitoring, detection, and manual incident investigation.

---

## ✅ What I Did

- Created an Azure **Resource Group**, **VNet**, and **Windows 10 VM**
- Configured **NSG** to allow all inbound traffic and disabled **Windows Firewall**
- Simulated failed RDP logins.Verified **Event ID 4625** in Event Viewer
- Connected the VM to a **Log Analytics Workspace**
- Installed and configured **Microsoft Sentinel**
- Used **KQL** to identify failed login attempts from attacker IPs
- Imported a **GeoIP watchlist** to enrich attacker data
- Created a **Sentinel Workbook** to visualize global attack locations
- Built a custom **Analytics Rule** to detect brute-force login patterns
- Investigated Sentinel-generated incidents via the **Investigation Graph**
- Validated attacker IPs using **VirusTotal** and manually closed **True Positive** incidents

---

## 📸 Screenshots 

🔓 0. VM Firewall Disabled (Inside the VM)
   ![Firewall Off](images/VM-FirewallsOff.png)

<details>
<summary>🔎 View Full Lab Walkthrough (Screenshots)</summary>
   

🔓 1. NSG Rule - Exposing VM to Inbound Traffic
    ![NSG Rule](images/NSG-Rule.png)
    
📊 2. KQL Query to Detect Failed Logins + GeoIP Lookup
    ![KQL Query + GeoIP](images/Logs-KQL-geo-search.png)

🌍 3. Global Attack Map - Brute Force Sources
   ![Geo Map](images/geo-map.png)

🚨 4.Logic App Automation Flow (Incident Trigger → Email)
    ![Logic App Designer](images/EmailOnBruteForceIncident(LogicApp).png)

   5.🔧Incident Email Alert (From Logic App)
   ![Email Alert](images/incident-email-alert.png)

   6.🧠Sentinel Generating Multiple Brute Force Incidents
   ![Incidents List](images/incidents.png)

 🕵️‍♂️ 7. Sentinel Incident Graph - Attack Entity Mapping
    ![Investigation Graph](images/investigation_graph.png)

🌐 8. Attacker Entity Investigation (IP Profile in Sentinel)
    ![Entity Details](images/investigation.png)

🧪 9. Verifying Attacker IP via VirusTotal
![VirusTotal Scan](images/virus_total.png)

✅ 10. Confirmed True Positive + Closed Incident
   ![Closed Incident](images/incident_closed.png)

🚫 11. Manual NSG Rule to Block Malicious IP  
   ![NSG Deny Rule](images/NSG-DenyMaliciousIP.png)

🧪 12. IP Flow Verification – Deny Rule Working  
   ![Flow Verify Denied](images/VerifyMaliciousIP-Denied.png)


   
</details>

---

## 🛠️ Tools & Technologies

- Microsoft Azure (Resource Group,VNet,VM,NSG)
- Microsoft Sentinel (SIEM)
- Log Analytics Workspace (LAW)
- Azure Monitor Agent (AMA)
- Kusto Query Language (KQL)
- Sentinel Analytics Rules & Workbooks
- VirusTotal
- RDP & Event Viewer

---

## 🧠 Insights & Lessons Learned

- Exposing the VM to the internet allowed me to simulate real-world attacks and observe how attackers behave in a short timeframe.
- Disabling the VM firewall and creating open NSG rules were intentional misconfigurations to attract brute-force attempts, which were successfully logged and analyzed.
- I used Microsoft Sentinel’s built-in rules to generate alerts and followed the full incident lifecycle: detection, investigation, validation, and closure.
- Validating malicious IPs using VirusTotal added confidence in classifying the incident as a true positive.
- This project helped me understand how cloud SIEM systems like Sentinel operate in detecting and managing security incidents end-to-end.

---

## 🙋‍♂️ Rakip
 
Cyber Security | AZ-900 Certified   
  
<!--📫 [LinkedIn] | [GitHub] -->
