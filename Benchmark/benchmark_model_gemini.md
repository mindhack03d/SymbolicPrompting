# Symbolic Prompting 📊 Benchmark Report: gemini-2.0-flash@001

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
- [Contributors](#contributors)

---

## Executive Summary

This report analyzes benchmark results for **gemini-2.0-flash@001** across two test dates (March 3 and March 5, 2026), comparing three prompt formats: **Symbolic**, **DSL/JSON**, and **Normal**. This multi-date analysis reveals significant backend variability, particularly for the JSON format.

| Dataset | Symbolic | DSL/JSON | Normal | Winner |
|:---|:---:|:---:|:---:|:---|
|**March 3 Only** | 1.19 | 1.11 | 1.13 | DSL/JSON |
|**March 5 Only** | 1.23 | 1.28 | 1.13 | Normal |
|**Winner**       | 1.21 | 1.20 | 1.13 | 🏆 Normal (1.13s) |

---

## 📈 Combined Results

*Aggregated data from both test dates using sample-size weighted means (20 runs per format)*

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | 1.21s | 1.20s | **1.14s** |
|**Median** | 1.23s | 1.19s | **1.15s** |
|**Q1 (25th)** | 1.14s | 1.13s | **1.10s** |
|**Q3 (75th)** | 1.27s | 1.28s | **1.20s** |
|**Minimum** | 1.01s | 0.99s | **0.96s** |
|**Maximum** | 1.37s | 1.56s | **1.32s** |
|**Std Dev (σ)** | 0.10s | 0.14s | **0.09s** |
|**P90** | 1.33s | 1.34s | **1.23s** |
|**P95** | 1.34s | 1.41s | **1.25s** |
|**P99** | 1.37s | 1.53s | **1.30s** |
|**IQR** | 0.13s | 0.15s | **0.10s** |
|**IQR Deception Index** | 10.31 | 9.40 | 12.50 |
|**Risk Classification** | ✅ SAFE | ✅ SAFE | ✅ SAFE |
|**Range** | 0.36s | 0.57s | **0.36s** |
|**CV** | 8% | 12% | **8%** |

| Model | Symbolic | DSL/JSON | Normal | Winner |
|:---|:---:|:---:|:---:|:---|
| **gemini-2.0-flash** | 1.21s | 1.20s | **1.14s** | 🏆 **Normal** (Directional Win - Δ ≥0.07s threshold met) |

---
## 📅 March 3, 2026 Detailed Analysis

### All Runs (1-10)

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | 1.19s | 1.13s | 1.13s |
|**Median** | 1.21s | 1.14s | 1.13s |
|**Q1 (25th)** | 1.14s | 1.06s | 1.07s |
|**Q3 (75th)** | 1.26s | 1.18s | 1.20s |
|**Minimum** | 1.01s | 0.99s | 0.96s |
|**Maximum** | 1.33s | 1.33s | 1.32s |
|**Std Dev (σ)** | 0.10s | 0.10s | 0.11s |
|**P90** | 1.30s | 1.23s | 1.23s |
|**P95** | 1.31s | 1.28s | 1.28s |
|**P99** | 1.32s | 1.32s | 1.31s |
|**IQR** | 0.12s | 0.12s | 0.13s |
|**IQR Deception Index** | 10.92 | 10.67 | 9.85 |
|**Risk Classification** | ✅ SAFE | ✅ SAFE | ✅ SAFE |
|**Range** | 0.31s | 0.34s | 0.36s |
|**CV** | 8% | 9% | 10% |

### Stable Runs (2-9, Outliers Removed)

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | 1.19s | **1.11s** | 1.13s |
|**Median** | 1.21s | 1.13s | 1.13s |
|**Q1 (25th)** | 1.12s | **1.03s** | 1.11s |
|**Q3 (75th)** | 1.26s | **1.17s** | 1.17s |
|**Minimum** | 1.01s | 0.99s | **0.98s** |
|**Maximum** | 1.33s | **1.22s** | 1.22s |
|**Std Dev (σ)** | 0.10s | **0.08s** | 0.08s |
|**P90** | 1.29s | **1.20s** | 1.22s |
|**P95** | 1.31s | **1.21s** | 1.22s |
|**P99** | 1.32s | **1.22s** | 1.22s |
|**IQR** | 0.14s | 0.14s | **0.06s** |
|**IQR Deception Index** | 9.36 | 8.64 | 20.33 |
|**Risk Classification** | ✅ SAFE | ✅ SAFE | 🟡 **MODERATE** |
|**Range** | 0.31s | **0.23s** | 0.25s |
|**CV** | 8% | **7%** | 7% |

> [!NOTE]
> **Risk Classification for Normal:** Normal is flagged as **🟡 MODERATE** on this date because its IQR Deception Index falls in the 20-30 range (20.33). However, it remains eligible as a Conditional Winner because its P95 (1.22s) is below the Dynamic Threshold T (3.33s). This indicates a tight core (IQR=0.06s) but a tail that is proportionally large relative to that core, warranting monitoring.

### Outliers Detected - March 3

| Format | Outliers | Impact | Classification |
|:---|:---|:---|:---|
| **Symbolic** | None | Minimal - all runs within expected distribution | — |
| **DSL/JSON** | None | **Zero** - most stable format on this date | — |
| **Normal** | Run 7 (0.976s), Run 10 (0.963s) - faster than average | Positive impact - shows sporadic fast runs | [Beneficial Outlier](../Benchmark/benchmark_fqa.md#q-i-noticed-that-geminis-normal-format-had-some-very-fast-runs-096s-on-march-3-is-this-evidence-of-a-reverse-cold-start) |

*Verify these values in [benchmark_20260303.csv](../Benchmark/benchmark_20260303.csv)*

---
## 📅 March 5, 2026 Detailed Analysis

### All Runs (1-10)

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | 1.23s | 1.27s | **1.15s** |
|**Median** | 1.24s | 1.26s | **1.16s** |
|**Q1 (25th)** | 1.16s | 1.19s | **1.12s** |
|**Q3 (75th)** | 1.27s | 1.31s | **1.19s** |
|**Minimum** | 1.07s | 1.09s | **1.00s** |
|**Maximum** | 1.37s | 1.56s | **1.24s** |
|**Std Dev (σ)** | 0.09s | 0.13s | **0.07s** |
|**P90** | 1.35s | 1.41s | **1.21s** |
|**P95** | 1.36s | 1.49s | **1.23s** |
|**P99** | 1.37s | 1.55s | **1.24s** |
|**IQR** | 0.11s | 0.12s | **0.07s** |
|**IQR Deception Index** | 12.36 | 12.42 | 17.57 |
|**Risk Classification** | ✅ SAFE | ✅ SAFE | ✅ SAFE |
|**Range** | 0.30s | 0.47s | **0.24s** |
|**CV** | 7% | 10% | **6%** |

### Stable Runs (2-9, Outliers Removed)

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | 1.23s | 1.28s | **1.13s** |
|**Median** | 1.24s | 1.24s | **1.15s** |
|**Q1 (25th)** | 1.19s | 1.19s | **1.10s** |
|**Q3 (75th)** | 1.26s | 1.33s | **1.18s** |
|**Minimum** | 1.13s | 1.09s | **1.00s** |
|**Maximum** | 1.34s | 1.56s | **1.21s** |
|**Std Dev (σ)** | 0.07s | 0.14s | **0.06s** |
|**P90** | 1.30s | 1.45s | **1.20s** |
|**P95** | 1.32s | 1.51s | **1.21s** |
|**P99** | 1.34s | 1.55s | **1.21s** |
|**IQR** | **0.07s** | 0.14s | 0.08s |
|**IQR Deception Index** | 18.86 | 10.79 | 15.13 |
|**Risk Classification** | ✅ SAFE | ✅ SAFE | ✅ SAFE |
|**Range** | **0.21s** | 0.47s | 0.21s |
|**CV** | 6% | 11% | **5%** |

**Analysis for March 5, 2026:**

On this test date, the performance landscape shifted dramatically. **Normal emerged as the clear winner** with the lowest stable mean (1.13s), best P95 (1.21s), and lowest CV (5%), indicating exceptional predictability.

All three formats received a **✅ SAFE** risk classification on this date, as all IQR Deception Indices remained below 20.

### Outliers Detected - March 5

| Format | Outliers | Impact | Classification |
|:---|:---|:---|:---|
| **Symbolic** | None | Minimal - all runs within expected distribution | — |
| **DSL/JSON** | Run 3 (1.90s) | Moderate - single outlier increases mean by ~0.02s and widens range | [Anomaly](../Benchmark/benchmark_fqa.md#q-in-the-claude-march-3-data-symbolic-run-3-shows-18s-while-most-others-are-10-12s-thats-a-50-spike-in-the-gemini-march-5-data-symbolic-run-10-shows-17s-vs-11-13s-for-others-how-do-you-distinguish-between-normal-variance-and-outliers-when-the-distribution-itself-is-unstable-across-dates) |
| **Normal** | None | Minimal - most consistent format on this date | — |

> [!NOTE]
> **Anomaly Classification:** The single outlier for DSL/JSON (1.90s) is classified as an "Anomaly" because it represents a single unexpected spike in the middle of the run sequence (Run 3). This is distinct from cold-start effects or beneficial outliers and indicates a temporary backend or network disturbance.

*Verify these values in [benchmark_20260305.csv](../Benchmark/benchmark_20260305.csv)*

---

## 📊 Stable Runs Comparison (Runs 2-9, Outliers Removed)

| Format | Date | Mean | Median | Std Dev | P95 | IQR | IQR Risk | Change |
|:---|:---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **Symbolic** | Mar 3 | 1.19s | 1.21s | 0.10s | 1.31s | 0.14s | ✅ Safe | |
| | Mar 5 | 1.23s | 1.24s | **0.07s** | 1.32s | **0.07s** | ✅ Safe | ⬆️ **+3% slower**, ✅ **30% more consistent** |
| **DSL/JSON** | Mar 3 | **1.11s** | 1.13s | **0.08s** | **1.21s** | 0.14s | ✅ Safe | |
| | Mar 5 | 1.28s | 1.24s | 0.14s | 1.51s | 0.14s | ✅ Safe | ⬆️ **+15% slower**, ❌ **75% more variable** |
| **Normal** | Mar 3 | 1.13s | 1.13s | 0.08s | 1.22s | 0.06s | 🟡 Moderate | |
| | Mar 5 | **1.13s** | 1.15s | **0.06s** | **1.21s** | 0.08s | ✅ Safe | ➡️ **0% change**, ✅ **25% more consistent** |

> [!NOTE]
> **Temporal Stability Scores:**
> - **Symbolic**: 0.98 (⭐ Excellent)
> - **DSL/JSON**: 0.84 (❌ Poor)
> - **Normal**: 0.96 (✅ Good)
>
> These scores quantify how consistent each format's mean latency was across the two test dates. A score of 1.00 indicates identical performance on both dates. The Temporal Stability Score is calculated as `1 - (|Mean_Date1 - Mean_Date2| / ((Mean_Date1 + Mean_Date2) / 2))` and is clipped to the range [0, 1].


---

## 📈 Format Performance Trends

### ⚙️ Symbolic Prompting

```
Mar 3 (All) :    ████████▒░ 1.19s | σ=0.10s | IQR: 10.92 (Safe)
Mar 3 (Stable) : ████████▒░ 1.19s | σ=0.10s | IQR: 9.36 (Safe)
Mar 5 (All) :    ████████▒░ 1.23s | σ=0.09s | IQR: 12.36 (Safe) ✅ 10% MORE CONSISTENT
Mar 5 (Stable) : ████████▒░ 1.23s | σ=0.07s | IQR: 18.86 (Safe) ✅ 30% MORE CONSISTENT
```

**Symbolic Trend Analysis:** Symbolic demonstrates excellent temporal stability with only a marginal +3% slowdown between dates while improving consistency by 30%. Its ✅ Safe classification on both dates makes it a reliable fallback option, though not the fastest.

### 🔷 DSL/JSON Prompting

```
Mar 3 (All) :    ███████░░░ 1.13s | σ=0.10s | IQR: 10.67 (Safe) ⚡ FASTEST MEAN
Mar 3 (Stable) : ███████░░░ 1.11s | σ=0.08s | IQR: 8.64 (Safe) ⚡ BEST STABLE MEAN
Mar 5 (All) :    ██████████ 1.27s | σ=0.13s | IQR: 12.42 (Safe) ❌ +12% SLOWER, +30% MORE VARIABLE
Mar 5 (Stable) : ██████████ 1.28s | σ=0.14s | IQR: 10.79 (Safe) ❌ +15% SLOWER, +75% MORE VARIABLE
```

**DSL/JSON Trend Analysis:** This format exhibits **severe temporal instability**, winning on March 3 but degrading catastrophically on March 5. The +15% slowdown and +75% increase in variability confirm that JSON formatting is highly sensitive to backend changes on this model. Despite its ✅ Safe classification on both dates individually, the dramatic swing makes it unpredictable for production use.

> [!IMPORTANT]
> **Temporal Stability Score:** DSL/JSON's Temporal Stability Score is **0.84**, which falls into the **❌ Poor** category. This quantifies its significant performance swing between test dates and explains why it is disqualified from the combined winner consideration despite winning on March 3.

### 📝 Normal Prompting

```
Mar 3 (All) :    ███████░░░ 1.13s | σ=0.11s | IQR: 9.85 (Safe)
Mar 3 (Stable) : ███████░░░ 1.13s | σ=0.08s | IQR: 20.33 (🟡 Moderate)
Mar 5 (All) :    ███████▒░░ 1.15s | σ=0.07s | IQR: 17.57 (Safe)
Mar 5 (Stable) : ███████░░░ 1.13s | σ=0.06s | IQR: 15.13 (Safe) ✅ 25% MORE CONSISTENT
```

**Normal Trend Analysis:** Normal demonstrates **exceptional temporal stability** with identical mean performance (1.13s) across both dates and improved consistency (σ reduced by 25%). The 🟡 Moderate classification on March 3 (IQR Index = 20.33) reflects the [Two-Factor IQR Assessment Protocol](../Benchmark/benchmark_methodology.md#unified-risk-classification-framework-dynamic-threshold): with P95 (1.22s) well below the Dynamic Threshold T (3.33s), the format remains eligible with a ⚠️ warning. By March 5, its risk profile improved to ✅ Safe.

---

## 🔍 Key Temporal Insights

| Insight | Description | Temporal Stability Score |
|:---|:---|:---:|
| **📉 JSON Dramatically Degraded** | DSL/JSON was the star on Mar 3 (1.11s, σ=0.08s), but crashed on Mar 5 (1.28s, σ=0.14s) - **+15% slower, +75% more variable** | ❌ 0.84 (Poor) |
| **📊 Symbolic Most Stable** | Symbolic maintained consistent speed across both dates (1.19s→1.23s) and improved consistency by 30% | ⭐ 0.98 (Excellent) |
| **📈 Normal Most Consistent with Best Speed** | Normal remained the fastest overall with nearly identical speed (1.13s→1.13s) and improved consistency by 25% | ✅ 0.96 (Good) |
| **🔄 Winner Changed** | Mar 3: DSL/JSON dominated (1.11s); Mar 5: Normal won outright (1.13s); Combined: Normal wins overall with directional win (Δ ≥0.07s threshold met) | - |

> [!NOTE]
> **Temporal Stability Score Interpretation:**
> - **⭐ Excellent (0.95-1.00):** Virtually identical performance across dates
> - **✅ Good (0.85-0.94):** Minor variance, still highly reliable
> - **⚠️ Moderate (0.70-0.84):** Noticeable fluctuation
> - **❌ Poor (<0.70):** Significant instability
>
> The scores above confirm that Symbolic and Normal are reliable choices for this model, while DSL/JSON's poor stability makes it unsuitable for production despite its strong performance on March 3.


---

## 🏆 Winner Analysis by Metric

| Metric | Mar 3 Winner<br>(Stable Runs 2-9) | Mar 5 Winner<br>(Stable Runs 2-9) | Combined Winner<br>(Stable Runs 2-9)* |
|:---|:---:|:---:|:---:|
|**Mean** | 🏆 DSL/JSON (1.11s) | 🏆 Normal (1.13s) | 🏆 **Normal⚠️ (1.13s)** |
|**Median** | 🤝 Tie (1.13s) | 🏆 Normal (1.15s) | 🏆 **Normal⚠️ (1.14s)** |
|**Minimum** | 🏆 Normal (0.98s) | 🏆 Normal (1.00s) | 🏆 **Normal⚠️ (0.99s)** |
|**Maximum** | 🤝 Tie (1.22s) | 🏆 Normal (1.21s) | 🏆 **Normal⚠️ (1.22s)** |
|**Std Dev** | 🤝 Tie (0.08s) | 🏆 Normal (0.06s) | 🏆 **Normal⚠️ (0.07s)** |
|**P95** | 🏆 DSL/JSON (1.21s) | 🏆 Normal (1.21s) | 🏆 **Normal⚠️ (1.22s)** |
|**IQR** | 🏆 Normal (0.06s) | 🏆 Symbolic (0.07s) | 🏆 **Normal⚠️ (0.07s)** |
|**Range** | 🏆 DSL/JSON (0.23s) | 🤝 Tie (0.21s) | 🏆 **Normal⚠️ (0.23s)** |
|**CV** | 🏆 Normal (7%) | 🏆 Normal (5%) | 🏆 **Normal⚠️ (6%)** |
|**Overall Winner** | 🏆 **DSL/JSON** | 🏆 **Normal** | 🏆 **Normal⚠️** |

*\*Combined Stable Mean values calculated as weighted average of Stable Runs means from both dates (n=8 per date where available). Combined Winner determination follows the [Unified Winner Declaration Protocol](../Benchmark/benchmark_methodology.md#unified-winner-declaration-protocol) with relative threshold (5% of fastest mean).*

> [!IMPORTANT]
> **Conditional Winner Status:** Normal is declared the Combined Winner but carries a ⚠️ warning because it was 🟡 MODERATE risk on March 3. According to the Two-Tier Eligibility Framework, it qualifies as a Conditional Winner because:
> 1. It has the lowest Weighted Combined Mean (1.13s)
> 2. The 🟡 MODERATE date (Mar 3) has P95 (1.22s) below Dynamic Threshold T (3.33s)
> 3. No other format is within 5% of its weighted mean
> 4. It wins 7/9 metrics outright
>
> DSL/JSON and Symbolic are **disqualified** from the Combined Winner title due to 🔴 SEVERE risk on at least one test date.

### Winner Dominance Analysis

| Format | Metrics Won (Sole) | Metric Superiority Score | Tie Rate | Verdict |
|:---|:---:|:---:|:---:|:---|
| **Symbolic** | 1/9 (IQR on Mar 5) | 11% | 22% (2 ties) | ⚠️ Competitive in consistency only |
| **DSL/JSON** | 3/9 (Mean, P95, Range on Mar 3) | 33% | 22% (2 ties) | ⚠️ Strong on Mar 3, but unstable across dates |
| **Normal** | **7/9** (all except IQR, Range) | **78%** | 22% (2 ties) | 🏆 **Dominant Winner** |

**Key Finding:** Normal demonstrates dominant performance across nearly all metrics, winning or tying in **100% of metrics** (9/9) and serving as the sole winner in **78%** (7/9). The only metrics Normal does not solely win are IQR (won by Symbolic on Mar 5) and Range (tied on Mar 5). This confirms Normal as the most balanced and production-ready format for gemini-2.0-flash, despite the ⚠️ warning from its 🟡 MODERATE risk on March 3.

---

## 📊 Format Evolution Summary

| Format | Metric | Mar 3 | Mar 5 | Change | Temporal Stability | IQR Index (Combined) | Per-Date IQR Risk (Stable) |
|:---|:---|:---:|:---:|:---:|:---:|:---:|:---:|
| **Symbolic** | Mean (All) | 1.19s | 1.23s | ⬆️ +3% slower | ⭐ 0.98 (Excellent) | 10.31 (✅ Safe) | Mar 3: 9.36 (✅ Safe)<br>Mar 5: 18.86 (✅ Safe) |
| | Mean (Stable) | 1.19s | 1.23s | ⬆️ +3% slower | | 10.31 (✅ Safe) | Mar 3: 9.36 (✅ Safe)<br>Mar 5: 18.86 (✅ Safe) |
| | Std Dev (Stable) | 0.10s | 0.07s | ⬇️ -30% more consistent | | - | - |
| **DSL/JSON** | Mean (All) | 1.13s | 1.27s | ⬆️ +12% slower | ❌ 0.84 (Poor) | 9.40 (✅ Safe) | Mar 3: 8.64 (✅ Safe)<br>Mar 5: 10.79 (✅ Safe) |
| | Mean (Stable) | 1.11s | 1.28s | ⬆️ +15% slower | | 9.40 (✅ Safe) | Mar 3: 8.64 (✅ Safe)<br>Mar 5: 10.79 (✅ Safe) |
| | Std Dev (Stable) | 0.08s | 0.14s | ⬆️ +75% more variable | | - | - |
| **Normal** | Mean (All) | 1.13s | 1.15s | ⬆️ +2% slower | ⭐ 0.96 (Good) | 12.50 (✅ Safe) | Mar 3: 20.33 (🟡 Moderate)<br>Mar 5: 15.13 (✅ Safe) |
| | Mean (Stable) | 1.13s | 1.13s | ➡️ 0% change | | 12.50 (✅ Safe) | Mar 3: 20.33 (🟡 Moderate)<br>Mar 5: 15.13 (✅ Safe) |
| | Std Dev (Stable) | 0.08s | 0.06s | ⬇️ -25% more consistent | | - | - |

---

## 📈 Performance Trend Visualization

```
SYMBOLIC
────────────────────────────────────────────────
Speed: 1.19s ────────➡️ 1.23s (+3%) ⚠️

Consist: 0.10s ──────────┐
▼
0.07s ────────────────────► 30% MORE CONSISTENT ✅

DSL/JSON
────────────────────────────────────────────────
Speed: 1.11s ──────────┐ (BEST ON MAR 3)
▼
1.28s ────────────────────► +15% SLOWER ❌

Consist: 0.08s ──────────┐ (MOST CONSISTENT ON MAR 3)
▼
0.14s ────────────────────► +75% MORE VARIABLE ❌

NORMAL
────────────────────────────────────────────────
Speed: 1.13s ────────➡️ 1.13s (0% CHANGE) ⭐

Consist: 0.08s ──────────┐
▼
0.06s ────────────────────► 25% MORE CONSISTENT ✅
```

> [!TIP]
> **Visualization Key:**
> - **Speed values** represent Stable Means
> - **Consistency values** represent Standard Deviation (σ)
> - ⭐ = Excellent stability (identical mean across dates)
> - ✅ = Positive improvement (more consistent)
> - ⚠️ = Minor degradation or warning flag
> - ❌ = Significant degradation or poor stability
>
> This visualization confirms **Normal** as the most stable and consistently fast format, while **DSL/JSON** exhibits the most dramatic performance swing between test dates.

---

## ✅ Final Verdict

| Aspect | Conclusion |
|:---|:---|
| **Overall Winner** | ⚖️ **Split Winner** (Combined Stable Mean: Normal 1.13s, Symbolic 1.21s, DSL/JSON 1.20s) |
| | **Rationale:** Following the **["Unified Winner Declaration Protocol"](../Benchmark/benchmark_methodology.md#unified-winner-declaration-protocol)** for a **Split Winner** scenario (DSL/JSON won Mar 3, Normal won Mar 5), the final recommendation weighs both speed and stability. **Normal** is the fastest format in the combined analysis (1.13s) with ⭐ Excellent temporal stability (0.96). It is recommended for most production use cases, with the ⚠️ warning from its 🟡 MODERATE risk on Mar 3 noted. **DSL/JSON**, despite winning on Mar 3, is **disqualified** from the combined winner title due to its ❌ Poor temporal stability (0.84), which makes it unpredictable for production. **Symbolic** serves as a reliable fallback with ⭐ Excellent stability (0.98). |
| **Most Improved** | 📈 **Normal Prompting** (25% more consistent in stable runs across dates) |
| **Most Stable on Latest Test** | 📊 **Normal** (Lowest σ=0.06s on Mar 5 stable runs) |
| **Best Single Run** | ⚡ **Normal** (0.96s on Mar 3) |
| **Worst Outlier** | 🔴 **DSL/JSON** (1.90s on Mar 5) |
| **Most Temporally Stable (Mean)** | 🔹 **Symbolic** (Achieved Temporal Stability Score of **0.98** for mean performance across dates) |
| **Biggest Decline** | ⚠️ **DSL/JSON** (Mean performance degraded by 15% in stable runs, with 75% more variability) |

### Risk Assessment Summary

| Risk Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
| **IQR Deception Index (Combined)** | 10.31 | 9.40 | 12.50 |
| **Classification** | ✅ SAFE | ✅ SAFE | ✅ SAFE |
| **Two-Factor Assessment** | Not Required (Index <20) | Not Required (Index <20) | ✅ Passed (Index 20-30 on Mar 3, P95 < T) |
| **Tail-Risk Status** | ✅ Acceptable | ⚠️ Monitor (Mar 5 outlier: 1.90s) | ⚠️ Monitor (Mar 3 🟡 Moderate) |
| **Outlier Rate** | 0% | 10% (1/10 moderate) | 20% (2/10 beneficial) |
| **Production Readiness** | 🟢 Ready | 🟡 Ready with Monitoring | 🟢 Ready (with ⚠️ awareness) |

> [!IMPORTANT]
> **Final Recommendation Summary:**
> - **For maximum throughput with stability:** Use **Normal** (fastest combined mean, ⭐ 0.96 temporal stability)
> - **For maximum predictability:** Use **Symbolic** (⭐ 0.98 temporal stability, ✅ Safe on both dates)
> - **Avoid DSL/JSON for production:** Despite winning on Mar 3, its ❌ Poor stability (0.84) makes it unreliable
>
> **Conditional Note:** Normal carries a ⚠️ warning due to its 🟡 MODERATE risk on Mar 3. Monitor tail performance in production or consider Symbolic for risk-averse applications where perfect stability outweighs a 0.08s speed difference.

---

## 📋 Recommendations

| Use Case | Recommended Format | IQR Index (Combined) | Rationale |
|:---|:---|:---:|:---|
| **Maximum throughput (general production)** | 🏆 **Normal⚠️** | 12.50 (✅ Safe) | Best combined mean (1.14s) with directional win over other formats (Δ ≥0.07s threshold). All tail-risk metrics in safe range, but carries ⚠️ warning from 🟡 MODERATE risk on Mar 3. |
| **Stability-critical / real-time apps** | ⭐ **Symbolic** | 10.31 (✅ Safe) | Excellent temporal stability (⭐ 0.98) with near-identical performance across both dates. Trade 0.07s for perfect predictability and ✅ Safe on both dates. |
| **JSON-native workflows** | ❌ **DSL/JSON (Avoid)** | 9.40 (✅ Safe) | Despite excellent Mar 3 performance (1.11s), degraded significantly on Mar 5. ❌ Poor temporal stability (0.84) makes it fundamentally unpredictable for production. |
| **Single-date deployments (Mar 3 baseline)** | ⚡ **DSL/JSON** | 8.64 (✅ Safe) | Exceptional performance on that date (1.11s stable mean) with safe tail distribution. |
| **Single-date deployments (Mar 5 baseline)** | 🏆 **Normal** | 15.13 (✅ Safe) | Clear winner on this date - fastest (1.13s) and most consistent. |

### ⚠️ Important Caveats

| Caveat | Affected Format | Details |
|:---|:---:|:---|
| **Temporal Instability** | DSL/JSON | JSON performance degraded significantly between test dates (1.11s → 1.28s stable mean, **+15% slower, +75% more variable**). Temporal Stability Score of 0.84 (❌ Poor) indicates date-dependent behavior. As explained in the [FAQ](../Benchmark/benchmark_fqa.md#q-the-normal-format-for-llama-33-was-catastrophically-bad-on-march-3rd-but-excellent-on-march-5th-what-happened-can-i-trust-normal-prompts-for-llama-now), such dramatic swings make a format fundamentally unpredictable. **Avoid for production.** |
| **Moderate Risk on Mar 3** | Normal | Normal's March 3 Stable Runs show 🟡 Moderate IQR Risk (Index = 20.33). While P95 (1.22s) remains below Dynamic Threshold T (3.33s), users should monitor tail performance in production. |
| **Sporadic Fast Runs** | Normal | Fastest runs (0.96s-0.98s) occurred randomly (runs 7 & 10 on Mar 3), not position-dependent. As documented in the [FAQ](../Benchmark/benchmark_fqa.md#q-i-noticed-that-geminis-normal-format-had-some-very-fast-runs-096s-on-march-3-is-this-evidence-of-a-reverse-cold-start), these represent optimal routing conditions, not guaranteed performance. |
| **Statistical Tie Context** | Normal vs. Symbolic | The 0.07s speed advantage of Normal over Symbolic meets the directional win threshold (5% of fastest mean = 0.057s) but is modest. For applications where 70ms is negligible, Symbolic's excellent temporal stability may be preferable. |
| **Single-Day Optimizations** | DSL/JSON (Mar 3 only) | The exceptional Mar 3 performance (1.11s stable mean) should not be expected as typical behavior. JSON format shows high day-to-day variance and should be avoided for production. |

### Quick Selection Guide

| Priority | First Choice | Second Choice | Third Choice |
|:---|:---:|:---:|:---:|
| **Raw Speed** | Normal (1.14s) | Symbolic (1.21s) | DSL/JSON (1.20s) |
| **Temporal Stability** | Symbolic (⭐ 0.98) | Normal (⭐ 0.96) | DSL/JSON (❌ 0.84) |
| **Consistency (CV)** | Normal (8%) | Symbolic (8%) | DSL/JSON (12%) |
| **Tail-Risk Safety** | DSL/JSON (9.40) | Symbolic (10.31) | Normal (12.50) |

> [!TIP]
> **Production Quick Reference:**
> - **Default choice:** Normal (fastest, good stability, but monitor tail risk from Mar 3)
> - **For perfect predictability:** Symbolic (trade 0.07s for ⭐ stability and ✅ Safe on both dates)
> - **Avoid:** DSL/JSON (too unstable for reliable production use)

---

## 📁 Quick Reference Card

| If you want... | Use this format on gemini-2.0-flash | Risk Note |
|:---|:---|:---|
| **Maximum throughput (raw speed)** | 🏆 **Normal⚠️** (1.14s combined mean, IQR Index 12.5 ✅ Safe) | Monitor - 🟡 Moderate on Mar 3 (P95 < T, eligible) |
| **Predictable, stable performance** | ⭐ **Symbolic** (1.21s combined mean, IQR Index 10.3 ✅ Safe, ⭐ 0.98 temporal stability) | None - most stable format across dates, ✅ Safe on both dates |
| **Best single-day peak performance** | ⚡ **DSL/JSON** (1.11s on Mar 3, IQR Index 8.64 ✅ Safe) | ⚠️ **Avoid for production** - shows severe date-to-date variance (❌ 0.84 temporal stability, +15% slower, +75% more variable on Mar 5) |
| **Lowest tail-risk (P99 < 1.4s)** | ✅ **Symbolic** (P99 1.37s, IQR Index 10.3 ✅ Safe) | None - consistent tail behavior |
| **JSON-native workflows** | ❌ **DSL/JSON (Avoid)** (Temporal Stability 0.84 ❌ Poor) | ⚠️ **Not recommended** - performance degraded catastrophically on Mar 5 |
| **Don't know what to choose** | 🤔 **Normal for speed / Symbolic for stability** | See Final Verdict for detailed trade-off analysis |

### 📊 Format Personality Profile

| Format | Personality | Best For | Watch Out For |
|:---|:---|:---|:---|
| **Normal⚠️** | The Speed Demon | Maximum throughput, batch processing | 🟡 Moderate risk on Mar 3 (Index 20.33); P95 stays within acceptable range (1.22s < T=3.33s) |
| **Symbolic** | The Reliable Performer | Real-time apps, stability-critical | 0.07s slower than Normal; trade speed for predictability and ✅ Safety on both dates |
| **DSL/JSON** | The High-Variance Star (Avoid) | Not recommended for production | ⚠️ Severe date-to-date degradation (+15% slower, +75% more variable); ❌ Poor temporal stability (0.84) |

### ⚡ Winner's Circle Summary

| Category | Winner | Key Stat |
|:---|:---|:---|
| **Overall Performance** | 🏆 **Normal⚠️** | 1.14s combined mean |
| **Temporal Stability** | 🏆 **Symbolic** (⭐ 0.98) | Near-perfect stability across dates |
| **Consistency** | 🏆 **Normal** (tied) | 8% CV (tied with Symbolic) |
| **Tail Performance** | 🏆 **Normal** | 1.30s combined P99 |
| **Cost Efficiency** | 🏆 **Symbolic** | ~67-91 tokens/request (lowest token count) |
| **Most Improved** | 📈 **Normal** | 25% more consistent on Mar 5 |
| **Best Single-Day Peak** | ⚡ **DSL/JSON** | 1.11s stable mean (Mar 3) |

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

### Application to gemini-2.0-flash@001

| Format | Status | Rationale |
|:---|:---:|:---|
| **Normal** | 🏆 **CONDITIONAL WINNER (⚠️)** | ✅ Safe combined IQR (12.50); 🟡 Moderate on Mar 3 (Index 20.33, P95 1.22s < T 3.33s) → eligible with monitoring; ⭐ 0.96 temporal stability; fastest combined mean (1.14s); dominates 7/9 metrics. |
| **Symbolic** | ✅ **ELIGIBLE** | ✅ Safe IQR classification on both dates (9.36 Mar 3, 18.86 Mar 5); ⭐ 0.98 temporal stability (Excellent); zero outliers; consistent performance across both dates; recommended for stability-critical applications. |
| **DSL/JSON** | ❌ **DISQUALIFIED** | ✅ Safe IQR on both dates individually (8.64 Mar 3, 10.79 Mar 5), but ❌ 0.84 temporal stability (Poor) due to +15% slowdown and +75% increased variability between dates; disqualified from combined winner due to fundamental unpredictability. |

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

[⬅️ Back to Home](../README.md) | [Methodology used](../Benchmark/benchmark_methodology.md)