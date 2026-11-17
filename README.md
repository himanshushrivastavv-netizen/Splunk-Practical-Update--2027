# Splunk SOC Analyst Practical Labs 🛡️

A structured hands-on repository documenting security analysis, telemetry baseline profiling, and Search Processing Language (SPL) practicals executed on local Splunk Enterprise.

---

## 📂 Repository Navigation

| Practical | Name | Focus Area | Status | Link |
| :--- | :--- | :--- | :---: | :--- |
| **Splunk Prac-1** | **Baseline Data Inventory** | Telemetry Discovery & Sourcetype Profiling | ✅ Completed | [View Notes](./Splunk%20Prac-1) |
| **Splunk Prac-2** | **Raw Events & Fields Exploration** | Windows Security Logs, Field Extraction & EventCode Profiling | ✅ Completed | [View Notes](./Splunk%20Prac-2) |
| **Splunk Prac-3** | **Windows EventCode Distribution** | Frequency Distribution, Bar Chart Visualization & Triage | ✅ Completed | [View Notes](./Splunk%20Prac-3) |

---

## 🛠️ Environment Specs
- **SIEM Platform:** Splunk Enterprise (Windows Local Instance)
- **Log Indexes:** 
  - `_internal` (System Diagnostic & Access Telemetry) - Prac-1
  - `main` (Local Windows Security Event Logs, host: Himanshu) - Prac-2, Prac-3
- **Analysis Approach:** Zero-download local ingestion, real-time daemon parsing, and SPL pipeline aggregation

---

## 🚀 Quick Execution Index

### [Splunk Prac-1: Baseline Data Inventory](./Splunk%20Prac-1)
- **Goal:** Ingest telemetry baseline and map high-volume event producers.
- **Primary SPL:**
  ```spl
  index=_internal earliest=-7d
  | stats count by sourcetype
  | sort - count
