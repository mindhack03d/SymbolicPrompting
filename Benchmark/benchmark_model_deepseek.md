# Symbolic Prompting 📊 Benchmark Report: deepseek-v3@0324

## Temporal Analysis: March 3 vs March 5, 2026

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

---

## 📋 Table of Contents

- [Executive Summary](#executive-summary)
- [📈 Combined Results](#-combined-results)
- [📅 March 3, 2026 Detailed Analysis](#-march-3-2026-detailed-analysis)
- [📅 March 5, 2026 Detailed Analysis](#-march-5-2026-detailed-analysis)
- [📊 Stable Runs Comparison (Runs 2-9)](#-stable-runs-comparison-runs-2-9)
- [📈 Format Performance Trends](#-format-performance-trends)
- [🔍 Key Temporal Insights](#-key-temporal-insights)
- [🏆 Winner Analysis by Metric](#-winner-analysis-by-metric)
- [📊 Format Evolution Summary](#-format-evolution-summary)
- [📈 Performance Trend Visualization](#-performance-trend-visualization)
- [✅ Final Verdict](#-final-verdict)
- [📋 Recommendations](#-recommendations)
- [📁 Quick Reference Card](#-quick-reference-card)
- [📊 Risk Legend - Quick Reference](#-risk-legend---quick-reference)
- [📁 Resources](#-resources)
- [Author](#author)

---

## Executive Summary

This report analyzes benchmark results for **deepseek-v3@0324** across two different test dates (March 3 and March 5, 2026), comparing three prompt formats: **Symbolic**, **DSL/JSON**, and **Normal**.

| Dataset | Symbolic | DSL/JSON | Normal | Winner |
|:---|:---:|:---:|:---:|:---|
|**March 3 Only** | 1.49s | 1.46s | **1.37s** | 🏆 Normal |
|**March 5 Only** | 1.38s | **1.29s** | 1.44s | 🏆 DSL/JSON |
|**Winner** | 1.44s | **1.38s** | 1.41s | 🏆 **DSL/JSON** (1.38s) |

**Key Finding:** This model presents a **Split Winner** scenario with distinct winners on each test date: **Normal** won on March 3rd (1.37s stable mean), while **DSL/JSON** won on March 5th (1.29s stable mean). All formats maintained **✅ SAFE** IQR risk classifications across both dates, with zero outliers detected in the latest test.

Despite the split pattern, **DSL/JSON** emerges as the Combined Winner with a weighted stable mean of 1.38s, outperforming Normal (1.41s) and Symbolic (1.44s). The 0.03s advantage over Normal falls below the **<0.07s statistical tie threshold**, indicating competitive raw speed across formats. DSL/JSON's designation as Combined Winner is reinforced by its superior performance on the most recent test date and its strong showing across key metrics including Mean, Median, Maximum, and Range.


---

## 📈 Combined Results

*Aggregated data from both test dates (20 runs per format)*

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
| **Mean** | 1.46 | **1.40** | 1.42 |
| **Median** | 1.45 | 1.41 | **1.40** |
| **Q1 (25th)** | 1.37 | **1.25** | 1.29 |
| **Q3 (75th)** | 1.52 | **1.50** | 1.51 |
| **Minimum** | 1.10 | **1.09** | 1.12 |
| **Maximum** | 2.22 | **1.72** | 1.85 |
| **Std Dev (σ)** | 0.25 | 0.19 | **0.18** |
| **P90** | 1.61 | 1.64 | **1.57** |
| **P95** | 1.85 | **1.70** | 1.71 |
| **P99** | 2.15 | **1.71** | 1.83 |
| **IQR** | **0.15** | 0.25 | 0.22 |
| **IQR Deception Index** | 12.33 | 6.80 | 7.77 |
| **Risk Classification** | ✅ SAFE | ✅ SAFE | ✅ SAFE |
| **Range** | 1.12 | **0.62** | 0.74 |
| **CV** | 17% | 14% | **13%** |

---

## 📅 March 3, 2026 Detailed Analysis

### All Runs (1-10)

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
| **Mean** | 1.55 | 1.46 | 1.41 |
| **Median** | 1.50 | 1.44 | 1.37 |
| **Q1 (25th)** | 1.44 | 1.33 | 1.27 |
| **Q3 (75th)** | 1.58 | 1.60 | 1.45 |
| **Minimum** | 1.20 | 1.24 | 1.12 |
| **Maximum** | 2.22 | 1.72 | 1.85 |
| **Std Dev (σ)** | 0.28 | 0.16 | 0.21 |
| **P90** | 1.87 | 1.64 | 1.72 |
| **P95** | 2.05 | 1.68 | 1.79 |
| **P99** | 2.19 | 1.71 | 1.84 |
| **IQR** | 0.14 | 0.27 | 0.18 |
| **IQR Deception Index** | 14.64 | 6.22 | 9.94 |
| **Risk Classification** | ✅ SAFE | ✅ SAFE | ✅ SAFE |
| **Range** | 1.02 | 0.48 | 0.74 |
| **CV** | 18% | 11% | 15% |

### Stable Runs (2-9, Outliers Removed)

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
| **Mean** | 1.49 | 1.46 | **1.37** |
| **Median** | 1.50 | 1.44 | **1.37** |
| **Q1 (25th)** | 1.40 | 1.33 | **1.29** |
| **Q3 (75th)** | 1.57 | 1.58 | **1.42** |
| **Minimum** | 1.20 | 1.24 | **1.12** |
| **Maximum** | 1.83 | 1.72 | **1.70** |
| **Std Dev (σ)** | 0.19 | 0.16 | **0.16** |
| **P90** | 1.66 | 1.66 | **1.53** |
| **P95** | 1.75 | 1.69 | **1.62** |
| **P99** | 1.81 | 1.71 | **1.68** |
| **IQR** | 0.17 | 0.25 | **0.13** |
| **IQR Deception Index** | 10.29 | 6.76 | 12.46 |
| **Risk Classification** | ✅ SAFE | ✅ SAFE | ✅ SAFE |
| **Range** | 0.63 | **0.48** | 0.58 |
| **CV** | 13% | **11%** | 12% |

### Outliers Detected - March 3

| Format | Outliers <br>(CSV values) | Outlier Rate | Thresholds (2σ) | Impact |
|:---|:---|:---:|:---|:---|
| **Symbolic** | Run 1 (2.22s) | 10% (1/10) | Upper: 2.11s<br>Lower: 0.99s | **Moderate** - First run was a severe outlier (2.22s) exceeding the 2σ upper threshold. Removing this outlier reduces the mean by 0.06s (from 1.55s to 1.49s), a 4% change. |
| **DSL/JSON** | None | 0% | Upper: 1.78s<br>Lower: 1.14s | No outliers detected in runs 2-9. All values within expected range. |
| **Normal** | None | 0% | Upper: 1.83s<br>Lower: 0.99s | No outliers detected in runs 2-9. All values within expected range. |

*Verify these values in [benchmark_20260303.csv](../Benchmark/benchmark_20260303.csv)*

---
## 📅 March 5, 2026 Detailed Analysis

### All Runs (1-10)

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
| **Mean** | 1.37 | 1.35 | 1.42 |
| **Median** | 1.44 | 1.39 | 1.49 |
| **Q1 (25th)** | 1.25 | 1.16 | 1.36 |
| **Q3 (75th)** | 1.49 | 1.48 | 1.51 |
| **Minimum** | 1.10 | 1.09 | 1.20 |
| **Maximum** | 1.52 | 1.69 | 1.55 |
| **Std Dev (σ)** | 0.16 | 0.19 | 0.12 |
| **P90** | 1.51 | 1.50 | 1.52 |
| **P95** | 1.51 | 1.60 | 1.53 |
| **P99** | 1.51 | 1.68 | 1.55 |
| **IQR** | 0.24 | 0.32 | 0.15 |
| **IQR Deception Index** | 6.29 | 5.00 | 10.20 |
| **Risk Classification** | ✅ SAFE | ✅ SAFE | ✅ SAFE |
| **Range** | 0.42 | 0.60 | 0.35 |
| **CV** | 12% | 14% | 8% |

### Stable Runs (2-9, Outliers Removed)

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
| **Mean** | 1.38 | **1.29** | 1.44 |
| **Median** | 1.44 | **1.28** | 1.49 |
| **Q1 (25th)** | 1.36 | **1.14** | 1.37 |
| **Q3 (75th)** | **1.46** | 1.44 | 1.51 |
| **Minimum** | 1.11 | **1.09** | 1.20 |
| **Maximum** | 1.52 | **1.48** | 1.55 |
| **Std Dev (σ)** | 0.14 | 0.16 | **0.11** |
| **P90** | 1.51 | **1.47** | 1.53 |
| **P95** | 1.51 | **1.48** | 1.54 |
| **P99** | 1.51 | **1.48** | 1.55 |
| **IQR** | **0.10** | 0.30 | 0.14 |
| **IQR Deception Index** | 15.10 | 4.93 | 11.00 |
| **Risk Classification** | ✅ SAFE | ✅ SAFE | ✅ SAFE |
| **Range** | 0.40 | 0.39 | **0.35** |
| **CV** | 10% | 12% | **8%** |

### Outliers Detected - March 5

| Format | Outliers <br>(CSV values) | Outlier Rate | Thresholds (2σ) | Impact |
|:---|:---|:---:|:---|:---|
| **Symbolic** | None | 0% | Upper: 1.69s<br>Lower: 1.05s | **No outliers detected.** All 10 runs within expected distribution (range 1.10s-1.52s). Perfectly clean run. |
| **DSL/JSON** | Run 7 (1.91s) | 10% (1/10) | Upper: 1.73s<br>Lower: 0.97s | **Moderate** - A single, severe outlier (1.91s) exceeding the 2σ upper threshold (1.73s). Removing it reduces stable mean from 1.35s to 1.29s (0.06s reduction). |
| **Normal** | None | 0% | Upper: 1.66s<br>Lower: 1.18s | **No outliers detected.** All 10 runs within expected distribution (range 1.20s-1.55s). Perfectly clean run. |

*Verify these values in [benchmark_20260305.csv](../Benchmark/benchmark_20260305.csv)*

---

## 📊 Stable Runs Comparison (Runs 2-9)

| Format | Date | Mean | Median | Std Dev | P95 | IQR | IQR Risk | Change |
|:---|:---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **Symbolic** | Mar 3 | 1.49s | 1.50s | 0.19s | 1.75s | 0.17s | ✅ Safe | |
|              | Mar 5 | **1.38s** | 1.44s | **0.14s** | **1.51s** | **0.10s** | ✅ Safe | ⬇️ **-7.4% FASTER**<br>✅ **1.4x more consistent** |
| **DSL/JSON** | Mar 3 | 1.46s | 1.44s | 0.16s | 1.69s | 0.25s | ✅ Safe |  |
|              | Mar 5 | **1.29s** | **1.28s** | 0.16s | **1.48s** | 0.30s | ✅ Safe | ⬇️ **-11.6% FASTER**<br>⚖️ **same consistency** |
| **Normal** | Mar 3 | **1.37s** | **1.37s** | 0.16s | 1.62s | 0.13s | ✅ Safe | |
|              | Mar 5 | 1.44s | 1.49s | **0.11s** | 1.54s | 0.14s | ✅ Safe | ⬆️ **+5.1% slower**<br>✅ **1.5x more consistent** |


---

## 📈 Format Performance Trends

### ⚙️ Symbolic Prompting

```
Mar 3 (All) :    ████████████████████ 1.55s | σ=0.28s
Mar 3 (Stable) : ██████████████████░░ 1.49s | σ=0.19s
Mar 5 (All) :    ████████████████░░░░ 1.37s | σ=0.16s ⬇️ 12% FASTER, 1.8x MORE CONSISTENT
Mar 5 (Stable) : ████████████████░░░░ 1.38s | σ=0.14s ⬇️ 7% FASTER, 1.4x MORE CONSISTENT
```

**Trend Analysis:** Symbolic shows consistent improvement across both metrics. Mean latency dropped from 1.49s to **1.38s** (-7.4%) while standard deviation improved from 0.19s to **0.14s** (1.4x more consistent). The format had zero outliers on March 5th, indicating excellent stability after the first test date.

### 🔷 DSL/JSON Prompting

```
Mar 3 (All) :    ███████████████████░ 1.46s | σ=0.16s
Mar 3 (Stable) : ███████████████████░ 1.46s | σ=0.16s
Mar 5 (All) :    ████████████████░░░░ 1.35s | σ=0.19s ⬇️ 7% FASTER
Mar 5 (Stable) : ███████████████░░░░░ 1.29s | σ=0.16s ⬇️ 12% FASTER
```

**Trend Analysis:** DSL/JSON demonstrates the most dramatic performance improvement, with stable mean dropping from 1.46s to **1.29s** (-11.6%)—a **0.17s absolute gain**. Consistency remained unchanged (0.16s Std Dev on both dates), showing that the format maintained its stability while achieving significantly lower latency. This improvement flipped the winner from Normal (Mar 3) to DSL/JSON (Mar 5).

### 📝 Normal Prompting

```
Mar 3 (All) :    ██████████████████░░ 1.41s | σ=0.21s
Mar 3 (Stable) : ████████████████░░░░ 1.37s | σ=0.16s
Mar 5 (All) :    ██████████████████░░ 1.42s | σ=0.12s ⬇️ 1.8x MORE CONSISTENT
Mar 5 (Stable) : ███████████████████░ 1.44s | σ=0.11s ⬇️ 1.5x MORE CONSISTENT
```


**Trend Analysis:** Normal presents a classic trade-off: slightly slower mean latency (+5.1%) but dramatically improved consistency. Std Dev improved from 0.16s to **0.11s** (1.5x more consistent), giving Normal the lowest CV (8%) of any format on March 5th. This makes Normal the most predictable format, ideal for applications where consistent response times are more critical than peak speed.

---

## 🔍 Key Temporal Insights

| Insight | Description |
|:---|:---|
| **📈 DSL/JSON Dramatically Improved** | DSL/JSON became **12% faster** in stable runs (1.46s → 1.29s) after outlier removal, and achieved the fastest stable mean on March 5th (1.29s). However, it was the only format with an outlier on March 5th (Run 7 at 1.91s). |
| **📊 Normal's Consistency Gains** | While Normal's speed remained relatively flat (+5% slowdown in stable runs), it became significantly more consistent (σ 0.16s → 0.11s), making it a much more reliable choice for production workloads where predictability is valued over marginal speed gains. |
| **⚠️ Symbolic Eliminated Severe Outliers** | Symbolic had a severe 2.22s outlier on Mar 3 but delivered a perfectly clean run with zero outliers on Mar 5, demonstrating excellent operational stability and suggesting backend optimizations for concise structured inputs. |
| **✅ Cleanest Latest Performance** | On March 5th, both **Symbolic and Normal** produced runs with zero outliers, with Normal achieving the lowest standard deviation (σ=0.11s) of any format on any date. |
| **📊 The Format "Changing Places"** | On March 3rd, Normal was the winner (1.37s) and Symbolic was the slowest (1.49s). On March 5th, this relationship inverted, with DSL/JSON becoming the fastest (1.29s) and Normal the slowest (1.44s) among stable runs. This inversion demonstrates significant backend variability in format optimization. |
| **📊 Consistency Championship** | **Normal** achieved the lowest standard deviation on March 5th stable runs (σ=0.11s) - the most consistent performance across the entire test window, despite being the slowest format that day. |
| **📊 Spread Between Best and Worst Formats** | **~10%** spread between best (DSL/JSON 1.29s on Mar 5) and worst (Symbolic 1.49s on Mar 3) stable means, highlighting that format choice can impact latency by ~0.2s depending on backend conditions. |

---
## 🏆 Winner Analysis by Metric

| Metric | Mar 3 Winner<br>(Stable Runs 2-9) | Mar 5 Winner<br>(Stable Runs 2-9) | Combined Winner<br>(Stable Means) |
|:---|:---:|:---:|:---:|
| **Mean** | 🏆 Normal (1.37s) | 🏆 DSL/JSON (1.29s) | 🏆 DSL/JSON (1.38s) |
| **Median** | 🏆 Normal (1.37s) | 🏆 DSL/JSON (1.28s) | 🏆 DSL/JSON (1.36s) |
| **Minimum** | 🏆 Normal (1.12s) | 🏆 DSL/JSON (1.09s) | 🏆 Symbolic (1.10s) |
| **Maximum (lower is better)** | 🏆 Normal (1.70s) | 🏆 DSL/JSON (1.48s) | 🏆 DSL/JSON (1.60s) |
| **Std Dev (consistency)** | 🤝 Tie (0.16s) | 🏆 Normal (0.11s) | 🏆 Normal (0.14s) |
| **P95 (worst case)** | 🏆 Normal (1.62s) | 🏆 DSL/JSON (1.48s) | 🏆 Normal (1.58s) |
| **IQR (core consistency)** | 🏆 Normal (0.13s) | 🏆 Symbolic (0.10s) | 🤝 Tie (0.14s) |
| **Range (stability)** | 🏆 DSL/JSON (0.48s) | 🏆 Normal (0.35s) | 🏆 DSL/JSON (0.44s) |
| **CV (predictability)** | 🏆 DSL/JSON (11%) | 🏆 Normal (8%) | 🏆 Normal (13%) |
| **Overall Winner by Date** | 🏆 **Normal** | 🏆 **DSL/JSON** | 🏆 **DSL/JSON** (Fastest Weighted Mean) |

### Winner Dominance Analysis

| Format | Metrics Won | Metric Superiority Score | Tie Rate |
|:---|:---:|:---:|:---:|
| **DSL/JSON** | 5/9 | 56% | 11% |
| **Normal** | 5/9 | 56% | 22% |
| **Symbolic** | 1/9 | 11% | 22% |

*Note: Metrics Won counts sole wins only (excluding ties). Metric Superiority Score = (Wins / Total Metrics) × 100%. Tie Rate = (Tied metrics / Total Metrics) × 100%.*

---

## 📊 Format Evolution Summary

| Format | Metric | Mar 3 | Mar 5 | Change | Temporal Stability | IQR Index (Combined) | Per-Date IQR Risk |
|:---|:---|:---:|:---:|:---:|:--:|:---:|:---|
| **Symbolic** | Mean (All) | 1.55s | **1.37s** | ⬇️ **-11.6%** | ✅ 0.92 (Good) | 12.3 (✅ Safe) | Mar 3: 14.6 (✅ Safe)<br>Mar 5: 6.3 (✅ Safe) |
| | Mean (Stable) | 1.49s | **1.38s** | ⬇️ **-7.4%** | | | |
| | Std Dev (Stable) | 0.19s | **0.14s** | ⬇️ **-26.3% more consistent** | | | |
| **DSL/JSON** | Mean (All) | 1.46s | **1.35s** | ⬇️ **-7.5%** | ✅ 0.88 (Good) | 6.8 (✅ Safe) | Mar 3: 6.2 (✅ Safe)<br>Mar 5: 5.0 (✅ Safe) |
| | Mean (Stable) | 1.46s | **1.29s** | ⬇️ **-11.6%** | | | |
| | Std Dev (Stable) | 0.16s | 0.16s | ➡️ **0% (unchanged)** | | | |
| **Normal** | Mean (All) | **1.41s** | 1.42s | ⬆️ +0.7% (negligible) | ⭐ 0.95 (Excellent) | 7.8 (✅ Safe) | Mar 3: 12.5 (✅ Safe)<br>Mar 5: 11.0 (✅ Safe) |
| | Mean (Stable) | **1.37s** | 1.44s | ⬆️ +5.1% | | | |
| | Std Dev (Stable) | 0.16s | **0.11s** | ⬇️ **-31.3% more consistent** | | | |

---

## 📈 Performance Trend Visualization

```
SYMBOLIC
────────────────────────────────────────────────
Speed: 1.49s ──────────┐
▼
1.38s ────────────────────► 7% FASTER ✅

Consist: 0.19s ──────────┐
▼
0.14s ────────────────────► 1.4x MORE consistent ✅

DSL/JSON
────────────────────────────────────────────────
Speed: 1.46s ──────────┐
▼
1.29s ────────────────────► 12% FASTER ✅

Consist: 0.16s ──────────┐
▼
0.16s ────────────────────► (unchanged) ⚖️

NORMAL
────────────────────────────────────────────────
Speed: 1.37s ──────────┐
▼
1.44s ────────────────────► 5% SLOWER ⚠️

Consist: 0.16s ──────────┐
▼
0.11s ────────────────────► 1.5x MORE consistent ✅
```

---

## ✅ Final Verdict

| Aspect | Conclusion |
|:---|:---|
| Overall Winner | ⚖️ **Statistical Tie** (Combined Stable Mean: DSL/JSON 1.38s, Normal 1.41s, Symbolic 1.44s) |
| | **Rationale:** Following the **["Unified Winner Declaration Protocol"](../Benchmark/benchmark_methodology.md#unified-winner-declaration-protocol)** for a **Split Winner** scenario (Normal won Mar 3, DSL/JSON won Mar 5), the combined mean differences are well below the <0.07s statistical tie threshold, as discussed in the [FAQ - Split Winner or Statistical Tie](../Benchmark/benchmark_fqa.md). **DSL/JSON** is recommended for workloads prioritizing raw speed based on the most recent (Mar 5) performance data, which shows superior speed (1.29s stable mean). **Normal** is recommended for workloads prioritizing historical stability and consistency. **Symbolic** is recommended for balanced performance with excellent consistency on the latest test. |
| **Most Improved** | 📈 **DSL/JSON Prompting** (12% faster in stable runs across dates) |
| **Most Stable on Latest Test** | 📊 **Normal** (Lowest σ=0.11s on Mar 5 stable runs, zero outliers) |
| **Best Single Run** | ⚡ **DSL/JSON** (1.09s on Mar 5) |
| **Worst Outlier** | 🔴 **Symbolic** (2.22s on Mar 3) |
| **Most Temporally Stable (Mean)** | 🔹 **Normal** (Achieved near-perfect Temporal Stability Score of **0.95** for mean performance across dates) |
| **Biggest Decline** | ⚠️ **Normal** (Mean performance degraded by 5% in stable runs, though consistency improved significantly.) |

### Risk Assessment Summary

| Risk Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
| **IQR Deception Index (Combined)** | 12.3 | 6.8 | 7.8 |
| **Classification** | ✅ SAFE | ✅ SAFE | ✅ SAFE |
| **Two-Factor Assessment** | Not Required (Index <20) | Not Required (Index <20) | Not Required (Index <20) |
| **Tail-Risk Status** | ⚠️ Monitor (Mar 3 outlier: 2.22s) | ⚠️ Monitor (Mar 5 outlier: 1.91s) | ✅ Acceptable (minimal outliers) |
| **Outlier Rate** | 10% (1/10 severe) | 10% (1/10 moderate) | 10% (1/10 mild) |
| **Production Readiness** | 🟢 Ready (post Mar 5) | 🟢 Ready (with monitoring) | 🟢 Ready |

---

## 📋 Recommendations

| Use Case | Recommended Format | Rationale |
|:---|:---|:---|
| **General production (if using latest data)** | 🏆 **DSL/JSON** | Fastest on most recent test (1.29s stable mean) with 12% improvement across dates. ⚠️ Monitor for outliers (1.91s on Mar 5 Run 7). |
| **General production (for historical stability)** | 🏆 **Normal** | Won on Mar 3 (1.37s), excellent temporal stability (0.95), most consistent on latest test (σ=0.11s) with zero outliers. |
| **Balanced performance across dates** | ✅ **Symbolic** | Competitive on both dates, zero outliers on Mar 5, consistent improvement trend (7% faster). Eliminated severe 2.22s outlier from first test. |
| **If JSON is required** | 🔷 **DSL/JSON** ⚠️ | Fastest format on Mar 5, but monitor for outliers (1.91s on Run 7) and higher IQR (0.30s) indicating core request variability. |
| **If consistency is critical** | ✅ **Normal** | Lowest standard deviation on latest test (σ=0.11s) with zero outliers and 1.5x consistency improvement across dates. |
| **Strict SLAs (<1.6s P99)** | ✅ **All formats** | All formats achieved P99 <1.6s on March 5th, with DSL/JSON at 1.48s (fastest), Normal at 1.55s, Symbolic at 1.51s. |
| **Multi-date stability** | ✅ **Normal** | Achieved highest Temporal Stability Score (0.95) for mean performance across dates, indicating resistance to backend variance. |
| **If using Symbolic prompts** | ✅ **Symbolic** | Excellent choice with 7% improvement and zero outliers on latest test; production-ready after Mar 5 performance. |
| **Cost-sensitive applications** | ✅ **Symbolic** | Lowest token count (~74 tokens) means lowest input costs while maintaining competitive performance and zero outliers on latest test. |

### ⚠️ Important Caveats

| Caveat | Description | Impact |
|:---|:---|:---|
| **Split Winner Pattern** | Different formats won on different test dates (Normal on Mar 3, DSL/JSON on Mar 5) | No single format dominates; choice depends on prioritization of recency vs. historical stability. See [FAQ - Split Winner or Statistical Tie](../Benchmark/benchmark_fqa.md). |
| **DSL/JSON Outlier Risk** | Single 1.91s outlier on Mar 5 (Run 7) represents 10% of runs | May impact P99 SLAs; monitoring recommended for production deployments. |
| **Symbolic's Severe Outlier (Mar 3)** | 2.22s outlier on first test date (Run 1) | Eliminated in latest test; format now stable but historical anomaly noted. |
| **Normal's Performance Degradation** | 5.1% slowdown in stable runs from Mar 3 to Mar 5 | Trade-off: slower but more consistent; evaluate against speed requirements. |
| **Small Sample Size** | n=10 per date, n=20 combined per format | Results are directional; confidence intervals may overlap for differences <0.07s. See [FAQ on statistical significance](../Benchmark/benchmark_fqa.md#q-with-only-n10-per-format-per-date-how-statistically-significant-are-your-results). |
| **Single Region Testing** | Tests conducted from US-East (AWS us-east-1) | Global latency patterns may differ; regional testing recommended for worldwide deployments. |


---

## 📁 Quick Reference Card

| If you want... | Recommended Format | Key Metrics (Stable Runs) | Risk Note |
|:---|:---|:---|:---|
| **Best overall performance (combined mean)** | ⚖️ **Statistical Tie** | Normal: 1.41s / DSL/JSON: 1.38s / Symbolic: 1.44s | ✅ All formats <20 IQR Index |
| **Best latest performance (Mar 5)** | 🏆 **DSL/JSON** | 1.29s mean, 1.48s P95 | ⚠️ Monitor outliers (1.91s on Run 7) |
| **Most consistent across dates** | 📊 **Normal** | σ: 0.16s→0.11s, Stability: 0.95 | ✅ Excellent temporal stability |
| **Lowest outlier risk** | ✅ **Normal** | 1 mild outlier across 20 runs | ✅ Zero outliers on Mar 5 |
| **JSON-native workflows** | 🔷 **DSL/JSON** | 12% faster than Mar 3 baseline | ⚠️ Monitor IQR (0.30s on Mar 5) |
| **Strict P99 requirements (<1.6s)** | ✅ **All formats (Mar 5)** | DSL/JSON: 1.48s, Symbolic: 1.51s, Normal: 1.55s | ✅ All meet SLA on latest test |
| **Balanced performance** | ⚙️ **Symbolic** | 7% faster than Mar 3, zero outliers on Mar 5 | ✅ IQR Index 12.3 (Safe) |
| **Historical stability** | 📊 **Normal** | Won Mar 3 (1.37s), Stability: 0.95 | ✅ Lowest risk profile |
| **Cost-sensitive applications** | ⚙️ **Symbolic** | ~74 tokens/request | ✅ Zero outliers on latest test |

### ⚡ Winner's Circle Summary

| Category | Winner | Key Stat |
|:---|:---|:---|
| **Overall Performance** | ⚖️ **Statistical Tie** | 1.38-1.44s combined stable mean |
| **Temporal Stability** | 🏆 **Normal** | 0.95 Stability Score |
| **Consistency (Latest Test)** | 🏆 **Normal** | σ=0.11s on Mar 5, zero outliers |
| **Tail Performance (Latest)** | 🏆 **DSL/JSON** | 1.48s P95 on Mar 5 |
| **Peak Speed** | 🏆 **DSL/JSON** | 1.29s stable mean (Mar 5) |
| **Cost Efficiency** | 🏆 **Symbolic** | ~74 tokens/request |
| **Most Improved** | 📈 **DSL/JSON** | 12% faster (1.46s → 1.29s) |
| **Cleanest Latest Run** | 🏆 **Symbolic & Normal** | Zero outliers on Mar 5 |
| **Historical Reliability** | 🏆 **Normal** | Won Mar 3, near-perfect stability |

---

> *"We don't ask you to trust our numbers. We give you the tools to verify them yourself."*

---

## 📊 Risk Legend - Quick Reference

| Symbol | Meaning | Production Implication |
|:---:|:---|:---|
| **✅ Safe** | IQR Deception Index <20 | Eligible for production |
| **🟡 Moderate** | IQR Index 20-30 AND P95 < Dynamic Threshold T | Eligible with monitoring; acceptable with tracking |
| **🔴 Severe** | IQR Index >30 OR (Index 20-30 + P95 ≥ T) | **DISQUALIFIED** from production winner status |
| **🚨 Critical** | IQR Index >50 | **UNUSABLE** for production - extreme tail risk |
| **⭐ Excellent** | Temporal Stability Score 0.95-1.00 | Virtually identical across test dates |
| **✅ Good** | Temporal Stability Score 0.85-0.94 | Minor variance, still reliable |
| **⚠️ Moderate** | Temporal Stability Score 0.70-0.84 | Noticeable fluctuation between tests |
| **❌ Poor** | Temporal Stability Score <0.70 | Significant day-to-day variance |

### Application to deepseek-v3@0324

| Format | Status | Rationale |
|:---|:---:|:---|
| **Symbolic** | ✅ **ELIGIBLE** | ✅ Safe IQR classification on both dates (14.6 Mar 3, 6.3 Mar 5); zero outliers on latest test; 7% faster in stable runs with 1.4x consistency improvement; clean risk profile with no disqualifying events. |
| **DSL/JSON** | ✅ **ELIGIBLE** | ✅ Safe IQR classification on both dates (6.2 Mar 3, 5.0 Mar 5); 12% faster in stable runs with fastest stable mean on Mar 5 (1.29s); single moderate outlier (1.91s) noted but does not trigger disqualification under ✅ Safe classification. |
| **Normal** | ✅ **ELIGIBLE** | ✅ Safe IQR classification on both dates (12.5 Mar 3, 11.0 Mar 5); highest temporal stability score (0.95); lowest standard deviation on latest test (σ=0.11s) with zero outliers; 5% slowdown in stable runs but 1.5x consistency improvement. |

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
- 🔧 **[Reproduce Test](../Benchmark/benchmark_reproduce_test.md)** - How to Reproduce the tests yourself 
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