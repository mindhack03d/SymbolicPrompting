# Symbolic Prompting - Roles

<div align="center">

[![Status](https://img.shields.io/badge/Status-Active_Course-success?style=plastic)](https://github.com/mindhack03d/SymbolicPrompting)
[![GitHub Stars](https://img.shields.io/github/stars/mindhack03d/SymbolicPrompting?style=plastic&logo=github&color=gold&cacheBus=1)](https://github.com/mindhack03d/SymbolicPrompting)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Course_Complete-success?style=plastic&logo=youtube)](https://youtube.com/playlist?list=PLNFL-2KY9QZVqoRwRzVLPN6qmDftpsjg6)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Reels_EN-success?style=plastic&logo=youtube)](https://www.youtube.com/playlist?list=PLNFL-2KY9QZXhGEfGUOrrZtzGdPESwh4l)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Reels_ES-success?style=plastic&logo=youtube)](https://youtube.com/playlist?list=PLNFL-2KY9QZUKlXC_4gnVUHoAJdd4s-AC&si=4N7ROWCD3G46y8t5l)<br>
[![License-MIT](https://img.shields.io/badge/License-MIT-green?style=plastic)](https://opensource.org/licenses/MIT)
[![Methodology-V2](https://img.shields.io/badge/Methodology-V2.0-blue?style=plastic)](../Benchmark/benchmark_methodology.md)
[![Benchmark](https://img.shields.io/badge/📊-Benchmark_Data-2a2a2a?style=plastic)](../Benchmark/symbolic_support_test.md)


**[ 🌎 English ]** | **[ 🇲🇽 Español Latino ]**

</div>

[🏠 Home](../README.md)

In Symbolic Prompting, the distinction between a natural language label (Literature Professor) and a symbolic/underscored label (Literature_Professor) usually centers on how the Large Language Model (LLM) weights the instruction and avoids "semantic drift."

While they might look similar, they trigger different behaviors in the model's latent space:


| Role Specification | Technical Nature | Effect on the LLM | 
| :--- | :--- | :--- |
| ```Literature Professor``` | **Natural Language.** descriptive prose. | The model draws broadly from its training data on what a professor "sounds like." It is more likely to be conversational and "flowery." |
| ```Literature_Professor``` | **Token/Variable Syntax.** Mimics scholarly conventions. | In symbolic prompting, the underscore tells the model to treat the two words as a single, unified concept or "Class." This creates a stronger "anchor" in the model's attention mechanism. |

**Literature Professor:** 
- **Tokenization:** The words "Literature" and "Professor" are often treated as distinct tokens. The model processes them as a sequence, which can sometimes lead to the model "forgetting" the persona if the conversation becomes long or complex.
- Bias toward "Helpful Assistant": Because it’s natural language, the model’s default safety and alignment filters (the "As an AI language model..." persona) can more easily override the requested role.

**Literature_Professor:** 
- **Reduced Drift:** By "coding" the persona as Literature_Professor, you are signaling that this is a system-level constraint rather than just a suggestion. It helps the model maintain the specific constraints of that persona (e.g., specific vocabulary, analytical tone) without reverting to generic AI speech.
- **Logical Execution:** If your prompt uses symbolic logic (e.g., IF user_query == analysis THEN Literature_Professor.execute()), the underscored version acts as a pointer to a specific set of behaviors you've defined elsewhere in the prompt.

***

## **You are... VERSUS Act as...**

We are exploring the **hierarchy of instructions**. In Large Language Models (LLMs), the order of the factors **does** change the product (the output). This happens because the model processes information sequentially and assigns different weights to what is defined as **'Personality'** (You are) versus what is defined as **'Action'** (Act as).

### The "You are" vs. "Act as" Power Dynamic
- **"You are ..."** is an **Identity Anchor**. It is harder for the model to "forget" this instruction during a long conversation. It defines the model's fundamental bias. 
- **"Act as ..."** is a **Behavioral Mode**. It is more dynamic and focuses on the *output format* and *style*. 

### **You are... VS Act as... — How to Use?**

1.  **For Depth and Consistency, use "You are..."** when you want the AI to fully inhabit a persona, maintain a specific tone, or apply a specialized lens throughout an extended conversation. It's the stronger command for **immersion**.
2.  **For Focus and Flexibility, use "Act as..."** when you need expert-level output for a discrete task without the overhead of a permanent persona. It's often cleaner for **task-specific simulations**.

### Pro-Tip: Hybrid Approach
The most effective prompts often combine both, or use even more explicit framing:

```You are an expert Python programmer with 20 years of experience. Your communication is clear, concise, and practical. For this entire session, act as my personal coding mentor. First, review this block of code and explain any inefficiencies you see...```

This structure:
1.  **Declares the identity** ("```You are an expert...```").
2.  **Sets the persistent behavior** ("```Your communication is...```").
3.  **Defines the temporary role/task** ("```act as my personal coding mentor```").
4.  **Gives the immediate instruction** ("```review this block...```").

If you are following the **Symbolic Prompting** syntax you prefer (using tags like ```[ROLE]```), you are essentially creating a container. In that context:

- **Use ```[ROLE] ::=> You are...```** when the goal is **Precision**. You want the model to adopt the strict constraints and knowledge base of a professional.
- **Use ```[ROLE] ::=> Act as...```** when the goal is **Empathy or Perspective**. You want to simulate a specific human interaction, tone, or emotional response.

### Core Distinction

<table>
<colgroup>
<col style="width: 19%" />
<col style="width: 41%" />
<col style="width: 39%" />
</colgroup>
<thead>
<tr>
<th>FEATURE / ASPECT</th>
<th>“You are …” (Identity / State)</th>
<th>“Act as …” (Performance / Roleplay)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Framing</td>
<td>Sets a fixed <strong>Identity</strong>. It tells the model what
it <em>is</em>.</td>
<td>Sets a <strong>Behavioral Mode</strong>. It tells the model how
to <em>behave</em>.</td>
</tr>
<tr>
<td>Internal Logic</td>
<td>Encourages the model to adopt the <strong>foundational
logic</strong> and constraints of the persona.</td>
<td>Encourages the model to adopt the <strong>external
traits</strong> and "vibes" of the persona.</td>
</tr>
<tr>
<td>Output Style</td>
<td>Often results in more direct, authoritative, and "default" expert
responses.</td>
<td>Often results in more "theatrical" or stylized responses (sometimes
including roleplay markers like *smiles*).</td>
</tr>
<tr>
<td>Best Use Case</td>
<td><ul>
<li><p>When you need the model to apply a specific professional
framework (e.g., "You are a Senior Python Architect").</p></li>
<li><p><strong>Long-form interactions, storytelling, consistent persona
maintenance.</strong> E.g., "You are a friendly, patient tutor for
beginners."</p></li>
</ul></td>
<td><ul>
<li><p>When you need a specific communication style or simulation (e.g.,
"Act as a customer who is frustrated with a product").</p></li>
<li><p><strong>Specific, bounded tasks, expert consultations, creative
simulations.</strong> E.g., "Act as a software architect reviewing this
code."</p></li>
</ul></td>
</tr>
<tr>
<td>Role strength</td>
<td>Strong</td>
<td>Moderate</td>
</tr>
<tr>
<td>Identity binding</td>
<td>High</td>
<td>Low–Medium</td>
</tr>
<tr>
<td>Behavioral focus</td>
<td>Secondary</td>
<td>Primary</td>
</tr>
<tr>
<td>Long-term consistency</td>
<td>High</td>
<td>Medium</td>
</tr>
<tr>
<td>Creativity</td>
<td>Lower</td>
<td>Higher</td>
</tr>
<tr>
<td>Expert reasoning</td>
<td>Stronger</td>
<td>Weaker unless specified</td>
</tr>
<tr>
<td>Core Semantics</td>
<td><strong>State of Being.</strong> It assigns an identity. The AI
internalizes the role as its new default self for the session.</td>
<td><strong>Performance of a Role.</strong> It instructs the AI to
simulate a character or expert for a specific purpose.</td>
</tr>
<tr>
<td>Psychological Frame</td>
<td>More immersive and absolute. "This is now <em>who you are</em>."
Often leads to more consistent in-character behavior.</td>
<td>More transactional and task-oriented. "Perform this function for me
now." Can feel more like a temporary collaboration.</td>
</tr>
<tr>
<td>Potential Pitfall</td>
<td>Can be too rigid. The AI might over-identify and have difficulty
stepping out of the role even when you need a straightforward
answer.</td>
<td>The AI might "break character" more easily after the immediate task
is done, or treat the role more superficially.</td>
</tr>
</tbody>
</table>

***

## Symbol Legend
- **The Hyphen (-) as a "Bridge":** It creates a directional link. In ```Lecture-Discussion```, the model assumes that the ```Lecture``` is the *method* and ```Discussion``` is the *target*. It limits the "creativity" of the model to keep it within professional boundaries.
- **The Plus (+) as a "Synthesizer":** It forces the model to perform a **High-Dimensional Fusion**. It tells the Transformer: "Do not choose between being Neural or being an Architecture; calculate the intersection of both simultaneously."
- **The Underscore (\_) as a "Unit":** The model treats that entire string as a single **Atomic Symbol**.

| SYMBOL | MEANING IN ROLE DEFINITION | PRIORITY | EXAMPLE |
|---------|--------------------------|----------|---------------------------|
| ```+``` | Addition/Combination (AND) | Medium | ```Lecture+Discussion = Lecture AND Discussion``` |
| ```-``` | Application/Specialization (FOR/IN) | High | ```Assessment-Writing = Assessment FOR Writing``` |
| ```_``` | Word joining within concept | Low | ```Thesis_Statement = "Thesis Statement"``` |
| ```->``` | Transformation/Output | Highest | ```Question->Answer = Question leads to Answer``` |
| ```/``` | Alternative/Or | Medium | ```Quiz/Exam = Quiz OR Exam``` |

### When and How to use...

<table> <colgroup> <col style="width: 11%" /> <col style="width: 21%" /> <col style="width: 28%" /> <col style="width: 38%" /> </colgroup> <thead> <tr> <th>SYMBOL</th> <th>DEFINITION</th> <th>HOW &amp; WHEN TO USE</th> <th>EDUCATIONAL EXAMPLE</th> </tr> </thead> <tbody> <tr> <td><code>[]</code></td> <td><strong>Attributes / Metadata</strong></td> <td>Use to define global parameters or system constraints for the learning session.</td> <td><code>[SCOPE] Undergraduate_Literature_Course<br /> [ROLE] ::=&gt; Act as Writing_Tutor<br /> [STATUS] Grading_in_Progress<br /> [RESTRICTION] Provide_Feedback_Only_No_Grade</code></td> </tr> <tr> <td><code>{}</code></td> <td><strong>Variables / Objects</strong></td> <td>Use for dynamic student data that needs to be processed.</td> <td><code>{STUDENT_NAME}: "Alex Johnson"<br /> {Assignment_Type: Essay, Due_Date: "2024-11-15", Status: Submitted}<br /> {THESIS_STATEMENT}: "Climate change requires immediate global action"<br /> {ERROR_LIST}: ["run-on sentence", "missing citation", "weak conclusion"]</code></td> </tr> <tr> <td><code>()</code></td> <td><strong>Parameters / Nuance</strong></td> <td>Use to provide specific "how-to" modifiers for an educational task.</td> <td><code>Evaluate essay (Focus: Thesis_Clarity)<br /> (METHOD) Use the Socratic method<br /> (TOOL) Reference MLA_9th_Handbook<br /> Provide feedback (Depth: Detailed, Tone: Encouraging)</code></td> </tr> <tr> <td><code>&lt;&gt;</code></td> <td><strong>Tags / Encapsulation</strong></td> <td>Use to wrap specific blocks of student work or instructions to isolate them.</td> <td><code>&lt;STUDENT_ESSAY&gt; The quick brown fox jumps over the lazy dog. &lt;/STUDENT_ESSAY&gt;</p> <p>&lt;GRADING_RUBRIC&gt;<br />   Check_Thesis(x) -&gt; Score_Thesis(x)<br />   Score_Thesis(x) &gt; 3? Output &lt;- "Pass"<br /> &lt;/GRADING_RUBRIC&gt;</code></td> </tr> <tr> <td><code>#</code></td> <td><strong>Primary Priority (H1)</strong></td> <td>Use for the main teaching role or core educational mission.</td> <td><code># ROLE: Senior_Writing_Instructor</code></td> </tr> <tr> <td><code>##</code></td> <td><strong>Secondary Priority (H2)</strong></td> <td>Use for major sections of a lesson plan or evaluation.</td> <td><code>## SECTION: Thesis_Evaluation</code></td> </tr> <tr> <td><code>###</code></td> <td><strong>Tertiary Priority (H3)</strong></td> <td>Use for specific substeps or detailed grading criteria.</td> <td><code>### SUBSTEP: Check_Citation_Format</code></td> </tr> <tr> <td><code>$</code></td> <td><strong>System Constant</strong></td> <td>Use to define an educational rule that the AI cannot break.</td> <td><code>$POLICY: "No_Plagiarism_Tolerance"<br /> $input_value : String<br /> $STANDARD: MLA_9th_Edition<br /> $OUTPUT_FORMAT: Detailed_Feedback_Only</code></td> </tr> </tbody> </table>

### Role definition

| OPERATOR | FUNCTION | AL INTERPRETATION |
|--------------|----------------|-------------------------------------------|
| ```[ROLE] Teacher``` | **Simple Label** | A soft thematic suggestion. The AI treats it as a general topic rather than a strict teaching persona. |
| ```[ROLE] : Teacher``` | **Attribute Definition** | Establishes a property. The model recognizes ```[ROLE]``` as having the qualities of a teacher. |
| ```[ROLE] :: Teacher``` | **Namespace Scoping** | **Strict Domain Isolation.** The AI filters its knowledge to only use the "Education" domain, ignoring unrelated data. |
| ```[ROLE] -> Teacher``` | **Directional Flow** | Processes input through the lens of a teacher. Ideal for transforming student questions into learning opportunities. |
| ```[ROLE] => Teacher``` | **Logical Implication** | **Conditional Necessity.** "If the system runs, then the output must be at a teacher's level." Stronger than a simple arrow. |
| ```[ROLE] :-> Teacher``` | **Functional Assignment** | Defines the role and triggers an immediate action or instructional workflow. |
| ```[ROLE] ::-> Teacher``` | **Scoped Projection** | Projects deep pedagogical knowledge (```from ::```) into an active teaching process. |
| ```[ROLE] :=> Teacher``` | **Strict Constraint** | **Immutable Binding.** Prevents the AI from slipping out of teaching character during long tutoring sessions. |
| ```[ROLE] ::=> Teacher``` | **Domain Axiom** | **The Gold Standard.** Treats the principles of effective pedagogy as absolute truths for the duration of the prompt. |
| ```[ROLE] = Teacher``` | **Direct Assignment** | A standard variable assignment. Equivalent to "Let Role equal Teacher." Reliable but lacks hierarchy. |
| ```[ROLE] := Teacher``` | **Dynamic Assignment** |In programming, this means "set and initialize." For an AI, it means "reset current state and become this teacher now." |
| ```[ROLE] ::= Teacher``` | **Formal Grammar (BNF)** | Defines the role as a **canonical rule**. The AI interprets this as a definition of its core educational identity structure. |

---

## The Underscore (\_) Placement

- When the underscore is in the **Primary position** (the first part of the prompt), the model prioritizes **Efficiency**. It treats your prompt like a function call.
- When the underscore is in the **Secondary position**, the model uses it to **Verify** its natural language response. It checks: *"Does my professional advice match the technical documentation?"*

***

## Quick Decision Guide

| IF YOU WANT TO EXPRESS… | USE THIS FORMAT | EXAMPLE |
|---------------------------|--------------------|-------------------------|
| Integrated curriculum or course framework | ```A-B-C-D``` | ```Thesis-Evidence-Conclusion-Works_Cited``` |
| Adding teaching approaches to established subject | ```X+Y-Z``` | ```Socratic+Inquiry-Mathematics``` |
| Combination of equal educational domains | ```A+B+C``` | ```Lecture+Discussion+Workshop``` |
| Specialization within an academic area | ```Specialty-Domain``` | ```Creative_Writing-Literature``` |
| Fusion of pedagogical concepts into new approach | ```FusionConcept-Application``` | ```ProjectBasedLearning-Science_Education``` |

---

## Summary of Key Distinctions:
- **Sequence vs. Fusion:** Arrows (```->```) imply a sequence or dependency, while plus/hyphen (```+, -```) imply combination or fusion.
- **Driver:** Parentheses (``` ```) often highlight the **driver** or primary domain (e.g., ```(OpsSec) means the role starts with the security problem```).
- **Direction of Creation:** The arrow direction matters. ```X -> Y``` means ```X``` creates ```Y```. ```Y <- X``` means ```Y``` is created by ```X```.
- **Abstraction Level:** ```::=>``` suggests a higher-level **transformation or remapping**, not just application or integration.

## Order of the Role

In **Symbolic Prompting**, the order of tokens in a hyphenated role creates a **Linear Attention Gradient**. The LLM processes the sequence from left to right, assigning the first term as the **Core Identity (Primary Heuristic)** and subsequent terms as **Modifiers or Tools (Secondary Constraints)**.

Changing the order shifts the "perspective" of the expert, even if the words remain the same.

**In Symbolic Prompting, the first token defines the “center of gravity” of the role.**  
Subsequent tokens **modify**, **specialize**, or **support** that center.

**Position matters** in symbolic role definitions:
1.  **First position** = Primary identity/driver \| Creativity and adaptive reasoning \|  Base Model \| The Anchor
2.  **Middle position** = Core methodology/approach \| Operation authority \|  Operating System \| The filter
3.  **Last position** = Application context/enhancement \| Structure and explainability \|  Output Filter  \| The surface

### Detailed Analysis Table

<table style="width:100%;"> <colgroup> <col style="width: 28%" /> <col style="width: 16%" /> <col style="width: 17%" /> <col style="width: 19%" /> <col style="width: 18%" /> </colgroup> <thead> <tr> <th>ASPECT</th> <th>FIRST POSITION</th> <th>MIDDLE POSITION</th> <th>LAST POSITION</th> <th>OVERALL EMPHASIS</th> </tr> </thead> <tbody> <tr> <td>Inquiry_Based-Constructivist-Science_Education</td> <td><p><strong>Inquiry_Based</strong> </p> <p>(teaching method-driven)</p></td> <td><p><strong>Constructivist</strong> </p> <p>(learning theory)</p></td> <td><p><strong>Science_Education</strong> </p> <p>(subject domain)</p></td> <td>Method → Theory → Domain</td> </tr> <tr> <td>Science_Education-Inquiry_Based-Constructivist</td> <td><p><strong>Science_Education</strong> </p> <p>(subject domain)</p></td> <td><p><strong>Inquiry_Based</strong> </p> <p>(teaching method)</p></td> <td><p><strong>Constructivist</strong> </p> <p>(theoretical foundation)</p></td> <td>Domain → Method → Theory</td> </tr> <tr> <td>Science_Education-Constructivist-Inquiry_Based</td> <td><p><strong>Science_Education</strong> </p> <p>(subject domain)</p></td> <td><p><strong>Constructivist</strong> </p> <p>(theoretical approach)</p></td> <td><p><strong>Inquiry_Based</strong> </p> <p>(practical method)</p></td> <td>Domain → Theory → Practice</td> </tr> <tr> <td>Constructivist-Inquiry_Based-Science_Education</td> <td><p><strong>Constructivist</strong> </p> <p>(core learning theory)</p></td> <td><p><strong>Inquiry_Based</strong> </p> <p>(methodological application)</p></td> <td><p><strong>Science_Education</strong> </p> <p>(use case)</p></td> <td>Theory → Method → Application</td> </tr> <tr> <td>Constructivist-Science_Education-Inquiry_Based</td> <td><p><strong>Constructivist</strong> </p> <p>(core learning theory)</p></td> <td><p><strong>Science_Education</strong> </p> <p>(primary domain)</p></td> <td><p><strong>Inquiry_Based</strong> </p> <p>(secondary feature)</p></td> <td>Theory → Domain → Method</td> </tr> </tbody> </table>

---

<details>
  <summary>⚖️ Legal Disclaimer (Click to expand)</summary>

This repository is for educational purposes only regarding Symbolic Prompting. The author is not responsible for the use that third parties may make of these techniques. The user is responsible for respecting the terms of service of AI platforms and applicable legislation. All content is provided "AS IS," without warranties.<br>
Compatibility may vary depending on model updates, tokenization behavior, and symbol parsing.
</details>

---

⭐ If this class helped you think differently about LLMs, consider starring the repository.

<div align="center">

![](https://img.shields.io/badge/Focus-Prompt_Engineering-blue?style=flat-square)
![](https://img.shields.io/badge/Logic-Symbolic_AI-blueviolet?style=flat-square)
![](https://img.shields.io/badge/Logic-Symbolic_Prompting-blueviolet?style=flat-square)
![](https://img.shields.io/badge/LLM-Deterministic_Outputs-orange?style=flat-square)
![](https://img.shields.io/badge/Architecture-State_Machines-ff69b4?style=flat-square)
![](https://img.shields.io/badge/Content-Educational_Course-success?style=flat-square)<br>

</div>

## Author
- Jesus Huerta aka <em><a href="https://github.com/mindhack03d" rel="nofollow">(@\_mindhack03d_)</a></em></br>


[🏠 Home](../README.md)