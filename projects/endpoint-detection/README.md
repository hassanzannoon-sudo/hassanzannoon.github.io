# 💻 Endpoint Forensics & Log Analysis (Sysmon/ELK)

### **1. 🚀 Executive Summary**

This project demonstrates proficiency in **Endpoint Detection and Response (EDR)** principles using **Sysmon** for deep telemetry collection, forwarded to the **ELK Stack (Elasticsearch, Logstash, Kibana)** for analysis. I successfully configured Sysmon with a robust configuration, built the logging pipeline, and utilized the collected data to conduct a full **Incident Investigation** of a simulated adversary attack.



---

### **2. 🛠️ Technical Implementation**

| Component | Role in Project | Demonstrated Skill |
| :--- | :--- | :--- |
| **Sysmon** | Provides high-fidelity, deep visibility into process creation (Event ID 1), network connections (Event ID 3), and file creation (Event ID 11). | **Endpoint Telemetry & Forensic Data Collection** |
| **Winlogbeat / Logstash** | Used to ship and process Sysmon event logs to Elasticsearch. | **Log Pipeline Management & Data Normalization** |
| **Kibana** | Utilized for querying data (KQL), visual analysis, and process tree reconstruction. | **Querying & Incident Investigation** |

#### **Incident Investigation Scenario**

* **Scenario:** Simulated a common attack chain (e.g., initial macro execution leading to PowerShell C2 beaconing).
* **Investigation Steps:**
    1.  Identified the initial suspicious process creation using **Sysmon Event ID 1**.
    2.  Traced the **Parent-Child Process relationships** to reconstruct the attack timeline.
    3.  Identified network C2 connections using **Sysmon Event ID 3**.
    4.  Determined the scope and impact using the full process execution graph.

---

### **3. 📈 Key Outcomes**

* **Attack Mapping:** Successfully mapped the intrusion steps back to the relevant **MITRE ATT&CK** stages (e.g., Execution, Command and Control).
* **Forensic Artifacts:** Extracted critical forensic artifacts, including Process IDs (PIDs), full Command Line arguments, and File Hash (SHA256).
* **Evidence:**
    * [Link to Sysmon Configuration File on GitHub]
