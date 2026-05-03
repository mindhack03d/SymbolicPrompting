# 🐍 Symbolic Prompting Framework: Service Signature Normalization to CPE

## Converting raw scan data (OpenSSH, PostgreSQL, Nginx) into standardized CPE 2.3 format

This example leverages the **Symbolic Prompting Framework (SPF)** to ingest raw database service signatures and normalize them into structured, actionable intelligence. By applying neural-symbolic logic, we bridge the gap between messy scan data and rigid security standards.

> [!IMPORTANT]
> Core Concept: Extract specific identifiers from strings like PostgreSQL 9.6.0+ and convert them into a JSON format compatible with CPE (Common Platform Enumeration) standards for automated vulnerability mapping.

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

## 🛠️ Core Concept: Automated CPE Mapping
The objective is to identify raw service strings—such as **PostgreSQL 9.6.0+**—and execute a logic-driven transformation. Using **Latent Space Mapping**, the framework resolves the service identity against known **Common Platform Enumeration (CPE)** patterns, producing a standardized JSON output optimized for automated vulnerability lookups.

### 🧩 Logic Workflow
- **Service Recognition**: The framework initiates `SERVICE_NAME_RECOGNIZE_CPE` to validate the input against the NVD database.
- **Fuzzy Matching**: If the service name is ambiguous, it triggers a `FUZZY_MATCH_THRESHOLD` of **0.85** to find the closest official CPE product name.
- **Neural Inference**: Employs `HYBRID_NEURAL_SYMBOLIC` reasoning to handle versioning syntax (like the `+` wildcard) that traditional regex might miss.
- **Strict Serialization**: Outputs a finalized URI in **CPE 2.3** format, ensuring 1:1 compatibility with modern cybersecurity scanners.

---

## 📜 The Symbolic Prompt
Run Ollama model.
```text
ollama run goekdenizguelmez/JOSIEFIED-Qwen3:4b
```

Copy the block below into your LLM (Optimized for JOSIEFIED-Qwen3):
```text
[ROLE] ::=> CYBERSECURITY_ANALYST+DATABASE_EXPERT-POSTGRESQL_ANALYST
[CONTEXT] ::= {COMMON_PLATFORM_ENUMERATION, NATIONAL_VULNERABILITY_DATABASE}
[HYBRID_NEURAL_SYMBOLIC] ::=> ENABLE
[NEURAL_INFERENCE] ::=> ENABLE
[LATENT_SPACE_MAPPING] ::=> ACTIVE
[FUZZY_MATCH_THRESHOLD] ::=> 0.85
[INPUT:SERVICE] ::= "postgresql"
[INPUT:VERSION] ::= "9.6.0+"
[LOGIC] ::=
  IF SERVICE_NAME_RECOGNIZE_CPE([INPUT:SERVICE]) == FALSE THEN
    _raw_match := FIND_MOST_SIMILAR_CPE_NAME([INPUT:SERVICE])
    _service_name := FORMAT_TO_CPE_URI(_raw_match, [INPUT:VERSION]).product
  ELSE
    _service_name := [INPUT:SERVICE]
  ENDIF
  RETURN(_service_name)
[CONSTRAINTS] ::= {STRICT_CPE_23_FORMAT, NO_ADD_COMMENTS, NO_ADD_PROSE}
[OUTPUT] :=  {"service": _service_name, "version": [INPUT:VERSION]}
```

Expected Output:
```json
[
  {
    "output": {
      "service": "postgresql",
      "version": "9.6.0+"
    }
  }
]
```

---

## 🛠️ Logic Breakdown (The SPF Engineering)
To understand how the **Symbolic Prompting Framework** operates, we must look at the intersection of deterministic programming and probabilistic neural inference. Unlike standard natural language prompts, SPF treats the LLM as a logical processor.

