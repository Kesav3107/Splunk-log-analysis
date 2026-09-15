# 📊 Splunk Log Analysis

<p align="center">
  <strong>Ingest • Analyze • Visualize • Detect</strong>
</p>

<p align="center">
  A dataset-driven log and event analysis project using Splunk Enterprise
</p>

---

## 📌 Project Overview

This project demonstrates the use of **Splunk Enterprise** for centralized
log ingestion, searching, analysis, visualization, and security-oriented
investigation.

The project uses **pre-existing log datasets** that are uploaded into
Splunk and organized using dedicated indexes and source types.

The analysis does not depend on live DNS, HTTP, FTP, SSH, VPN, SMTP, DHCP,
or firewall servers. Instead, representative datasets are analyzed inside
Splunk.

> ⚠️ **Project Scope:** This is a dataset-driven academic project.
> Findings represent patterns observed in the supplied datasets and should
> be validated with additional evidence in real-world environments.

---

## 🎯 Objectives

- Learn the installation and configuration workflow of Splunk Enterprise
- Organize log datasets using dedicated indexes and source types
- Ingest pre-existing log files through Splunk Data Inputs
- Use Splunk Processing Language (SPL) for event analysis
- Search, filter, aggregate, and summarize log events
- Create dashboards and visualizations
- Identify authentication failures and unusual activity patterns
- Analyze errors and blocked traffic
- Investigate source and destination activity
- Extract operational and security-related insights from logs

---

## 🔄 Project Workflow

```text
        ┌─────────────────────────┐
        │   Pre-existing Logs     │
        │   Multiple Log Sources  │
        └────────────┬────────────┘
                     │
                     ▼
        ┌─────────────────────────┐
        │  1. Add / Upload Data   │
        │  Splunk Data Inputs     │
        └────────────┬────────────┘
                     │
                     ▼
        ┌─────────────────────────┐
        │  2. Create Indexes      │
        │  DNS / HTTP / FTP / SSH │
        │  Tunnel / SMTP / DHCP   │
        │  Firewall               │
        └────────────┬────────────┘
                     │
                     ▼
        ┌─────────────────────────┐
        │  3. Verify Ingestion    │
        │  Index / Sourcetype     │
        │  Host / Events          │
        └────────────┬────────────┘
                     │
                     ▼
        ┌─────────────────────────┐
        │  4. SPL Search &        │
        │     Analysis            │
        │  Counts / Trends /      │
        │  Rankings / Patterns    │
        └────────────┬────────────┘
                     │
                     ▼
        ┌─────────────────────────┐
        │  5. Dashboards &        │
        │     Visualizations      │
        └────────────┬────────────┘
                     │
                     ▼
        ┌─────────────────────────┐
        │  6. Investigation &     │
        │     Interpretation      │
        └────────────┬────────────┘
                     │
                     ▼
        ┌─────────────────────────┐
        │   Operational &         │
        │   Security Insights     │
        └─────────────────────────┘
```
🧰 Tools & Technologies
| Technology            | Purpose                                                    |
| --------------------- | ---------------------------------------------------------- |
| **Splunk Enterprise** | Log ingestion, searching, analysis and visualization       |
| **SPL**               | Searching, filtering, aggregation and statistical analysis |
| **Splunk Indexes**    | Organizing different log datasets                          |
| **Splunk Dashboards** | Visualizing events, trends and distributions               |
| **Windows**           | Local environment used for Splunk Enterprise               |

---
📂 Log Sources Analyzed
The project analyzes eight major log categories.
| # | Log Category | Index      | Primary Analysis                                                |
| - | ------------ | ---------- | --------------------------------------------------------------- |
| 1 | 🌐 DNS       | `dns`      | Queries, query types, source IPs and potential C2 patterns      |
| 2 | 🌍 HTTP      | `http`     | Requests, status codes, URLs, user agents and risky requests    |
| 3 | 📁 FTP       | `ftp`      | Logins, failures, users and file transfers                      |
| 4 | 🔐 SSH       | `ssh`      | Authentication, failed logins, users and source IPs             |
| 5 | 🔀 Tunnel    | `tunnel`   | Protocols, successful/failed tunnels and source/destination IPs |
| 6 | 📧 SMTP      | `smtp`     | Delivery results, senders, recipients and email patterns        |
| 7 | 🌐 DHCP      | `dhcp`     | Discover/Request/Ack/Nak/Release activity, clients and leases   |
| 8 | 🛡️ Firewall | `firewall` | Allowed/blocked traffic and source/destination IPs              |

---
🔍 Log Analysis Modules
* 1️⃣ DNS Log Analysis
* 2️⃣ HTTP Log Analysis
* 3️⃣ FTP Log Analysis
* 4️⃣ SSH Log Analysis
* 5️⃣ Tunnel Log Analysis
* 6️⃣ SMTP Log Analysis
* 7️⃣ DHCP Log Analysis
* 8️⃣ Firewall Log Analysis

