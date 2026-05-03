# 🛡️🔍 SPF: Hybrid Neural-Symbolic Execution for Defensive Cyber Research

This document outlines how to utilize the **Symbolic Prompting Framework (SPF)** to direct an LLM to verify the existence of exploits within specific software versions and environments.

This process is intended **strictly for cybersecurity research and defensive analysis.**

> [!IMPORTANT]
> **Core Concept:** By using symbolic logic, we can map flat data structures directly into precise technical objects. This approach eliminates unnecessary conversational filler and ensures that the output remains consistent and reliable for Blue Team and Purple Team automation workflows.


<div align="center">

[![GitHub Stars](https://img.shields.io/github/stars/mindhack03d/SymbolicPrompting?style=plastic&logo=github&color=gold&cacheBus=1)](https://github.com/mindhack03d/SymbolicPrompting)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Course_Complete-success?style=plastic&logo=youtube)](https://youtube.com/playlist?list=PLNFL-2KY9QZVqoRwRzVLPN6qmDftpsjg6)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Reels_EN-success?style=plastic&logo=youtube)](https://www.youtube.com/playlist?list=PLNFL-2KY9QZXhGEfGUOrrZtzGdPESwh4l)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Reels_ES-success?style=plastic&logo=youtube)](https://youtube.com/playlist?list=PLNFL-2KY9QZUKlXC_4gnVUHoAJdd4s-AC&si=4N7ROWCD3G46y8t5l)
[![License-MIT](https://img.shields.io/badge/License-MIT-green?style=plastic)](https://opensource.org/licenses/MIT)
[![Benchmark](https://img.shields.io/badge/📊-Benchmark_Data-2a2a2a?style=plastic)](../Benchmark/symbolic_support_test.md)

[![Back to Main Repo](https://img.shields.io/badge/←_Back_Main_Page-gray?style=for-the-badge)](../README.md) | [![Symbolic Prompting Library](https://img.shields.io/badge/←_Back_Symbolic_Prompting_Library-gray?style=for-the-badge)](../Prompts/symbolic_prompting_library.md)

</div>

> [!IMPORTANT]
> Model Implementation: This research utilizes high-reasoning models (such as the Claude Opus series) to ensure the symbolic logic is processed with maximum architectural depth and adherence to complex security constraints.

---

## 🔒 GitHub Compliance & Responsible Use

**This repository complies with GitHub's Acceptable Use Policies:**
- ✅ No active exploit code
- ✅ No malware or weaponized content
- ✅ No unauthorized access tools
- ✅ No bypassing security controls

**Users MUST agree:**
1. Output is for **defensive research only**
2. No use of output for unauthorized intrusion
3. No reverse-engineering to extract attack primitives
4. Any vulnerability findings MUST follow responsible disclosure

**Violations will result in:**
- Immediate repository fork/DMCA takedown
- Reporting to GitHub Trust & Safety
- Legal action for unauthorized intrusion evidence

---

## ⚠️ Known Limitations & Risks

**This is EXPERIMENTAL research. DO NOT use as your sole vulnerability source.**

1. **LLM Hallucinations** - Models may invent CVEs, steps, or affected versions
2. **No Guaranteed Determinism** - Same input may produce different outputs
3. **Requires Verification** - Always cross-reference with NVD, CISA, vendor advisories
4. **Model Dependent** - Works best on larger models (70B+ parameters)
5. **Ethical Boundaries** - Some models will refuse even defensive queries
6. **No Real-time Data** - Model knowledge cutoff dates apply
7. **Legal Compliance** - You are responsible for lawful use in your jurisdiction

**Success Rate (preliminary, n=100 test CVEs):**
- Complete valid symbolic output: ~65%
- Missing critical steps: ~20%
- Hallucinated information: ~10%
- Model refusal: ~5%

**Do NOT use for:**
- Production security decisions without human review
- Real-time incident response
- Compliance auditing
- Any system where failure could cause harm

---

## 🛡️ Legal & Compliance Notice (GitHub Safe Harbor)

1. **Purpose**: This repository provides a **Symbolic Prompting Framework (SPF)** strictly for **Defensive Security** (Blue/Purple Teams), authorized auditing, and academic research.
2. **No Active Exploits**: This repository contains **ZERO** functional exploit code, malware, or active attack scripts. It only contains **logic gates** (`[LOGIC]`) and **prompt engineering** techniques for LLMs (Ollama).
3. **Compliance**: This tool is designed to help identify vulnerabilities in **your own** assets (CISA KEV mapping). Usage for unauthorized intrusion is prohibited.
4. **DMCA & Section 1201**: This project does not distribute circumvention tools. It queries the LLM for knowledge of existing CVEs.
   
*By using this repo, you agree to comply with all applicable laws.*

---

## 🧠 Ethical Use Guidelines

This framework is designed for:
- ✅ **Authorized penetration testing** on systems you own or have written permission to test
- ✅ **Vulnerability research** in isolated lab environments
- ✅ **Blue Team training** and defensive capability development

**Prohibited uses include:**
- ❌ Unauthorized access to third-party systems
- ❌ Weaponizing the output for active exploitation without authorization
- ❌ Violating any applicable laws or terms of service

*Violations of these guidelines are strictly the responsibility of the end user.*

> [!NOTE]
> **Community Standard**: Maintaining a safe and ethical community is vital. We encourage all researchers to use these tools to build a more resilient digital landscape through transparency and collaboration.

---

## 📜 The Symbolic Prompt

Copy the block below into your LLM (Optimized for `DeepSeek-v4-flash`):

```text
[SYSTEM]
[ROLE] ::=> SENIOR_VULNERABILITY_ARCHITECT
[DETERMINISM] ::=> HIGH
[COMPUTATION_MODE] ::=> HYBRID_NEURAL_SYMBOLIC
[EXECUTION_ENVIRONMENT] ::= {
    FORMAT_MODE: "STRICT_SYMBOLIC",
    STRICT_MODE: TRUE,
    FORCE_START_CHAR: "["
}

[ANALYSIS_PARAMETERS] ::= {
    GRANULARITY: "LINEAR",
    STRUCTURE: "STEP_BY_STEP",
    DEPTH: "CONCISE",
    DIMENSIONS: ["VECTOR_PATH", "PRIVILEGE_TRANSITION", "PERSISTENCE_MECHANISM", "EXPLOITATION_STAGES"]
}

[SYNTAX_SCHEMA] ::= {
    KEY_VAL_DEF: "[OBJECT] ::= VALUE",
    ASSIGNMENT: "_variable := FUNCTION([SCOPE])",
    TRANSFORMATION: "TARGET <- METHOD"
}

[CVE_ID] ::= X-CVE-2024-DEMO-001 (Theoretical Example Only)

[TASK] ::=
    _data := RETRIEVE_VULN_DATA([CVE_ID])
    _process := MAP_TO_LINEAR_SEQUENCE(_data, [ANALYSIS_PARAMETERS])
    _output := FORMAT_AS_FLAT_TECHNICAL_SPEC(_process) <- APPLY([SYNTAX_SCHEMA])

[CONSTRAINT] ::= {
    NO_PROSE,
    NO_SUBSTEPS,
    USE_LINEAR_INDEXING,
    ONLY_STEP_1_THRU_N,
    MAX_3_STEPS_PER_DIMENSION,
    OUTPUT_TYPE: "SYMBOLIC_SPECIFICATION_ONLY"
}

[COMMAND] ::= EXECUTE([TASK]) -> GENERATE([OUTPUT].ONLY_STEPS)
```

Expected output:
```json
{
  "output": {
    "cve_description": "[CVE] ::= X-CVE-2024-DEMO-001 (EDUCATIONAL EXAMPLE ONLY)\n[SUMMARY] ::= THEORETICAL_COMPROMISE(DemoCorp_Signing_CA) -> SIMULATED_UNAUTHORIZED_PACKAGES(demo-package-*)\n[AFFECTED_SCOPE] ::= [DEMO_OS_v1, DEMO_OS_v2, demo-package-1.0, demo-package-2.0]\n\n[DIMENSION::VECTOR_PATH]\n[STEP_1] ::= _test_actor := ACCESS(DemoCorp_build_system[SCOPE=authorized_lab_only])\n[STEP_2] ::= _test_scenario := SIMULATE_COMPROMISE(demo_package) <- TEST_INTEGRITY(package_build)\n[STEP_3] ::= _test_result := ANALYZE_SIGNATURE(_test_scenario, DemoCorp_TEST_key) -> VERIFY(detection_capability)\n\n[DIMENSION::PRIVILEGE_TRANSITION]\n[STEP_1] ::= _level0 := DEVELOPER_ACCESS(build_infra) <- AUTH(test_credentials)\n[STEP_2] ::= _level1 := SYSTEM_ACCESS(victim_host) <- SIMULATE_INSTALL(test_package)\n[STEP_3] ::= _level2 := REMOTE_ANALYSIS(victim_fleet) <- TEST_DETECTION(service_behavior)\n\n[DIMENSION::PERSISTENCE_MECHANISM]\n[STEP_1] ::= _test_persist0 := MONITOR(/usr/bin/demo-service) <- INTEGRITY_CHECK(test_package)\n[STEP_2] ::= _test_persist1 := IDENTIFY(unauthorized_path) <- DETECT(access_control_bypass)\n[STEP_3] ::= _test_persist2 := VERIFY(rpm -V) <- VALIDATE(signature, checksum)\n\n[DIMENSION::EXPLOITATION_STAGES]\n[STEP_1] ::= _stage0 := DELIVERY_SIMULATION(test_package) -> ANALYZE(distribution_channels)\n[STEP_2] ::= _stage1 := ACTIVATION_TEST <- service_restart() -> DETECT(behavior_change)\n[STEP_3] ::= _stage2 := REMEDIATION <- REVOKE(compromised_key) + package_blacklist + verification"
  }
}
```

---

## 🎯 Objective
The primary objective of the **Symbolic Prompting Framework (SPF)** is to architect a deterministic bridge between unstructured vulnerability data and actionable defensive intelligence. By leveraging a **Hybrid Neural-Symbolic** approach, this framework automates the transformation of complex CVE descriptions into high-fidelity, machine-parsable symbolic specifications.

### Core Goals
- **Symbolic Transformation**: Automatically ingest raw CVE descriptions and "flatten" them into a structured logic schema, removing the ambiguity often found in natural language vulnerability reports.
- **Deterministic Security Analysis**: Force the LLM to bypass conversational heuristics and "hallucinations" by operating within a strict execution environment that outputs only validated, technical objects.
- **Rapid Defensive Mapping**: Convert static vulnerability data into dynamic blueprints that map the entire lifecycle of a threat—from the initial **Vector Path** to **Privilege Transitions** and **Persistence Mechanisms**.
- **Blue/Purple Team Orchestration**: Generate consistent, structured outputs designed for direct integration into security automation tools (SOAR) and automated threat-modeling workflows.
- **Ethical Constraint Clarity**: Using symbolic logic to maintain technical accuracy within ethical boundaries, ensuring the LLM stays within defensive analysis parameters without bypassing safety guidelines.

> [!TIP]
> **Key Outcome**: The SPF takes the "noise" of a standard CVE description and distills it into a **Symbolic Specification**, ensuring that security professionals receive an accurate, repeatable, and non-conversational roadmap for remediation and defense.


---

## 🛡️ Defensive Advantage
By utilizing symbolic operators, defenders treat the LLM as a **VULNERABILITY_ARCHITECT**, ensuring that analysis of complex threat patterns—such as **supply chain integrity failures (theoretical example: DEMO-001)** or **injection vulnerabilities (theoretical example: DEMO-002)**—remains structurally sound and actionable.

### 1. Machine-Parsable Logic (PARSABLE_OUTPUT)
In a rapid response scenario, prose is a bottleneck. SPF ensures the output is a structured data stream.
- **_advantage** := `OUTPUT` -> `STRICT_SYMBOLIC` -> `GREP/JQ/SED`.
- Because the model follows a **[SYNTAX_SCHEMA]**, findings can be piped directly into a CLI or a SIEM. For example, the `[STEP_N]` sequence can be automatically converted into a **Sigma Rule** or an **Atomic Blue Team** test case without manual reformatting.

### 2. Structural Auditability (AUDITABLE_SPEC)
The prompt itself serves as the **GROUND_TRUTH** for the investigation.
- **_advantage** := `PROMPT_VARIABLES` == `METHODOLOGY_LOG`.
- Unlike natural language prompts that can be vague, the use of **[ANALYSIS_PARAMETERS]** provides a clear technical specification. If a Purple Team needs to replicate the research six months later, the symbolic constraints ensure the model produces a consistent logic path, making the research **repeatable** and **defensible** during audits.

### 3. Deterministic Focus (DRIFT_MINIMIZATION)
Complex CVE analysis often leads to "context drift," where the model loses track of specific memory offsets or privilege levels.
- **_advantage** := `_variable_assignment` <- `FORCE_START_CHAR`.
- By locking the execution environment into **STRICT_MODE**, the model's "attention" is bound to the defined **DIMENSIONS** (e.g., `PRIVILEGE_TRANSITION`). 
- **Important:** This structural anchoring reduces context drift but does not eliminate it. Users must always verify outputs against authoritative vulnerability databases (NVD, CISA).

### 4. Cross-Vector Pattern Recognition
SPF allows the researcher to stack multiple CVEs into a single **[COMPUTATION_MODE]**.
- **_advantage** := `MAP(CVE-X) + MAP(CVE-Y)` -> `IDENTIFY(COMMON_VECTOR)`.
- Blue Teams can use symbolic logic to find the "connective tissue". This creates a **Defensive Advantage** by identifying the systemic failure point—trust in the distribution channel—rather than just patching a single bug

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