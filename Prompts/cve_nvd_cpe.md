# 🐍 Case Study: Python Script Expert for CVE/CPE Parsing

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
Develop a **high-precision ETL pipeline** via a Python script designed to ingest and normalize **NVD JSON 2.0** feeds. The core engine utilizes advanced **Regex Pattern Matching** and **Cognitive Scripting** logic to deconstruct complex **CPE (Common Platform Enumeration)** strings and multi-version **CVSS (2.0, 3.x, 4.0)** metrics.

The final output is a strictly formatted, **PostgreSQL-compatible CSV**, optimized for seamless integration into security data lakes and vulnerability management ecosystems.

### 🛠️ Key Capabilities
- **Recursive CVSS Extraction**: Dynamically identifies and maps all available scoring versions for a single CVE.
- **Granular CPE Parsing**: Breaks down criteria strings into 11 distinct attributes (vendor, product, version, etc.).
- **Integrity Filtering**: Automated exclusion of "Rejected" status entries to ensure data reliability.
- **Deterministic Normalization**: Ensures every row adheres to a fixed schema ready for relational database ingestion.

---

## 🛠️ Data Pipeline & Pre-requisites

To ensure 100% determinism in massive nested structures, we follow a specific pipeline:
1. **Raw Data**: Download the JSON feed (e.g., [nvdcve-2.0-2003.json.zip](https://nvd.nist.gov/feeds/json/cve/2.0/nvdcve-2.0-2003.json.zip)). [CPE Download Files Per Year - JSON 2.0 Feeds](https://nvd.nist.gov/vuln/data-feeds)
2. **Flattening**: We convert the hierarchical JSON into a "Path-Value" flat dictionary using `jq`. This simplifies the LLM's attention mechanism.

> [!NOTE]
> This process requires `jq` installed on your system (`sudo apt install jq`).

### 📇 Normalizer Script (Pre-processing)
Use this script to prepare your `output.txt` for the Symbolic Prompt:

<details>
  <summary> (Click to expand)</summary>

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
  "resultsPerPage" : 1555,
  "startIndex" : 0,
  "totalResults" : 1555,
  "format" : "NVD_CVE",
  "version" : "2.0",
  "timestamp" : "2025-05-23T03:01:42.1365068",
  "vulnerabilities" : [ {
    "cve" : {
      "id" : "CVE-2003-0061",
      "sourceIdentifier" : "cve@mitre.org",
      "published" : "2002-01-11T05:00:00.000",
      "lastModified" : "2025-04-03T01:03:51.193",
      "vulnStatus" : "Deferred",
      "cveTags" : [ ],
      "descriptions" : [ {
        "lang" : "en",
        "value" : "Buffer overflow in passwd for HP UX B.10.20 allows local users to execute arbitrary commands with root privileges via a long LANG en
vironment variable."
      } ],
      "metrics" : {
  . . .
```

</details>

---


### 📋 Flattened File (Example)


<details>
  <summary> (Click to expand)</summary>

```json
{
	"resultsPerPage": 1555,
	"startIndex": 0,
	"totalResults": 1555,
	"format": "NVD_CVE",
	"version": "2.0",
	"timestamp": "2025-05-23T03:01:42.1365068",
	"vulnerabilities.0.cve.id": "CVE-2003-0061",
	"vulnerabilities.0.cve.sourceIdentifier": "cve@mitre.org",
	"vulnerabilities.0.cve.published": "2002-01-11T05:00:00.000",
	"vulnerabilities.0.cve.lastModified": "2025-04-03T01:03:51.193",
	"vulnerabilities.0.cve.vulnStatus": "Deferred",
	"vulnerabilities.0.cve.descriptions.0.lang": "en",
	"vulnerabilities.0.cve.descriptions.0.value": "Buffer overflow in passwd for HP UX B.10.20 allows local users to execute arbitrary commands with root privileges via a long LANG environment variable.",
	"vulnerabilities.0.cve.metrics.cvssMetricV2.0.source": "nvd@nist.gov",
	"vulnerabilities.0.cve.metrics.cvssMetricV2.0.type": "Primary",
	"vulnerabilities.0.cve.metrics.cvssMetricV2.0.cvssData.version": "2.0",
	"vulnerabilities.0.cve.metrics.cvssMetricV2.0.cvssData.vectorString": "AV:L/AC:L/Au:N/C:C/I:C/A:C",
	"vulnerabilities.0.cve.metrics.cvssMetricV2.0.cvssData.baseScore": 7.2,
	"vulnerabilities.0.cve.metrics.cvssMetricV2.0.cvssData.accessVector": "LOCAL",
	"vulnerabilities.0.cve.metrics.cvssMetricV2.0.cvssData.accessComplexity": "LOW",
	"vulnerabilities.0.cve.metrics.cvssMetricV2.0.cvssData.authentication": "NONE",
	"vulnerabilities.0.cve.metrics.cvssMetricV2.0.cvssData.confidentialityImpact": "COMPLETE",
	"vulnerabilities.0.cve.metrics.cvssMetricV2.0.cvssData.integrityImpact": "COMPLETE",
	"vulnerabilities.0.cve.metrics.cvssMetricV2.0.cvssData.availabilityImpact": "COMPLETE",
	"vulnerabilities.0.cve.metrics.cvssMetricV2.0.baseSeverity": "HIGH",
	"vulnerabilities.0.cve.metrics.cvssMetricV2.0.exploitabilityScore": 3.9,
	"vulnerabilities.0.cve.metrics.cvssMetricV2.0.impactScore": 10.0,
	"vulnerabilities.0.cve.metrics.cvssMetricV2.0.obtainAllPrivilege": true,
  . . .
```

</details>

---

## 📜 The Symbolic Prompt
Copy the block below into your LLM (Optimized for Gemini):

```text
[SYSTEM]
[ROLE] ::=> COGNITIVE_PYTHON_SCRIPT_EXPERT+CPE_ANALYST-REGEX_SPECIALIST-PATTERN_SPECIALIST
[DETERMINISM] ::= MAX
[CONTEXT] ::=> {COMMON_VULNERABILITIES_AND_EXPOSURE, JSON_FLATTENED, IDENTIFY_PATTERNS, COMMON_VULNERABILITY_SCORING_SYSTEM, NATIONAL_VULNERABILITY_DATABASE, COMMON_PLATFORM_ENUMERATION}
[SCHEMA:CSV_HEADERS] ::= ("cve_id", "cvss_version", "vectorString", "baseScore", "baseSeverity", "exploitabilityScore", "impactScore", "part", "vendor", "product", "version", "update", "edition", "language", "sw_edition", "target_sw", "target_hw", "versionStartIncluding", "versionEndIncluding", "versionStartExcluding", "versionEndExcluding")
[INPUT] ::= "output_2006.txt"
OUTPUT_EXAMPLE ::= """
CVE-2006-0054,2.0,AV:N/AC:L/Au:N/C:N/I:N/A:P,5.0,MEDIUM,10.0,2.9,o,freebsd,freebsd,6.0,-,*,*,*,*,*,,,,
CVE-2006-0054,3.1,CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:N/I:N/A:L,5.3,MEDIUM,3.9,1.4,o,freebsd,freebsd,6.0,-,*,*,*,*,*,,,,
CVE-2006-0614,2.0,AV:N/AC:L/Au:N/C:P/I:P/A:N,6.4,MEDIUM,10.0,4.9,a,sun,jre,*:*:*:*:*:*,1.4.0,1.4.2_8,,
CVE-2006-0994,2.0,AV:N/AC:L/Au:N/C:P/I:P/A:P,7.5,HIGH,10.0,6.4,a,sophos,sophos_anti-virus,*,*,*,*,*,*,,,4.00,4.05
CVE-2006-0485,2.0,AV:L/AC:L/Au:N/C:P/I:P/A:P,4.6,MEDIUM,3.9,6.4,o,cisco,ios,12.3(11)yl,*,*,*,*,*,*,,,
"""
[FUNCTION:CVSS_VERSION] ::=
	_cvss_metrics := IDENTIFY_FIELD(line, "cvssData") 
	_cvss_version := EXTRACT_ALL_VALUES(_cvss_metrics, "version") <- LINE_PER_VERSION(DYNAMIC_VERSION_RECOGNITION) -> RETURN
[FUNCTION:CVSS_DETAILS] ::=
	_cvss_metric_branch := BASED_ON(_cve_id) -> IDENTIFY_CVSS_VERSION(line.KEY, LITERAL_REGEX["cvssMetric*"])
	_cvss_details := IDENTIFY_FIELDS(line, ("vectorString", "baseScore", "baseSeverity", "exploitabilityScore", "impactScore")).SELECT_ALL_VERSIONS -> RETURN
[FUNCTION:CRITERIA_DETAILS] ::=
	_cve_criteria_value := IDENTIFY_FIELDS(line, "criteria")
	_cve_criteria_details := CPE_PARSE(_cve_criteria_value, ("part", "vendor", "product", "version", "update", "edition", "language", "sw_edition", "target_sw", "target_hw")) -> RETURN
[FUNCTION:VERSIONING] ::=
	_version_Start_Including := FIELD_COULD_EXIST(IDENTIFY_FIELD(line,"versionStartIncluding")) -> RETURN
	_version_End_Including := FIELD_COULD_EXIST(IDENTIFY_FIELD(line,"versionEndIncluding")) -> RETURN
[FUNCTION:VERSION_EXCLUDING] ::=
	_version_Start_Excluding := FIELD_COULD_EXIST(IDENTIFY_FIELD(line,"versionStartExcluding")) -> RETURN
	_version_End_Excluding := FIELD_COULD_EXIST(IDENTIFY_FIELD(line,"versionEndExcluding")) -> RETURN
[SIMULATOR] ::=
	_execution_success := SIMULATE_EXECUTION{PYTHON_SCRIPT:OUTPUT_SCRIPT, INPUT: "output_2006.txt"} <~> SIMILAR_EXPECTED_RESULT(OUTPUT_EXAMPLE)
	IF _execution_success == TRUE THEN
		PRINT_SCRIPT(OUTPUT_SCRIPT) -> RETURN
[TASK] ::=
	READ_FILE(INPUT) -> RECOGNIZE_DYNAMIC_STRUCTURE.JSON_FLATTENED -> _raw_data 
	_vuln_status := IDENTIFY_FIELD(_raw_data, "vulnStatus")
	IF _vuln_status != "Rejected" THEN
		FOR EACH line IN _raw_data:
			_cve_id := EXTRACT_CVE_ID(line, "cve_id")
			CALL [FUNCTION:CVSS_VERSION] WITH line -> _cvss_version
			CALL [FUNCTION:CVSS_DETAILS] WITH {line, _cve_id, _cvss_version} -> _cvss_details
			CALL [FUNCTION:CRITERIA_DETAILS] WITH {line} -> _cve_criteria_details <- _cve_criteria_details.version.REMOVE_CHAR["\"]
			CALL [FUNCTION:VERSION_INCLUDING] WITH line -> {_version_Start_Including, _version_End_Including}
			CALL [FUNCTION:VERSION_EXCLUDING] WITH line -> {_version_Start_Excluding, _version_End_Excluding}
			ADD_LINE_TO(_cve_*, _cvss_version, _cvss_details, _cve_criteria_details, _version_Start_Including, _version_End_Including, _version_Start_Excluding, _version_End_Excluding) -> _python_script
		[NEXT]
	ENDIF -> STORE_LINE_TO_SCRIPT
	GENERATE_PYTHON_SCRIPT(_python_script) ->> OUTPUT_SCRIPT
	CALL [SIMULATOR] WITH {OUTPUT_SCRIPT, [FUNCTION:*].OUTPUT)
[CONSTRAINTS] ::= {
	CSV_RESULT_OUTPUT(SAVE_IN_FILE("cve_report_2026.csv")),
	NO_ADD_PROSE,
	ALLOW_DUPLICATE_LINES: (CVE_ID, CVSS_VERSION + CVSS_DETAILS)
}
[OUTPUT] ::= OUTPUT_SCRIPT
```

---
## 🛠️ Logic Breakdown (The SPF Engineering)
The **Symbolic Prompting Framework (SPF)** utilizes a high-determinism architecture to eliminate probabilistic "guessing" in favor of structured execution.
- `[CONTEXT]` **(Boundary Enforcement)**: Strictly confines the LLM’s operational logic to NVD-specific schemas (CVSS, CPE, NVD 2.0). This hard-codes the "knowledge world," effectively neutralizing hallucinations and the inclusion of irrelevant libraries.
- `[SCHEMA]` **(Deterministic Structuring)**: Rather than allowing the AI to infer headers, we **program the data contract** using CSV_HEADERS. This ensures the output script generates a file that is 100% compliant with downstream database engines.
- `[FUNCTION:CPE_PARSE]` **(Sub-State Logic)**: Defines an explicit extraction micro-service. It forces the model to treat the CPE string as a structured array rather than a flat text block, ensuring accurate mapping of vendor, product, and version.
- `->>` **(Direct Stream Execution)**: This operator triggers the **Zero-Filler Protocol**. It bypasses conversational prose and instructs the engine to output only the sanitized, executable Python payload.
- `[SIMULATOR]` **(Validation Loop)**: Implements a self-correcting logic gate that compares the generated script's logic against an `OUTPUT_EXAMPLE` before finalizing the result, guaranteeing high-fidelity script generation.

---

## ✅ 📇 Expected Output Result (Python)

The LLM will generate a script that implements the `[SCHEMA:CSV_HEADERS]` and `[FUNCTION:CRITERIA_DETAILS]` logic exactly as defined. The output is a deterministic, production-ready tool that handles nested JSON structures and flattens them into a relational format.

<details>
  <summary> (Click to expand)</summary>

```python
import json
import csv
import re

def extract_cvss_v2(vuln, cve_id):
    """Extracts CVSS v2.0 metrics."""
    metrics = []
    # Identify fields based on LITERAL_REGEX["cvssMetric*"]
    # For JSON flattened keys like 'vulnerabilities.1.cve.metrics.cvssMetricV2.0...'
    v2_key = None
    for key in vuln:
        if 'metrics.cvssMetricV2' in key and '.cvssData.version' in key:
            v2_key = key.rsplit('.', 1)[0]
            break
            
    if v2_key:
        metrics.append({
            "cvss_version": vuln.get(f"{v2_key}.version", "2.0"),
            "vectorString": vuln.get(f"{v2_key}.vectorString", ""),
            "baseScore": vuln.get(f"{v2_key}.baseScore", ""),
            "baseSeverity": vuln.get(f"{v2_key.replace('.cvssData', '')}.baseSeverity", ""),
            "exploitabilityScore": vuln.get(f"{v2_key.replace('.cvssData', '')}.exploitabilityScore", ""),
            "impactScore": vuln.get(f"{v2_key.replace('.cvssData', '')}.impactScore", "")
        })
    return metrics

def parse_cpe(criteria_string):
    """Parses CPE 2.3 string into components."""
    # cpe:2.3:part:vendor:product:version:update:edition:language:sw_edition:target_sw:target_hw:other
    parts = criteria_string.split(':')
    details = {
        "part": parts[2] if len(parts) > 2 else "",
        "vendor": parts[3] if len(parts) > 3 else "",
        "product": parts[4] if len(parts) > 4 else "",
        "version": parts[5].replace('\\', '') if len(parts) > 5 else "",
        "update": parts[6] if len(parts) > 6 else "",
        "edition": parts[7] if len(parts) > 7 else "",
        "language": parts[8] if len(parts) > 8 else "",
        "sw_edition": parts[9] if len(parts) > 9 else "",
        "target_sw": parts[10] if len(parts) > 10 else "",
        "target_hw": parts[11] if len(parts) > 11 else ""
    }
    return details

def process_vulnerabilities(input_file, output_file):
    with open(input_file, 'r') as f:
        data = json.load(f)

    # The flattened JSON logic: group keys by their vulnerability index
    vuln_groups = {}
    for key, value in data.items():
        match = re.match(r'vulnerabilities\.(\d+)\.(.*)', key)
        if match:
            idx = match.group(1)
            field = match.group(2)
            if idx not in vuln_groups:
                vuln_groups[idx] = {}
            vuln_groups[idx][field] = value

    headers = [
        "cve_id", "cvss_version", "vectorString", "baseScore", "baseSeverity", 
        "exploitabilityScore", "impactScore", "part", "vendor", "product", 
        "version", "update", "edition", "language", "sw_edition", "target_sw", 
        "target_hw", "versionStartIncluding", "versionEndIncluding", 
        "versionStartExcluding", "versionEndExcluding"
    ]

    with open(output_file, 'w', newline='') as csvfile:
        writer = csv.DictWriter(csvfile, fieldnames=headers)
        writer.writeheader()

        for idx in sorted(vuln_groups.keys(), key=int):
            vuln = vuln_groups[idx]
            cve_id = vuln.get("cve.id")
            vuln_status = vuln.get("cve.vulnStatus")

            if vuln_status == "Rejected":
                continue

            # Extract CVSS (Function: CVSS_VERSION & CVSS_DETAILS)
            # Find version paths dynamically (cvssMetricV2, cvssMetricV3, etc)
            cvss_list = []
            for k in vuln:
                if 'metrics.cvssMetric' in k and '.cvssData.version' in k:
                    base_path = k.rsplit('.cvssData.version', 1)[0]
                    cvss_list.append({
                        "cvss_version": vuln.get(f"{base_path}.cvssData.version"),
                        "vectorString": vuln.get(f"{base_path}.cvssData.vectorString"),
                        "baseScore": vuln.get(f"{base_path}.cvssData.baseScore"),
                        "baseSeverity": vuln.get(f"{base_path}.baseSeverity"),
                        "exploitabilityScore": vuln.get(f"{base_path}.exploitabilityScore"),
                        "impactScore": vuln.get(f"{base_path}.impactScore")
                    })

            # Extract CPE Criteria (Function: CRITERIA_DETAILS)
            # Flattened logic for config nodes and cpe matches
            cpe_matches = []
            for k in vuln:
                # Pattern vulnerabilities.X.cve.configurations.0.nodes.0.cpeMatch.0.criteria
                if 'configurations' in k and '.criteria' in k:
                    base_cpe_path = k.rsplit('.criteria', 1)[0]
                    criteria = vuln.get(k)
                    cpe_info = parse_cpe(criteria)
                    
                    # Function: VERSIONING & VERSION_EXCLUDING
                    cpe_info["versionStartIncluding"] = vuln.get(f"{base_cpe_path}.versionStartIncluding", "")
                    cpe_info["versionEndIncluding"] = vuln.get(f"{base_cpe_path}.versionEndIncluding", "")
                    cpe_info["versionStartExcluding"] = vuln.get(f"{base_cpe_path}.versionStartExcluding", "")
                    cpe_info["versionEndExcluding"] = vuln.get(f"{base_cpe_path}.versionEndExcluding", "")
                    
                    cpe_matches.append(cpe_info)

            # Generate rows (LINE_PER_VERSION logic)
            for cvss in (cvss_list or [None]):
                for cpe in (cpe_matches or [None]):
                    row = {"cve_id": cve_id}
                    if cvss:
                        row.update(cvss)
                    if cpe:
                        row.update(cpe)
                    # Clean None values for CSV consistency
                    row = {k: (v if v is not None else "") for k, v in row.items()}
                    writer.writerow(row)

if __name__ == "__main__":
    process_vulnerabilities("output_2006.txt", "cve_report_2026.csv")
```

</details>

### ✅ 📋 Expected Output Result (CSV)

The script generated by the **SPF engine** produces a strictly structured CSV file. This output reflects the successful execution of `[FUNCTION:CVSS_DETAILS]` and the multi-field breakdown of `[FUNCTION:CRITERIA_DETAILS]`, ensuring compatibility with **PostgreSQL** and other relational databases.

<details>
  <summary> (Click to expand)</summary>

```csv
cve_id,cvss_version,vectorString,baseScore,baseSeverity,exploitabilityScore,impactScore,part,vendor,product,version,update,edition,language,sw_edition,target_sw,target_hw
CVE-2006-0064,2.0,AV:N/AC:L/Au:N/C:P/I:P/A:P,7.5,,,,a,devellion,cubecart,*,*,*,*,*,*,*
CVE-2006-0065,2.0,AV:N/AC:L/Au:N/C:P/I:P/A:P,7.5,,,,a,vego,vego_web_forum,*,*,*,*,*,*,*
CVE-2006-0066,2.0,AV:N/AC:L/Au:N/C:P/I:P/A:P,7.5,,,,a,phpjournaler,phpjournaler,1.0,*,*,*,*,*,*
CVE-2006-0067,2.0,AV:N/AC:L/Au:N/C:P/I:P/A:P,7.5,,,,a,vego,vego_links_builder,*,*,*,*,*,*,*
CVE-2006-0068,2.0,AV:N/AC:L/Au:N/C:P/I:P/A:P,7.5,,,,a,primo_place,primo_cart,*,*,*,*,*,*,*
CVE-2006-0069,2.0,AV:N/AC:M/Au:N/C:N/I:P/A:N,4.3,,,,a,chipmunk_scripts,chipmunk_guestbook,*,*,*,*,*,*,*
CVE-2006-0070,2.0,AV:N/AC:M/Au:N/C:N/I:P/A:N,4.3,,,,a,drupal,drupal,4.5.6,*,*,*,*,*,*
CVE-2006-0070,2.0,AV:N/AC:M/Au:N/C:N/I:P/A:N,4.3,,,,a,drupal,drupal,4.6.4,*,*,*,*,*,*
CVE-2006-0071,2.0,AV:L/AC:L/Au:N/C:C/I:C/A:N,6.6,,,,a,gentoo,app-crypt_pinentry,0.7.2,*,*,*,*,*,*
```

</details>

---

## 🔍 Why this is better than Natural Language?

|Feature |Conversational Prompt |Symbolic Prompt |
|:-- |:-- |:-- |
|**Header Consistency** |Likely to rename, omit, or capitalize columns inconsistently. |**Enforced** by `[SCHEMA:CSV_HEADERS]` symbol; impossible to deviate. |
|**Logic Flow** |AI chooses the execution order, often skipping edge cases. |**Deterministic** execution via the `->` operator and `[TASK]` sequence. |
|**Hallucination** |May invent JSON keys or libraries if the structure is complex. |**Restricted** by `[CONTEXT]` and `IDENTIFY_FIELDS` scope; zero "imagination." |
|**Multi-Version Data** |Often collapses multiple scores into one row, losing data. | **Explicitly handled** by `LINE_PER_VERSION` and `ALLOW_DUPLICATE_LINES` |
|**Scalability** |Hard to debug logic within a "paragraph" of instructions. |**Modular functions** (`[FUNCTION:*]`) allow for unit-testing the prompt logic. |

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

