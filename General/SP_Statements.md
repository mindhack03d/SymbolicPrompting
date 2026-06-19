# Symbolic Prompting - Statements

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

As part of Symbolic Prompting, you can use different statements like: ```IF-THEN-ELSE, WHILE, FOR, LOOP, EXIT, BREAK, GOTO,...```

***

## IF-THEN-ELSE statement

| Logic Gate | Symbolic Variable | Meaning to the AI |
|-----------|-----------------|---------------------------------------|
| ```IF``` | ```[CONDITION]``` | "If the input matches this pattern..." |
| ```THEN``` | ```=>``` | "...then strictly produce this output." |
| ```ELSE IF``` | ```:::``` | "If the previous failed, check this sub-condition." |
| ```ELSE``` | \` | or \[DEFAULT\]\` |

### Example:
```
#[BIOLOGICAL_ENGINE]  
IF {BODY_TEMP} > 37.5°C  
    => [STATE]: "Hyperthermia Detected"  
    => [ACTION]: Trigger Vasodilation & Sweat Gland Activation  
ELSE IF {BODY_TEMP} < 36.0°C  
    => [STATE]: "Hypothermia Detected"  
    => [ACTION]: Trigger Vasoconstriction & Thermogenesis (Shivering)  
ELSE  
    => [STATE]: "Homeostasis" => [ACTION]: Maintain Normal Metabolic Rate
```

Using ```::: (Else If)``` allows for nested priority levels.

```
# [SUBSTANCE_CLASSIFIER]
[IF] (pH_Value < 3) => $CATEGORY: STRONGLY ACIDIC
::: (pH_Value >= 3 AND pH_Value < 7) => $CATEGORY: WEAKLY ACIDIC
::: (pH_Value == 7) => $CATEGORY: NEUTRAL (Pure Water)
::: (pH_Value > 7 AND pH_Value <= 11) => $CATEGORY: WEAKLY ALKALINE
| [ELSE] => $CATEGORY: STRONGLY ALKALINE
```

***

## Regular Expression
```
[RULE_SET]::= 
   User_Input(ip) ::=> IF (regex_match("\^\[0-9\\\]+\$")) THEN 
      (Process) 
    ELSE 
       (Reject & Log)
```

***

## WHILE statement

| OPERATOR | SYMBOLIC VARIABLE | MEANING TO THE AI |
|-------------|--------------------|----------------------------------------|
| ```WHILE``` | ```[WHILE] or (LOOP)``` | "Repeatedly apply this logic..." |
| ```CONDITION``` | ```[UNTIL] or [BREAK]``` | "...until the data is readable or a limit is reached." |
| ```ACTION``` | ```=>``` | "Perform this transformation in each cycle." |

### Example:

```
# [LITERARY_DECODER]   
[WHILE] {TEXT_PASSAGE} contains ("Metaphor" OR "Allusion" OR "Irony")  
     => (ACTION): Analyze Subtext of {TEXT_PASSAGE}  
     => (LOG): "Surface layer bypassed. Identifying deeper theme..."  
[BREAK] IF {TEXT_PASSAGE} == "Literal_Fact" 

(WHILE) reading <CHARACTER_DIALOGUE>:  
    IF [WORDS] contains "Weather_Imagery" AND "Dark_Adjectives" => $MOOD: "Foreshadowing_Danger"  
    ELSE IF [SENTENCE] length > 50 words => $MOOD: "Stream_of_Consciousness"  
[END_LOOP]
```

***

## FOR statement

| OPERATOR | SYMBOLIC VARIABLE | MEANING TO THE AI |
|-----------|----------------------|---------------------------------|
| ```FOR``` | ```[FOR_EACH] or (ITERATE)``` | "Take every item in this collection..." |
| ```IN``` | ```:: or IN``` | "...found within this specific set/file." |
| ```DO``` | ```=>``` | "Apply this security analysis to the item." |
| ```END``` | ```[NEXT] or [DONE]``` | "Move to the next item until finished." |

### Example 
```
# [BIODIVERSITY_AUDIT_PROTOCOL]    
[FOR_EACH] {SPECIES} IN <SURVEY_DATA>  
   (ACTION) => Compare {SPECIES} against $NATIVE_FLORA_DATABASE  
   IF (NO_MATCH) => $ALERT: "Invasive Species Detected: {SPECIES}"  
   ELSE => [LOG]: "Species {SPECIES} is indigenous to this region"  
[NEXT]

# [LITERARY_CRITIQUE_REVIEW]  
(ITERATE) through [ARGUMENTS] in <ESSAY_DRAFT>:  
   [FOR_EACH] argument:  
      1. Search for "Everyone knows", "Always", or "Never"  
      2. IF detected => [MARK]: "Potential Generalization Fallacy"  
      3. (REPORT) => Return paragraph number and suggestion for evidence   