---

📊 Dashboard & Visualization

The project uses Splunk dashboards to transform raw events into
visual summaries.

The dashboards include:

* 📈 Time-based activity trends
* 📊 Event-volume analysis
* 🍩 Distribution charts
* 🔢 Key event metrics
* 🌐 Source and destination analysis
* 📋 Event tables
* 🔍 SPL search examples
* ⚠️ Indicators requiring further investigation

The dashboard screenshots demonstrate how different log categories can be
analyzed through a common Splunk interface.

---
🔎 Evidence
Project Overview

Splunk Workflow & Dashboards

Installation & Configuration

Index Configuration

Log Upload

DNS Analysis

HTTP Analysis

FTP Analysis

SSH Analysis

Tunnel Analysis

SMTP Analysis

DHCP Analysis

Firewall Analysis

---
🧠 Results & Findings

The project demonstrates that Splunk can provide a common analysis layer
for heterogeneous log data.

The same core workflow can be applied across different datasets:
```
Indexing
   ↓
SPL Searching
   ↓
Aggregation
   ↓
Visualization
   ↓
Investigation
   ↓
Security / Operational Insights
```
---
Key Findings
* 🔐 SSH and FTP logs provide visibility into repeated authentication
  failures and user/source-IP behavior.
* 🌐 HTTP and firewall logs provide visibility into errors, blocked
  traffic and source/destination activity.
* 🔎 DNS analysis can highlight high-volume domains and unusual query
  behavior requiring investigation.
* 📧 SMTP analysis can reveal failed deliveries and unusual
  sender/recipient relationships.
* 🌐 DHCP analysis can reveal unusual lease and request behavior.
* 🔀 Tunnel logs provide visibility into protocol usage and repeated
  failed tunnel attempts.

Important: A suspicious indicator in a dataset is not automatically
proof of malicious activity. Additional evidence and validation are
required in real-world investigations.

---

📚 SPL Query Skills Demonstrated

The project includes SPL examples covering:

* stats
* sort
* count
* timechart
* Distinct-count analysis
* Filtering
* Ranking
* Event aggregation
* Source-IP analysis
* Destination-IP analysis
* Traffic/activity-volume analysis

Example: 
```
index=ssh sourcetype=ssh_logs result="failed"
| stats count by src_ip
| sort -count
| head 10
```
---
🎓 Skills Demonstrated
Splunk

* Splunk Enterprise
* Data ingestion
* Index configuration
* Source types
* SPL searching
* Event analysis
* Dashboard creation
* Data visualization

Log Analysis

* DNS analysis
* HTTP analysis
* FTP analysis
* SSH analysis
* Tunnel analysis
* SMTP analysis
* DHCP analysis
* Firewall analysis

Security Analysis

* Authentication-failure analysis
* Source-IP investigation
* Blocked-traffic analysis
* Error analysis
* Suspicious-pattern identification
* Event correlation and investigation

---
⚠️ Limitations
* The project uses uploaded/pre-existing datasets rather than live
  production streams.
* The project does not demonstrate deployment of actual DNS, FTP, SSH,
  VPN, SMTP, DHCP or firewall servers.
* Suspicious-activity indicators should be validated with additional
  evidence in real environments.
* Results depend on the quality, completeness, timestamps and field
  structure of the input datasets.

  ---
🚀 Future Enhancements

Possible future improvements include:

* Connect Splunk to live log sources through forwarders or network inputs
* Create scheduled alerts for repeated authentication failures
* Create alerts for blocked firewall traffic
* Add threshold-based anomaly detection
* Develop correlation searches
* Integrate threat-intelligence lookups
* Add external IP/domain enrichment
* Build role-based SOC dashboards
* Build operations and management dashboards

---
📄 Project Report

The complete project report is available here:

📘 View Project Report

The report contains the complete project methodology, SPL query library,
module explanations, dashboard evidence, findings, limitations and
future enhancements.

---
🏁 Conclusion

Splunk Log Analysis demonstrates how Splunk Enterprise can be used to
ingest, organize, search, analyze and visualize heterogeneous log datasets.

By creating dedicated indexes and focused dashboards for eight different
log categories, the project demonstrates how SPL and Splunk visualizations
can transform raw event data into useful operational and security insights.

The project is intentionally dataset-driven and does not depend on virtual
machines, Ubuntu or separate server infrastructure.

---
👨‍💻 Author

Chavali Keshava Gopalu

🔐 Cybersecurity Enthusiast | SOC Analyst Aspirant

🛡️ Network Security | Threat Detection | Log Analysis

🐍 Python | Linux | Splunk | Wireshark
