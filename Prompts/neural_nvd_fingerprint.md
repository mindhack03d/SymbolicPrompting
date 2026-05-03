# 🐍 Hybrid Neural-Symbolic Prompting for Cybersecurity: Automated NVD & Software Fingerprinting

This example showcases the power of the **Symbolic Prompting Framework (SPF)**. By leveraging high-determinism hybrid neural-symbolic logic, we can transform unstructured reconnaissance data—such as NMAP service banners—into precise, standardized identifiers suitable for security orchestration.

---

### Core Analytical Flow
The framework utilizes `NEURAL_CLEANSE` and `LATENT_SPACE_MAPPING` to resolve the ambiguity of raw service strings into formal **Common Platform Enumerators (CPE)**. In this instance, the input `Node.js Express framework` was decomposed into its constituent components:

* **Runtime Environment:** `cpe:2.3:a:nodejs:node.js:*:*:*:*:*:*:*:*`
* **Web Framework:** `cpe:2.3:a:expressjs:express:*:*:*:*:*:*:*:*`

---

> [!IMPORTANT]
> **Core Concept**: SPF facilitates the automated transition from **Latent Space Mapping** to **Structured CPE Synthesis**. By programmatically normalizing version strings and vendor metadata, the framework enables seamless integration between raw asset discovery and **NVD (National Vulnerability Database)** correlation.

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
The primary goal of this workflow is to leverage the **Symbolic Prompting Framework (SPF)** to parse raw service banners and scan results, effectively isolating a specific software identity from high-entropy data via **Hybrid Neural-Symbolic** inference.

### 1. Symbolic Pattern Recognition
By utilizing the `NEURAL_CLEANSE` and `PATTERN_MATCHING` logic, the framework performs deep inspection of the input string. It bypasses noise—such as HTTP headers or environment-specific metadata—to isolate the core software name and version via `SEMANTIC_EMBEDDING_SEARCH`. 

For example, it programmatically strips distribution-specific suffixes (like `Debian5` or `Ubuntu1`) to identify the **CPE Base** for accurate vulnerability mapping. This process reduces the "entropy" of raw reconnaissance data, distilling it into its most analytically useful form.

### 2. Deterministic Structured Output
The framework is configured for **High Determinism**, ensuring that raw, unstructured strings are transformed into machine-readable JSON through `LATENT_SPACE_MAPPING`. This transition is critical for:

* **CPE Correlation**: Instant mapping to Common Platform Enumeration standards via `CONVERT_TO_CPE_FORMAT`.
* **Vulnerability Linking**: Direct integration with CVE databases using `PROBABILISTIC_WEIGHTING` to ensure the most likely exploit matches are prioritized.
* **Asset Management**: Seamless ingestion into automated security dashboards and Red Team orchestration tools.

---

## 📜 The Symbolic Prompt
Run Ollama model.
```text
ollama run goekdenizguelmez/JOSIEFIED-Qwen3:4b
ollama run f0rc3ps/nu11secur1tyAIRedTeamLite:latest
```

Copy the block below into your LLM (Optimized for GEMINI/JOSIEFIED-Qwen3:4b/nu11secur1tyAIRedTeamLite:latest):
```text
[SYSTEM]
[ROLE] ::=> CVE_CPE_NVD_ANALYST+CYBERSECURITY_ANALYST
[COMPUTATION_MODE] ::=> HYBRID_NEURAL_SYMBOLIC
[DETERMINISM] ::=> HIGH
[HYBRID_NEURAL_SYMBOLIC] ::=> ENABLE
[NEURAL_INFERENCE] ::=> ENABLE
[LATENT_SPACE_MAPPING] ::=> ACTIVE
[FUZZY_MATCH_THRESHOLD] ::=> 0.85
[NEURAL_ENGINE_FLAGS] ::=> {PATTERN_MATCHING: TRUE, SEMANTIC_EXPANSION: TRUE}
[INPUT] ::= {"port": "8080", "protocol": "tcp", "service": "http", "version": "Node.js Express framework"}
[TASK] ::=
  _normalized_input := NEURAL_CLEANSE(service, version)+SEMANTIC_EMBEDDING_SEARCH
  _cpe_base := CONVERT_TO_CPE_FORMAT(_normalized_input)
  _latent_matches := SEMANTIC_SEARCH(NVD_DATABASE, _cpe_base)+PROBABILISTIC_WEIGHTING(candidates)
  FOR EACH _candidate IN _latent_matches:
    IF PROBABILITY_SCORE(_candidate) > 0.90:
      _extract_data := EXTRACT_VALUES(vendor, product, version) FROM _candidate
      _cpe_combinations := GENERATE_CPE_COMBINATIONS(_extract_data)
    ENDIF
  [NEXT]
[CONSTRAINT] ::= {NO_ADD_COMMENTS, NO_ADD_PROSE, JSON_FORMAT({"vendor": vendor, "product": product, "version": version})}
[OUTPUT] ::= 
  FOR EACH _cpe_line in _cpe_combinations:
    IF (_cpe_line.version == "Any") OR (_cpe_line.version == "*") OR (_cpe_line.version == "") THEN
      _cpe_line.version = "*"
   ENDIF
    RETURN_VALUE(_cpe_line, [vendor, product, version]) -> RETURN
  [NEXT]
```