[DONE]

# [SENTENCE_PARSER_V1]  
(FOR_EACH) {CLAUSE} IN <STUDENT_WRITING>:  
   [STEP_1] => Extract substring after "Subject="  
   [STEP_2] => [IF] substring contains NO "Verb" THEN (Classify as "Sentence Fragment")  
   [STEP_3] => (OUTPUT) Format as Grammar Correction Feedback  
[NEXT]

# [CHEMICAL_REACTION_SCANNER]   
(FOR_EACH) {EQUATION} IN <LAB_SAMPLES>  
   [ITERATOR] : {i} = sample_number  
   (LOG) => "Processing Sample #{i}..."  
   [STEP 1] => Count atoms for each element in {EQUATION}  
   [STEP 2] => IF {EQUATION} contains ("O2" as reactant AND "CO2 + H2O" as product)  
                THEN => [STATUS]: "Combustion_Reaction_Verified"  
                ELSE => [STATUS]: "Alternative_Reaction_Detected"  
   [STEP 3] => (OUTPUT) Format result for Sample {i} in a Lab Report Table.  
[NEXT_ITEM]

<LAB_SAMPLES> contains:
1.  CH4 + 2O2 -> CO2 + 2H2O
2.  2H2 + O2 -> 2H2O
```
***

##  GO-TO statement

| OPERATOR | SYMBOLIC VARIABLE | MEANING TO THE AI |
|-----------|--------------------|-----------------------------------------|
| ```LABEL``` | ```::LABEL_NAME::``` | A destination point in the prompt. |
| ```GOTO``` | ```[GOTO] or -->``` | "Skip all intermediate steps and move to the label." |
| ```RETURN``` | ```[RETURN]``` | "Go back to where you jumped from" (Optional). |

### Example
```
# [TRIAGE_ANALYSIS_FLOW]   
[STEP 1] Scan {PATIENT_VITALS} for basic irregularities (Pulse, BP, Temp).  
[STEP 2] IF {PATIENT_STATUS} contains "Unconscious" OR "Severe_Hemorrhage"  
         THEN [GOTO] ::CRITICAL_CARE_PROTOCOL::  
[STEP 3] Perform standard low-priority categorization (Minor injury/Stable).  
[STEP 4] Log to "patient_intake_records.db".  
[GOTO] ::DISCHARGE_OR_TRANSFER::  
  
::CRITICAL_CARE_PROTOCOL::  
   (ACTION) => Alert Trauma Surgeon and ER Staff immediately.  
   (ACTION) => Prepare 0.9% Saline IV and Oxygen Supplementation.  
   (ACTION) => Isolate Patient in $STABILIZATION_ROOM_1.  
   [RETURN] or [GOTO] ::DISCHARGE_OR_TRANSFER::  
  
::DISCHARGE_OR_TRANSFER::  
   (FINALIZE) => "Triage Assessment Complete."
```

***

##  TRY-CATCH-FINALLY statement

| OPERATOR | SYMBOLIC VARIABLE | MEANING TO THE AI |
|------------|---------------------|---------------------------------------|
| ```TRY``` | ```[TRY] or (ATTEMPT)``` | "Try to execute this high-complexity analysis..." |
| ```EXCEPTION``` | ```[CATCH] or [ON_ERROR]``` | "...if the data is malformed or analysis fails..." |
| ```FINALLY``` | ```[FINALLY]``` | "...always execute this (e.g., logging) regardless." |

### Example
```
# [LAB_EXPERIMENT_PARSER]  
[TRY]  
   (ACTION) => Combine {REACTANT_A} and {REACTANT_B} in a vacuum.  
   (ACTION) => Measure "Temperature_Change" and "Gas_Volume".  
   (ACTION) => Map results to {THERMODYNAMIC_MODEL}.  
[CATCH] (IF_REACTION_FAILS OR IF_NO_PRECIPITATE)  
   => [LOG]: "Warning: Reaction inhibited or concentration too low."  
   => (ACTION): Flag for Re-calibration of Scale.  
   => [GOTO] ::CLEAN_UP::  
[FINALLY]  
   => Update "lab_journal.pdf" with Timestamp and Sample_ID.

# [HISTORICAL_SOURCE_DECODER]  
[TRY]  
   (STEP) => Translate {MANUSCRIPT} using Latin_Grammar_Logic.  
   (STEP) => Scan text for "Key_Political_Figures" and "Dates".  
[CATCH] (TRANSLATION_ERROR)  
   => [REPORT]: "Dialect is non-standard; attempting Contextual_Clue_Scan."  
   => (STEP) => Scan physical {MANUSCRIPT} for seals or watermarks.  
[FINALLY]  
   => Generate $AUTHENTICITY_REPORT.
