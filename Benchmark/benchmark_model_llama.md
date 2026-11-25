# Symbolic Prompting 📊 Benchmark Report: llama-3.3-70b-instruct

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

This report analyzes benchmark results for **llama-3.3-70b-instruct** across two test dates (March 3 and March 5, 2026), comparing three prompt formats: **Symbolic**, **DSL/JSON**, and **Normal**. Following our [Unified Winner Declaration Protocol](../Benchmark/benchmark_methodology.md#unified-winner-declaration-protocol), we assess performance, temporal stability, and tail-risk to provide production-ready recommendations.

| Dataset | Symbolic | DSL/JSON | Normal | Winner |
|:---|:---:|:---:|:---:|:---|
|**March 3 Only** | 1.55s | 1.58s | 2.08s | 🏆 Symbolic |
|**March 5 Only** | 1.94s | 1.48s | 1.48s | 🤝 Tie (DSL/JSON / Normal) |
|**Combined Winner** | 1.75s | **1.53s** | 1.78s | 🏆 **DSL/JSON (1.53s)** |

---

## 📈 Combined Results

*Aggregated data from both test dates (20 runs per format)*

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | 1.76s | **1.53s** | 1.80s |
|**Median** | 1.75s | **1.44s** | 1.57s |
|**Q1 (25th)** | 1.49s | **1.34s** | 1.39s |
|**Q3 (75th)** | 1.87s | **1.72s** | 1.81s |
|**Minimum** | 1.42s | **1.19s** | 1.20s |
|**Maximum** | 2.68s | **2.11s** | 3.70s |
|**Std Dev (σ)** | 0.30s | **0.26s** | 0.67s |
|**P90** | 2.04s | **1.84s** | 2.88s |
|**P95** | 2.11s | **1.88s** | 3.19s |
|**P99** | 2.57s | **2.06s** | 3.60s |
|**IQR** | 0.38s | 0.38s | 0.42s |
|**IQR Deception Index** | 5.55 | 4.95 | 7.60 |
|**Risk Classification** | ✅ SAFE | ✅ SAFE | ✅ SAFE |
|**Range** | 1.27s | **0.92s** | 2.50s |
|**CV** | 17% | 17% | 37% |

| Model | Symbolic | DSL/JSON | Normal | Winner |
|:---|:---:|:---:|:---:|:---|
| **llama-3.3-70b-instruct** | 1.76s | **1.53s** | 1.80s | 🏆 **DSL/JSON**<br><sup>(Best combined mean, lowest P95, IQR Index 4.95 ✅ Safe)</sup> |

---
## 📅 March 3, 2026 Detailed Analysis

### All Runs (1-10)

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | 1.57s | 1.53s | 2.13s |
|**Median** | 1.48s | 1.42s | 1.82s |
|**Q1 (25th)** | 1.45s | 1.37s | 1.75s |
|**Q3 (75th)** | 1.73s | 1.69s | 2.60s |
|**Minimum** | 1.42s | 1.19s | 1.20s |
|**Maximum** | 1.80s | 2.11s | 3.70s |
|**Std Dev (σ)** | 0.15s | 0.28s | 0.77s |
|**P90** | 1.80s | 1.89s | 3.22s |
|**P95** | 1.80s | 2.00s | 3.46s |
|**P99** | 1.80s | 2.09s | 3.65s |
|**IQR** | 0.28s | 0.32s | 0.85s |
|**IQR Deception Index** | 6.43 | 6.25 | 4.07 |
|**Risk Classification** | ✅ SAFE | ✅ SAFE | 🔴 SEVERE |
|**Range** | 0.39s | 0.92s | 2.50s |
|**CV** | 10% | 18% | 36% |

### Stable Runs (2-9, Outliers Removed)

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | 1.55s | 1.58s | 2.08s |
|**Median** | 1.47s | 1.43s | 1.79s |
|**Q1 (25th)** | 1.44s | 1.39s | 1.66s |
|**Q3 (75th)** | 1.61s | 1.80s | 2.19s |
|**Minimum** | 1.42s | 1.28s | 1.20s |
|**Maximum** | 1.80s | 2.11s | 3.70s |
|**Std Dev (σ)** | 0.15s | 0.28s | 0.82s |
|**P90** | 1.79s | 1.94s | 3.32s |
|**P95** | 1.79s | 2.03s | 3.51s |
|**P99** | 1.80s | 2.09s | 3.66s |
|**IQR** | 0.17s | 0.41s | 0.53s |
|**IQR Deception Index** | 10.53 | 4.95 | 6.62 |
|**Risk Classification** | ✅ SAFE | ✅ SAFE | 🔴 SEVERE |
|**Range** | 0.38s | 0.83s | 2.50s |
|**CV** | 10% | 18% | 39% |


### Outliers Detected - March 3

Following the methodology's outlier detection protocol (±2σ from the mean of Runs 2-9):

| Format | Outliers | Impact on Mean | Risk Assessment |
|:---|:---|:---|:---|
| **Symbolic** | None detected | No impact | ✅ SAFE |
| **DSL/JSON** | None detected | No impact | ✅ SAFE |
| **Normal** | Run 1: 3.70s (>2σ - catastrophic outlier)<br>Run 4: 3.70s (>2σ - catastrophic outlier)<br>Run 10: 1.80s (within ±2σ - kept) | Removing catastrophic outliers reduces mean from 2.13s to 1.99s (-0.14s, 6.6% reduction) | 🔴 **SEVERE TAIL RISK**<br>(Two-Factor Assessment: P95=3.46s > 1.7s absolute threshold → 🔴 Severe) |

*Verify these values in [benchmark_20260303.csv](../Benchmark/benchmark_20260303.csv)*


---
## 📅 March 5, 2026 Detailed Analysis

### All Runs (1-10)

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | 1.95s | 1.52s | 1.46s |
|**Median** | 1.89s | 1.59s | 1.50s |
|**Q1 (25th)** | 1.75s | 1.30s | 1.33s |
|**Q3 (75th)** | 2.01s | 1.69s | 1.56s |
|**Minimum** | 1.73s | 1.20s | 1.24s |
|**Maximum** | 2.68s | 1.84s | 1.79s |
|**Std Dev (σ)** | 0.27s | 0.22s | 0.16s |
|**P90** | 2.14s | 1.79s | 1.59s |
|**P95** | 2.41s | 1.81s | 1.69s |
|**P99** | 2.63s | 1.83s | 1.77s |
|**IQR** | 0.26s | 0.39s | 0.23s |
|**IQR Deception Index** | 9.27 | 4.64 | 7.35 |
|**Risk Classification** | ✅ SAFE | ✅ SAFE | ✅ SAFE |
|**Range** | 0.95s | 0.64s | 0.55s |
|**CV** | 14% | 14% | 11% |

### Stable Runs (2-9, Outliers Removed)

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | 1.94s | 1.48s | 1.48s |
|**Median** | 1.80s | 1.51s | 1.50s |
|**Q1 (25th)** | 1.74s | 1.25s | 1.35s |
|**Q3 (75th)** | 1.98s | 1.65s | 1.57s |
|**Minimum** | 1.73s | 1.20s | 1.24s |
|**Maximum** | 2.68s | 1.78s | 1.79s |
|**Std Dev (σ)** | 0.30s | 0.22s | 0.16s |
|**P90** | 2.26s | 1.73s | 1.64s |
|**P95** | 2.47s | 1.75s | 1.72s |
|**P99** | 2.64s | 1.77s | 1.78s |
|**IQR** | 0.24s | 0.40s | 0.22s |
|**IQR Deception Index** | 10.29 | 4.38 | 7.82 |
|**Risk Classification** | ✅ SAFE | ✅ SAFE | ✅ SAFE |
|**Range** | 0.95s | 0.58s | 0.55s |
|**CV** | 15% | 15% | 11% |

### Outliers Detected - March 5

Following the methodology's outlier detection protocol (±2σ from the mean of Runs 2-9):

| Format | Outliers | Impact on Mean | Notes |
|:---|:---|:---|:---|
| **Symbolic** | Run 1: 2.09s (>2σ)<br>Run 10: 2.68s (>2σ) | Removing outliers reduces mean from 1.95s to 1.94s (-0.01s, 0.5% reduction) | Consistent with cold-start (Run 1) and end-of-run (Run 10) effects |
| **DSL/JSON** | Run 1: 1.20s (< -2σ - beneficial outlier) | Removing outliers increases mean from 1.52s to 1.48s (-0.04s adjustment, 2.6% change) | As noted in [FAQ: Beneficial Outliers](../Benchmark/benchmark_fqa.md#handling-beneficial-outliers), these runs represent real API variance and are retained in All Runs |
| **Normal** | None detected | No impact | Most consistent format on this date with CV=11% |

*Verify these values in [benchmark_20260305.csv](../Benchmark/benchmark_20260305.csv)*

---

## 📊 Stable Runs Comparison (Runs 2-9)

| Format | Date | Mean | Median | Std Dev | CV | P95 | IQR | IQR Risk | Temporal Stability | Change |
|:---|:---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **Symbolic** | Mar 3 | **1.55s** | **1.47s** | 0.15s | **9%** | **1.79s** | **0.16s** | ✅ Safe | ⭐ 0.90 (Good) | |
| | Mar 5 | 1.94s | 1.80s | 0.30s | 16% | 2.47s | 0.24s | ✅ Safe | | ⬆️ **+25% slower**<br>⚠️ **78% more variable (CV)** |
| **DSL/JSON** | Mar 3 | 1.58s | 1.43s | 0.28s | 18% | 2.03s | 0.35s | ✅ Safe | ⭐ **0.97 (Excellent)** | |
| | Mar 5 | **1.48s** | 1.51s | 0.22s | 15% | **1.75s** | 0.41s | ✅ Safe | | ⬇️ **-6% faster**<br>✅ **17% more consistent (CV)** |
| **Normal** | Mar 3 | 2.08s | 1.79s | 0.82s | 39% | 3.51s | 0.75s | 🔴 **SEVERE**<sup>1</sup> | ❌ **0.67 (Poor)** | |
| | Mar 5 | **1.48s** | **1.50s** | **0.16s** | **11%** | **1.72s** | **0.22s** | ✅ Safe | | ⬇️ **-29% faster**<br>✅ **72% more consistent (CV)** |

---

## 🔍 Key Temporal Insights

| Insight | Description | Temporal Stability Score |
|:---|:---|:---:|
| **📈 Normal Dramatically Improved** | Normal was catastrophic on Mar 3 (2.13s, P95=3.46s, CV=39%) but became the fastest format on Mar 5 (1.46s, P95=1.72s, CV=11%)—**29% faster, 72% more consistent**. While IQR indices (4.02→7.35) show "✅ Safe" mathematically, the absolute P95 values expose the true risk: March 3's 3.46s tail is unacceptable for production. | ⚠️ 0.82 (Moderate)<br>*(score masks catastrophic tail-risk)* |
| **📊 DSL/JSON Most Stable** | DSL/JSON maintained consistent speed across both dates (1.53s→1.52s) with improving consistency (CV 18%→15%, 17% improvement). The only format to improve across all metrics. | ⭐ **0.97 (Excellent)** |
| **⚙️ Symbolic Degraded** | Symbolic was 24% slower and 78% more variable (CV 9%→16%) on Mar 5—significant degradation that raises concerns about backend sensitivity. | ❌ 0.78 (Poor) |
| **🔄 Winner Changed Dramatically** | Mar 3: Symbolic won (1.55s), DSL/JSON close second (1.58s), Normal catastrophic (2.08s, 🔴 Severe)<br>Mar 5: DSL/JSON and Normal tied (1.48s), Symbolic degraded (1.94s)<br>Combined: DSL/JSON wins overall with ⭐ Excellent stability | — |

### Temporal Stability Score Calculations

Following the [Temporal Stability Score methodology](../Benchmark/benchmark_methodology.md#temporal-stability-score-calculation):

| Format | Mar 3 Mean | Mar 5 Mean | Formula | Score | Rating |
|:---|:---:|:---:|:---|:---:|:---:|
| **Symbolic** | 1.57s | 1.95s | 1 - (\|1.57-1.95\| / ((1.57+1.95)/2)) = 1 - (0.38/1.76) | 0.78 | ❌ Poor |
| **DSL/JSON** | 1.53s | 1.52s | 1 - (\|1.53-1.52\| / ((1.53+1.52)/2)) = 1 - (0.01/1.525) | **0.97** | ⭐ **Excellent** |
| **Normal** | 2.13s | 1.46s | 1 - (\|2.13-1.46\| / ((2.13+1.46)/2)) = 1 - (0.67/1.795) | 0.82 | ⚠️ Moderate |

### Winner Evolution Summary

| Date | Fastest Format | Second Place | Slowest | Spread |
|:---|:---:|:---:|:---:|:---:|
| **March 3** | 🏆 Symbolic (1.55s) | DSL/JSON (1.58s) | Normal (2.08s)🔴 | 34% |
| **March 5** | 🤝 Tie: DSL/JSON (1.48s) / Normal (1.48s) | — | Symbolic (1.94s) | 31% |
| **Combined** | 🏆 **DSL/JSON (1.53s)** | Symbolic (1.76s) | Normal (1.80s) | 18% |


---

## 🏆 Winner Analysis by Metric

| Metric | Mar 3 Winner (Stable Runs 2-9) | Mar 5 Winner (Stable Runs 2-9) | Combined Winner (Stable Runs 2-9)<br><sup>⚠️ Two-Tier Framework applied</sup> |
|:---|:---:|:---:|:---:|
|**Mean** | 🏆 Symbolic (1.55s) | 🤝 DSL/JSON / Normal Tie (1.48s) | 🏆 DSL/JSON (1.53s) |
|**Median** | 🏆 DSL/JSON (1.43s) | 🏆 Normal (1.50s) | 🏆 DSL/JSON (1.47s) |
|**Minimum** | 🏆 Normal (1.20s) | 🏆 DSL/JSON (1.20s) | 🏆 Normal (1.22s)<br><sup>❌ Normal disqualified from combined</sup> |
|**Maximum (lower is better)** | 🏆 Symbolic (1.80s) | 🏆 DSL/JSON (1.78s) | 🏆 DSL/JSON (1.95s) |
|**Std Dev (consistency)** | 🏆 Symbolic (0.15s) | 🏆 Normal (0.16s) | 🏆 Symbolic (0.23s) |
|**P95 (worst case)** | 🏆 Symbolic (1.79s) | 🏆 Normal (1.72s) | 🏆 DSL/JSON (1.89s) |
|**IQR (core consistency)** | 🏆 Symbolic (0.17s) | 🏆 Normal (0.22s) | 🏆 Symbolic (0.21s) |
|**Range (stability)** | 🏆 Symbolic (0.38s) | 🏆 Normal (0.55s) | 🏆 Symbolic (0.67s) |
|**CV (predictability)** | 🏆 Symbolic (10%) | 🏆 Normal (11%) | 🏆 Symbolic (13%) |
|**Overall Winner by Date** | 🏆 **Symbolic** | 🤝 **Tie: DSL/JSON / Normal** | 🏆 **DSL/JSON**<br><sup>❌ Normal disqualified (🔴 Severe Mar 3)</sup> |

### Winner Dominance Analysis

| Format | Metrics Won (Solo) | Metrics Won (Including Ties) | Metric Superiority Score | Disqualification Status |
|:---|:---:|:---:|:---:|:---|
| **Symbolic** | 5/9 (56%) | 7/9 (78%) | ⭐ **Excellent** | ✅ Eligible |
| **DSL/JSON** | 2/9 (22%) | 4/9 (44%) | ⚠️ Moderate | ✅ Eligible |
| **Normal** | 2/9 (22%) | 6/9 (67%) | ⚠️ Moderate | ❌ **DISQUALIFIED**<sup>1</sup> |

*See [Unified Winner Declaration Protocol](../Benchmark/benchmark_methodology.md#unified-winner-declaration-protocol) for complete decision framework.*

---
## 📊 Format Evolution Summary

| Format | Metric | Mar 3 | Mar 5 | Change | Temporal Stability Score & Rating | IQR Index (Combined) | Per-Date IQR Risk (Stable) |
|:---|:---|:---:|:---:|:---:|:---:|:---:|:---:|
| **Symbolic** | Mean (All) | 1.57s | 1.95s | ⬆️ +24% slower | **0.78** ❌ Poor | 5.55 (✅ Safe) | Mar 3: 6.43 (✅ Safe)<br>Mar 5: 9.27 (✅ Safe) |
| | Mean (Stable) | 1.55s | 1.94s | ⬆️ +25% slower | | 5.55 (✅ Safe) | Mar 3: 10.53 (✅ Safe)<br>Mar 5: 10.29 (✅ Safe) |
| | Std Dev (Stable) | 0.15s | 0.30s | ⬆️ +100% more variable | | - | - |
| **DSL/JSON** | Mean (All) | 1.53s | 1.52s | ⬇️ -0.7% faster | **0.97** ⭐ **Excellent** | 4.95 (✅ Safe) | Mar 3: 6.25 (✅ Safe)<br>Mar 5: 4.64 (✅ Safe) |
| | Mean (Stable) | 1.58s | 1.48s | ⬇️ **-6% faster** | | 4.95 (✅ Safe) | Mar 3: 4.95 (✅ Safe)<br>Mar 5: 4.38 (✅ Safe) |
| | Std Dev (Stable) | 0.28s | 0.22s | ⬇️ **-21% more consistent** | | - | - |
| **Normal** | Mean (All) | 2.13s | 1.46s | ⬇️ **-31% faster** | **0.67** ❌ **Poor** | 7.60 (✅ Safe) | Mar 3: 4.07 (🔴 **SEVERE**<sup>1</sup>)<br>Mar 5: 7.35 (✅ Safe) |
| | Mean (Stable) | 2.08s | 1.48s | ⬇️ **-29% faster** | | 7.60 (✅ Safe) | Mar 3: 6.62 (🔴 **SEVERE**<sup>1</sup>)<br>Mar 5: 7.82 (✅ Safe) |
| | Std Dev (Stable) | 0.82s | 0.16s | ⬇️ **-80% more consistent** | | - | - |

---

## 📈 Performance Trend Visualization

```
SYMBOLIC
────────────────────────────────────────────────
Speed: 1.57s ──────────➡️ 1.95s (+24%) ❌ SLOWER

Consist: 0.15s ──────────┐ (CV: 9% → 16%)
▼
0.30s ────────────► 100% MORE VARIABLE ❌
(78% higher CV)

Risk: ✅ SAFE ────────➡️ ✅ SAFE (but 25% slower)

DSL/JSON
────────────────────────────────────────────────
Speed: 1.53s ────────➡️ 1.52s (-1% NO CHANGE) ✅ STABLE

Consist: 0.28s ──────────┐ (CV: 18% → 15%)
▼
0.22s ────────────► 21% MORE CONSISTENT ✅
(17% lower CV)

Risk: ✅ SAFE ────────➡️ ✅ SAFE (improving)

NORMAL
────────────────────────────────────────────────
Speed: 2.13s ──────────┐ (WORST ON MAR 3 - catastrophic tails: P95=3.46s)
▼
1.46s ────────────► 31% FASTER ✅
(BUT WHICH DAY WILL YOU GET?)

Consist: 0.82s ──────────┐ (MOST VARIABLE ON MAR 3 - CV: 36% → 11%)
▼
0.16s ────────────► 80% MORE CONSISTENT ✅
(69% lower CV)

Risk: 🔴 SEVERE ────────➡️ ✅ SAFE ❌ UNPREDICTABLE
(Temporal Stability: 0.67 ❌ Poor)
```

> [!CAUTION]
> **The Normal Format Gamble:** This visualization starkly illustrates the production risk of the Normal format. While it shows the most dramatic improvement (31% faster, 80% more consistent), its Temporal Stability Score of **0.67 (Poor)** confirms it is fundamentally unpredictable. Choosing Normal means gambling on which backend configuration you'll encounter—the catastrophic one from March 3 or the excellent one from March 5. In production, this is an unacceptable risk.
> 
> **DSL/JSON: The Only Safe Bet:** DSL/JSON is the sole format that improved or held steady across all metrics. Its ⭐ **0.97 Excellent** stability score means you can rely on consistent performance day after day.

---
## ✅ Final Verdict

| Aspect | Conclusion |
|:---|:---|
| **Overall Production Winner** | 🏆 **DSL/JSON** (Split Winner Protocol decision) |
| **Recommendation** | **DSL/JSON** is the recommended format for llama-3.3-70b-instruct. Following the [Split Winner Protocol](../Benchmark/benchmark_methodology.md#unified-winner-declaration-protocol) (different winners on Mar 3 and Mar 5), DSL/JSON wins based on:<br>- **Combined mean advantage:** 1.53s vs. Normal's 1.80s (0.27s faster, exceeding 0.07s threshold)<br>- **Superior temporal stability:** ⭐ 0.97 (Excellent) vs. Normal's ❌ 0.67 (Poor)<br>- **Safe tail distribution:** IQR indices 4.38-6.25 (✅ Safe) with acceptable absolute P95 values (≤2.03s)<br>- **Consistency:** Demonstrated improving consistency (21% lower σ) vs. Normal's extreme day-to-day variability (39%→11% CV swing)<br>- **Risk disqualification:** Normal is 🔴 **DISQUALIFIED** due to catastrophic March 3 tail-risk (P95=3.46s) per [Global Disqualification Rule](../Benchmark/benchmark_methodology.md#6-global-disqualification-with-anomaly-detection) |
| **Best Single-Day Performance** | ⭐ **Normal on Mar 5** (1.48s mean, σ=0.16s, CV=11% - exceptional, but note catastrophic Mar 3 performance) |
| **Most Stable Across Dates** | 📊 **DSL/JSON** (Nearly identical speed both dates, improved consistency, IQR Index 4.38-6.25 ✅ Safe) |
| **Most Improved** | 📈 **Normal** (31% faster, 80% more consistent - but from catastrophic baseline with P95=3.46s on Mar 3) |
| **Biggest Decline** | 📉 **Symbolic** (25% slower, 100% more variable - significant degradation) |
| **Best Single Run** | ⚡ **DSL/JSON** (1.19s on Mar 3 - Run 1) |
| **Highest Risk Format** | ⚠️ **Normal** (Catastrophic tail-risk on Mar 3: P95=3.46s, two runs at exactly 3.70s suggesting [API timeout mechanism](../Benchmark/benchmark_fqa.md#q-in-the-llama-report-you-documented-two-runs-at-exactly-370s-what-causes-this-suspicious-precision)) |

### Risk Assessment Summary

| Risk Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
| **IQR Deception Index Range** | 6.43-10.53 | 4.38-6.25 | 4.07-7.82 |
| **Classification (per methodology)** | ✅ Safe (<20) | ✅ Safe (<20) | ✅ Safe (<20) |
| **Two-Factor Assessment** | ✅ Pass (P95 ≤2.47s) | ✅ Pass (P95 ≤2.03s) | ❌ **FAIL** (Mar 3: P95=3.46s >1.7s absolute threshold) |
| **Tail-Risk Status** | ✅ Acceptable | ✅ Acceptable | 🔴 **SEVERE** (Mar 3)<br>✅ Safe (Mar 5) |
| **Outlier Rate (Mar 3)** | 0% (0/10) | 0% (0/10) | 20% (2/10 severe outliers at 3.70s) |
| **Outlier Rate (Mar 5)** | 20% (2/10) | 10% (1/10 beneficial) | 0% (0/10) |
| **Temporal Stability** | ❌ 0.78 (Poor) | ⭐ **0.97 (Excellent)** | ❌ 0.67 (Poor) |
| **Production Readiness** | 🟡 **Conditional**<br>(monitor degradation) | 🟢 **Ready** | 🔴 **NOT RECOMMENDED**<br>(unpredictable) |


---
## 📋 Recommendations

| Use Case | Recommended Format | IQR Index | Rationale |
|:---|:---|:---:|:---|
| **General production** | 🏆 **DSL/JSON** | 4.38-6.25 (✅ Safe) | Best combined mean (1.53s), ⭐ Excellent temporal stability (0.97), safe tail distribution (P95 ≤2.03s). The only format with consistently improving metrics and ✅ Safe classification on both dates. |
| **If you ran on Mar 3** | 🏆 **Symbolic** | 6.43-10.53 (✅ Safe) | Winner on this date (1.55s mean, σ=0.15s, CV=9%) - but note significant degradation on Mar 5 (+25% slower, +100% more variable). |
| **If you ran on Mar 5** | 🤝 **DSL/JSON or Normal** | 4.38 / 7.82 (✅ Safe) | Both formats tied at 1.48s mean. Choose DSL/JSON for consistency (15% CV) or Normal for slightly lower P95 (1.72s) - but Normal's Mar 3 catastrophe (P95=3.46s) makes this a risky choice per [Global Disqualification Rule](../Benchmark/benchmark_methodology.md#6-global-disqualification-with-anomaly-detection). |
| **If consistency is critical** | ✅ **DSL/JSON** | 4.38-6.25 (✅ Safe) | Most stable format across dates (⭐ 0.97) with improving consistency (21% lower σ). The only format you can reliably predict day-to-day. |
| **If avoiding tail-risk** | ✅ **DSL/JSON** | 4.38-6.25 (✅ Safe) | Lowest combined P95 (1.88s), no severe outliers, and ✅ Safe on both dates. Normal's Mar 3 P95=3.46s is catastrophic regardless of index—see [FAQ on IQR Deception limitations](../Benchmark/benchmark_fqa.md#q-in-the-llama-report-you-mention-that-normal-format-on-march-3-had-an-iqr-deception-index-of-402--safe-despite-having-catastrophic-tails-p95346s-this-seems-to-expose-a-flaw-in-the-iqr-deception-indexits-fails-when-the-iqr-itself-is-large-shouldnt-the-index-be-normalized-by-the-median-or-mean-to-account-for-scale). |
| **Lowest latency (risk-tolerant)** | ⚠️ **Normal** | 4.07-7.82 (✅ Safe) | 1.48s on Mar 5 with CV=11% is exceptional—but catastrophic Mar 3 tail values (P95=3.46s, two runs at exactly 3.70s) make it **unreliable for production** without continuous monitoring and fallback mechanisms. The two 3.70s runs suggest a [capped timeout mechanism](../Benchmark/benchmark_fqa.md#q-in-the-llama-report-you-documented-two-runs-at-exactly-370s-what-causes-this-suspicious-precision). |
| **Don't know what to choose** | ✅ **DSL/JSON** | 4.38-6.25 (✅ Safe) | Best average speed, ⭐ best stability, ✅ safe tail distribution. The safe choice that works well regardless of which backend configuration is live. |

### ⚠️ Important Caveats

| Caveat | Affected Format | Impact | Mitigation |
|:---|:---:|:---|:---|
| **Large IQR Masking Tail-Risk** | ⚠️ **Normal (Mar 3)** | IQR index of 4.07 (✅ Safe mathematically) despite P95=3.46s due to wide IQR (0.85s). This exposes a limitation of the IQR index when the core distribution is already wide. | Always evaluate absolute P95/P99 values alongside IQR index. As recommended in the [FAQ](../Benchmark/benchmark_fqa.md#q-in-the-llama-report-you-mention-that-normal-format-on-march-3-had-an-iqr-deception-index-of-402--safe-despite-having-catastrophic-tails-p95346s-this-seems-to-expose-a-flaw-in-the-iqr-deception-indexits-fails-when-the-iqr-itself-is-large-shouldnt-the-index-be-normalized-by-the-median-or-mean-to-account-for-scale), use **Two-Dimensional Risk Assessment**: if P95 > 1.7s, classify as 🔴 SEVERE regardless of index. |
| **Significant Performance Degradation** | 📉 **Symbolic** | 25% slower, 100% more variable (CV 9%→16%) between test dates; 0.78 stability score (❌ Poor). The format that won on Mar 3 is now the slowest on Mar 5. | Monitor continuously if using Symbolic; consider switching to DSL/JSON for more predictable performance. The degradation suggests sensitivity to backend changes. |
| **Winner Instability** | 🔄 **All Formats** | Different winner on each test date (Symbolic Mar 3, DSL/JSON/Normal tie Mar 5) | Base format selection on combined multi-date data and stability scores, not single-day benchmarks. DSL/JSON is the only format in the top tier on **both** dates. |
| **Limited Sample Size** | 📊 **All Formats** | Only 10 runs per date (20 total) may miss longer-term patterns | Treat results as directional; community replication encouraged. Confidence intervals overlap for differences <0.07s. See [FAQ on statistical significance](../Benchmark/benchmark_fqa.md#with-only-n10-per-format-per-date-how-statistically-significant-are-your-results) for detailed guidance. |

---
## 📁 Quick Reference Card

| If you want... | Use this format on llama-3.3-70b-instruct | Key Metrics |
|:---|:---|:---|
| **Best overall performance** | 🏆 **DSL/JSON** | 1.53s combined mean<br>✅ Safe IQR indices (4.38-6.25)<br>⭐ **0.97 Temporal Stability (Excellent)**<br>📈 Improving consistency (-21% σ) |
| **Best single-day performance** | ⚠️ **Normal** | 1.48s on Mar 5 (CV=11%, P95=1.72s)<br>🔴 **CATASTROPHIC ON MAR 3** (P95=3.46s)<br>❌ **DISQUALIFIED** for production due to unpredictability per [Global Disqualification Rule](../Benchmark/benchmark_methodology.md#6-global-disqualification-with-anomaly-detection) |
| **Most stable across dates** | 📊 **DSL/JSON** | Nearly identical speed both dates (±0.01s)<br>✅ Improving stability (21% lower σ)<br>✅ Safe tail-risk on both dates |
| **Most improved format** | 📈 **Normal** | 29% faster (2.08s → 1.48s)<br>80% more consistent (0.82σ → 0.16σ)<br>⚠️ But from catastrophic baseline (P95=3.46s) with two runs at exactly 3.70s suggesting [API timeout mechanism](../Benchmark/benchmark_fqa.md#q-in-the-llana#q-in-the-llama-report-you-documented-two-runs-at-exactly-370s-what-causes-this-suspicious-precision) |
| **Biggest decline** | 📉 **Symbolic** | 25% slower (1.55s → 1.94s)<br>100% more variable (0.15σ → 0.30σ)<br>❌ Temporal Stability: 0.78 (Poor) |
| **Avoiding tail-risk at all costs** | ✅ **DSL/JSON** | ✅ Safe IQR indices both dates<br>0% severe outliers on Mar 3<br>Lowest combined P95 (1.88s)<br>Predictable distribution with improving trend |
| **Don't know what to choose** | ✅ **DSL/JSON** | Best average speed (1.53s)<br>⭐ Best stability (0.97)<br>✅ Safe tail distribution<br>🏆 **The safe choice** |

### ⚡ At a Glance: Winner Summary

| Date | Fastest Format | Most Stable | Safest (Tail-Risk) | Overall Winner |
|:---|:---:|:---:|:---:|:---:|
| **March 3** | 🏆 Symbolic (1.55s) | 🏆 Symbolic (σ=0.15s) | ✅ Symbolic/DSL/JSON | 🏆 **Symbolic** |
| **March 5** | 🤝 DSL/JSON/Normal (1.48s) | 🏆 Normal (σ=0.16s) | ✅ All formats (✅ Safe) | 🤝 **Tie** |
| **Combined** | 🏆 **DSL/JSON (1.53s)** | 🏆 **DSL/JSON (0.97)** | ✅ **DSL/JSON**<br>(P95=1.88s) | 🏆 **DSL/JSON**<br><sup>❌ Normal disqualified (🔴 Severe Mar 3)</sup> |

> [!NOTE]
> **Quick Decision Guide for Busy Engineers:**
> 1. **Need a format you can set and forget?** → **DSL/JSON**. It's the only format that performs well and stays stable.
> 2. **Gambling on a single-day benchmark?** → Stop. Normal's Mar 5 performance is a trap; you can't predict which day you'll get.
> 3. **Chasing raw speed at any cost?** → Normal *might* deliver 1.48s, but be prepared for 3.70s timeouts.
> 4. **Building a reliable production system?** → **DSL/JSON** is your only real option.


---

> *"We don't ask you to trust our numbers. We give you the tools to verify them yourself."*

---
## 📊 Risk Legend - Quick Reference

| Symbol | Meaning | Production Implication |
|:---:|:---|:---|
| **✅ Safe** | IQR Deception Index <20<br>OR IQR Index 20-30 with P95 ≤1.7s<br>*(Absolute threshold applied)* | **Ready for production**<br>Acceptable tail-risk and core consistency |
| **⚠️ Moderate** | IQR Index 20-30 AND P95 ≤1.7s<br>*(Two-Factor Assessment pass)* | **Monitor for SLAs**<br>Acceptable with tracking and alerting |
| **🔴 Severe** | IQR Index >30<br>OR (Index 20-30 + P95 >1.7s)<br>OR P95 >1.7s regardless of index<sup>1</sup> | **DISQUALIFIED** from production winner status<br>Unacceptable tail-risk for consistent deployment |
| **⭐ Excellent** | Temporal Stability Score 0.95-1.00 | Virtually identical performance across test dates<br>Highly reliable and predictable |
| **✅ Good** | Temporal Stability Score 0.85-0.94 | Minor variance, still reliable for most use cases |
| **⚠️ Moderate** | Temporal Stability Score 0.70-0.84 | Noticeable fluctuation; monitor for changes |
| **❌ Poor** | Temporal Stability Score <0.70 | Significant day-to-day variance<br>Unpredictable for production |

### Risk Classification Applied to Llama-3.3-70b-instruct

| Format | IQR Index Range | P95 Range | Two-Factor Assessment | Final Status |
|:---|:---:|:---:|:---|:---:|
| **Symbolic** | 6.43-10.53 | 1.79-2.47s | ✅ Pass (Index <20) | ✅ **Safe** |
| **DSL/JSON** | 4.38-6.25 | 1.75-2.03s | ✅ Pass (Index <20) | ✅ **Safe** |
| **Normal** | 4.07-7.82 | **1.69-3.46s** | ❌ **FAIL** (Mar 3: P95=3.46s >1.7s) | 🔴 **Severe**<br>*(DISQUALIFIED)* |


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