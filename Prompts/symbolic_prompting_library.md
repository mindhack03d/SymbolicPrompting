# 📂 Symbolic Prompting Library

Welcome to the official repository of **Symbolic Prompting** examples. This collection is designed to demonstrate how to transform probabilistic LLM outputs into deterministic, state-driven execution.

> [!TIP]
> Each prompt here follows the **SPF (Symbolic Prompting Framework)** standards: Atomic tokens, explicit roles, and defined state transitions.

<div align="center">

[![GitHub Stars](https://img.shields.io/github/stars/mindhack03d/SymbolicPrompting?style=plastic&logo=github&color=gold&cacheBus=1)](https://github.com/mindhack03d/SymbolicPrompting)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Course_Complete-success?style=plastic&logo=youtube)](https://youtube.com/playlist?list=PLNFL-2KY9QZVqoRwRzVLPN6qmDftpsjg6)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Reels_EN-success?style=plastic&logo=youtube)](https://www.youtube.com/playlist?list=PLNFL-2KY9QZXhGEfGUOrrZtzGdPESwh4l)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Reels_ES-success?style=plastic&logo=youtube)](https://youtube.com/playlist?list=PLNFL-2KY9QZUKlXC_4gnVUHoAJdd4s-AC&si=4N7ROWCD3G46y8t5l)
[![License-MIT](https://img.shields.io/badge/License-MIT-green?style=plastic)](https://opensource.org/licenses/MIT)
[![Benchmark](https://img.shields.io/badge/📊-Benchmark_Data-2a2a2a?style=plastic)](../Benchmark/symbolic_support_test.md)



[![Back to Main Repo](https://img.shields.io/badge/←_Back_to_Course-Main_Page-gray?style=for-the-badge)](../README.md)

</div>

---

## 📑 Index 

### 🟠 Security Engineering: CVE/CPE Data Pipeline
**Objective:** Deterministic generation of a Python parser for the NVD (NIST) API. It maps complex JSON/CPE structures into a normalized CSV format ready for PostgreSQL ingestion.
* [**Case Study: CVE-NVD-CPE Parser**](cve_nvd_cpe.md)

### 🟠 Security Engineering: CWE/CVE Data Pipeline
**Objective**: Deterministic parsing of the CISA KEV catalog. Specifically focuses on mapping many-to-one relationships between CVEs and their associated CWE weaknesses. It maps complex JSON/CWE structures into a normalized CSV format ready for PostgreSQL ingestion.
- **Recursive Flattening**: Navigates deep JSON nesting (e.g., `vulnerabilities.i.cwes.j`) without field omission.
     - **Symbolic Binding**: Employs the `<~>` operator to map logical collections to physical CSV rows.
* [**Case Study: CWE-CVE Parser**](cwe_cve.md)

### 🔴 Vulnerability Research: Vulnerability Analysis via Ollama CLI
**Objective**: Deterministic validation of vulnerability exploits using the Symbolic Prompting Framework (SPF) within the Ollama CLI. It maps version-specific inputs (e.g., `OpenSSH 10.2p1 Debian5`) against internal CVE/KEV datasets using symbolic logic gates, returning zero-prose, machine-parsable results for Blue/Purple Team automation.
* [**Case Study: Vulnerability Mapping via SPF**](vulnerability_mapping_via_spf.md)

### 🟠 Security Analyst: CVE/CPE Extraction from Raw NMAP Scans
**Objective:** Deterministic extraction of granular package metadata from high-entropy NMAP service strings. This workflow automates the translation of raw version banners into standardized CPE (Common Platform Enumeration) identifiers, bypassing the need for fragile, manually maintained Regular Expressions.
* [**Case Study: CVE/CPE Extraction from Raw NMAP Scans**](cve_cpe_extraction_nmap_scan.md)

### 🟠 Security Analyst: Transforming Raw NMAP Banners into Structured JSON using Symbolic Prompting
**Objective**: To transform unstructured NMAP service banners into machine-parsable JSON objects. By applying formal symbolic logic to raw network responses, the framework isolates core software identities and versioning from environment noise (headers/meta-tags), enabling direct integration with automated vulnerability scanners.
* [**Case Study: Transforming Raw NMAP Banners into Structured JSON using Symbolic Prompting**](transform_nmap_banner_json.md)

### 🔵 Security Analyst: CPE & NVD Mapping: Automating Software Fingerprinting via Hybrid Neural-Symbolic Inference
**Objective**: To resolve high-entropy reconnaissance data into precise Common Platform Enumerators (CPE). By leveraging the **Symbolic Prompting Framework (SPF)**, this workflow programmatically normalizes version strings and maps them to the National Vulnerability Database (NVD), facilitating a deterministic bridge between raw asset discovery and proactive vulnerability correlation.
* [**Case Study: Precise CPE Identification and NVD Correlation using Symbolic Prompting**](neural_nvd_fingerprint.md)

### 🟠 Security Engineering: SPF-Powered CPE Normalization: From Raw Service Strings to Production-Ready Asset Intelligence
**Objective**: To transform messy reconnaissance data into standardized Common Platform Enumeration (CPE) identifiers using hybrid neural-symbolic execution. The **Symbolic Prompting Framework (SPF)** applies fuzzy matching logic (`IF/THEN` decision matrices), latent space mapping, and strict formatting constraints to convert inputs like `"PostgreSQL 9.6.0+"` into machine-parseable CPE 2.3 JSON—enabling automated vulnerability lookups, asset inventory normalization, and zero-prose API integration.
* [**Case Study: Symbolic Service Normalization for PostgreSQL, Nginx, and OpenSSH**](postgresql_normalization.md)

### 🔵 Security Analyst: SPF-Powered Nmap Intelligence: From Noisy Service Fingerprints to Production-Ready CPE
**Objective**: To replace brittle regex parsing with hybrid neural-symbolic logic for processing raw network scan data. The **Symbolic Prompting Framework (SPF)** ingests Nmap JSON, applies heuristic decision trees (`servicefp` prioritization), triggers latent space mapping for ambiguous strings, and enforces probabilistic weighting (≥90% confidence) to return standardized CPE identifiers with malicious software detection—enabling deterministic asset inventory, automated vulnerability correlation, and zero-prose API integration.
* [**Case Study: Symbolic Processing of Nmap Output for Blue Team Automation**](turn_raw_nmap_scan_into_structured_security_data.md)

### 🔴 Vulnerability Research: Hybrid Neural-Symbolic CVE Analysis: Automating Vulnerability Logic Mapping via SPF
**Objective**: To transform unstructured CVE descriptions into machine-parsable symbolic specifications for defensive security workflows. By leveraging the **Symbolic Prompting Framework (SPF)**, this process programmatically maps vulnerability data across four key dimensions—**VECTOR_PATH**, **PRIVILEGE_TRANSITION**, **PERSISTENCE_MECHANISM**, and **EXPLOITATION_STAGES**—eliminating conversational ambiguity and enabling deterministic integration with SOAR, SIEM, and Blue Team automation pipelines.
* [**Case Study: Symbolic Analysis of Supply Chain Integrity Failures (Theoretical Example: DEMO-001)**](hybrid_execution_defensive_research.md)

---

## 🛠️ Anatomy of a Prompt File
Every example in this folder follows this structure to ensure clarity:

1. **Objective**: What does this prompt solve?
2. **The Prompt**: The raw symbolic code (ready to copy-paste).
3. **Expected Output**: The deterministic result you should get.
4. **Logic Breakdown**: Why it works (the "engineering" behind it).

---

## 🚀 How to use these prompts
1. **Choose** a prompt from the list above.
2. **Copy** the code block inside the `.md` file.
3. **Paste** it into any compatible LLM (Gemini 3 Flash, GPT-4o, DeepSeek-V3).
4. **Observe** the deterministic behavior.

---

## 🤝 Contributing
Have you engineered a deterministic prompt using SPF? 
1. Fork the repo.
2. Add your `.md` file to this folder.
3. Update this index.
4. Open a Pull Request!

---

<details>
  <summary>⚖️ Legal Disclaimer (Click to expand)</summary>

This repository is for educational purposes only regarding Symbolic Prompting. The author is not responsible for the use that third parties may make of these techniques. The user is responsible for respecting the terms of service of AI platforms and applicable legislation. All content is provided "AS IS," without warranties.<br>
Compatibility may vary depending on model updates, tokenization behavior, and symbol parsing.
</details>

***

<div align="center">

![](https://img.shields.io/badge/Focus-Prompt_Engineering-blue?style=flat-square)
![](https://img.shields.io/badge/Logic-Symbolic_AI-blueviolet?style=flat-square)
![](https://img.shields.io/badge/Logic-Symbolic_Prompting-blueviolet?style=flat-square)
![](https://img.shields.io/badge/Architecture-State_Machines-ff69b4?style=flat-square)
![](https://img.shields.io/badge/LLM-Deterministic_Outputs-orange?style=flat-square)
![](https://img.shields.io/badge/Content-Educational_Course-success?style=flat-square)

</div>

---

## Author
- Jesus Huerta aka <em><a href="https://github.com/mindhack03d" rel="nofollow">@(\_mindhack03d_)</a></em></br>

---

<div align="center">

[![Back to Main Repo](https://img.shields.io/badge/←_Back_to_Course-Main_Page-gray?style=for-the-badge)](../README.md)

</div>

