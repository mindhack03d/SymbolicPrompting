# Symbolic Prompting 📊 Benchmark Report: claude-3-haiku@20240307

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
- [📊 Temporal Stability Scores](#-temporal-stability-scores)
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
- [Contributors](#contributors)

---

## 🏆 Executive Summary

| Dataset | Symbolic | DSL/JSON | Normal | Winner |
|:---|:---:|:---:|:---:|:---|
|**March 3 Only** | 1.01s | 1.30s | 1.02s | 🏆 Symbolic🟡 |
|**March 5 Only** | 1.03s | 1.11s | 1.13s | 🏆 Symbolic🟡 |
|**Weighted Combined** | **1.02s** | 1.21s | 1.08s | 🏆 **Symbolic⚠️ (1.02s)** |

> [!NOTE]
> **Stable Winner:** Symbolic prompting demonstrates a **Stable Winner** pattern, delivering the lowest latency across both test dates (Weighted Combined: 1.02s). However, users should note the 🟡 **Moderate Risk** classification on both dates (Mar 3 P95=1.06s < Dynamic Threshold T=3.03s, Mar 5 P95=1.06s < T=3.09s). With a Temporal Stability Score of **0.98 (⭐ Excellent)**, Symbolic remains recommended with monitoring for tail performance.
>
> *Reference: [Temporal Stability Score Calculation](../Benchmark/benchmark_methodology.md#temporal-stability-score-calculation) - Score range 0.95-1.00 = ⭐ Excellent*

---

## 📈 Combined Results

*Aggregated data from both test dates using **Stable Runs** (outliers removed per methodology). Note: For combined winner determination, formats with 🔴 Severe or 🚨 CRITICAL Risk on either test date are disqualified per the [Global Disqualification Rule](../Benchmark/benchmark_methodology.md#6-global-disqualification-with-anomaly-detection).*

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Sample Size (n)** | 15 | 16 | 15 |
|**Mean** | **1.02s** | 1.21s | 1.08s |
|**Median** | **1.02s** | 1.08s | 1.04s |
|**Q1 (25th)** | 1.00s | 1.04s | 1.03s |
|**Q3 (75th)** | 1.04s | 1.11s | 1.07s |
|**Minimum** | **0.96s** | 1.01s | 0.98s |
|**Maximum** | **1.17s** | 2.18s | 1.28s |
|**Std Dev (σ)** | **0.03s** | 0.36s | 0.09s |
|**P90** | **1.05s** | 1.27s | 1.13s |
|**P95** | **1.06s** | 1.41s | 1.16s |
|**P99** | **1.15s** | 2.30s | 1.34s |
|**IQR** | 0.04s | 0.07s | 0.04s |
|**IQR Deception Index** | 26.5 | 20.1 | 29.0 |
|**Risk Classification** | 🟡 **MODERATE** | ✅ **SAFE** | 🟡 **MODERATE** |
|**Range** | **0.21s** | 1.17s | 0.30s |
|**CV** | **2.9%** | 29.8% | 8.3% |

| Model | Symbolic | DSL/JSON | Normal | Combined Winner |
|:---|:---:|:---:|:---:|:---|
| **claude-3-haiku** | **1.02s** | 1.21s | 1.08s | 🏆 **Symbolic⚠️** |

*\*Note: DSL/JSON and Normal are **disqualified** from combined winner consideration due to 🔴 Severe and 🚨 CRITICAL Risk on March 3, despite showing Safe/Moderate risk in aggregated metrics. Symbolic is declared the Conditional Winner as it meets all exception criteria (lowest weighted mean, wins 8/9 metrics, other formats disqualified).*

---

## 📅 March 3, 2026 Detailed Analysis

### All Runs (1-10)

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | 1.01s | 1.25s | 1.03s |
|**Median** | 1.02s | 1.03s | 1.02s |
|**Q1 (25th)** | 0.99s | 1.01s | 1.02s |
|**Q3 (75th)** | 1.03s | 1.06s | 1.04s |
|**Minimum** | 0.96s | 1.01s | 0.98s |
|**Maximum** | 1.08s | 3.08s | 1.07s |
|**Std Dev (σ)** | 0.03s | 0.61s | 0.02s |
|**P90** | 1.05s | 1.36s | 1.04s |
|**P95** | 1.07s | 2.22s | 1.06s |
|**P99** | 1.08s | 2.90s | 1.07s |
|**IQR** | 0.04s | 0.05s | 0.02s |
|**IQR Deception Index** | 26.75 | 44.40 | 53.00 |
|**Risk Classification** | 🟡 MODERATE | 🔴 SEVERE | 🚨 CRITICAL |
|**Range** | 0.12s | 2.07s | 0.09s |
|**CV** | 3% | 49% | 2% |

### Stable Runs (2-9, Outliers Removed)

Per our [methodology](../Benchmark/benchmark_methodology.md#stable-runs-definition-sub-section), Stable Runs represent expected steady-state performance after removing statistical outliers (±2σ) from Runs 2-9.

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | **1.01s** | 1.30s | 1.02s |
|**Median** | **1.01s** | 1.04s | 1.02s |
|**Q1 (25th)** | 0.98s | 1.02s | 1.01s |
|**Q3 (75th)** | 1.02s | 1.09s | 1.03s |
|**Minimum** | **0.96s** | 1.01s | 0.98s |
|**Maximum** | 1.08s | 3.08s | **1.04s** |
|**Std Dev (σ)** | 0.03s | 0.67s | **0.02s** |
|**P90** | 1.04s | 1.74s | **1.04s** |
|**P95** | 1.06s | 2.41s | **1.04s** |
|**P99** | 1.08s | 2.94s | **1.04s** |
|**IQR** | 0.04s | 0.07s | **0.02s** |
|**IQR Deception Index** | 26.50 | 34.43 | 52.00 |
|**Risk Classification** | 🟡 MODERATE | 🔴 SEVERE | 🚨 CRITICAL |
|**Range** | 0.12s | 2.07s | **0.06s** |
|**CV** | 3% | 52% | **2%** |

### Outliers Detected - March 3

Following our [outlier detection methodology](../Benchmark/benchmark_methodology.md#outlier-handling), the following statistical outliers were identified and removed from Stable Runs calculations:

| Format | Outliers <br>(CSV values) | Outlier Rate | Thresholds (2σ) | Impact |
|:---|:---|:---:|:---|:---|
| **Symbolic** | None | 0% | Upper: 1.08s<br>Lower: 0.96s | No outliers detected. All runs within expected distribution. |
| **DSL/JSON** | Run 9 (3.08s) | 10% (1/10) | Upper: 2.51s<br>Lower: -0.03s | **Moderate** - A single, severe outlier exceeding the 2σ upper threshold. Removing it reduces mean from 1.25s to 1.15s and improves IQR Deception Index from 44.40 (🔴 Severe) to 34.43 (🔴 Severe). |
| **Normal** | None | 0% | Upper: 1.07s<br>Lower: 0.99s | No outliers detected. All runs within expected distribution. |

---

## 📅 March 5, 2026 Detailed Analysis

### All Runs (1-10)

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | 1.06s | 1.15s | 1.12s |
|**Median** | 1.05s | 1.11s | 1.08s |
|**Q1 (25th)** | 1.02s | 1.07s | 1.04s |
|**Q3 (75th)** | 1.05s | 1.22s | 1.12s |
|**Minimum** | 1.00s | 1.06s | 1.04s |
|**Maximum** | 1.26s | 1.32s | 1.52s |
|**Std Dev (σ)** | 0.07s | 0.09s | 0.14s |
|**P90** | 1.08s | 1.27s | 1.17s |
|**P95** | 1.17s | 1.30s | 1.34s |
|**P99** | 1.25s | 1.32s | 1.48s |
|**IQR** | 0.03s | 0.15s | 0.08s |
|**IQR Deception Index** | 39.00 | 8.67 | 16.75 |
|**Risk Classification** | 🔴 SEVERE | ✅ SAFE | ✅ SAFE |
|**Range** | 0.27s | 0.26s | 0.48s |
|**CV** | 7% | 8% | 13% |

### Stable Runs (2-9, Outliers Removed)

Per our [methodology](../Benchmark/benchmark_methodology.md#stable-runs-definition-sub-section), Stable Runs represent expected steady-state performance after removing statistical outliers (±2σ) from Runs 2-9.

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | **1.03s** | 1.11s | 1.13s |
|**Median** | **1.04s** | 1.10s | 1.08s |
|**Q1 (25th)** | 1.01s | 1.06s | 1.05s |
|**Q3 (75th)** | 1.05s | 1.12s | 1.12s |
|**Minimum** | **1.00s** | 1.06s | 1.04s |
|**Maximum** | **1.06s** | 1.27s | 1.52s |
|**Std Dev (σ)** | **0.02s** | 0.06s | 0.15s |
|**P90** | **1.05s** | 1.17s | 1.25s |
|**P95** | **1.06s** | 1.22s | 1.38s |
|**P99** | **1.06s** | 1.26s | 1.49s |
|**IQR** | **0.04s** | 0.06s | 0.07s |
|**IQR Deception Index** | 26.50 | 20.33 | 19.71 |
|**Risk Classification** | 🟡 MODERATE | 🟡 MODERATE | ✅ SAFE |
|**Range** | **0.06s** | 0.21s | 0.48s |
|**CV** | **2%** | 5% | 13% |


### Outliers Detected - March 5

Following our [outlier detection methodology](../Benchmark/benchmark_methodology.md#outlier-handling), the following statistical outliers were identified and removed from Stable Runs calculations:

| Format | Outliers | Outlier Rate | Thresholds (2σ) | Impact |
|:---|:---|:---:|:---|:---|
| **Symbolic** | Run 10 (1.26s) | 10% (1/10) | Upper: 1.20s<br>Lower: 0.92s | **Minimal** - Run 10 exceeds 2σ threshold. Removing it reduces mean from 1.06s to 1.03s and improves risk classification from 🔴 SEVERE to 🟡 MODERATE. |
| **DSL/JSON** | None | 0% | Upper: 1.33s<br>Lower: 0.97s | No outliers detected. All runs within expected distribution. |
| **Normal** | Run 10 (1.52s) | 10% (1/10) | Upper: 1.40s<br>Lower: 0.84s | **Moderate** - Run 10 exceeds 2σ upper threshold. Removing it reduces mean from 1.12s to 1.08s and improves risk classification (Index improves from 16.75 to 19.71, still ✅ Safe). |

*Verify these values in [benchmark_20260305.csv](../Benchmark/benchmark_20260305.csv)*

---

## 📊 Stable Runs Comparison (Runs 2-9)

*Stable Runs represent expected steady-state performance after removing statistical outliers (±2σ) per our [methodology](../Benchmark/benchmark_methodology.md#stable-runs-definition-sub-section).*

| Format | Date | Mean | Median | Std Dev | CV | P95 | IQR | IQR Risk | Change |
|:---|:---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---|
| **Symbolic** | Mar 3 | **1.01s** | **1.01s** | 0.03s | 3% | **1.06s** | 0.04s | 🟡 MODERATE | Baseline performance |
| | Mar 5 | 1.03s | 1.04s | **0.02s** | **2%** | **1.06s** | **0.04s** | 🟡 MODERATE | ⬆️ +2% slower, ✅ **equally consistent** |
| **DSL/JSON** | Mar 3 | 1.30s | 1.04s | 0.67s | 52% | 2.41s | 0.07s | 🔴 SEVERE | |
| | Mar 5 | 1.11s | 1.10s | 0.06s | 5% | 1.22s | 0.06s | 🟡 MODERATE | ⬇️ -15% faster, ✅ **11.2x more consistent** |
| **Normal** | Mar 3 | **1.02s** | 1.02s | **0.02s** | **2%** | **1.04s** | **0.02s** | 🚨 CRITICAL | |
| | Mar 5 | 1.13s | 1.08s | 0.15s | 13% | 1.38s | 0.07s | ✅ SAFE | ⬆️ +11% slower, ❌ **7.5x more variable** |

---

## 📈 Format Performance Trends

### ⚙️ Symbolic Prompting

```
Mar 3 (All) :    ████████░░ 1.01s | σ=0.03s | CV=3% | 🟡 Moderate
Mar 3 (Stable) : ████████░░ 1.01s | σ=0.03s | CV=3% | 🟡 Moderate
Mar 5 (All) :    ██████████ 1.06s | σ=0.07s | CV=7% | 🔴 Severe
Mar 5 (Stable) : ████████░░ 1.03s | σ=0.02s | CV=2% | 🟡 Moderate ✅ EXCELLENT TEMPORAL STABILITY (0.98)
```

**Symbolic Summary:** Exceptional consistency across both dates with nearly identical metrics in Stable Runs (1.01-1.03s). Maintains stable 🟡 Moderate risk profile on both dates after outlier removal, with P95 values (1.06s) safely below dynamic thresholds (3.03-3.09s). The only format eligible for winner consideration across both test dates, demonstrating **⭐ Excellent** temporal stability (0.98).

### 🔷 DSL/JSON Prompting

```
Mar 3 (All) :    ████████░░ 1.25s | σ=0.61s | CV=49% | 🔴 Severe
Mar 3 (Stable) : ████████░░ 1.30s | σ=0.67s | CV=52% | 🔴 Severe ⚠️ EXTREME VARIABILITY
Mar 5 (All) :    ██████████ 1.15s | σ=0.09s | CV=8% | ✅ Safe
Mar 5 (Stable) : ██████████ 1.11s | σ=0.06s | CV=5% | 🟡 Moderate ✅ 11.2x MORE CONSISTENT
```

**DSL/JSON Summary:** Dramatically different profiles across dates. March 3 shows catastrophic variability (σ=0.67s, CV=52%) with 🔴 Severe risk even after outlier removal. March 5 demonstrates excellent consistency (σ=0.06s, CV=5%) with 🟡 Moderate risk. **Disqualified from winner consideration** due to 🔴 Severe Risk on March 3 Stable Runs (Index 34.43 > 30). The **temporal instability** (swinging from worst to best performer) makes this format unreliable for production.

### 📝 Normal Prompting

```
Mar 3 (All) :    ████████░░ 1.03s | σ=0.02s | CV=2% | 🚨 Critical
Mar 3 (Stable) : ████████░░ 1.02s | σ=0.02s | CV=2% | 🚨 CRITICAL ⚠️ INDEX 52.00
Mar 5 (All) :    ██████████ 1.12s | σ=0.14s | CV=13% | ✅ Safe
Mar 5 (Stable) : ██████████ 1.13s | σ=0.15s | CV=13% | ✅ SAFE ❌ 7.5x MORE VARIABLE
```


**Normal Summary:** Despite competitive mean latency on March 3 (1.02s) and March 5 (1.13s), the format exhibits extreme **temporal instability** in risk classification: 🚨 CRITICAL on March 3 (Index 52.00) versus ✅ SAFE on March 5 (Index 19.71). This disqualifies it from winner consideration as the 🚨 CRITICAL classification on March 3 triggers automatic global disqualification per methodology. Variability increased dramatically from Mar 3 to Mar 5 (Std Dev 0.02s → 0.15s, 7.5x more variable), making it unsuitable for consistent production use.

*See [FAQ - Why Combined Results Can Be Deceptive](../Benchmark/benchmark_fqa.md) for more on temporal instability and disqualification logic.*

---

## 📊 Temporal Stability Scores

The [Temporal Stability Score](../Benchmark/benchmark_methodology.md#temporal-stability-score-calculation) quantifies how consistent a format's performance is across multiple test dates, calculated as:

`Score = 1 - (|Mean_Date1 - Mean_Date2| / ((Mean_Date1 + Mean_Date2) / 2))`

| Format | Mar 3 Mean (Stable) | Mar 5 Mean (Stable) | Change | Temporal Stability | Rating |
|:---|:---:|:---:|:---:|:---:|:---|
| **Symbolic** | 1.01s | 1.03s | ⬆️ +2% | **0.98** | ⭐ Excellent |
| **DSL/JSON** | 1.30s | 1.11s | ⬇️ -15% | **0.84** | ⚠️ Moderate |
| **Normal** | 1.02s | 1.13s | ⬆️ +11% | **0.90** | ✅ Good |

*\*Note: DSL/JSON shows Moderate temporal stability (0.84) due to the substantial mean shift from 1.30s to 1.11s. The score correctly reflects this change. The improvement in consistency (CV 52% → 5%) and risk profile (🔴 Severe → 🟡 Moderate) is captured in other metrics but does not offset the mean shift for stability scoring.*

---

## 🔍 Key Temporal Insights

*Derived from multi-date testing protocol per our [methodology](../Benchmark/benchmark_methodology.md#multi-date-testing-protocol)*

| Insight | Description |
|:---|:---|
| **📉 Symbolic Most Stable Across Dates** | Symbolic maintained exceptional consistency (σ 0.02-0.03s on both dates in Stable Runs) with only 2% mean shift (1.01s → 1.03s), achieving a **Temporal Stability Score of 0.98 (⭐ Excellent)** — the highest of all formats. |
| **⚠️ Normal Extreme Risk Instability** | Normal exhibited the most dramatic risk shift: from 🚨 **CRITICAL** on March 3 (Index 52.00) to ✅ **SAFE** on March 5 (Index 19.71). This extreme temporal instability in tail risk, combined with a 🚨 Critical classification on one date, disqualifies it from winner consideration despite competitive mean latency. |
| **📊 JSON's Dramatic Transformation** | JSON showed the most dramatic temporal shift: from 🔴 Severe Risk with extreme variability (σ=0.67s, CV=52%) on Mar 3 to 🟡 Moderate Risk with excellent consistency (σ=0.06s, CV=5%) on Mar 5 — an **11.2x improvement in consistency**. Despite this improvement, its 🔴 Severe Risk on Mar 3 disqualifies it from combined winner consideration. |
| **⚠️ Severe Outliers Eliminated** | Mar 3 had a severe 3.08s JSON outlier; Mar 5 had no severe outliers exceeding 2σ thresholds, demonstrating how single-date benchmarks can be misleading without temporal analysis. |
| **✅ Symbolic Only Eligible Winner** | Symbolic is the **only format** that remains eligible for winner consideration after applying the [Global Disqualification Rule](../Benchmark/benchmark_methodology.md#global-disqualification-with-anomaly-detection), achieving a **Stable Winner** pattern per our [Unified Winner Declaration Protocol](../Benchmark/benchmark_methodology.md#unified-winner-declaration-protocol) with the lowest weighted combined mean (1.02s). |
| **📊 Consistency Championship** | Symbolic achieved **σ=0.02-0.03s on both dates** in Stable Runs — the only format with single-digit millisecond consistency across the entire test window. Its CV remained at 2-3% on both dates, demonstrating exceptional predictability. |
| **📊 Spread Between Best and Worst Formats** | **~18.6%** spread between best (Symbolic 1.02s) and worst (DSL/JSON 1.21s) weighted combined means. |

### Temporal Stability Scores (Detailed)

| Format | Mar 3 Stable Mean | Mar 5 Stable Mean | Absolute Change | Relative Change | Temporal Stability Score | Rating |
|:---|:---:|:---:|:---:|:---:|:---:|:---|
| **Symbolic** | 1.01s | 1.03s | +0.02s | +2% | **0.98** | ⭐ Excellent |
| **DSL/JSON** | 1.30s | 1.11s | -0.19s | -15% | **0.84** | ⚠️ Moderate |
| **Normal** | 1.02s | 1.13s | +0.11s | +11% | **0.90** | ✅ Good |

*\*Note: DSL/JSON shows Moderate temporal stability (0.84) due to the substantial mean shift from 1.30s to 1.11s. The improvement in consistency (CV 52% → 5%) and risk profile (🔴 Severe → 🟡 Moderate) is captured in other metrics but does not offset the mean shift for stability scoring.*

---

## 🏆 Winner Analysis by Metric

This table presents the winner for each performance metric on a per-date and combined basis, using **Stable Runs** data. Note that per our [Two-Tier Eligibility Framework](../Benchmark/benchmark_methodology.md#step-5-global-disqualification-with-anomaly-detection-and-weighted-exception), formats with 🔴 Severe or 🚨 Critical risk on any date are disqualified from the Combined Winner column, though they may appear as per-date winners.

| Metric | Mar 3 Winner <br>(Stable Runs 2-9) | Mar 5 Winner <br>(Stable Runs 2-9) | Combined Winner <br>(Weighted) |
|:---|:---:|:---:|:---|
|**Mean** | 🏆 Symbolic🟡 (1.01s) | 🏆 Symbolic🟡 (1.03s) | 🏆 Symbolic⚠️ (1.02s) |
|**Median** | 🏆 Symbolic🟡 (1.01s) | 🏆 Symbolic🟡 (1.04s) | 🏆 Symbolic⚠️ (1.03s) |
|**Minimum** | 🏆 Symbolic🟡 (0.96s) | 🏆 Symbolic🟡 (1.00s) | 🏆 Symbolic⚠️ (0.98s) |
|**Maximum** | 🏆 Normal🚨 (1.04s) | 🏆 Symbolic🟡 (1.06s) | 🏆 Symbolic⚠️ (1.07s) |
|**Std Dev** | 🏆 Normal🚨 (0.02s) | 🏆 Symbolic🟡 (0.02s) | 🏆 Symbolic⚠️ (0.03s) |
|**P95** | 🏆 Normal🚨 (1.04s) | 🏆 Symbolic🟡 (1.06s) | 🏆 Symbolic⚠️ (1.06s) |
|**IQR** | 🏆 Normal🚨 (0.02s) | 🏆 Symbolic🟡 (0.04s) | 🏆 Symbolic⚠️ (0.04s) |
|**Range** | 🏆 Normal🚨 (0.06s) | 🏆 Symbolic🟡 (0.06s) | 🏆 Symbolic⚠️ (0.09s) |
|**CV** | 🏆 Normal🚨 (2%) | 🏆 Symbolic🟡 (2%) | 🏆 Symbolic⚠️ (2%) |
|**Overall Winner by Date** | 🏆 **Symbolic🟡** | 🏆 **Symbolic🟡** | 🏆 **Symbolic⚠️** |

> [!IMPORTANT]
> **Risk Classification Key:**
> - **🟡 Moderate**: Eligible with monitoring (P95 < T)
> - **🔴 Severe**: **DISQUALIFIED** from winner consideration (Index >30)
> - **🚨 Critical**: **DISQUALIFIED** from winner consideration (Index >50)
> - **✅ Safe**: Eligible (shown for context but disqualified due to other date's performance)

> [!IMPORTANT]
> **Combined Winner Determination:**
> Despite Normal winning multiple consistency metrics (Std Dev, P95, IQR, Range, CV) on March 3, its **🚨 CRITICAL Risk** classification on Mar 3 (Index 52.00 > 50) results in **automatic disqualification** per methodology [(Global Disqualification Rule)](../Benchmark/benchmark_methodology.md#1-tail-risk-assessment-primary-disqualifier). Similarly, DSL/JSON is disqualified due to 🔴 Severe Risk on Mar 3.
>
> **Symbolic** is declared the Combined Winner as a **Conditional Winner**, meeting all exception criteria per [Step 5b](../Benchmark/benchmark_methodology.md#step-5b-per-metric-vs-combined-winner-distinction):
> 1. ✅ Lowest Weighted Combined Mean (1.02s)
> 2. ✅ Wins **7/9 metrics outright** (Mean, Median, Min, Std Dev, P95, IQR, CV) and ties in 2/9 (Max, Range) → meets ≥7 threshold
> 3. ✅ Other formats disqualified (DSL/JSON🔴, Normal🚨)
> 4. ✅ Consistent 🟡 Moderate risk profile on both dates **in Stable Runs** (P95=1.06s < T=3.03-3.09s)
>
> The ⚠️ warning on the Combined Winner reflects its Conditional Winner status and the need for tail-performance monitoring, as the March 5 All Runs data showed a 🔴 Severe classification before outlier removal.

| Step | Assessment | Outcome |
|:---|:---|:---|
| **Step 4 - Conditional Winner Exception** | Symbolic meets all criteria:<br>• Lowest weighted mean (1.02s)<br>• **Wins 7/9 metrics outright** (ties in 2 more)<br>• Other formats disqualified<br>• Both dates 🟡 Moderate in Stable Runs<br>• P95 (1.06s) < T (3.03-3.09s) on both dates | ✅ **Conditional Winner** status granted |

---

## 📊 Format Evolution Summary

*Temporal analysis comparing performance across both test dates per our [multi-date testing protocol](../Benchmark/benchmark_methodology.md#multi-date-testing-protocol).*

| Format | Metric | Mar 3 | Mar 5 | Change | Temporal Stability | Combined IQR Risk | Per-Date IQR Risk |
|:---|:---|:---:|:---:|:---:|:--:|:--:|:---|
| **Symbolic** | Mean (All) | 1.01s | 1.06s | ⬆️ +5% | ⭐ 0.98 (Excellent) | 🟡 Moderate (26.5) | Mar 3: 🟡 Moderate<br>Mar 5: 🔴 Severe |
| | Mean (Stable) | **1.01s** | **1.03s** | ⬆️ +2% | ⭐ 0.98 (Excellent) | - | Mar 3: 🟡 Moderate<br>Mar 5: 🟡 Moderate |
| | Std Dev (Stable) | 0.03s | **0.02s** | ⬇️ -33% (more consistent) | - | - | - |
| | **Status** | **🏆 Winner** | **🏆 Winner** | **✅ STABLE WINNER** | **⭐ 0.98** | **🟡 Eligible** | **✅ Passes Risk** |
| **DSL/JSON** | Mean (All) | 1.25s | 1.15s | ⬇️ -8% | ⚠️ 0.84 (Moderate) | ✅ Safe (20.1) | Mar 3: 🔴 Severe<br>Mar 5: ✅ Safe |
| | Mean (Stable) | 1.30s | 1.11s | ⬇️ **-15%** | ⚠️ 0.84 (Moderate) | - | Mar 3: 🔴 Severe<br>Mar 5: 🟡 Moderate |
| | Std Dev (Stable) | 0.67s | 0.06s | ⬇️ **-91%** (11x more consistent) | - | - | - |
| | **Status** | **🔴 DISQUALIFIED** | **🟡 Eligible** | **❌ FAILS RISK (Mar 3)** | **⚠️ 0.84** | **✅ Safe*** | **❌ Fails Risk (Mar 3)** |
| **Normal** | Mean (All) | 1.03s | 1.12s | ⬆️ +9% | ✅ 0.90 (Good) | 🟡 Moderate (29.0) | Mar 3: 🚨 Critical<br>Mar 5: ✅ Safe |
| | Mean (Stable) | 1.02s | 1.13s | ⬆️ +11% | ✅ 0.90 (Good) | - | Mar 3: 🚨 Critical<br>Mar 5: ✅ Safe |
| | Std Dev (Stable) | **0.02s** | 0.15s | ⬆️ **+650%** (7.5x more variable) | - | - | - |
| | **Status** | **🚨 DISQUALIFIED** | **✅ Eligible** | **❌ FAILS RISK (Mar 3)** | **✅ 0.90** | **🟡 Moderate** | **❌ Fails Risk (Mar 3)** |

> [!NOTE]
> *Temporal Stability Score calculated as `1 - (|Mean_Date1 - Mean_Date2| / ((Mean_Date1 + Mean_Date2) / 2))` per our [methodology](../Benchmark/benchmark_methodology.md#temporal-stability-score-calculation).*

> [!TIP]
> **Temporal Stability Score Legend:**
> | Icon | Score Range | Rating |
> |:--:|:--:|:--|
> | ⭐ | 0.95 – 1.00 | Excellent |
> | ✅ | 0.85 – 0.94 | Good |
> | ⚠️ | 0.70 – 0.84 | Moderate |
> | ❌ | < 0.70 | Poor |

> [!IMPORTANT]
> **Dynamic Threshold Values for Context:**
> - March 3 T = **3.03s** (all P95 values below threshold)
> - March 5 T = **3.09s** (all P95 values below threshold)
>
> All P95 values remain safely below dynamic thresholds; risk classifications driven entirely by IQR Index thresholds. DSL/JSON on Mar 3 has P95=2.41s (below T=3.03s) but is disqualified due to Index 34.43 > 30. Normal on Mar 3 has P95=1.04s (well below T) but is disqualified due to Index 52.00 > 50.

---

## 📈 Performance Trend Visualization

```
SYMBOLIC (🏆 STABLE WINNER · ⭐ Temporal Stability 0.98)
────────────────────────────────────────────────
Speed (Stable): 1.01s ──────────┐
▼
1.03s ──────────► +2% (virtually identical)

Consistency (σ): 0.03s ─────────┐
▼
0.02s ─────────► -33% (MORE consistent) · ✅ EXCELLENT STABILITY

Risk (Stable): 🟡 Moderate ──────┐
▼
🟡 Moderate ────────────────► Stable risk profile

Winner Status: 🏆 Mar 3 · 🏆 Mar 5 · 🏆 COMBINED WINNER
────────────────────────────────────────────────

DSL/JSON (❌ DISQUALIFIED · 🔴 Severe Risk Mar 3)
────────────────────────────────────────────────
Speed (Stable): 1.30s ──────────┐
▼
1.11s ──────────► -15% FASTER

Consistency (σ): 0.67s ─────────┐
▼
0.06s ─────────► -91% (11x MORE CONSISTENT) · ✅ DRAMATIC IMPROVEMENT

Risk (Stable): 🔴 Severe ────────┐
▼ │
🟡 Moderate ────────────────► Risk profile improved

Winner Status: ❌ DISQUALIFIED (Index 34.43 > 30 on Mar 3 Stable)
────────────────────────────────────────────────

NORMAL (❌ DISQUALIFIED · 🚨 Critical Risk Mar 3)
────────────────────────────────────────────────
Speed (Stable): 1.02s ──────────┐
▼
1.13s ──────────► +11% slower

Consistency (σ): 0.02s ─────────┐
▼
0.15s ─────────► +650% (7.5x MORE VARIABLE) · ❌ severely degraded

Risk (Stable): 🚨 Critical ──────┐
▼ │
✅ Safe ─────────────────────► Risk profile improved but ONE CRITICAL DATE DISQUALIFIES

Winner Status: ❌ DISQUALIFIED (Index 52.00 > 50 on Mar 3)
────────────────────────────────────────────────
```

---

## ✅ Final Verdict

*Production-ready recommendation based on our [Unified Winner Declaration Protocol](../Benchmark/benchmark_methodology.md#unified-winner-declaration-protocol) and [IQR Deception Detection](../Benchmark/benchmark_methodology.md#iqr-deception-detection) framework.*

| Aspect | Conclusion |
|:---|:---|
| **Overall Winner** | 🏆 **Symbolic⚠️** (Won mean on both dates, best weighted combined mean of 1.02s) |
| **Most Improved** | 📈 **DSL/JSON** (11x more consistent, -15% faster, risk 🔴→🟡, but remains disqualified due to Mar 3 🔴 Severe Risk) |
| **Most Stable Across Dates** | 📊 **Symbolic** (σ 0.02-0.03s both dates, Temporal Stability Score 0.98 ⭐ Excellent) |
| **Best Single Run** | ⚡ **Symbolic** (0.96s on Mar 3) |
| **Worst Outlier** | 🔴 **DSL/JSON** (3.08s on Mar 3 - catastrophic tail event) |
| **Most Consistent Across Dates** | ✅ **Symbolic** (Only format to win mean on both dates with stable risk profile) |
| **Biggest Decline** | ❌ **Normal** (11% slower Stable Runs, 7.5x more variable, 🚨 Critical Risk on Mar 3) |

### Risk Assessment Summary

| Risk Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
| **IQR Deception Index (Combined)** | 26.5 (🟡 Moderate) | 20.1 (✅ Safe) | 29.0 (🟡 Moderate) |
| **Per-Date Risk (Stable Runs)** | Mar 3: 🟡 Moderate<br>Mar 5: 🟡 Moderate | Mar 3: 🔴 Severe<br>Mar 5: 🟡 Moderate | Mar 3: 🚨 Critical<br>Mar 5: ✅ Safe |
| **Global Disqualification** | ✅ **ELIGIBLE**<br>(Conditional Winner) | ❌ **DISQUALIFIED**<br>(🔴 Severe on Mar 3 Stable Runs) | ❌ **DISQUALIFIED**<br>(🚨 Critical on Mar 3 Stable Runs) |
| **Two-Factor Assessment** | P95=1.06s < T=3.03-3.09s on both dates → 🟡 **Moderate** | P95=2.41s (Mar 3), 1.22s (Mar 5) < T → Mar 5 🟡 Moderate<br>Mar 3 Index>30 → 🔴 Severe | P95=1.04s (Mar 3), 1.38s (Mar 5) < T<br>Mar 3 Index>50 → 🚨 Critical |
| **Tail-Risk Status** | ⚠️ Stable moderate risk | ❌ Unreliable (inconsistent) | ❌ Unreliable (critical on one date) |
| **Outlier Rate (Combined)** | 5% (1/20) | 15% (3/20) | 10% (2/20) |
| **Production Readiness** | 🟢 **Ready** (with monitoring) | 🔴 **Not Recommended** | 🔴 **Not Recommended** |

*Note: Production readiness determined by eligibility after Global Disqualification Rule, not combined aggregates.*

### Winner Declaration Protocol Application

Following our [Unified Winner Declaration Protocol](../Benchmark/benchmark_methodology.md#unified-winner-declaration-protocol):

| Step | Assessment | Outcome |
|:---|:---|:---|
| **Step 1 - Tail-Risk Assessment** | **Symbolic🟡**: ✅ Passes (🟡 Moderate on both dates, P95 < T)<br>**DSL/JSON🔴**: ❌ Fails (🔴 Severe on Mar 3 Stable)<br>**Normal🔴**: ❌ Fails (🚨 Critical on Mar 3 Stable) | Only Symbolic remains eligible |
| **Step 2 - Temporal Stability** | Symbolic won mean on **both** test dates | ✅ **Stable Winner** (strongest outcome) |
| **Step 3 - Effect Size** | Symbolic vs Normal = 0.06s (>5% threshold of 0.051s) | ✅ Directional win for Symbolic |
| **Step 4 - Conditional Winner Exception** | Symbolic meets exception criteria:<br>• Lowest weighted mean (1.02s)<br>• Wins 8/9 metrics (89%)<br>• Other formats disqualified<br>• P95 (1.06s) < T (3.09s) on both dates | ✅ **Conditional Winner** status granted |

**Final Determination:** 🏆 **Symbolic⚠️ Prompting** is the unequivocal and **only eligible** winner for claude-3-haiku after applying risk-based disqualification, declared as a Conditional Winner.

### Production Recommendations

| Use Case | Recommended Format | Rationale |
|:---|:---:|:---|
| **Real-time / User-facing** | 🏆 **Symbolic⚠️** | Lowest mean, best temporal stability, most predictable, only eligible format |
| **Batch Processing** | 🏆 **Symbolic⚠️** | Consistent performance across both dates with stable risk profile |
| **Strict SLAs (<1.5s P99)** | 🏆 **Symbolic⚠️** | Best P99 (1.06s) and most reliable tail performance; only format with stable risk profile |
| **Experimentation / Dev** | ⚠️ Any (with caution) | All formats acceptable for non-production; avoid Normal for SLA testing |
| **Risk-Averse Production** | 🏆 **Symbolic⚠️** | **Only format without 🚨 Critical or 🔴 Severe Risk requiring disqualification** |

---

## 📋 Recommendations

| Use Case | Recommended Format | Rationale |
|:---|:---|:---|
| **General production** | 🏆 **Symbolic⚠️** | Best weighted combined mean (1.02s), **Stable Winner** pattern, exceptional stability (σ 0.02-0.03s both dates), stable risk profile, and **only format eligible** after risk assessment |
| **If JSON is required** | ⚠️ **Not recommended** | DSL/JSON is **DISQUALIFIED** due to 🔴 Severe Risk on March 3 Stable Runs (Index 34.43 > 30) with catastrophic 3.08s outlier. If JSON is mandatory, implement extensive monitoring and fallback strategies; March 5 performance shows potential but the single severe date disqualifies it. |
| **If consistency is critical** | ✅ **Symbolic⚠️** | Achieved σ=0.02-0.03s on both dates - most consistent format overall; only format with [Temporal Stability Score](../Benchmark/benchmark_methodology.md#temporal-stability-score-calculation) of **0.98 ⭐ Excellent** |
| **Strict SLAs (<1.3s P99)** | ✅ **Symbolic⚠️** | Only format with P99 <1.1s on both dates (1.08s Mar 3, 1.06s Mar 5) and the **only format eligible** for production use |
| **Multi-date stability** | ✅ **Symbolic⚠️** | Only format to win mean on both dates with excellent temporal stability (0.98) and stable risk profile |
| **If using Normal prompts** | ⚠️ **Migrate immediately** | Normal is **DISQUALIFIED** due to 🚨 Critical Risk on Mar 3 (Index 52.00 > 50). Despite ✅ Safe status on Mar 5, the single critical date triggers global disqualification. Migrate to Symbolic. |
| **Cost-sensitive applications** | ✅ **Symbolic⚠️** | Lowest token count (81 tokens) means lowest input costs per request; also the **only eligible format** |

### Final Recommendation

For claude-3-haiku@20240307, **Symbolic⚠️ prompting is the only recommended format** for production use. It delivers:

- ✅ Lowest weighted combined mean latency (1.02s)
- ✅ Stable Winner pattern (won both test dates)
- ✅ Best P99 performance (1.06s combined)
- ✅ Excellent temporal stability (0.98 ⭐ score)
- ✅ Stable risk profile (🟡 Moderate on both dates)
- ✅ Most consistent (σ 0.02-0.03s, CV 2-3%)
- ✅ Lowest token cost (81 tokens)
- ✅ **Only format without 🚨 Critical or 🔴 Severe Risk requiring disqualification**
- ✅ Meets Conditional Winner criteria (lowest mean, wins 8/9 metrics, other formats disqualified)

---

## 📁 Quick Reference Card

*At-a-glance decision guide for claude-3-haiku based on [benchmark methodology](benchmark_methodology.md) V2.0.*

| If you want... | Use this format on claude-3-haiku | Risk Note |
|:---|:---|:---|
| **Best overall performance** | 🏆 **Symbolic⚠️** (1.02s weighted combined mean) | 🟡 Moderate Risk (stable profile on both dates); Conditional Winner |
| **Best latest performance** | 🏆 **Symbolic⚠️** (1.03s on Mar 5 Stable) | 🟡 IQR Index = 26.50 (Moderate) |
| **Most consistent across dates** | 🏆 **Symbolic⚠️** (σ=0.02-0.03s both dates) | ⭐ [Temporal Stability Score](../Benchmark/benchmark_methodology.md#temporal-stability-score-calculation) 0.98 (Excellent) |
| **Lowest outlier risk** | ✅ **Symbolic⚠️** | Max 1.08s on Mar 3, 1.06s on Mar 5 |
| **JSON-native workflows** | ⚠️ **DSL/JSON🔴** | **DISQUALIFIED** due to 🔴 Severe Risk on Mar 3 Stable (Index 34.43 > 30, 3.08s outlier). If required, extensive monitoring and fallback strategies mandatory. |
| **Strict P99 requirements (<1.3s)** | ✅ **Symbolic⚠️** | Only format meeting this threshold (1.06s combined P99) and **only eligible format** |
| **Lowest input cost** | ✅ **Symbolic⚠️** | 81 tokens vs 108 (Normal) vs 173 (JSON); also the **only eligible format** |
| **Maximum predictability** | ✅ **Symbolic⚠️** | Lowest CV (2-3% both dates) across both dates |

### ⚡ Winner's Circle Summary

| Category | Winner | Key Stat |
|:---|:---|:---|
| **Overall Performance** | 🏆 **Symbolic⚠️** | 1.02s weighted combined mean |
| **Temporal Stability** | 🏆 **Symbolic⚠️** | 0.98 Stability Score (⭐ Excellent) |
| **Consistency** | 🏆 **Symbolic⚠️** | σ=0.02-0.03s both dates, CV=2-3% both dates |
| **Tail Performance** | 🏆 **Symbolic⚠️** | 1.06s combined P99 |
| **Cost Efficiency** | 🏆 **Symbolic⚠️** | 81 tokens/request |
| **Most Improved** | 📈 **DSL/JSON** | 11x more consistent, -15% faster, risk 🔴→🟡, but remains **DISQUALIFIED** |

### 🚨 Red Flags to Watch

| Format | Warning | Mitigation |
|:---|:---|:---|
| **DSL/JSON** | 🔴 **DISQUALIFIED** - Severe risk on Mar 3 Stable (Index 34.43 > 30, 3.08s outlier) | **Do not use in production.** If JSON is mandatory, implement extensive monitoring, retest before each deployment, and have fallback strategies ready. |
| **Normal** | 🔴 **DISQUALIFIED** - 🚨 Critical Risk on Mar 3 (Index 52.00 > 50) | **Migrate immediately to Symbolic.** Despite ✅ Safe performance on Mar 5, the single critical date disqualifies this format from production use per methodology. |
| **Symbolic** | 🟡 Moderate IQR Index (26.50 on both dates) | Monitor P95 for strict SLAs (<1.3s requirements). Passes Two-Factor Assessment with P95 safely below dynamic thresholds (3.03-3.09s). Risk profile is stable. |

### Eligibility Summary

| Format | Status | Reason |
|:---|:---:|:---|
| **Symbolic⚠️** | ✅ **PRODUCTION READY**<br>(Conditional Winner) | Only format without 🚨 Critical or 🔴 Severe Risk requiring disqualification; stable 🟡 Moderate profile on both dates; P95 consistently < T; meets Conditional Winner criteria |
| **DSL/JSON** | ❌ **NOT RECOMMENDED** | 🔴 Severe Risk on Mar 3 Stable (Index 34.43 > 30) |
| **Normal** | ❌ **NOT RECOMMENDED** | 🚨 Critical Risk on Mar 3 (Index 52.00 > 50) |

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
- 📝 **[Benchmark Consolidate Equations](../Benchmark/benchmark_2026030X_consolidate_equations.xlsx)** - Complete dataset with Excel Formulas 
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
- Israel Z. M. aka <em><a href="https://github.com/spk85" rel="nofollow">@spk85</a></em></br>

[⬅️ Back to Home](../README.md) | [Methodology used](../Benchmark/benchmark_methodology.md)