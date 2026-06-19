# Symbolic Prompting: Converting Natural Language to Symbolic Prompting format for CyberSecurity

The **Symbolic Prompting Framework** transforms **unstructured natural language** into **structured symbolic notation** through a systematic conversion process. This enables machines to parse, analyze, and act upon human-readable security intelligence with precision.

> [!IMPORTANT]
> **Core Concept**: The framework's primary purpose is **language translation** — converting the inherent ambiguity of human language into the deterministic precision of symbolic notation. This bridges the gap between security researchers (who think in natural language) and automated systems (which require structured data).

> [!TIP]
> Use this framework whenever you need to transform free-text security intelligence into machine-readable formats for SIEM integration, automated vulnerability management, or DevSecOps pipelines.

<div align="center">

[![GitHub Stars](https://img.shields.io/github/stars/mindhack03d/SymbolicPrompting?style=plastic&logo=github&color=gold&cacheBus=1)](https://github.com/mindhack03d/SymbolicPrompting)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Course_Complete-success?style=plastic&logo=youtube)](https://youtube.com/playlist?list=PLNFL-2KY9QZVqoRwRzVLPN6qmDftpsjg6)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Reels_EN-success?style=plastic&logo=youtube)](https://www.youtube.com/playlist?list=PLNFL-2KY9QZXhGEfGUOrrZtzGdPESwh4l)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Reels_ES-success?style=plastic&logo=youtube)](https://youtube.com/playlist?list=PLNFL-2KY9QZUKlXC_4gnVUHoAJdd4s-AC&si=4N7ROWCD3G46y8t5l)
[![License-MIT](https://img.shields.io/badge/License-MIT-green?style=plastic)](https://opensource.org/licenses/MIT)
[![Benchmark](https://img.shields.io/badge/📊-Benchmark_Data-2a2a2a?style=plastic)](../Benchmark/symbolic_support_test.md)

[![Back to Main Repo](https://img.shields.io/badge/←_Back_Main_Page-gray?style=for-the-badge)](../README.md) | [![Symbolic Prompting Library](https://img.shields.io/badge/←_Back_Symbolic_Prompting_Library-gray?style=for-the-badge)](../examples/symbolic_prompting_library.md)

</div>

---

## 🎯 Objective

The Symbolic Prompting Framework (SPF) exists to solve a fundamental challenge in cybersecurity automation: **bridging the gap between human-readable intelligence and machine-executable logic**.

### Strategic Key Targets
1. **Language Translation**
   
   Convert unstructured natural language descriptions of vulnerabilities, system states, and security events into deterministic symbolic notation that machines can parse, validate, and act upon without human intervention.

2. **Eliminate Ambiguity**
   Replace subjective or vague terminology with strict hierarchical structures, typed data fields, and explicit operational rules (conditions, loops, sequences) that remove interpretation errors.

3. **Enable Automation**
   Produce standardized output that integrates directly into DevSecOps pipelines, SIEM systems, vulnerability scanners, and automated remediation workflows — transforming security intelligence from documentation into actionable data.

4. **Preserve Semantic Fidelity**
   Maintain the full context and relationships of the original information through structured grouping ({}, [], ()), relational operators (->, <~>), and metadata tagging, ensuring no meaning is lost during conversion.

5. **Zero-Trust Analysis**
   Implement strict validation rules over all incoming data, automatically filtering out OS background noise, irrelevant metrics, and untrusted sources to deliver only verified, actionable intelligence.

6. **Continuous Auditing**
   Enable real-time transformation pipelines that continuously ingest raw execution logs, environment variables, and process indicators, converting them into structured security data for ongoing threat monitoring.

---

## 📜 The Symbolic Prompt

Copy the block below into your LLM (Optimized for DeepSeek):

```shell
[ROLE] ::= SYMBOLIC_PROMPTING_TRANSLATOR
[CONVERSION_RULES] ::= {
    ENTITIES -> [STEP:SECTION|SUB_SECTION] ::= {},
    ACTIONS -> OPERATORS(::=, ->, |, &, ::=>),
    CONDITIONS -> IF/THEN/ELSE,
    LOOPS -> FOR/IN/DO,
    SEQUENCES -> (->|<-|->>|<<-) (arrows),
    EQUIVALENCE -> (<~>, ==), 
    PARALLEL -> | (pipe),
    GROUPS -> (()|[]|{})
}
[CVE_DESCRIPTION] ::= {
# CVE-2021-41773 — Practical Vulnerability Analysis

**Target:** Apache HTTP Server 2.4.49 on Debian 9.4

---

## STEP 0 — AFFECTED VERSION ANALYSIS
- **[0.1] PRODUCT_MATCH:** Apache HTTP Server (`cpe:2.3:a:apache:http_server:2.4.49`). Confirmed match for `http_server`.
- **[0.2] VERSION_MATCH:** 2.4.49 is the **only** version affected by CVE-2021-41773. Vulnerability was introduced by a change in 2.4.49 specifically. (Note: CVE-2021-42013 extends to 2.4.50 due to incomplete fix.)
- **[0.3] PATCH_STATUS:** **UNPATCHED** — 2.4.49 is vulnerable. Fixed in 2.4.50 (which itself was insufficient → 2.4.51 is the complete fix).
- **[0.4] CONFIDENCE:** **HIGH** — exact version string match to documented affected version.

---

## STEP 1 — ROOT CAUSE ANALYSIS
- **[1.1] VULNERABILITY_TYPE:** Path Traversal (CWE-22) leading to information disclosure; under specific conditions, Remote Code Execution.
- **[1.2] ANOMALOUS_BEHAVIOR:** A change to path normalization in 2.4.49 allowed URL-encoded traversal sequences (`%2e`) to bypass the normalization that would otherwise reject `../`. The `ap_normalize_path` logic failed to decode-then-normalize correctly, permitting traversal outside the configured `DocumentRoot` aliased directories.
}
[REQUIREMENTS] ::= {
    NO_MARKDOWN: FALSE,
    INCLUDE_COMMENTS: TRUE,
    EXPLAIN_TRANSFORMATION: FALSE,
    INCLUDE_SUBSTEPS: TRUE
}
[TASK] ::= CONVERT_NATURAL_LANGUAGE_TO_SYMBOLIC_PROMPTING([CVE_DESCRIPTION])
[OUTPUT_REQUIREMENTS] ::= {
    FORMAT = "SYMBOLIC_NOTATION",
    INCLUDE_DATA_TYPES = TRUE,
    ADD_ERROR_HANDLING = TRUE,
    SHOW_HIERARCHY = TRUE
}
```

---

### 🏗️ DEEPSEEK RESULT (EXPECTED)

```shell
[SYMBOLIC_PROMPTING] ::= {
    [CVE-2021-41773] ::= {
        [METADATA] ::= {
           TARGET: "Apache HTTP Server 2.4.49 on Debian 9.4",
           CWE: "CWE-22",
           CVSS_V3.1: "AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:N/A:N",
           SCORE: 7.5
        },
        [STEP_0: AFFECTED_VERSION_ANALYSIS] ::= {
            [0.1: PRODUCT_MATCH] ::= {
                ENTITY: "Apache HTTP Server",
                CPE: "cpe:2.3:a:apache:http_server:2.4.49",
                STATUS: "CONFIRMED"
            },
            [0.2: VERSION_MATCH] ::= {
                AFFECTED_VERSIONS: ["2.4.49"],
                NOTE: "CVE-2021-42013 extends to 2.4.50"
            },
            [0.3: PATCH_STATUS] ::= "UNPATCHED",
            [0.4: CONFIDENCE] ::= "HIGH"
        },
        [STEP_1: ROOT_CAUSE_ANALYSIS] ::= {
            [1.1: VULNERABILITY_TYPE] ::= "Path Traversal (CWE-22)",
            [1.2: ANOMALOUS_BEHAVIOR] ::= {
                FUNCTION: "ap_normalize_path",
                FLAW: "Incorrect handling of URL-encoded traversal sequences (%2e)",
                RESULT: "Bypass of path normalization, allowing access outside DocumentRoot"
            }
        }
    }
}
```

---

## 🧠 The Engineering Advantage

The Symbolic Prompting Framework delivers measurable engineering value by transforming how security intelligence is processed, analyzed, and operationalized. This section outlines the technical advantages that distinguish SPF from traditional natural language processing approaches

---

### Key Technical Pillars

1. **Deterministic Transformation**
   SPF guarantees **identical output for identical input** through strict rule-based conversion, eliminating the variability inherent in probabilistic NLP models.

   **Advantage**: Enables version-controlled security intelligence where every transformation is auditable, testable, and revertible — critical for compliance and forensic analysis.

2. **Semantic Preservation**
   Unlike traditional parsing that loses context, SPF maintains **full semantic fidelity** through structured hierarchies, relationship operators, and metadata tagging.
   
   **Advantage**: Security analysts can trace every piece of symbolic output back to its original natural language source, ensuring no intelligence is lost during conversion.

3. **Zero-Trust Data Processing**
   SPF implements a zero-trust architecture where all input is validated, sanitized, and structured before being passed to downstream systems.
   
   **Advantage**: Raw execution metrics, environment variables, and process indicators are automatically sanitized, removing false positives and noise before they reach security analysts.

4. **Human-Machine Bilingualism**
   SPF serves as a bidirectional translator — converting human intelligence to machine-readable format and enabling machines to present structured findings back to humans.
   
   **Advantage**: Bridges the communication gap between security researchers (who think in natural language) and automated systems (which require structured data), enabling seamless collaboration.

5. **Automated Auditing & Continuous Monitoring**
   SPF enables real-time transformation pipelines that continuously ingest and process execution data for ongoing security monitoring.
   
   **Advantage**: Security teams receive actionable intelligence as events occur, reducing mean time to detection (MTTD) and enabling rapid incident response.

6. **Extensible Rule Architecture**
   The framework is built on a modular rule engine that allows new patterns, entities, and operators to be added without core system changes.
   
   **Advantage**: Organizations can customize SPF to handle proprietary data formats, internal naming conventions, and organization-specific security intelligence without engineering overhead.

7. **Error Resilience & Graceful Degradation**
   SPF includes comprehensive error handling that ensures partial outputs when full transformation is impossible, preventing pipeline failures.
   
   **Advantage**: Security operations continue uninterrupted even when malformed or incomplete input is encountered, with clear error reporting for manual intervention.

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


[![Back to Main Repo](https://img.shields.io/badge/←_Back_Main_Page-gray?style=for-the-badge)](../README.md) | [![Symbolic Prompting Library](https://img.shields.io/badge/←_Back_Symbolic_Prompting_Library-gray?style=for-the-badge)](../examples/symbolic_prompting_library.md)