# Automating Malicious NPM Package Extraction from HTML via Symbolic Prompting

In modern security operations, Blue Teams are frequently overwhelmed by unstructured runtime telemetry, raw process parameters, and erratic log formats. Traditional natural language prompts often yield inconsistent parsing results, leaving security analysts to manually filter out operating system background noise. By leveraging the Symbolic Prompting Framework (SPF)—as demonstrated in our recent NPM supply chain analysis models—security engineers can enforce strict parsing logic, zero-trust data constraints, and deterministic outputs

<div align="center">

[![GitHub Stars](https://img.shields.io/github/stars/mindhack03d/SymbolicPrompting?style=plastic&logo=github&color=gold&cacheBus=1)](https://github.com/mindhack03d/SymbolicPrompting)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Course_Complete-success?style=plastic&logo=youtube)](https://youtube.com/playlist?list=PLNFL-2KY9QZVqoRwRzVLPN6qmDftpsjg6)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Reels_EN-success?style=plastic&logo=youtube)](https://www.youtube.com/playlist?list=PLNFL-2KY9QZXhGEfGUOrrZtzGdPESwh4l)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Reels_ES-success?style=plastic&logo=youtube)](https://youtube.com/playlist?list=PLNFL-2KY9QZUKlXC_4gnVUHoAJdd4s-AC&si=4N7ROWCD3G46y8t5l)
[![License-MIT](https://img.shields.io/badge/License-MIT-green?style=plastic)](https://opensource.org/licenses/MIT)
[![Benchmark](https://img.shields.io/badge/📊-Benchmark_Data-2a2a2a?style=plastic)](../Benchmark/symbolic_support_test.md)

[![Back to Main Repo](https://img.shields.io/badge/←_Back_Main_Page-gray?style=for-the-badge)](../README.md) | [![Symbolic Prompting Library](https://img.shields.io/badge/←_Back_Symbolic_Prompting_Library-gray?style=for-the-badge)](../examples/npm_supply_chain_extracted_internet.md)

</div>

---

## 🎯 The Challenge of Natural Language in Threat Hunting
Standard natural language prompts rely heavily on descriptive phrasing and probabilistic interpretations. When applied to high-velocity threat hunting, this introduces several operational bottlenecks:

- **Parsing Inconsistency:** Natural language models may misinterpret package version delimiters or miss critical Indicator of Compromise (IoC) fields when formatting JSON output.

- **Token Bloat:** Excessive conversational filler increases token consumption and latency in automated workflows (such as n8n pipelines).

- **Deterministic Failure:** Without explicit logical operators (IF-THEN-ELSE, variable mapping arrays), LLMs can hallucinate MITRE ATT&CK mapping IDs or fail to suppress false positives when analyzing benign packages.

---

### 📜 The Normal Prompt

This prompt is using natural language (English)

> [!NOTE]
> Based on https://platform.openai.com/tokenizer GPT-5. The number of token are: 1,070.

```shell
# ROLE
You are an expert at detecting patterns and extracting information from HTML code related to detect NPM package names and versions. Based on what you read, you have the skills to detect MITRE ID.

# TASK
You read the full article and MUST validate if the article is written about NPM, mentions at least 2 malicious npm packages, and mentions something regarding "CyberSecurity Malicious Attacks Campaigns to NPM Packages".
- If the article talked about NPM and CyberSecurity Attacks, follow all the INSTRUCTIONS.
- If the article did NOT talk about NPM and CyberSecurity Attacks OR NOT contain npm packages. You need to follow the instructions, but the result MUST BE the output should be in JSON format, only the name of the npm package (empty), version of the npm package (empty), title (empty), date_published in the format (YYYY/MM/DD), mitre_variable (empty), attack_comment (empty), and hash_value (empty).


INSTRUCTIONS:
You need to read the full article and validate/extract some information:
- Identify the name of the attack, then validate if the title proposal can be matched from this list: {{ $json.family_types }}; in case the title did not match then generate a cybersecurity title that MUST only contain 3 words. The title should be easy to identify, and try to standardise the title using keywords like: SOCIAL ENGINEERING ATTACK, PHANTOMRAVEN SUPPLY CHAIN, LAZARUS TYPOSQUATTING MALWARE, NORTHKOREA MALWARE EXFILTRATION,... The main point of the title is to create a family of Attacks to easy to track. Save the title value in the variable "title".
- You need to extract the main tactics based on MITRE ATT&CK (ID and Title of MITRE ATT&CK). The MITRE ID must be real and exist. You can save the list in one variable like an OBJECT single JSON, as part of the variable is "mitre_variable". In case you can not find any related "MITRE-ID", create the variable "mitre_variable" in JSON format, empty.
- You MUST create a description (Using fewer than 70 words) that can help you identify the main cybersecurity tactics / malicious attack effects (Example: CWE-123, CVE-2024-1234, IP: 8.12.15.24, Country: North Korean, Operative System: Linux, Attack: typosquatting, Dependency confusion, Dependency Hijacking, ...), and save the value in the variable "attack_comment".
- You MUST create a random hash, the hash must be a unique identifier, and save the value in "hash_value".
- You MUST extract the date when the article was published in the format YYYY/MM/DD save the value in the variable "date_published"
- You MUST extract and detect ALL NPM packages written in the article based on the following patterns:

Patterns of the name format:
- @package/name@version
- @package/name
- name version
- name@version
- name@version, name@version, name@version
- name (version)
- name version, version, version
- name: version, version

Pattern of the version format:
- 2.0.15
- 10.15.350
- 15.150.1

Completed pattern example: @package/name - version such as: debug - 1.0.15, chalk - 20.4.103
In case you find a similar result: debug - 100.1 million, chalk - compromised, then you need to write debug - , chalk - .

You need to find the information of the npm package and the version affected.
The pattern could be inside of a table or in the HTML code.

When the data is inside of the table, you can find tables similar to the following example:

| PACKAGE | COMPROMISED VERSION(s) |
| @art-ws/common | 2.0.22, 2.0.28 |

In this example, you need to extract the npm package name and version. Example of the case, name: @art-ws/common, version: 2.0.22, name:@art-ws/common, version: 2.0.28

There exist some conditions to extract the name of the package.
- The npm package name always could contain a version.
- In case you can not find the version, you need to write name: NPM Package, version: ""
All the information extracted should be in the variable "packages".

# OUTPUT
The output should be in JSON format, only the name of the npm package, version of the npm package, title (Title MUST BE in UPPERCASE and NOT use plural words), date_published (Format YYYY/MM/DD), mitre_variable (The format MUST BE in JSON & ARRAY like this "ID": "MITRE-ID", "Text": "Mitre Title"), attack_comment, and hash_value (The format must like SHA1).
You don't need to add a description or comments. 

In case you can not identify nothing about the npm package, print an empty response.
```

---

## Enforcing Deterministic Security Parsing
The SPF methodology replaces conversational ambiguity with explicit structural declarations. By defining strict system states, contextual inputs, and conditional control flows, the LLM transitions from a conversational assistant to a deterministic data transformation engine.

As shown in our implementation architecture, the framework enforces rigorous validation rules:

- **Zero-Trust Validation:** Articles or telemetry payloads are programmatically evaluated against specific threat criteria (e.g., verifying malicious campaign indicators and package dependencies) before downstream data extraction occurs.

- **Controlled Taxonomy Mapping:** Extracted tactics are strictly cross-referenced against official MITRE ATT&CK identifiers, ensuring that output schemas remain uniform for SIEM ingestion.

- **SEO & Knowledge Sharing:** Structuring technical breakdowns this way allows security researchers to publish high-utility, machine-parsable documentation that directly integrates into automated threat-intelligence feeds and educational repositories.

By treating prompt engineering as code, Blue Teams can reliably bridge the gap between unstructured threat research and structured, actionable security intelligence.

---

### 📜 The Symbolic Prompt

Copy the block below into your LLM (Optimized for Gemini-3-flash):

> [!NOTE]
> Based on https://platform.openai.com/tokenizer GPT-5. The number of token are: 811.

```shell
[SYSTEM]
[ROLE] ::=> DETECTING_PATTERNS-EXTRACTING_INFORMATION+NPM_MANAGER
[CONTEXT] ::= {HTML_CODE, NPM_PACKAGE(NAME, VERSION), MITRE_ATTACK_LIST: [ { "id": MITRE_ATTACK_ID, "tactic": MITRE_TITLE} ]}
[INPUT] ::= '''HTML_CODE_WEB_PAGE (Change it)'''
[URL_INPUT] ::= '''URL_OF_WEB_PAGE (Change it)'''
[INPUT_NAMES] ::= "NPM_SUPPLY_CHAIN_FAMILIES (Change it)"
[GLOBAL] ::= 
- npm_array := [{"title": "", "date_published": "", "date_extracted": "{{ $('LOOP:URL').item.json.date }}", "mitre_variable": [], "attack_comment": "", "hash_value": "", "packages": []}]
[TASK] ::= {
	cyber_flag := READ_ARTICLE([INPUT]).DETECT(CYBERSECURITY_ATTACKS, NPM_PACKAGES)
	IF cyber_flag == TRUE THEN
		npm_array[0]["mitre_variable"] := BASED_ON_([INPUT]) -> DETERMINE_MITRE_ID_({"id": MITRE_ID, "text": MITRE_TITLE})
        npm_title_article := BASED_ON([INPUT]&&[URL_INPUT])[TITLE, ARTICLE] -> DEFINE_TITLE.FORMAT(THREE_WORDS, UPPERCASE)
        IF npm_title_article NOT IN [INPUT_NAMES] OR npm_title_article NOT SIMILAR IN [INPUT_NAMES] THEN
    		npm_array[0]["title"] ::= npm_title_article
        ELSE
            npm_array[0]["title"] ::= BASED_ON([INPUT]&&[URL_INPUT]).SELECT_BEST_TITLE([INPUT_NAMES])
        ENDIF
        npm_comments := BASED_ON_([INPUT]) -> EXTRACT_ONLY_IF_EXIST[CVE_ID, VECTOR_TYPE, ATTACK_TYPE, IoCs, COUNTRY_ATTACK, PATCH:(YES|NOT), POC:(YES|NOT)] <- IF_NOT_EXIST.SET(EMPTY)
        IF npm_comments == TRUE THEN
          npm_array[0]["attack_comment"] := npm_comments
        ELSE
          npm_array[0]["attack_comment"] := "no_comments"
        ENDIF
        npm_array[0]["date_published"] := BASED_ON([INPUT]).GET_DATE_PUBLISHED
		FOR npm_pkg_detail IN EXTRACT_NPM_DATA([INPUT]) DO
			IF npm_pkg_detail.VERSION == TRUE THEN 
				npm_pkg_version := npm_pkg_detail.VERSION
			ELSE
				npm_pkg_version := ""
			ENDIF
			npm_array[0]["packages"].APPEND({"name": npm_pkg_detail.NAME, "version": npm_pkg_version})
		DONE
	ENDIF
}
[CONSTRAINTS] ::= {
- NO_PROSE,
- NO_ADDITIONAL_COMMENTS,
- MARKDOWN_SYNTAX: OFF,
- ONLY_PRINT([OUTPUT]),
- OUTPUT_FORMAT: JSON
}
[OUTPUT_FORMAT] ::= 
{
	"title": npm_array[0]["title"],
    "date_published": npm_array[0]["date_published"].FORMAT:YYYY/MM/DD,
    "date_extracted": npm_array[0]["date_extracted"].FORMAT:YYYY/MM/DD,
    "mitre_variable": [ { "id": "MITRE_ID", "text": "MITRE_TITLE"}, { "id": "MITRE_ID", "text": "MITRE_TITLE"}, ... ],
    "attack_comment": "ARTICLE_COMMENTS",
	"hash_value": "ARTICLE&&URL.HASH_FORMAT:SHA1 <- 32_CHARS", 
	"packages": [ 
		{ "name": "NPM_PKG_NAME", "version": "NPM_PKG_VERSION" },
		{ "name": "NPM_PKG_NAME", "version": "NPM_PKG_VERSION" },
		...
	]
}
[OUTPUT] ::= npm_array
```

---

### 🏗️ Main difference

| Natural Language Prompting | Symbolic Prompting |
| :--- | :--- |
| Relies on conversational paragraphs, descriptive guidelines, and few-shot examples. | Uses formal pseudo-code structures, state variables, arrays, and explicit syntax blocks. |
| Depends on the model's probabilistic interpretation to handle instructions and edge cases. | Enforces explicit conditional execution paths, boolean flags, and loops (`IF-THEN-ELSE`). |
| Frequently produces conversational filler, markdown variations, or inconsistent output schemas. | Guarantees rigid schema adherence optimized for automated pipelines like n8n and API ingestion. |
| Lacks programmatic mechanisms to track variables or pass state across execution steps. | Initializes, modifies, and appends data dynamically to global arrays (e.g., `npm_array`). |
| Handles missing data through loose conversational instructions ("in case you cannot find..."). | Applies strict fallback operators and deterministic default sets (`<- IF_NOT_EXIST.SET(EMPTY)`). |

---

## 🧠 The Engineering Advantage

Symbolic prompting bridges the gap between large language models and production software engineering, transforming unpredictable text generation into a reliable component of automated security pipelines. 

* **Deterministic API Contracts:** Defining rigid output schemas and array assignments eliminates the need for downstream regex parsers or fragile text extraction scripts within orchestrators like n8n.
* **Minimized Token Latency:** Replacing verbose natural language instructions with concise symbolic blocks (`[SYSTEM]`, `[TASK]`, `[CONSTRAINTS]`) reduces payload sizes and cuts execution latency during high-volume threat intelligence ingestion.
* **Programmatic Error Recovery:** Explicit fallback operators and conditional flags (e.g., `<- IF_NOT_EXIST.SET(EMPTY)`) ensure that incomplete telemetry or missing version data will not corrupt downstream databases or dashboard logs.
* **Maintainable Version Control:** Treating prompts like source code allows security teams to track logic changes, review syntax diffs, and audit prompt modifications through standard version control systems like Git.

Enforcing these software-defined constraints enables Blue Teams to deploy AI models as deterministic microservices rather than probabilistic chat interfaces.

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


[![Back to Main Repo](https://img.shields.io/badge/←_Back_Main_Page-gray?style=for-the-badge)](../README.md) | [![Symbolic Prompting Library](https://img.shields.io/badge/←_Back_Symbolic_Prompting_Library-gray?style=for-the-badge)](../examples/npm_supply_chain_extracted_internet.md)