### 1. The Decision Matrix ([LOGIC])
The core of this operation is a conditional loop that ensures data integrity even when the input is malformed:
- **Recognition Layer**: The function `SERVICE_NAME_RECOGNIZE_CPE` acts as a gatekeeper. It checks if the input `"postgresql"` exists within the known `COMMON_PLATFORM_ENUMERATION` namespace.
- **The Contingency (Fuzzy Logic)**: If recognition fails, the system doesn't hallucinate. It triggers `FIND_MOST_SIMILAR_CPE_NAME` with a **Fuzzy Match Threshold of 0.85**. This ensures that `"Postgres"` or `"PGSQL"` is correctly mapped to the official "postgresql" product name.
- **Formatting Layer**: Once the product is identified, `FORMAT_TO_CPE_URI` constructs the formal string, preserving the `[INPUT:VERSION]` variable.

### 2. Hybrid Neural-Symbolic Execution
This section defines how the AI thinks:
- `NEURAL_INFERENCE`: Allows the model to understand context and intent (e.g., recognizing that `"9.6.0+"` implies a version range).
- `LATENT_SPACE_MAPPING`: Maps the user's high-level text input into a specific coordinate in the model's knowledge base that corresponds to cybersecurity standards.
- **Constraint Enforcement**: The `STRICT_CPE_23_FORMAT` constraint acts as a hard filter, stripping away any "conversational" AI filler and ensuring the output is ready for a production database.

### 3. Engineering Constraints

|Component |Function |Purpose |
|:--- |:--- |:--- |
|FUZZY_MATCH_THRESHOLD |0.85 |Balances flexibility with accuracy to prevent false positives. |
|CPE_23_FORMAT |Standardized URI |"Ensures interoperability with tools like Clair, Trivy, or Snyk." |
|NO_ADD_PROSE |Clean Output |"Eliminates ""Here is your result"" text, making the prompt safe for API integration."|

> [!NOTE]
> **SPF Insight**: By defining the **Role** as a `CYBERSECURITY_ANALYST+DATABASE_EXPERT`, we prime the model's weights to prioritize technical precision over creative variety, effectively turning a generative model into a specialized ETL (Extract, Transform, Load) tool.
---

## 🧠 The Engineering Advantage
By shifting from traditional "chat-based" instructions to the **Symbolic Prompting Framework (SPF)**, we move from unpredictable natural language to **deterministic prompt engineering**. This approach offers three critical advantages for technical deployments.

### 1. Deterministic Reliability (Low Variance)
Traditional prompts often suffer from "temperature drift," where the same input yields different formatting results. SPF uses **Symbolic Logic Constraints** to force the model into a state of high consistency.
- **Predictable I/O**: By defining logic gates (`IF/THEN`), the model functions as a predictable state machine.
- **Production-Ready**: This reliability allows SPF to be integrated directly into CI/CD pipelines where a single misplaced comma in a JSON string could break a build.

### 2. Latent Space Precision
SPF utilizes `LATENT_SPACE_MAPPING` to narrow the model's focus. Instead of searching its entire training set, the framework pins the model to specific high-dimensional vectors related to **CPE** and **NVD** standards.
- **Reduced Hallucination**: By setting a `FUZZY_MATCH_THRESHOLD` of **0.85**, we programmatically forbid the model from "guessing" a service name that doesn't meet a specific statistical confidence level.

### 3. Token Efficiency & Throughput
Because SPF uses dense, symbolic notation (e.g., `::=>` and `::=`), it communicates complex instructions using fewer tokens than long-form English prose.
- **Context Window Optimization**: You can fit more complex business logic into the same context window.
- **Lower Latency**: Shorter instructions and a "No Prose" constraint mean the model reaches the "Stop Token" faster, reducing API costs and improving response times for real-time security scanning.

### Comparison: Standard vs. Symbolic

|Feature |Standard Prompting |Symbolic Prompting (SPF) |
|:-- |:-- |:-- |
|Instruction Style |Descriptive / Conversational |Declarative / Mathematical |
|Logic Handling |Implicit (Model guesses) |Explicit (Defined via [LOGIC]) |
|Output Stability |"Variable (Prone to ""Chatter"")" |Fixed (Strict JSON/URI) |
|Integration |Manual Review Required |API / Automation Ready |

> [!NOTE]
> **Engineering Note**: SPF effectively treats the LLM as a **Hybrid Neural-Symbolic Processor**. We aren't just asking it to "be an expert"; we are defining the specific logical architecture the expert must use to process the data.
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