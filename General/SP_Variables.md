# Symbolic Prompting - Variables (For Educationl Use Only)

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

There exist different way to define variables as part of Symbolic Prompt.

## Use Atomic, Unambiguous Names

<table style="width:56%;"> <colgroup> <col style="width: 29%" /> <col style="width: 26%" /> </colgroup> <thead> <tr> <th>GOOD</th> <th>BAD</th> </tr> </thead> <tbody> <tr> <td><code>essay_difficulty_level</code><br /> <code>feedback_required</code><br /> <code>student_grade_level</code></td> <td><code>level Thing</code><br /> <code>status</code><br /> <code>grade</code></td> </tr> </tbody> </table>

---

## Apply Consistent Naming Conventions

| CONVENTION       | PURPOSE                | EXAMPLE                |
|------------------|------------------------|------------------------|
| ```snake_case``` | Mutable variables      | ```essay_difficulty_level``` |
| ```UPPER_SNAKE_CASE``` | Constants / ENUM types | ```DIFFICULTY_LEVEL```    |
| ```PascalCase``` | Types / schemas        | ```EssayType```      |
| ```lowercase values``` | Free text (limited)    | ```"literary analysis"```       |
| ```UPPERCASE values``` | ENUM members           | ```BEGINNER, INTERMEDIATE, ADVANCED```         |

### Syntax of Names

