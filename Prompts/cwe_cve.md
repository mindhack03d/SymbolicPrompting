# 🐍 Case Study: Python Script Expert for CWE/CVE Parsing

This example demonstrates how to use the **Symbolic Prompting Framework (SPF)** to transform a complex data extraction task into a deterministic engineering process. Instead of asking the AI to "write a script," we define the **logic flow** and **data structures** explicitly.

> [!IMPORTANT]
> **Core Concept:** Using symbolic logic to map flattened JSON structures directly into Python objects, eliminating conversational overhead and output variance.

<div align="center">

[![GitHub Stars](https://img.shields.io/github/stars/mindhack03d/SymbolicPrompting?style=plastic&logo=github&color=gold&cacheBus=1)](https://github.com/mindhack03d/SymbolicPrompting)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Course_Complete-success?style=plastic&logo=youtube)](https://youtube.com/playlist?list=PLNFL-2KY9QZVqoRwRzVLPN6qmDftpsjg6)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Reels_EN-success?style=plastic&logo=youtube)](https://www.youtube.com/playlist?list=PLNFL-2KY9QZXhGEfGUOrrZtzGdPESwh4l)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Reels_ES-success?style=plastic&logo=youtube)](https://youtube.com/playlist?list=PLNFL-2KY9QZUKlXC_4gnVUHoAJdd4s-AC&si=4N7ROWCD3G46y8t5l)
[![License-MIT](https://img.shields.io/badge/License-MIT-green?style=plastic)](https://opensource.org/licenses/MIT)
[![Benchmark](https://img.shields.io/badge/📊-Benchmark_Data-2a2a2a?style=plastic)](../Benchmark/symbolic_support_test.md)

[![Back to Main Repo](https://img.shields.io/badge/←_Back_Main_Page-gray?style=for-the-badge)](../README.md) | [![Symbolic Prompting Library](https://img.shields.io/badge/←_Back_Symbolic_Prompting_Library-gray?style=for-the-badge)](../Prompts/symbolic_prompting_library.md)

</div>

---

## 🎯 Objective
Generate a production-ready Python script capable of:
1. Parsing **NVD 2.0 / CISA KEV** JSON feeds.
2. Handling recursive flattening of nested arrays (CWEs).
3. Exporting normalized results into a PostgreSQL-compatible CSV format.

---

## 🛠️ Data Pipeline & Pre-requisites

To ensure 100% determinism in massive nested structures, we follow a specific pipeline:
1. **Raw Data**: Fetch the JSON feed (e.g., [CISA KEV](https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json)).
2. **Flattening**: Convert hierarchical JSON into a "Path-Value" flat dictionary using `jq`. This simplifies the LLM's attention mechanism by providing direct key access.

> [!NOTE]
> This process requires `jq` installed (`sudo apt install jq`).

### 📇 Normalizer Script (Pre-processing)
Use this script to prepare your `output.txt` for the Symbolic Prompt:

<details>
  <summary> 🛠️ Click to expand Python Normalizer</summary>

```python
#!/usr/bin/python3
import json, re, subprocess, os, sys

def plane_json(args_infile):
        cmd = """jq '[paths(scalars) as $p | {"path": $p | join("."), "value": getpath($p)}]' """ + args_infile
        result = subprocess.run(cmd, shell=True, capture_output=True, text=True)
        return json.loads(result.stdout.strip())

def flatten_json_recursive(return_json_plane):
        items = {}
        for index in return_json_plane:
                items[index['path']] = index['value']
        with open("output_2026.txt", "w") as f:
                f.write(json.dumps(items))
        print("File finished")

def test():
        full_path = "/home/jhuerta/CVE/cvelistV5/CWE/known_exploited_vulnerabilities.json"
        return_json_plane = plane_json(full_path)
        flatten_json_recursive(return_json_plane)

if __name__ == "__main__":
        test()

```

</details>

---

### 🗒️ Normal File (Example)

<details>
  <summary> (Click to expand)</summary>

```json
{
    "title": "CISA Catalog of Known Exploited Vulnerabilities",
    "catalogVersion": "2026.04.16",
    "dateReleased": "2026-04-16T17:01:07.1675Z",
    "count": 1569,
    "vulnerabilities": [
        {
            "cveID": "CVE-2026-34197",
            "vendorProject": "Apache",
            "product": "ActiveMQ",
            "vulnerabilityName": "Apache ActiveMQ Improper Input Validation Vulnerability",
            "dateAdded": "2026-04-16",
            "shortDescription": "Apache ActiveMQ contains an improper input validation vulnerability that allows for code injection.",
            "requiredAction": "Apply mitigations per vendor instructions, follow applicable BOD 22-01 guidance for cloud services, or discontinue use of the product if mitigations are
 unavailable.",
            "dueDate": "2026-04-30",
            "knownRansomwareCampaignUse": "Unknown",
            "notes": "https:\/\/activemq.apache.org\/security-advisories.data\/CVE-2026-34197-announcement.txt ; https:\/\/nvd.nist.gov\/vuln\/detail\/CVE-2026-34197",
            "cwes": [
                "CWE-20",
                "CWE-94"
            ]
        },

  . . .
```

</details>

---

### 📋 Flattened File (Example)

<details>
  <summary> (Click to expand)</summary>

```json
{
	"title": "CISA Catalog of Known Exploited Vulnerabilities",
	"catalogVersion": "2026.04.16",
	"dateReleased": "2026-04-16T17:01:07.1675Z",
	"count": 1569,
	"vulnerabilities.0.cveID": "CVE-2026-34197",
	"vulnerabilities.0.vendorProject": "Apache",
	"vulnerabilities.0.product": "ActiveMQ",
	"vulnerabilities.0.vulnerabilityName": "Apache ActiveMQ Improper Input Validation Vulnerability",
	"vulnerabilities.0.dateAdded": "2026-04-16",
	"vulnerabilities.0.shortDescription": "Apache ActiveMQ contains an improper input validation vulnerability that allows for code injection.",
	"vulnerabilities.0.requiredAction": "Apply mitigations per vendor instructions, follow applicable BOD 22-01 guidance for cloud services, or discontinue use of the product if mitigations are unavailable.",
	"vulnerabilities.0.dueDate": "2026-04-30",
	"vulnerabilities.0.knownRansomwareCampaignUse": "Unknown",
	"vulnerabilities.0.notes": "https://activemq.apache.org/security-advisories.data/CVE-2026-34197-announcement.txt ; https://nvd.nist.gov/vuln/detail/CVE-2026-34197",
	"vulnerabilities.0.cwes.0": "CWE-20",
	"vulnerabilities.0.cwes.1": "CWE-94",
  . . .
```

</details>

---

## 📜 The Symbolic Prompt
Copy the block below into your LLM (Optimized for Gemini):

```text
[SYSTEM]
[ROLE] ::=> PYTHON_SCRIPT_EXPERT-CWE_ANALYST
[CONTEXT] ::= {CVE_NVD_CPE, RECURSIVE_JSON_READ, IDENTIFY_PATTENRS, CPE_PATTERN_RECOGNIZE, COMMON_WEAKNESS_ENUMERATION}
[INPUT] ::= "cwe_output_2026.txt" (file_attached)
[TASK] ::=
  READ_FILE(INPUT) -> GENERATE_STRUCTURE -> _output_structure
  COLLECT_DATA(cveID, PER_CVE(cwes, knownRansomwareCampaignUse)) -> _collect_data
  IF _collect_data.CWES == TRUE THEN
      GENERATE_PYTHON_SCRIPT(CSV_FORMAT(cve_id, cwe_id, ransom_campaign) <~> _collect_data.CWES_PER_LINE+KNOWNRANSOMWARECAMPAIGNUSE ) -> _python_script
ENDIF
[OUTPUT] ::= _python_script
```

---

## 🛠️ Logic Breakdown (The SPF Engineering)
* **`[ROLE]`**: Assigns a high-density persona (**PYTHON_SCRIPT_EXPERT-CWE_ANALYST**) to ensure the code adheres to cybersecurity best practices and accurate data mapping.
* **`[CONTEXT]`**: Constrains the operational environment to **CVE/CPE** and **CWE** standards, ensuring the logic handles recursive JSON structures and specific security identifiers without "hallucinating" generic data types.
* **`[TASK]`**: Employs a functional programming syntax to define the data pipeline:
    * **`READ_FILE -> GENERATE_STRUCTURE`**: Establishes the memory schema before processing.
    * **`COLLECT_DATA`**: Orchestrates the extraction of specific nested fields (cveID, cwes, and ransomware flags).
    * **`GENERATE_PYTHON_SCRIPT <~>`**: Uses the mapping operator (**`<~>`**) to bind the filtered CWE collection directly to the CSV row-generation logic, ensuring data integrity during the transformation.
    * **`IF/ENDIF` Logic**: Implements a conditional trigger—only generating the script if valid CWE data is present, preventing empty or broken outputs.
* **`[OUTPUT]`**: Uses the direct assignment **`_python_script`** to bypass conversational fluff and force the generation of raw, executable code in the requested CSV-centric format.

---

## ✅ 📇 Expected Output Result (Python)

The LLM will generate a script that implements the `TABLE_HEADERS` and `CPE_PARSING` logic exactly as defined:

<details>
  <summary> (Click to expand)</summary>

```python
import json
import csv

def generate_vulnerability_csv(input_filename, output_filename):
    """
    READ_FILE(INPUT) -> GENERATE_STRUCTURE
    Recursively parses the CISA catalog to identify all CWEs per CVE and 
    associated ransomware campaign data.
    """
    try:
        with open(input_filename, 'r') as f:
            data = json.load(f)
    except (FileNotFoundError, json.JSONDecodeError) as e:
        print(f"Error processing file: {e}")
        return

    # Metadata 'count' defines the range of vulnerabilities to process
    total_vulnerabilities = data.get("count", 0)
    _collect_data = []

    for i in range(total_vulnerabilities):
        # Identify standard patterns for CVE ID and Ransomware Campaign status
        cve_id = data.get(f"vulnerabilities.{i}.cveID")
        ransom_campaign = data.get(f"vulnerabilities.{i}.knownRansomwareCampaignUse", "Unknown")

        if cve_id:
            # RECURSIVE_JSON_READ to find all CWEs (cwes.0, cwes.1, etc.)
            cwe_index = 0
            while True:
                cwe_key = f"vulnerabilities.{i}.cwes.{cwe_index}"
                if cwe_key in data:
                    cwe_id = data[cwe_key]
                    
                    # IF _collect_data.CWES == TRUE (Collect if CWE entry is found)
                    _collect_data.append({
                        'cve_id': cve_id,
                        'cwe_id': cwe_id,
                        'ransom_campaign': ransom_campaign
                    })
                    cwe_index += 1
                else:
                    break

    # GENERATE_PYTHON_SCRIPT(CSV_FORMAT)
    headers = ['cve_id', 'cwe_id', 'ransom_campaign']
    with open(output_filename, 'w', newline='') as csvfile:
        writer = csv.DictWriter(csvfile, fieldnames=headers)
        writer.writeheader()
        writer.writerows(_collect_data)

    print(f"Successfully generated {output_filename} with {len(_collect_data)} entries.")

if __name__ == "__main__":
    INPUT_FILE = "cwe_output_2026.txt"
    OUTPUT_FILE = "vulnerability_cwe_report.csv"
    generate_vulnerability_csv(INPUT_FILE, OUTPUT_FILE)
```

</details>

### ✅ 📋 Expected Output Result (CSV)

The LLM will generate a script that implements the `TABLE_HEADERS` and `CPE_PARSING` logic exactly as defined:

```csv
cve_id,cwe_id,ransom_campaign
CVE-2026-34197,CWE-20,Unknown
CVE-2026-34197,CWE-94,Unknown
CVE-2009-0238,CWE-94,Unknown
CVE-2026-32201,CWE-20,Unknown
CVE-2012-1854,CWE-426,Unknown
CVE-2025-60710,CWE-59,Unknown
CVE-2023-21529,CWE-502,Unknown
CVE-2023-36424,CWE-125,Unknown
CVE-2020-9715,CWE-416,Unknown
CVE-2026-21643,CWE-89,Unknown
CVE-2026-34621,CWE-1321,Unknown
CVE-2026-1340,CWE-94,Unknown
```

---

## 🔍 Why this is better than Natural Language?

Shifting from conversational prose to the **Symbolic Prompting Framework (SPF)** moves the interaction from "asking a favor" to "executing a specification."

|Feature |Conversational Prompt |Symbolic Prompt |
|:-- |:-- |:-- |
|**Logic Flow** |LLM decides execution order. |**Deterministic** by the `[TASK]` sequence. |
|**Data Binding**	|Vague instructions like "map the data."	|Explicit mapping using the `<~>` operator. |
|**Noise Level**	|High (e.g., "Sure, I can help you with that!").	|**Zero-Shot**; direct-to-code output via `->>`. |
|**Error Margin**	|High risk of omitting nested keys (CWE arrays).	|Strict adherence to the `RECURSIVE_JSON_READ` context. |
|**Reproducibility**	|Variable; different seeds produce different code.	|**Fixed**; the symbolic structure forces consistent logic. |

### 🧠 The Engineering Advantage
- **State Control**: In the symbolic version, the `IF/ENDIF` block acts as a logical gate. A standard prompt might attempt to generate a script even if the input data is malformed; SPF ensures the `_python_script` only instantiates when `_collect_data.CWES` is validated as `TRUE`.
- **Context Density**: By defining `[CONTEXT]` using domain-specific constants (e.g., `CVE_NVD_CPE`), we prime the model's internal weights for security standards, drastically reducing the "hallucination" of non-existent Python libraries.
- **Linear Transformation**: The use of functional operators like `->` transforms the prompt into a directed acyclic graph (DAG) of operations, making it significantly easier for the LLM to maintain long-range coherence in complex scripts.

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


[![Back to Main Repo](https://img.shields.io/badge/←_Back_Main_Page-gray?style=for-the-badge)](../README.md) | [![Symbolic Prompting Library](https://img.shields.io/badge/←_Back_Symbolic_Prompting_Library-gray?style=for-the-badge)](../Prompts/symbolic_prompting_library.md)