```

***

##  ARRAY 

| Operator | Symbolic Syntax | Effect |
|----------|-----------------|----------------------------------------|
| ```PUSH``` | ```[ARRAY] << {value}``` | Adds the value to the **end** of the list (Standard). |
| ```UNSHIFT``` | ```[ARRAY] <+ {value}``` | Adds the value to the **beginning** (High priority). |
| ```UNION``` | ```[ARRAY] U {list}``` | Merges two lists while removing duplicates. |
| ```INDEX``` | ```[ARRAY][n]``` | Retrieves the item at position n (Starting at 0 or 1). |
| ```POP``` | ```[ARRAY] >> {var}``` | Removes and retrieves the **last** item. |
| ```SHIFT``` | ```[ARRAY] -+ {var}``` | Removes and retrieves the **first** item. |
| ```SLICE``` | ```[ARRAY][1:3]``` | Extracts a range of items. |

### Example
```
[PRIMARY_SOURCES] = ["Diary_Entries", "Original_Photographs"]  

IF {document_origin} == "Eyewitness_Account" 
   THEN [PRIMARY_SOURCES] << {document_origin}
```
**Result:** ```[PRIMARY_SOURCES] = ["Diary_Entries", "Original_Photographs", "Eyewitness_Account"]```

```
[BOOK_QUOTES] = ["The sun smiled", "He was a lion in battle", "The wind whispered"]  
(ACTION) => Analyze [BOOK_QUOTES][1]  // Extracts: "He was a lion in battle" (Metaphor)

# [QUOTE_FILTER]  
{METAPHORS} = [BOOK_QUOTES] WHERE {item} CONTAINS "Direct_Comparison"

# [DATA_CLEANING_PROTOCOL]  
{VALID_SAMPLES} = [RIVER_WATER_DATA] WHERE {pH_level} NOT IN $CONTAMINATED_RANGE  
  
# [UNIT_TRANSFORMER]  
{CELSIUS_LIST} = [FAHRENHEIT_DATA] => (ACTION): Convert_to_Celsius

# [GEOMETRIC_TRANSFORMER]  
{SCALED_SHAPES} = [ORIGINAL_POLYGONS] => (ACTION): Multiply_Dimensions_by_2  

# [SHAPE_SORTER]
{QUADRILATERALS} = [SHAPE_LIST] WHERE {sides} == 4
```

##  EXIT OR BREAK
**EXIT:** Stop the execution
```
[SOURCE_VALIDATION_TREE] ::= 
  IF Eyewitness_Account == TRUE AND Created_During_Event == TRUE
    THEN CATEGORY ::= PRIMARY_SOURCE
    EXIT 
  ELSE
    THEN CATEGORY ::= SECONDARY_SOURCE
```
**BREAK:** Stop the cycle
```
[ANIMAL_CLASSIFICATION_TREE] ::= 
  IF Produces_Milk == TRUE AND Has_Hair_or_Fur == TRUE
    THEN CLASS ::= MAMMAL
    EXIT 
  ELSE
    THEN CLASS ::= NON_MAMMALIAN_SPECIES
```

<details>
  <summary>⚖️ Legal Disclaimer (Click to expand)</summary>

This repository is for educational purposes only regarding Symbolic Prompting. The author is not responsible for the use that third parties may make of these techniques. The user is responsible for respecting the terms of service of AI platforms and applicable legislation. All content is provided "AS IS," without warranties.<br>
Compatibility may vary depending on model updates, tokenization behavior, and symbol parsing.
</details>

⭐ If this class helped you think differently about LLMs, consider starring the repository.

<div align="center">

![](https://img.shields.io/badge/Focus-Prompt_Engineering-blue?style=flat-square)
![](https://img.shields.io/badge/Logic-Symbolic_AI-blueviolet?style=flat-square)
![](https://img.shields.io/badge/Logic-Symbolic_Prompting-blueviolet?style=flat-square)
![](https://img.shields.io/badge/LLM-Deterministic_Outputs-orange?style=flat-square)
![](https://img.shields.io/badge/Architecture-State_Machines-ff69b4?style=flat-square)
![](https://img.shields.io/badge/Content-Educational_Course-success?style=flat-square)<br>
![](https://img.shields.io/badge/Learn-System_Role-success?style=flat-square)
![](https://img.shields.io/badge/Content-LLM_PERSONA-success?style=flat-square)
![](https://img.shields.io/badge/Content-Prompt_Architecture-success?style=flat-square)

</div>

## Author
- Jesus Huerta aka <em><a href="https://github.com/mindhack03d" rel="nofollow">(@\_mindhack03d_)</a></em></br>

## Contributors
- Alex Hernandez aka <em><a href="https://twitter.com/_alt3kx_" rel="nofollow">(@\_alt3kx\_)</a></em></br>
- SpartanTri aka <em><a href="https://github.com/spartantri" rel="nofollow">(@\_spartantri\_)</a></em></br>

[🏠 Home](../README.md)