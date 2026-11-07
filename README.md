# Splunk SOC Analyst Practical Labs 🛡️

A structured hands-on repository documenting security analysis, telemetry baseline profiling, and Search Processing Language (SPL) practicals executed on local Splunk Enterprise.

---

## 📂 Repository Navigation

| Practical | Name | Focus Area | Status | Link |
| :--- | :--- | :--- | :---: | :--- |
| **Splunk Prac-1** | **Baseline Data Inventory** | Telemetry Discovery & Sourcetype Profiling | ✅ Completed | [View Notes](./practicals/Splunk Prac-1.md) |

---

## 🛠️ Environment Specs
- **SIEM Platform:** Splunk Enterprise (Windows Local Instance)
- **Log Index:** `_internal` (System Diagnostic & Access Telemetry)
- **Analysis Approach:** Zero-download local ingestion, real-time daemon parsing, and SPL pipeline aggregation

---

## 🚀 Quick Execution Index

### [Splunk Prac-1: Baseline Data Inventory](./practicals/splunk-prac-1.md)
- **Goal:** Ingest telemetry baseline and map high-volume event producers.
- **Primary SPL:**
  ```spl
  index=_internal earliest=-7d
  | stats count by sourcetype
  | sort - count
  