Expected Output:
```json
[
  {
    "vendor": "nodejs",
    "product": "node.js",
    "version": "*"
  },
  {
    "vendor": "expressjs",
    "product": "express",
    "version": "*"
  }
]
```

![Symbolic Prompting - Identify Package Name and Package Version](sp_identify_pkg_name_based_fingerprint_img_00.png)

---

## 🛠️ Logic Breakdown (The SPF Engineering)
The **Symbolic Prompting Framework (SPF)** utilized in this recognition task relies on declarative logic gates to achieve surgical precision. Unlike standard "chat" prompts, this structure treats the LLM as a deterministic processor.


### Engineering Components of the Logic

* **`[ROLE]` ::=> CVE_CPE_NVD_ANALYST+CYBERSECURITY_ANALYST**<br>
  Assigns a high-density persona. This forces the model to bypass natural language interpretation and instead operate as a specialized scanner, prioritizing technical pattern matching and NVD database logic over conversational context.

* **`[DETERMINISM]` ::=> HIGH**<br>
  This instruction acts as a manual override for the model's stochastic sampling. By setting determinism to maximum, we ensure that the same input consistently yields the exact same JSON structure, effectively eliminating the "hallucination" of extra text or varying formats.

* **`[COMPUTATION_MODE]` ::=> HYBRID_NEURAL_SYMBOLIC**<br>
  Enables a dual-layer processing approach. It uses **Neural Inference** to handle the fuzzy, unstructured nature of service banners (like `Node.js Express framework`) and **Symbolic Logic** to enforce rigid rules for CPE formatting and JSON construction.

* **`[TASK]` ::=> FUNCTIONAL_PIPELINE**<br>
  Employs a symbolic data flow to isolate variables:
    * **NEURAL_CLEANSE**: A symbolic function that scrubs the input of noise to find the root application name.
    * **GENERATE_CPE_COMBINATIONS**: A targeted extraction logic that maps discovered entities directly into standardized `cpe:2.3` schema components.

* **`[CONSTRAINT]` ::=> HARD_FIREWALL**<br>
  Acts as a strict filter against model verbosity.
    * **NO_ADD_COMMENTS / NO_ADD_PROSE**: These tokens effectively "mute" the AI’s generative tendencies, forcing the output to function like a raw CLI tool response.

* **`[OUTPUT]` ::=> JSON_SCHEMA**<br>
  Defines the specific structure for the data. This ensures the output is "clean" and ready for immediate injection into automated security pipelines, such as vulnerability scanners or asset inventories.

### Execution Trace
Following the defined logic, the framework processed the input `{"service": "http", "version": "Node.js Express framework"}` to synthesize the following validated identities:

```json
[
  {
    "vendor": "nodejs",
    "product": "node.js",
    "version": "*"
  },
  {
    "vendor": "expressjs",
    "product": "express",
    "version": "*"
  }
]
```

---

## 🔍 Why this is better than Natural Language?

Shifting from conversational prose to the **Symbolic Prompting Framework (SPF)** moves the interaction from "asking a favor" to "executing a specification." By using structured identifiers, we eliminate the ambiguity inherent in human syntax and treat the LLM as a logical processor.

| Feature | Conversational Prompt | Symbolic Prompt (SPF) |
| :--- | :--- | :--- |
| **Logic Flow** | LLM decides execution order based on intent. | **Deterministic** via defined `[TASK]` and `[LOGIC]` gates. |
| **Data Extraction** | Vague: "Find the software version." | Explicit `NEURAL_CLEANSE` and `EXTRACT_VALUES` operators. |
| **Noise Level** | High (e.g., "Sure, I can help with that...") | **Zero-Shot**; direct-to-data via `[CONSTRAINT]` logic. |
| **Error Margin** | High risk of hallucinating prose or context. | Strict filtering via `NO_ADD_COMMENTS` and `HARD_FIREWALL`. |
| **Reproducibility** | Variable; inconsistent formatting across sessions. | **Fixed**; forced schema via `JSON_FORMAT` and `RETURN_VALUE`. |


### 🧠 The Engineering Advantage

* **State Control**: In the symbolic version, the `[DETERMINISM]` parameter acts as a logical throttle. While a standard prompt might "chat" about the server architecture, SPF locks the model into a state of **maximum precision**, ensuring that high-entropy strings (like the NMAP scan results) are treated as a set of variables rather than a narrative.
* **Context Density**: By defining `[ROLE]` and `[NEURAL_ENGINE_FLAGS]` using domain-specific constants (e.g., `PATTERN_MATCHING: TRUE`), we prime the model's internal weights for specific data structures. This drastically reduces the "hallucination" of incorrect versioning formats by grounding the output in known technical patterns.
* **Linear Transformation**: The use of symbolic assignment operators like `::=>` and `::=` transforms the prompt into a linear data pipeline. This makes it significantly easier for the LLM to maintain **long-range coherence**, ensuring that the software name extracted from the meta-tags is precisely what appears in the final JSON key without losing data integrity during the inference phase.

### 🚀 Conclusion
By treating the LLM as a **Hybrid Neural-Symbolic** engine, we achieve a level of reliability previously reserved for hard-coded scripts, while maintaining the flexibility of neural language understanding to parse complex, real-world cybersecurity data.

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