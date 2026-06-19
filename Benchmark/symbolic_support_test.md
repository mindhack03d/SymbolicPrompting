# Symbolic Prompting - Benchmark Overview & Compatibility

## *"We don't ask you to trust our numbers. We give you the tools to verify them yourself."*

<div align="center">

[![Status](https://img.shields.io/badge/Status-Active_Course-success?style=plastic)](https://github.com/mindhack03d/SymbolicPrompting)
[![GitHub Stars](https://img.shields.io/github/stars/mindhack03d/SymbolicPrompting?style=plastic&logo=github&color=gold&cacheBus=1)](https://github.com/mindhack03d/SymbolicPrompting)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Course_Complete-success?style=plastic&logo=youtube)](https://youtube.com/playlist?list=PLNFL-2KY9QZVqoRwRzVLPN6qmDftpsjg6)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Reels_EN-success?style=plastic&logo=youtube)](https://www.youtube.com/playlist?list=PLNFL-2KY9QZXhGEfGUOrrZtzGdPESwh4l)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Reels_ES-success?style=plastic&logo=youtube)](https://youtube.com/playlist?list=PLNFL-2KY9QZUKlXC_4gnVUHoAJdd4s-AC&si=4N7ROWCD3G46y8t5l)<br>
[![License-MIT](https://img.shields.io/badge/License-MIT-green?style=plastic)](https://opensource.org/licenses/MIT)
[![Methodology-V2](https://img.shields.io/badge/Methodology-V2.0-blue?style=plastic)](../Benchmark/benchmark_methodology.md)
[![Benchmark](https://img.shields.io/badge/📊-Benchmark_Data-2a2a2a?style=plastic)](../Benchmark/symbolic_support_test.md)

</div>

[⬅️ Back to Home](../README.md) | [Methodology used](../Benchmark/benchmark_methodology.md)

## 🚀 Quick Overview Dashboard

*Your 30-second guide to the benchmark reports. Click any model for full temporal analysis.*

## 📊 Benchmark Summary

This table consolidates key findings across all five models, highlighting overall winners and each model's sensitivity to different prompt formats.

|🔗 Model | March 3 Only | March 5 Only | Winner (Combined Average) |
|:-- |:-- |:-- |:-- |
|[**claude-3-haiku**](../Benchmark/benchmark_model_claude.md) | 🏆 Symbolic | 🏆 Symbolic | 🏆 Symbolic |
|[**deepseek-v3**](../Benchmark/benchmark_model_deepseek.md) | 🏆 Normal | 🏆 DSL/JSON | 🏆 DSL/JSON |
|[**gemini-2.0-flash**](../Benchmark/benchmark_model_gemini.md) | 🏆 DSL/JSON | 🏆 Normal | 🏆 Normal |
|[**llama-3.3-70b**](../Benchmark/benchmark_model_llama.md) | 🏆 Symbolic | 🤝 Tie (DSL/JSON / Normal) | 🏆 DSL/JSON |
|[**gpt-4o-mini**](../Benchmark/benchmark_model_openai.md) | 🏆 Normal | 🏆 Normal | 🏆 Normal |

### 🔗 Quick Navigation

- 📊 **[Benchmark Methodology](../Benchmark/benchmark_methodology.md)** - Multi-date testing protocol, IQR Deception detection, temporal analysis framework 
- 📊 **[Benchmark Overview & Compatibility](../Benchmark/symbolic_support_test.md)** - Cross-model summary dashboard & compatibility test results for various models 
- 📝 **[Claude Report](../Benchmark/benchmark_model_claude.md)** - Deep-dive analysis for claude-3-haiku 
- 📝 **[DeepSeek Report](../Benchmark/benchmark_model_deepseek.md)** - Deep-dive analysis for deepseek-v3 
- 📝 **[Gemini Report](../Benchmark/benchmark_model_gemini.md)** - Deep-dive analysis for gemini-2.0-flash 
- 📝 **[Llama Report](../Benchmark/benchmark_model_llama.md)** - Deep-dive analysis for llama-3.3-70b 
- 📝 **[OpenAI Report](../Benchmark/benchmark_model_openai.md)** - Deep-dive analysis for gpt-4o-mini 
- ❓ **[Benchmark FAQ](../Benchmark/benchmark_fqa.md)** - Answers to community questions about our findings and methodology 
- 📥 **[Raw Data (CSV) Mar 3](../Benchmark/benchmark_20260303.csv)** - Complete dataset from March 3, 2026 
- 📥 **[Raw Data (CSV) Mar 5](../Benchmark/benchmark_20260305.csv)** - Complete dataset from March 5, 2026 
- 📝 **[Benchmark Consolidate Equations](../Benchmark/benchmark_2026030X_consolidate_equations.xlsx)** - Complete dataset with Excel Formulas 
- 🔧 **[Reproduce Test](../Benchmark/benchmark_reproduce_test.md)** - How to  Reproduce the tests yourself 
- 🔧 **[n8n Workflow](../Benchmark/n8n_benchmark.json)** - Reproduce the tests yourself in N8N

---

### What "Supported" Means

| Status | Definition |
|:---|:---|
| ✅ Supported | Model completed task, all required fields present, no hallucinations |
| ⚠️ Partial | Model completed but with minor format deviations (e.g., extra text) |
| ❌ Unsupported | Model failed to follow structure, omitted required fields, or hallucinated significantly |

---

The following models were tested only for **COMPATIBILITY** with Symbolic Prompting syntax. 
They successfully executed the ```Hello``` Symbolic Prompt and ```Complex``` Symbolic Prompt, but full benchmarks were not run due to resource constraints.

<details>
  <summary><h3>📚 Model Test - Simple Symbolic Prompt vs Complex Symbolic Prompt <i>(Click to expand ...)</i></h3></summary>
<table>
  <thead>
    <tr>
      <th>Model</th>
      <th>Symbolic (Hello Prompt)</th>
      <th>Symbolic (Complex)</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>claude-3.5-haiku@20241022</td>
      <td>Supported</td>
      <td>Supported TTR:14.2s</td>
      <td></td>
    </tr>
    <tr>
      <td>claude-3.7-sonnet@20250219</td>
      <td>Supported</td>
      <td>Supported TTR:10.7s</td>
      <td></td>
    </tr>
    <tr>
      <td>claude-3-haiku@20240307</td>
      <td>Supported</td>
      <td><strong>Supported TTR:4.5s</strong></td>
      <td></td>
    </tr>
    <tr>
      <td>claude-haiku-4-5@20251001</td>
      <td>Supported</td>
      <td><strong>Supported TTR:7.2s</strong></td>
      <td></td>
    </tr>
    <tr>
      <td>claude-opus-4-5@20251101</td>
      <td>Supported</td>
      <td><strong>Supported TTR:9.8s</strong></td>
      <td></td>
    </tr>
    <tr>
      <td>claude-sonnet-4@20250514</td>
      <td>Supported</td>
      <td>Supported TTR:12.7s</td>
      <td></td>
    </tr>
    <tr>
      <td>claude-sonnet-4-5@20250929</td>
      <td>Supported</td>
      <td>Supported TTR:11.5s</td>
      <td></td>
    </tr>
    <tr>
      <td>deepseek-r1@0528</td>
      <td>Supported</td>
      <td>Supported TTR:44.5s</td>
      <td>⚠️ Rate limited—not representative</td>
    </tr>
    <tr>
      <td>deepseek-v3@0324</td>
      <td>Supported</td>
      <td><strong>Supported TTR:6.8s</strong></td>
      <td></td>
    </tr>
    <tr>
      <td>deepseek-v3.1</td>
      <td>Supported</td>
      <td><strong>Supported TTR:7.3s</strong></td>
      <td></td>
    </tr>
    <tr>
      <td>deepseek-v3.2</td>
      <td>Supported</td>
      <td>Supported TTR:13.01s</td>
      <td></td>
    </tr>
    <tr>
      <td>gemini-2.0-flash@001</td>
      <td>Supported</td>
      <td><strong>Supported TTR:4.0s</strong></td>
      <td></td>
    </tr>
    <tr>
      <td>gemini-2.0-flash-lite@001</td>
      <td>Supported</td>
      <td>Supported TTR:45.3s</td>
      <td></td>
    </tr>
    <tr>
      <td>gemini-2.5-flash</td>
      <td>Supported</td>
      <td>Supported TTR:13.5s</td>
      <td>Tested during peak hours</td>
    </tr>
    <tr>
      <td>gemini-2.5-pro</td>
      <td>Supported</td>
      <td>Supported TTR:18.8s</td>
      <td></td>
    </tr>
    <tr>
      <td>gpt-4.1@2025-04-14</td>
      <td>Supported</td>
      <td><strong>Supported TTR:6.1s</strong></td>
      <td></td>
    </tr>
    <tr>
      <td>gpt-4.1-mini@2025-04-14</td>
      <td>Supported</td>
      <td><strong>Supported TTR:5.1s</strong></td>
      <td></td>
    </tr>
    <tr>
      <td>gpt-4.1-nano@2025-04-14</td>
      <td>Supported</td>
      <td><strong>Supported TTR:3.1s</strong></td>
      <td></td>
    </tr>
    <tr>
      <td>gpt-4o@2024-08-06</td>
      <td>Supported</td>
      <td><strong>Supported TTR:4.9s</strong></td>
      <td></td>
    </tr>
    <tr>
      <td>gpt-4o@2024-11-20</td>
      <td>Supported</td>
      <td><strong>Supported TTR:3.7</strong></td>
      <td></td>
    </tr>
    <tr>
      <td>gpt-4o-mini@2024-07-18</td>
      <td>Supported</td>
      <td><strong>Supported TTR:4.1s</strong></td>
      <td></td>
    </tr>
    <tr>
      <td>llama-3.3-70b-instruct</td>
      <td>Supported</td>
      <td>Supported TTR:20.1s</td>
      <td></td>
    </tr>
  </tbody>
</table>

### NOTES Section

#### Deepseek-r1 Note

> [!NOTE]
> ```deepseek-r1@0528``` - ⚠️ Consistently high latency—likely rate limiting.<br>
> Value excluded from performance comparison due to confirmed rate limiting

#### Gemini Notes

> [!NOTE]
> Gemini 2.5 Flash showed higher latency than 2.0 Flash in our tests. This may be due to API routing differences rather than model performance—investigating.<br>
> *"Note: Tests were run at different times of day. Gemini 2.5 Flash was tested during peak hours, which may explain higher latency. We are re-running to confirm."*

</details>

---

## Pure Prompt Tokens based on OpenAI Tokenizer

> [!IMPORTANT]
> These token counts are from **isolated tests on gemini-2.0-flash@001** using the complex prompts shown below. They **are not** part of the main benchmark dataset and should not be compared directly to the simple "HELLO" task results. The dramatic difference in token counts between formats reflects the inherent conciseness of Symbolic syntax versus verbose Natural Language or structured JSON.

|Feature |Prompt 1: Natural Language |Prompt 2: DSL (JSON-based) |Prompt 3: Symbolic Prompting |
|:-- |:-- |:-- |:-- |
|Tokens Consumed |1025 (High) |796 (Medium) | 481 (Low) |

> [!IMPORTANT]
> Prompts are not normalized for length—symbolic format is inherently more concise. Comparison is functional (same task), not instructional equality. Complex Symbolic Prompt

### Test 1: INPUT is "1" as string.

|Feature |Prompt 1: Natural Language |Prompt 2: DSL (JSON-based) |Prompt 3: Symbolic Prompting |
|:-- |:-- |:-- |:-- |
|Tokens Consumed |1154 (High) |900 (Medium) | 636 (Low) |
|Response Time |2.4s (Average) | 5.1s (Slow) | 2.3s (Fast) |

> [!NOTE]
> **1**: *"Tests run on gemini-2.0-flash@001 to isolate prompt format performance"* <br>
> **2:** I used the following Prompt (Normal - DLS/JSON - Symbolic) inside of PROMPT Sections. Instead to add text, I used as input the number as string "1".

### Test 2: Full Article Input

|Feature |Prompt 1: Natural Language |Prompt 2: DSL (JSON-based) |Prompt 3: Symbolic Prompting |
|:-- |:-- |:-- |:-- |
|Tokens Consumed |2246 (High) |1992 (Medium) | 1728 (Low) |
|Response Time |4.6s (Average) | 19.4s (Slow) | 4.1s (Fast) |

> [!NOTE]
> **1:** *"Tests run on gemini-2.0-flash@001 to isolate prompt format performance"*<br>
> **2:** I used the following Prompt (Normal - DLS/JSON - Symbolic) inside of PROMPT Sections. I used the TEXT INPUT as Prompt INPUT.

> [!NOTE]
> **Key Observations:**
> - Symbolic consistently uses **23-45% fewer tokens** than Natural Language
> - DSL/JSON shows **severe degradation** with long inputs (19.4s vs 4.1s for Symbolic), suggesting JSON parsing overhead scales poorly with content length
> - These results align with our methodology's [analysis of format efficiency vs. prompt length](../Benchmark/benchmark_fqa.md#q-how-do-you-separate-format-effects-from-prompt-length-isnt-this-just-measuring-shorter-prompts-are-faster)

---

## Comparative Table between Prompts
|Feature |Prompt 1: Natural Language |Prompt 2: DSL (JSON-based) |Prompt 3: Symbolic Prompting |
|:-- |:-- |:-- |:-- |
|Core Architecture |Narrative/Conversational |Schema-driven / Rigid| Logic-driven / Functional|
|Efficiency Ratio |Low (Filler text included) |Medium (High metadata) |High (Information Density)|
|Contextual Focus |Broad / Interpretative |Structural Validation | Execution Flow ($Variables) |
|Best Use Case | Prototyping & Creativity |API Integration / Type Safety |Production / High-Scale ETL|
| **Processing Load** | **High:** Model must parse prose, infer intent, and reason about conditional logic. | **Very High:** Model must navigate a complex JSON tree, map nested keys, and perform internal validation against the schema. | **Low:** Model executes direct, function-like calls with minimal ambiguity. |
| **Efficiency Bottleneck** | **Semantic Ambiguity.** The model spends cycles "understanding" the instructions rather than just following them. | **Structural Overhead.** The JSON format requires the model to constantly parse and validate keys and values, leading to a 2x slowdown compared to Prompt 1. | **None.** The syntax mimics code, which LLMs process extremely efficiently. The flow is pre-defined. |
| **LLM Behavior** | Acts like a **intern reading a memo**. It has to interpret the task before starting. | Acts like a **clerk filling out a complex form**. It meticulously checks each field against the rules. | Acts like a **virtual machine executing bytecode**. It follows a direct, sequential flow of operations. |
| **Key Takeaway** | Good for complex, one-off tasks where clarity is needed, but inefficient for high-volume processing. | Improves output structure but introduces significant computational overhead due to its complexity. | **Optimal for performance.** Exploits the model's pattern-matching abilities to minimize latency and token usage. |

---

## 🎯 PROMPT Section

### Simple Prompt (Hello Prompt)

This prompt was used only to validate if the LLM Model support the initial test of the Symbolic Prompting.

```
[SYSTEM]
[ROLE] ::=> User_Say_Hello
[TASK] ::=
  _response_user := "HELLO"
[CONSTRAINTS] ::=
- NO_ADD_COMMENTS_OR_PROSE
[OUTPUT] ::= _response_user
```

> [!NOTE]
> The next prompt was validate the Models TTR.

---

### Input Text for Testing Prompts
The following text was used only for testing purpose in all the prompts.

<details>
  <summary><h3><strong>📑 Text INPUT For Prompts</strong> <i>(Click to expand . . .)</i></h3></summary>

"   In the fast-paced world of software development, open source dependencies are the building blocks that enable innovation and efficiency. But as we've seen time and again, they can also introduce significant risks if not properly managed. The recent supply chain attack on the npm registry, uncovered September 8, 2025, serves as a stark reminder of these vulnerabilities. Attackers compromised 18 widely used packages through a phishing campaign targeting open source project maintainers, and published malicious versions that could have impacted billions of downloads weekly.        What happened in the attack?     The incident involved popular utility libraries essential for tasks like color manipulation, debugging, and ANSI string handling in JavaScript applications. The compromised packages included  ansi-regex (version 6.2.1) ansi-styles (6.2.2) backslash (0.2.1) chalk (5.6.1) chalk-template (1.1.1) color-convert (3.1.1) color-name (2.0.1) color-string (2.1.1) debug (4.4.2) has-ansi (6.0.1) is-arrayish (0.3.3) simple-swizzle (0.2.3) slice-ansi (7.1.1) strip-ansi (7.1.1) supports-color (10.2.1) supports-hyperlinks (4.1.1) wrap-ansi (9.0.1) And others like color (5.0.1)  These packages collectively boast over 2 billion weekly downloads, making this one of the largest supply chain incidents in npm's history. The attackers injected obfuscated JavaScript code designed to act as a cryptocurrency stealer. By wrapping browser APIs, the malware intercepted web3 transactions and silently replaced wallet addresses to redirect funds to the attacker's control. Fortunately, the attack was detected quickly—thanks in part to a well-known obfuscator that made the malicious code easier to spot. Although the compromised versions were downloaded over 2.5 million times, the actual financial impact was minimal, with only around $500 in stolen cryptocurrency reported. Still, the potential for widespread damage was enormous, highlighting how a single point of failure in the open source ecosystem can ripple through countless applications.        The broader implications for your software supply chain     This event underscores a growing trend: Supply chain attacks are becoming more sophisticated and targeted. Phishing attacks on open source project maintainers to gain publishing rights bypasses traditional security measures, allowing bad actors to inject malware directly into trusted repositories. For organizations relying on npm packages—whether in front-end UI components or back-end services—the risks include data exposure, unauthorized access, and compromised production environments. Without proper visibility into your dependencies, it's challenging to identify and respond to such threats. This is where a Software Bill of Materials (SBOM) becomes invaluable. An SBOM is a comprehensive inventory of all components in an application, including their versions, licenses, and potential vulnerabilities. Having this data at your fingertips makes it faster and easier to find and remediate any component that is discovered to be vulnerable or becomes compromised.        How Black Duck can help strengthen your defenses     At Black Duck, we've long advocated for proactive supply chain security, and tools like software composition analysis (SCA) are designed to address exactly these kinds of challenges. Black Duck® SCA offers complete visibility into your software dependencies, helping you detect malicious packages early in the development life cycle. For instance, Black Duck SCA can identify anomalous or compromised components, such as those with obfuscated code or unexpected behaviors. And it can generate SBOMs in standardized formats like SPDX and CycloneDX, ensuring compliance with regulations and building trust with your stakeholders. In the wake of this npm attack, teams using Black Duck SCA could quickly audit their dependency manifests (e.g., package-lock.json) for the affected versions, purge any poisoned caches, and rebuild from safe sources. Additionally, integrating Black Duck SCA into your CI/CD pipelines enables automated checks that block vulnerable or malicious dependencies before they reach production. This not only mitigates immediate risks but also fosters a secure-by-design culture.        Key takeaways and recommendations     As we reflect on this incident, here are some practical steps to enhance your supply chain security.  Audit your dependencies regularly: Review lockfiles and registries for known compromised versions. Tools like Black Duck SCA make this process efficient and scalable. Implement multifactor authentication and access controls: Encourage open source project maintainers to use strong security practices to prevent phishing successes. Generate and share SBOMs: Make SBOMs a standard part of your release process to provide transparency and enable quick vulnerability assessments. Monitor for runtime anomalies: Look for unusual behaviors in logs, such as unexpected network activity or API manipulations. Stay informed and act swiftly: Subscribe to security alerts from sources like npm and integrate threat intelligence into your tools.  Supply chain attacks like this npm incident are a call to action for all of us in the software community. By prioritizing visibility, detection, and remediation, we can turn these challenges into opportunities to build more resilient applications. If you're looking to evaluate how Black Duck can fit into your security strategy, reach out to our team—we're here to help secure your software from the ground up.     "

</details>

> [!NOTE]
> Text extracted from https://www.blackduck.com/blog/recent-npm-software-supply-chain-attack-security-lessons.html

---

### Normal Prompt

This prompt was defined using Natural Language

<details>
  <summary><h3><strong>📑 Normal Prompt </strong> <i>(Click to expand . . .)</i></h3></summary>
<pre>
&#35; ROLE
You are an expert at detecting patterns and extracting information from HTML code related to detect NPM package names and versions. Based on what you read, you have the skills to detect MITRE ID.<br>

&#35; TASK
You read the full article "INPUT" and MUST validate if the article is written about NPM, mentions at least 2 malicious npm packages, and mentions something regarding "CyberSecurity Malicious Attacks Campaigns to NPM Packages".
&#45; If the article talked about NPM and CyberSecurity Attacks, follow all the INSTRUCTIONS.
&#45; If the article did NOT talk about NPM and CyberSecurity Attacks OR NOT contain npm packages. You need to follow the instructions, but the result MUST BE the output should be in JSON format, only the name of the npm package (empty), version of the npm package (empty), title (empty), date_published in the format (YYYY/MM/DD), mitre_variable (empty), attack_comment (empty), and hash_value (empty).

INSTRUCTIONS:
You need to read the full article and validate/extract some information:
&#45; Generate a cybersecurity title that MUST only contain 3 words. The title should be easy to identify, and try to standardise the title using keywords like: SOCIAL ENGINEERING ATTACK, PHANTOMRAVEN SUPPLY CHAIN, LAZARUS TYPOSQUATTING MALWARE, XSEC MALWARE EXFILTRATION,... The main point of the title is to create a family of Attacks to easy to track. Save the title value in the variable "title".
&#45; You need to extract the main tactics based on MITRE ATT&CK (ID and Title of MITRE ATT&CK). The MITRE ID must be real and exist. You can save the list in one variable like an OBJECT single JSON, as part of the variable is "mitre_variable". In case you can not find any related "MITRE-ID", create the variable "mitre_variable" in JSON format, empty.
&#45; You MUST create a description (Using fewer than 70 words) that can help you identify the main cybersecurity tactics / malicious attack effects (Example: CWE-123, CVE-2024-1234, IP: 8.12.15.24, Country: North Korean, Operative System: Linux, Attack: typosquatting, Dependency confusion, Dependency Hijacking, ...), and save the value in the variable "attack_comment".
&#45; You MUST create a random hash, the hash must be a unique identifier, and save the value in "hash_value".
&#45; You MUST extract the date when the article was published in the format YYYY/MM/DD save the value in the variable "date_published"
&#45; You MUST extract and detect ALL NPM packages written in the article based on the following patterns:

Patterns of the name format:
&#45; @package/name@version
&#45; @package/name
&#45; name version
&#45; name@version
&#45; name@version, name@version, name@version
&#45; name (version)
&#45; name version, version, version
&#45; name: version, version

Pattern of the version format:
&#45; 2.0.15
&#45; 10.15.350
&#45; 15.150.1

Completed pattern example: @package/name - version such as: debug - 1.0.15, chalk - 20.4.103
In case you find a similar result: debug - 100.1 million, chalk - compromised, then you need to write debug - , chalk - .

You need to find the information of the npm package and the version affected.
The pattern could be inside of a table or in the HTML code.

When the data is inside of the table, you can find tables similar to the following example:

| PACKAGE | COMPROMISED VERSION(s) |
| @art-ws/common | 2.0.22, 2.0.28 |

In this example, you need to extract the npm package name and version. Example of the case, name: @art-ws/common, version: 2.0.22, name:@art-ws/common, version: 2.0.28

There exist some conditions to extract the name of the package.
&#45; The npm package name always could contain a version.
&#45; In case you can not find the version, you need to write name: NPM Package, version: ""
All the information extracted should be in the variable "packages".

&#35; OUTPUT
The output should be in JSON format, only the name of the npm package, version of the npm package, title (Title MUST BE in UPPERCASE and NOT use plural words), date_published (Format YYYY/MM/DD), mitre_variable (The format MUST BE in JSON & ARRAY like this "ID": "MITRE-ID", "Text": "Mitre Title"), attack_comment, and hash_value (The format must like SHA1).
You don't need to add a description or comments. 

In case you can not identify nothing about the npm package, print an empty response.
</pre>
</details>

---

### Domain-Specific Language DSL/JSON Prompt

Based on Normal Prompt (Natural Language) this prompt was converted or moved to DLS/JSON Format.

<details>
  <summary><h3><strong>📑 DSL/JSON </strong> <i>(Click to expand . . .)</i></h3></summary>
<pre>
{
  "prompt_configuration": {
    "role": "Expert at detecting patterns and extracting information from HTML code to identify NPM package names, versions, and MITRE IDs.",
    "context": "Analysis of articles regarding CyberSecurity Malicious Attacks Campaigns to NPM Packages.",
    "input_variable": "{{$INPUT}}"
  },
  "validation_logic": {
    "conditions": [
      "Article is written about NPM",
      "Mentions at least 2 malicious npm packages",
      "Mentions 'CyberSecurity Malicious Attacks Campaigns to NPM Packages'"
    ],
    "fallback_action": {
      "condition": "If validation fails (not about NPM/Attacks or no packages found)",
      "required_output": {
        "npm_package": "",
        "version": "",
        "title": "",
        "date_published": "YYYY/MM/DD",
        "mitre_variable": [],
        "attack_comment": "",
        "hash_value": ""
      }
    }
  },
  "instructions": {
    "title_generation": {
      "variable": "title",
      "constraints": [
        "Must contain exactly 3 words",
        "Uppercase only",
        "No plural words",
        "Standardized keywords: SOCIAL ENGINEERING ATTACK, PHANTOMRAVEN SUPPLY CHAIN, LAZARUS TYPOSQUATTING MALWARE, XSEC MALWARE EXFILTRATION"
      ]
    },
    "mitre_extraction": {
      "variable": "mitre_variable",
      "format": "JSON Array of Objects: {'ID': 'MITRE-ID', 'Text': 'Mitre Title'}",
      "requirement": "Must be real and existing MITRE ATT&CK IDs. If not found, return empty array."
    },
    "attack_description": {
      "variable": "attack_comment",
      "constraints": [
        "Fewer than 70 words",
        "Include tactics/effects (e.g., CWE, CVE, IPs, Country, OS, Attack type)"
      ]
    },
    "identifier_generation": {
      "variable": "hash_value",
      "format": "SHA1",
      "requirement": "Must be a unique random hash."
    },
    "date_extraction": {
      "variable": "date_published",
      "format": "YYYY/MM/DD"
    },
    "npm_extraction": {
      "variable": "packages",
      "patterns_name": [
        "@package/name@version",
        "@package/name",
        "name version",
        "name@version",
        "name (version)",
        "name: version, version"
      ],
      "patterns_version": [
        "X.X.X",
        "XX.XX.XXX"
      ],
      "extraction_rules": [
        "Extract from text or HTML tables",
        "If multiple versions exist for one package (e.g., 2.0.22, 2.0.28), create separate entries for each",
        "If version is invalid (e.g., '100.1 million' or 'compromised'), leave version empty",
        "If no version found, set version to ''"
      ]
    }
  },
  "output_format": {
    "type": "JSON",
    "structure": {
      "npm_package": "string",
      "version": "string",
      "title": "string (UPPERCASE)",
      "date_published": "string (YYYY/MM/DD)",
      "mitre_variable": "array",
      "attack_comment": "string",
      "hash_value": "string (SHA1)"
    },
    "final_notes": "No description or comments. If no npm package is identified, print an empty response."
  }
}

</pre>
</details>

---

### Symbolic Prompt (Complex)

Based on Normal Prompt (Natural Language) this prompt was converted or moved to Symbolic Format.

<details>
  <summary><h3><strong>📑 Symbolic Prompt - Complex </strong> <i>(Click to expand . . .)</i></h3></summary>
<pre>
[SYSTEM]
[ROLE] ::=> HTML_Pattern_Detector+Cyber_Security_Analyst
[CONTEXT] ::=> HTML_Code+NPM_Packages+MITRE_ID
$RAW_LOG := """THE_INPUT"""
[LOGIC] ::=
	IF NPM_Package_Syntax($RAW_LOG) == true THEN:
		_npm_pkg_detected ::= true
	ELSE:
		_npm_pkg_detected ::= false
	ENDIF
[TASK] ::=
	IF _npm_pkg_detected == true THEN:
		_npm_list := Extract_NPM_Package($RAW_LOG)
		IF Contain_Version(_npm_list) THEN:
			_output_format := Output_Format_JSON(_npm_list, "PkgName:Package_Name" + "Version:Package_Version")
		ELSE:
			_output_format := Output_Format_JSON(_npm_list, "PkgName:Package_Name" + "Version:")
[F_CREATE_TITLE] {
	_title_new := Create_Title_Based($RAW_LOG)+RESTRICT(3_words) <- UPPER_CASE
}
[F_MITRE_ID] {
	_mitre_id_detected := Extract_Tacticts(Read_Article($RAW_LOG))+MITRE_ATT&CK_ID <- JSON_Format{"ID":"Mitre_ID","Title":"Mitre_Title"}
}
[F_TITLE_DESC] {
	_title_description := Generate_Description(Identify_Values($RAW_LOG) <- Cyber_Security_Assets[IP_ADDRESS,CWE,CVE,Country])-MAXIMUM_70_WORDS
}
[FLOW] ::= 
	CALL [LOGIC] WITH $RAW_LOG -> _npm_pkg_detected
	CALL [TASK] WITH {$RAW_LOG, _npm_pkg_detected} -> [OUTPUT]
	CALL [F_CREATE_TITLE] WITH $RAW_LOG -> [OUTPUT] 
	CALL [F_MITRE_ID] WITH $RAW_LOG -> [OUTPUT]
	CALL [F_TITLE_DESC] WITH $RAW_LOG -> [OUTPUT]
[CONSTRAINTS] ::=
- UPPER_CASE_FORMAT(_title_new)
- NO_ADD_COMMENTS_OR_PROSE
- RAW_JSON_FORMAT([OUTPUT],_mitre_id_detected)
- NO_MARKDOWN([OUTPUT],_mitre_id_detected)
- STRICT_NPM_VALIDATOR
[OUTPUT] ::= {"Title": _title_new, "Package_List": _output_format, "MITRE": _mitre_id_detected, "Description": _title_description}
</pre>
</details>

> [!NOTE]
> The next prompt was validate the Models TTR.

---

## References
1. n8n Documentation – https://docs.n8n.io
2. NocoDB Documentation – https://docs.nocodb.com
3. Anthropic API Reference – https://docs.anthropic.com
4. OpenAI API Reference – https://platform.openai.com/docs
5. Google AI Studio – https://ai.google.dev
6. DeepSeek API – https://platform.deepseek.com

---

## 📁 Resources

- 📊 **[Benchmark Methodology](../Benchmark/benchmark_methodology.md)** - Multi-date testing protocol, IQR Deception detection, temporal analysis framework 
- 📊 **[Benchmark Overview & Compatibility](../Benchmark/symbolic_support_test.md)** - Cross-model summary dashboard & compatibility test results for various models 
- 📝 **[Claude Report](../Benchmark/benchmark_model_claude.md)** - Deep-dive analysis for claude-3-haiku 
- 📝 **[DeepSeek Report](../Benchmark/benchmark_model_deepseek.md)** - Deep-dive analysis for deepseek-v3 
- 📝 **[Gemini Report](../Benchmark/benchmark_model_gemini.md)** - Deep-dive analysis for gemini-2.0-flash 
- 📝 **[Llama Report](../Benchmark/benchmark_model_llama.md)** - Deep-dive analysis for llama-3.3-70b 
- 📝 **[OpenAI Report](../Benchmark/benchmark_model_openai.md)** - Deep-dive analysis for gpt-4o-mini 
- ❓ **[Benchmark FAQ](../Benchmark/benchmark_fqa.md)** - Answers to community questions about our findings and methodology 
- 📥 **[Raw Data (CSV) Mar 3](../Benchmark/benchmark_20260303.csv)** - Complete dataset from March 3, 2026 
- 📥 **[Raw Data (CSV) Mar 5](../Benchmark/benchmark_20260305.csv)** - Complete dataset from March 5, 2026 
- 📝 **[Benchmark Consolidate Equations](Benchmark/benchmark_2026030X_consolidate_equations.xlsx)** - Complete dataset with Excel Formulas 
- 🔧 **[Reproduce Test](../Benchmark/benchmark_reproduce_test.md)** - How to  Reproduce the tests yourself 
- 🔧 **[n8n Workflow](../Benchmark/n8n_benchmark.json)** - Reproduce the tests yourself in N8N

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
- Jesus Huerta aka <em><a href="https://github.com/mindhack03d" rel="nofollow">(@\_mindhack03d_)</a></em></br>

## Contributors
- Alex Hernandez aka <em><a href="https://twitter.com/_alt3kx_" rel="nofollow">(@\_alt3kx\_)</a></em></br>

[⬅️ Back to Home](../README.md) | [Methodology used](../Benchmark/benchmark_methodology.md)