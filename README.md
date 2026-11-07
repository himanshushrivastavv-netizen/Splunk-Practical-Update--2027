# Splunk SOC Analyst Practical Labs 🛡️

A structured hands-on repository documenting security analysis, telemetry baseline profiling, threat triage, and Search Processing Language (SPL) practicals executed on local Splunk Enterprise.

---

## 📂 Repository Structure & Navigation

| Module | Practical Name | Focus Area | Status | Link |
| :--- | :--- | :--- | :---: | :--- |
| **B1** | **Baseline Data Inventory** | Telemetry Discovery & Sourcetype Profiling | ✅ Completed | [View Notes](./practicals/B1-data-inventory.md) |
| **B2** | **Error & Anomaly Triage** | Daemon Component Failures & Warning Analysis | ⏳ In Progress | [View Notes](./practicals/B2-anomaly-detection.md) |
| **B3** | **Access & Endpoint Telemetry** | HTTP Status Codes & REST API Audit | 📋 Planned | [View Notes](./practicals/B3-access-telemetry.md) |
| **B4** | **Detection Rules & Alerting** | Threshold-based Anomaly Alerting | 📋 Planned | [View Notes](./practicals/B4-detection-rules.md) |

---

## 🛠️ Environment Specs
- **SIEM Platform:** Splunk Enterprise (Windows Local Instance)
- **Log Index:** `_internal` (System Diagnostic & Access Telemetry)
- **Analysis Approach:** Zero-download local ingestion, real-time daemon parsing, and SPL pipeline aggregation

---

## 🚀 Quick Execution Index

### [B1: Baseline Data Inventory](./practicals/B1-data-inventory.md)
- **Goal:** Ingest telemetry baseline and map high-volume event producers.
- **Primary SPL:**
  ```spl
  index=_internal earliest=-7d
  | stats count by sourcetype
  | sort - count