<table> <colgroup> <col style="width: 28%" /> <col style="width: 23%" /> <col style="width: 48%" /> </colgroup> <thead> <tr> <th>DEFINITION</th> <th>INTERPRETER</th> <th>EXAMPLE</th> </tr> </thead> <tbody> <tr> <td><code>TYPE_ESSAY =</code></td> <td>Constant / Enum Global / Value not change</td> <td><code>TYPE_ESSAY = NARRATIVE | EXPOSITORY | ARGUMENTATIVE</code></td> </tr> <tr> <td><code>type_essay = </code></td> <td>Variable or Constant / Update value</td> <td><code>type_essay = {narrative, expository, argumentative, descriptive}</code></td> </tr> <tr> <td><code>Type_Essay = {...</code></td> <td>Type or Class</td> <td><code>Type_Essay = Narrative | Expository | Argumentative</code></td> </tr> <tr> <td><code>TypeEssay = {...</code></td> <td>Type or Class</td> <td><code>TypeEssay = {</code><br> <code>category: EssayCategory,</code><br> <code>word_count: Integer,</code><br> <code>required_sections: List<String></code> <code>}</code></td> </tr> <tr> <td><strong>Compact Syntax</strong></td> <td><strong>Not Recommended</strong></td> <td><code>typeessay={lit,pers,exp,desc}</code></td> </tr> </tbody> </table>

---

## Variable Definition Method Comparison

| METHOD | SYNTAX | BEST FOR | EXAMPLE | LLM CLARITY |
|--------------|------------------|-------------|--------------------|---------|
| Explicit Typing | ```variable: Type = value``` | Formal systems, type safety | ```difficulty: DifficultyLevel = Intermediate``` | High |
| Set Membership | ```variable ∈ {values}``` | Discrete choices, enumerations | ```essay_type ∈ {Narrative, Expository, Persuasive}``` | High |
| Mathematical Range | ```variable ∈ [min..max]``` | Numerical ranges, intervals | ```min_pass_score ∈ [70..80]``` | High |
| Assignment | ```variable = value``` | Simple values, constants | ```min_pass_score = 70``` | Medium-High |
| Definition | ```variable := expression``` | Derived values, aliases | ```passing := student_score ≥ min_pass_score``` | Medium |
| Predicate Form | ```is_property(variable)``` | Boolean conditions, flags | ```is_advanced(essay)``` | Medium |
| Structured | ```variable = {field: value}``` | Objects, records, entities | ```essay = {id: "E123", type: Persuasive, score: 85}``` | High |

### Variable Definition Patterns by Use Case 

| USE CASE | RECOMMENDED PATTER | EXAMPLE | WHY IT WORKS |
|--------------|---------------|-------------------------------|-------------|
| Essay Classification | Enumeration with membership | ```difficulty_level ∈ {Beginner, Intermediate, Advanced, Expert}``` | Clear categories, easy validation |
| Lesson Planning | Structured objects | ```lesson_plan = {topic: String, duration: Minutes, objectives: List<String>, materials: List<String>}``` | Captures complex relationships |
| Student Assessment | Derived booleans | ```is_proficient := (score ≥ 80) ∧ (completion_rate ≥ 0.9)``` | Computable conditions |
| Assignment Management | Typed variables with ranges | ```due_date: Date ∈ [today..today+7]``` | Quantitative constraints |
| Curriculum Design | Set operations | ```advanced_topics ⊆ all_topics ∩ (math_topics ∪ science_topics)``` | Mathematical precision |
| Essay Evaluation | Predicate functions | ```has_thesis_statement(essay)``` | Functional approach |


### Symbol Selection for Variable Types

| VARIABLE TYPE | RECOMMENDED SYMBOL | EXAMPLE | ALTERNATIVE |
|-------------|----------------|--------------------------|------------------|
| Enumeration | ```∈ {values}``` | ```essay_type ∈ {Narrative, Expository}``` | ```: EnumType``` |
| Range | ```∈ [min..max]``` | ```grade_level ∈ [1..12]``` | ```: NumberRange``` |
| Boolean | ```: Boolean``` | ```has_conclusion: Boolean``` | ```∈ {true, false}``` |
| String | ```: String``` | ```student_name: String``` | ```= "value"``` |
| Integer | ```: Integer``` | ```page_count: Integer``` | ```∈ ℤ``` |
| Float | ```: Float``` | ```essay_score: Float``` | ```∈ ℝ``` |
| List | ```: List<Type>``` | ```topics: List<String>``` | ```= [value1, value2]``` |
| Set | ```: Set<Type>``` | ```prerequisites: Set<Course>``` | ```⊆ {values}``` |
| Object | ```: ObjectType``` | ```submission: StudentWork``` | ```= {field: value}``` |

---

## Declare Domains

<table> <colgroup> <col style="width: 65%" /> <col style="width: 34%" /> </colgroup> <thead> <tr> <th>GOOD</th> <th>BAD</th> </tr> </thead> <tbody> <tr> <td><code>DIFFICULTY_LEVEL = {BEGINNER, INTERMEDIATE, ADVANCED, EXPERT}</code><br /> <code>essay_difficulty in DIFFICULTY_LEVEL</code></td> <td><code>d = {b, i, a, e}</code></br> <code>essay_difficulty = advanced</code></td> </tr> </tbody> </table>

---

## Prefer Closed Sets (ENUM) Over free Text

| GOOD | BAD |
|---------------------------------------------|---------------------------|
| ```feedback_type in {GRAMMAR, STRUCTURE, CONTENT, CITATIONS}``` | ```feedback_type = "whatever the essay needs"``` |

--- 
## Boolean Flags

| GOOD                        | BAD                      |
|-----------------------------|--------------------------|
| ```needs_revision = true``` | ```revision_status = "pending"``` |
| ```has_thesis = false```    | ```thesis_present = "no"``` |
| ```is_plagiarized = false```| ```plagiarism_check = "clean"``` |

--- 

## Avoid Reassigning Constants

Constants define ontology, not state.

<table> <colgroup> <col style="width: 59%" /> <col style="width: 40%" /> </colgroup> <thead> <tr> <th>GOOD</th> <th>BAD</th> </tr> </thead> <tbody> <tr> <td><code>DIFFICULTY_LEVEL = {BEGINNER, INTERMEDIATE, ADVANCED, EXPERT}</code><br /> <code>essay_difficulty = ADVANCED</code></td> <td><code>DIFFICULTY_LEVEL = ADVANCED</code></td> </tr> </tbody> </table>

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

## Contributors
- Alex Hernandez aka <em><a href="https://twitter.com/_alt3kx_" rel="nofollow">(@\_alt3kx\_)</a></em></br>
- SpartanTri aka <em><a href="https://github.com/spartantri" rel="nofollow">(@\_spartantri\_)</a></em></br>
- Israel Z. M. aka <em><a href="https://github.com/spk85" rel="nofollow">@spk85</a></em></br>

[🏠 Home](../README.md)