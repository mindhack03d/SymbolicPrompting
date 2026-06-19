# Symbolic Prompting 📊 Benchmark Report: gpt-4o-mini@2024-07-18

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

This report analyzes benchmark results for **gpt-4o-mini@2024-07-18** across two separate test dates (March 3 and March 5, 2026). The analysis compares three prompt formats—**Symbolic**, **DSL/JSON**, and **Normal**—using the multi-date testing protocol defined in the V2.0 methodology.

| Dataset | Symbolic | DSL/JSON | Normal | Winner |
|:---|:---:|:---:|:---:|:---|
|**March 3 Only** | 1.39 | 1.25 | 1.21 | Normal | 
|**March 5 Only** | 1.48 | 1.52 | 1.44 | Normal | 
|**Winner**       | 1.44 | 1.39 | 1.33 | 🏆 Normal (1.33s) | 

**Key Finding:** Normal prompting is the only format eligible for Combined Winner status after applying the Unified Winner Declaration Protocol. While the Combined Results table shows Normal with the fastest weighted mean (1.33s), March 3 data shows "No Eligible Winner" due to Symbolic's 🔴 SEVERE risk classification and DSL/JSON's 🟡 MODERATE risk on that date. Normal wins the mean on both test dates, making it the Stable Winner.

---

## 📈 Combined Results

*Aggregated data from both test dates using weighted stable means (Runs 2-9, outliers removed)*

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | 1.40s | 1.43s | **1.34s** |
|**Median** | 1.30s | 1.29s | **1.24s** |
|**Q1 (25th)** | 1.27s | **1.22s** | 1.15s |
|**Q3 (75th)** | **1.42s** | 1.43s | 1.46s |
|**Minimum** | 1.11s | 1.11s | **1.10s** |
|**Maximum** | 2.26s | 2.54s | **2.03s** |
|**Std Dev (σ)** | **0.27s** | 0.38s | **0.27s** |
|**P90** | 1.69s | 1.97s | **1.64s** |
|**P95** | **1.79s** | 2.31s | 1.99s |
|**P99** | 2.17s | 2.49s | **2.02s** |
|**IQR** | **0.15s** | 0.21s | 0.31s |
|**IQR Deception Index** | 11.93 | 11.00 | **6.42** |
|**Risk Classification** | ✅ SAFE | ✅ SAFE | ✅ SAFE |
|**Range** | 1.15s | 1.43s | **0.93s** |
|**CV** | 19% | 27% | **20%** |

---

## 📅 March 3, 2026 Detailed Analysis

### All Runs (1-10)

*Raw data including cold-starts (Run 1), end-of-run effects (Run 10), and statistical outliers.*

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | 1.35s | 1.36s | **1.21s** |
|**Median** | 1.28s | 1.24s | **1.16s** |
|**Q1 (25th)** | 1.25s | 1.18s | **1.14s** |
|**Q3 (75th)** | 1.31s | 1.27s | **1.24s** |
|**Minimum** | 1.11s | 1.11s | **1.10s** |
|**Maximum** | 2.26s | 2.54s | **1.49s** |
|**Std Dev (σ)** | 0.31s | 0.40s | **0.11s** |
|**P90** | 1.45s | 1.61s | **1.29s** |
|**P95** | 1.86s | 2.07s | **1.39s** |
|**P99** | 2.18s | 2.44s | **1.47s** |
|**IQR** | **0.06s** | 0.09s | 0.10s |
|**IQR Deception Index** | 31.00 | 23.00 | **13.90** |
|**Risk Classification** | 🔴 **SEVERE** | 🟡 **MODERATE** | ✅ SAFE |
|**Range** | 1.15s | 1.43s | **0.39s** |
|**CV** | 23% | 29% | **9%** |

### Stable Runs (2-9, Outliers Removed)

*Represents expected steady-state performance after removing runs 1, 10, and statistical outliers (±2σ).*

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | 1.39s | 1.25s | **1.21s** |
|**Median** | 1.28s | 1.24s | **1.16s** |
|**Q1 (25th)** | 1.26s | 1.18s | **1.14s** |
|**Q3 (75th)** | 1.32s | 1.26s | **1.24s** |
|**Minimum** | 1.11s | 1.11s | **1.12s** |
|**Maximum** | 2.26s | **1.50s** | 1.49s |
|**Std Dev (σ)** | 0.34s | **0.11s** | **0.11s** |
|**P90** | 1.63s | **1.34s** | 1.31s |
|**P95** | 1.95s | 1.42s | **1.40s** |
|**P99** | 2.20s | 1.49s | **1.48s** |
|**IQR** | **0.06s** | 0.08s | 0.10s |
|**IQR Deception Index** | 32.50 | **17.75** | 14.00 |
|**Risk Classification** | 🔴 **SEVERE** | ✅ SAFE | ✅ SAFE |
|**Range** | 1.15s | 0.40s | **0.37s** |
|**CV** | 24% | **9%** | **9%** |

### Outliers Detected - March 3

| Format | Outlier Runs | Value | Threshold (2σ) | Type | Impact |
|:---|:---:|:---:|:---:|:---|:---|
| **Symbolic**🔴 | 6 | 2.26s | >1.47s | Anomaly | Removing increases mean by 0.04s (3.0%) |
| **DSL/JSON** | 10 | 2.54s | >1.47s | Anomaly | Removing reduces mean by 0.11s (8.8%) |
| **Normal** | 10 | 1.99s | >1.43s | End-of-run | Removing reduces mean by 0.03s (2.4%) |

> [!NOTE]
> **IQR Deception Classification:** On this date, Symbolic's IQR Deception Index of 32.5 places it in the 🔴 SEVERE category, leading to its disqualification from Combined Winner consideration. DSL/JSON's index of 23.0 falls into the 🟡 MODERATE range, but its P95 of 1.42s is less than the Dynamic Threshold (T = 3 × 1.21s = 3.63s), classifying it as eligible with an ⚠️ warning.

*Verify these values in [benchmark_20260303.csv](../Benchmark/benchmark_20260303.csv)*

### 📊 Risk Assessment (Mar 3)

| Format | IQR | P95 | Index | T (3× Winner Mean) | P95 < T? | Classification |
|:---|:---:|:---:|:---:|:---:|:---:|:---|
| **Symbolic** | 0.06s | 1.95s | 32.50 | 3.63s | ✅ Yes | 🔴 **SEVERE** (Index >30) |
| **DSL/JSON** | 0.08s | 1.42s | 17.75 | 3.63s | ✅ Yes | ✅ SAFE |
| **Normal** | 0.10s | 1.40s | 14.00 | 3.63s | ✅ Yes | ✅ SAFE |

---
## 📅 March 5, 2026 Detailed Analysis

### All Runs (1-10)

*Raw data including cold-starts (Run 1), end-of-run effects (Run 10), and statistical outliers.*

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | **1.45s** | 1.49s | 1.48s |
|**Median** | 1.33s | **1.34s** | 1.42s |
|**Q1 (25th)** | 1.29s | 1.31s | **1.26s** |
|**Q3 (75th)** | 1.65s | **1.47s** | 1.57s |
|**Minimum** | 1.25s | 1.21s | **1.11s** |
|**Maximum** | **1.76s** | 2.30s | 2.03s |
|**Std Dev (σ)** | **0.19s** | 0.33s | 0.30s |
|**P90** | **1.69s** | 1.97s | 1.99s |
|**P95** | **1.73s** | 2.13s | 2.01s |
|**P99** | **1.76s** | 2.26s | 2.02s |
|**IQR** | 0.36s | **0.16s** | 0.31s |
|**IQR Deception Index** | **4.81** | 13.31 | 6.48 |
|**Risk Classification** | ✅ SAFE | ✅ SAFE | ✅ SAFE |
|**Range** | **0.52s** | 1.09s | 0.91s |
|**CV** | **13%** | 22% | 20% |

### Stable Runs (2-9, Outliers Removed)

*Represents expected steady-state performance after removing runs 1, 10, and statistical outliers (±2σ).*

| Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
|**Mean** | 1.48s | 1.52s | **1.44s** |
|**Median** | 1.44s | **1.33s** | 1.42s |
|**Q1 (25th)** | 1.29s | 1.30s | **1.26s** |
|**Q3 (75th)** | 1.67s | 1.60s | **1.52s** |
|**Minimum** | 1.25s | 1.21s | **1.11s** |
|**Maximum** | **1.76s** | 2.30s | 1.99s |
|**Std Dev (σ)** | **0.20s** | 0.36s | 0.26s |
|**P90** | **1.71s** | 2.04s | 1.72s |
|**P95** | **1.74s** | 2.17s | 1.85s |
|**P99** | **1.76s** | 2.27s | 1.96s |
|**IQR** | 0.38s | 0.30s | **0.26s** |
|**IQR Deception Index** | **4.58** | 7.23 | 7.12 |
|**Risk Classification** | ✅ SAFE | ✅ SAFE | ✅ SAFE |
|**Range** | **0.52s** | 1.09s | 0.88s |
|**CV** | **14%** | 24% | 18% |

### Outliers Detected - March 5

| Format | Outlier Runs | Value | Threshold (2σ) | Type | Impact |
|:---|:---:|:---:|:---:|:---|:---|
| **Symbolic** | None | — | — | — | No outliers detected |
| **DSL/JSON** | 6 | 2.30s | >2.24s | Anomaly | Removing reduces mean by 0.07s (4.9%) |
| **Normal** | 10 | 2.03s | >1.96s | End-of-run | Removing reduces mean by 0.06s (4.1%) |

> [!NOTE]
> **Dynamic Threshold Calculation:** For the Stable Runs on March 5, the Dynamic Threshold (T) is calculated as `3 × Winner_Stable_Mean = 3 × 1.44s = 4.32s`. All formats have P95 values below this threshold, contributing to their ✅ SAFE classification.

*Verify these values in [benchmark_20260305.csv](../Benchmark/benchmark_20260305.csv)*

---

## 📊 Stable Runs Comparison (Runs 2-9)

*Comparing steady-state performance across test dates after outlier removal.*

| Format | Date | Mean | Median | Std Dev | CV | P95 | IQR | IQR Risk | Temporal Change |
|:---|:---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **Symbolic** | Mar 3 | 1.39s | 1.28s | 0.36s | 26% | 1.95s | 0.06s | 🔴 **SEVERE** (32.50) | |
| | Mar 5 | 1.48s | 1.44s | **0.20s** | **14%** | **1.74s** | 0.38s | ✅ SAFE (4.58) | ⬆️ +6.5% slower |
| **DSL/JSON** | Mar 3 | **1.25s** | **1.24s** | **0.11s** | **9%** | **1.42s** | **0.08s** | ✅ SAFE (17.75) | ⭐ **BEST MAR 3 PERFORMANCE** |
| | Mar 5 | 1.52s | 1.33s | 0.36s | 24% | 2.17s | 0.30s | ✅ SAFE (7.23) | ⬆️ **+22% slower** |
| **Normal** | Mar 3 | **1.21s** | **1.16s** | **0.11s** | **9%** | **1.40s** | 0.10s | ✅ SAFE (14.00) | ⭐ **BEST OVERALL MAR 3** |
| | Mar 5 | **1.44s** | 1.42s | 0.26s | 18% | 1.85s | **0.26s** | ✅ SAFE (7.12) | ⬆️ **+19% slower** |

**Temporal Stability Analysis:**

| Format | Temporal Stability Score | Rating | Interpretation |
|:---|:---:|:---:|:---|
| **Symbolic** | `1 - (\|1.39 - 1.48\| / ((1.39 + 1.48)/2)) = 0.94` | ✅ Good | Stable performance across dates despite risk classification change |
| **DSL/JSON** | `1 - (\|1.25 - 1.52\| / ((1.25 + 1.52)/2)) = 0.81` | ⚠️ Moderate | Significant slowdown (+22%) indicates format sensitivity to backend changes |
| **Normal** | `1 - (\|1.21 - 1.44\| / ((1.21 + 1.44)/2)) = 0.83` | ⚠️ Moderate | Consistent slowdown pattern (+19%), predictable degradation |

> [!NOTE]
> **Temporal Stability Score:** This score quantifies consistency across dates. It is calculated as `1 - (|Mean_Date1 - Mean_Date2| / ((Mean_Date1 + Mean_Date2) / 2))` and clipped to the range [0, 1]. A score of **0.95-1.00** is ⭐ Excellent, **0.85-0.94** is ✅ Good, **0.70-0.84** is ⚠️ Moderate, and **<0.70** is ❌ Poor.

---

## 📈 Format Performance Trends

*Visualizing temporal stability and performance evolution across test dates.*

### ⚙️ Symbolic Prompting 🔴

```
Mar 3 (All) :    ████████▒░ 1.35s | σ=0.31s | IQR=0.06s 🔴 SEVERE IQR DECEPTION (Index 30.83)
Mar 3 (Stable) : ████████▒░ 1.39s | σ=0.34s | IQR=0.06s 🔴 CATASTROPHIC TAILS (P95=1.95s)
──────────────────────────────────────────────────────────────────────────────
Mar 5 (All) :    █████████░ 1.45s | σ=0.19s ✅ 39% MORE CONSISTENT than Mar 3 All
Mar 5 (Stable) : █████████░ 1.48s | σ=0.20s ✅ 41% MORE CONSISTENT than Mar 3 Stable
```

**Trend Analysis:** The `Symbolic` format exhibits a dramatic improvement in risk profile between dates, moving from `🔴 SEVERE` (Index 31.00) on Mar 3 to `✅ SAFE` (Index 4.58) on Mar 5. However, this improvement comes with a +6.5% increase in mean latency.

### 🔷 DSL/JSON Prompting


```
Mar 3 (All) :    ████████░░ 1.36s | σ=0.40s | Outlier: 2.54s (Run 10)
Mar 3 (Stable) : ████████░░ 1.25s | σ=0.11s ⭐ EXCELLENT CONSISTENCY (CV=9%)
──────────────────────────────────────────────────────────────────────────────
Mar 5 (All) :    ██████████ 1.49s | σ=0.33s ❌ 9.5% SLOWER than Mar 3 All
Mar 5 (Stable) : ██████████ 1.52s | σ=0.36s ❌ 22% SLOWER, 3.3x MORE VARIABLE than Mar 3 Stable
```

**Trend Analysis:** `DSL/JSON` demonstrates the most severe temporal degradation, with a **22% slowdown** between stable runs and a **3.3x increase in variability** (σ: 0.11s → 0.36s). This pattern exemplifies a format highly sensitive to backend infrastructure changes. Its Temporal Stability Score of 0.81 (`⚠️ Moderate`) confirms this instability.

### 📝 Normal Prompting


```
Mar 3 (All) :    ████████░░ 1.21s | σ=0.11s ⭐ BEST PERFORMANCE (Fastest mean, CV=9%)
Mar 3 (Stable) : ████████░░ 1.21s | σ=0.11s ⭐ BEST PERFORMANCE (P95=1.40s)
──────────────────────────────────────────────────────────────────────────────
Mar 5 (All) :    █████████░ 1.48s | σ=0.30s ❌ 22% SLOWER than Mar 3 All
Mar 5 (Stable) : █████████░ 1.44s | σ=0.26s ❌ 19% SLOWER, 2.4x MORE VARIABLE than Mar 3 Stable
```

**Trend Analysis:** While `Normal` shows significant degradation between dates (+19% slower), its risk profile remains `✅ SAFE` on both dates with predictable variance patterns. The format maintains the lowest combined mean (1.33s) and is the **only format without a `🔴 SEVERE` risk classification on either date**.

---

## 🔍 Key Temporal Insights

| Insight | Description |
|:---|:---|
| **📉 All Formats Degraded** | Every format was slower on March 5—possible backend changes or increased load. Mean performance degraded across all formats by **6.5-22%** , highlighting the importance of multi-date testing. |
| **⚠️ Severe IQR Deception on Mar 3** | On March 3, `Symbolic` showed a **Severe IQR Deception Index of 32.50**—a tight core (IQR=0.06s) but catastrophic tails (P95=1.95s). This pattern is particularly dangerous for production because it masks tail risk and disqualifies `Symbolic` from combined winner consideration despite competitive means. |
| **📈 JSON Collapsed** | `DSL/JSON` went from stellar performance (**1.25s, σ=0.11s, CV=9%**) on Mar 3 to poor (**1.52s, σ=0.36s, CV=24%**) on Mar 5—**22% slower, 3.3x more variable**. Its Temporal Stability Score of **⚠️ 0.81** reflects this instability, confirming it as a high-risk format for production workloads. |
| **📉 Normal Lost Its Edge** | `Normal` went from best performer (1.21s) on Mar 3 to winner (1.44s) on Mar 5—**19% degradation**. Despite this slowdown, it maintains an **⚠️ 0.83 Temporal Stability Score** and is the **only format without a `🔴 SEVERE` risk classification on either date**, making it the sole eligible candidate for the combined winner title. |
| **🔄 Winner Pattern Analysis** | Applying the Unified Winner Declaration Protocol:<br>• **Mar 3 Raw Winner:** `Normal` (1.21s)<br>• **Mar 5 Raw Winner:** `Normal` (1.44s)<br>• **Combined Means:** `Normal` (1.33s) vs. `Symbolic` (1.40s) — a 0.07s difference.<br><br>`Normal` is the **🏆 Stable Winner**, winning the mean on both test dates with `✅ SAFE` risk classification on both dates. |

---
## 🏆 Winner Analysis by Metric

| Metric | Mar 3 Winner<br>(Stable Runs 2-9) | Mar 5 Winner<br>(Stable Runs 2-9) | Combined Winner<br>(Stable Runs 2-9)<br><sup>⚠️ Two-Tier Framework applied</sup> |
|:---|:---:|:---:|:---:|
|**Mean** | 🏆 Normal (1.21s) | 🏆 Normal (1.44s) | 🏆 Normal (1.33s) |
|**Median** | 🏆 Normal (1.16s) | 🏆 DSL/JSON (1.33s) | 🏆 Normal (1.29s)<br><sup>❌ DSL/JSON disqualified</sup> |
|**Minimum** | 🤝 Tie (1.11s) | 🏆 Normal (1.11s) | 🏆 Normal (1.12s) |
|**Maximum** | 🏆 Normal (1.49s) | 🏆 Symbolic (1.76s) | 🏆 Normal (1.74s)<br><sup>❌ Symbolic disqualified</sup> |
|**Std Dev** | 🤝 Tie (0.11s) | 🏆 Symbolic (0.20s) | 🏆 Normal (0.19s)<br><sup>❌ Symbolic disqualified</sup> |
|**P95** | 🏆 Normal (1.40s) | 🏆 Symbolic (1.74s) | 🏆 Normal (1.63s)<br><sup>❌ Symbolic disqualified</sup> |
|**IQR** | 🏆 Symbolic (0.06s) | 🏆 Normal (0.26s) | 🏆 Normal (0.18s)<br><sup>❌ Symbolic disqualified</sup> |
|**Range** | 🏆 Normal (0.37s) | 🏆 Symbolic (0.52s) | 🏆 Normal (0.63s)<br><sup>❌ Symbolic disqualified</sup> |
|**CV** | 🏆 DSL/JSON (0.09s) | 🏆 Symbolic (0.14s) | 🏆 Normal (0.14s)<br><sup>❌ DSL/JSON, Symbolic disqualified</sup> |
|**Overall Winner by Date** | 🏆 **Normal** | 🏆 **Normal** | 🏆 **Normal** |

**Winner Dominance Analysis:**

| Format | Metrics Won | Metric Superiority Score | Tie Rate |
|:---|:---:|:---:|:---:|
| **Normal** | 7/9 | 78% | 11% |
| **Symbolic** | 1/9 | 11% | 11% |
| **DSL/JSON** | 1/9 | 11% | 11% |

---

## 📊 Format Evolution Summary

*Tracking performance changes and temporal stability across test dates.*

| Format | Metric | Mar 3 | Mar 5 | Change | Temporal Stability | Combined IQR Index | Per-Date IQR Risk |
|:---|:---|:---:|:---:|:---|:--:|:---:|:---|
| **Symbolic** | Mean (All) | 1.35s | **1.45s** | ⬆️ +7.4% | ✅ 0.93 (Good) | 11.93 (✅ Safe) | 🔴 **SEVERE on Mar 3** (31.00) |
| | Mean (Stable) | 1.39s | 1.48s | ⬆️ +6.5% | ✅ 0.94 (Good) | | ✅ Safe on Mar 5 (4.81) |
| | Std Dev (Stable) | 0.34s | **0.20s** | ⬇️ **-41% MORE CONSISTENT** | N/A | | |
| **DSL/JSON** | Mean (All) | 1.36s | 1.49s | ⬆️ +9.5% | ✅ 0.91 (Good) | 11.00 (✅ Safe) | 🟡 **MODERATE on Mar 3** (23.00) |
| | Mean (Stable) | **1.25s** | 1.52s | ⬆️ **+22% SLOWER** | ⚠️ **0.81 (Moderate)** | | ✅ Safe on Mar 5 (13.31) |
| | Std Dev (Stable) | **0.11s** | 0.36s | ⬆️ **+227% MORE VARIABLE (3.3x)** | N/A | | |
| **Normal** | Mean (All) | **1.21s** | 1.48s | ⬆️ +22% | ⚠️ **0.80 (Moderate)** | **6.42** (✅ Safe) | ✅ **SAFE ON ALL DATES** |
| | Mean (Stable) | **1.21s** | **1.44s** | ⬆️ **+19% SLOWER** | ⚠️ **0.83 (Moderate)** | | Mar 3: 14.00 (✅) |
| | Std Dev (Stable) | **0.11s** | 0.26s | ⬆️ **+136% MORE VARIABLE (2.4x)** | N/A | | Mar 5: 7.12 (✅) |

---

## 📈 Performance Trend Visualization

```
SYMBOLIC 🔴 (DISQUALIFIED - 🔴 SEVERE RISK ON MAR 3)
────────────────────────────────────────────────
Speed: 1.39s ──────────┐
▼
1.48s ────────────────────► +6.5% SLOWER

Consist: 0.34s ────────┐ (σ)
▼
0.20s ────────────────────► 41% MORE CONSISTENT ✅

IQR Risk: 🔴 SEVERE (Mar 3) → ✅ SAFE (Mar 5)

DSL/JSON (DISQUALIFIED - 🔴 SEVERE RISK ON MAR 3)
────────────────────────────────────────────────
Speed: 1.25s ──────────┐ ⭐ BEST ON MAR 3
▼
1.52s ────────────────────► +22% SLOWER ❌

Consist: 0.11s ────────┐ ⭐ MOST CONSISTENT ON MAR 3
▼
0.36s ────────────────────► 227% MORE VARIABLE (3.3x) ❌

Temporal Stability: ⚠️ 0.81 (Moderate)

NORMAL (🏆 COMBINED WINNER)
────────────────────────────────────────────────
Speed: 1.21s ──────────┐ ⭐ BEST ON MAR 3
▼
1.44s ────────────────────► +19% SLOWER ❌

Consist: 0.11s ────────┐ ⭐ MOST CONSISTENT ON MAR 3
▼
0.26s ────────────────────► 136% MORE VARIABLE (2.4x) ❌

IQR Risk: ✅ SAFE (Mar 3) → ✅ SAFE (Mar 5)
Temporal Stability: ⚠️ 0.83 (Moderate)
```


---

## ✅ Final Verdict

| Aspect | Conclusion |
|:---|:---|
| **Overall Production Winner** | 🏆 **Normal** |
| | **Rationale:** Following the IQR Deception methodology and the Unified Winner Declaration Protocol, `Normal` is the **only format eligible for combined winner consideration**. It maintains `✅ SAFE` IQR classifications across **both test dates** (14.00 on Mar 3, 7.12 on Mar 5) and exhibits **no severe tail-risk events**. It also has the fastest combined mean (1.33s) and acceptable temporal stability (⚠️ 0.83). Both `Symbolic` and `DSL/JSON` are **disqualified** due to risk-based disqualification—`Symbolic` for `🔴 SEVERE` IQR risk on March 3, and `DSL/JSON` for having the highest combined mean (1.43s) after risk screening. |
| | **For Maximum Reliability:** 🏆 **Normal** (No severe tail-risk events, consistent across both dates, fastest combined mean) |
| | **For Maximum Speed (with continuous monitoring):** ⚡ **Symbolic** (Competitive mean, better Mar 5 performance, 41% more consistent on latest test) |
| | *Critical Context: Symbolic's Mar 3 IQR Deception (Index 32.50, P95=1.95s) is a real production risk. If choosing Symbolic, you must implement continuous P95 monitoring and have a fallback to Normal.* |
| **Best Single-Day Performance** | ⭐ **Normal on Mar 3** (1.21s stable mean, σ=0.11s) |
| **Most Stable Across Dates** | 📊 **Symbolic** (Smallest degradation at 6.5%, 41% improved consistency, but **disqualified** due to 🔴 Severe IQR risk on Mar 3) |
| **Most Improved** | 📈 **Symbolic** (41% more consistent while limiting speed loss, but carries **🔴 Severe IQR risk** from Mar 3 - **NOT production-safe**) |
| **Biggest Decline** | 📉 **DSL/JSON** (22% slower, 227% more variable - catastrophic instability) |
| **Most Unpredictable Format** | ⚠️ **DSL/JSON** (Stellar on Mar 3: 1.25s, σ=0.11s; terrible on Mar 5: 1.52s, σ=0.36s) |

### Risk Assessment Summary

| Risk Metric | Symbolic | DSL/JSON | Normal |
|:---|:---:|:---:|:---:|
| **IQR Deception Index (Mar 3)** | **32.50** (🔴 Severe) | **17.75** (✅ Safe) | 14.00 (✅ Safe) |
| **IQR Deception Index (Mar 5)** | 4.58 (✅ Safe) | 7.23 (✅ Safe) | 7.12 (✅ Safe) |
| **Two-Factor Assessment (Mar 3)** | Index >30 → 🔴 **Severe Risk** | Index <20 → ✅ **Safe** | ✅ **Safe** |
| **Tail-Risk Status (Mar 3)** | 🔴 **CATASTROPHIC** (5% >1.95s) | ✅ **Acceptable** (5% >1.42s) | ✅ **Acceptable** |
| **Outlier Rate (Mar 3)** | 10% (1/10) | 10% (1/10) | 10% (1/10) |
| **Temporal Stability Score** | ✅ 0.94 (Good) | ⚠️ 0.81 (Moderate) | ⚠️ 0.83 (Moderate) |
| **Global Eligibility Status** | ❌ **DISQUALIFIED** | ❌ **DISQUALIFIED** | ✅ **ELIGIBLE** |
| **Production Readiness** | 🔴 **NOT RECOMMENDED** | 🔴 **NOT RECOMMENDED** | 🟢 **READY** |

---

## 📋 Recommendations

| Use Case | Recommended Format | Rationale |
|:---|:---|:---|
| **General production (SAFE CHOICE)** | ✅ **Normal** | Fastest combined mean (1.33s) and the **only format with `✅ SAFE` IQR classifications across all dates** (14.00 on Mar 3, 7.12 on Mar 5). No severe tail-risk events. |
| **If you need maximum speed and can tolerate significant tail-risk** | ⚠️ **Symbolic** (with caveats) | Competitive combined mean (1.40s) but **disqualified** due to `🔴 SEVERE` IQR Deception on Mar 3 (Index 32.50, P95=1.95s). 5% of requests on that date were catastrophically slow. **NOT suitable for strict SLAs.** Requires continuous P95 monitoring and automated fallback to `Normal`. |
| **If you ran only on Mar 3** | ⭐ **Normal** | Exceptional performance on that date (1.21s stable mean, σ=0.11s, CV=9%) with `✅ SAFE` IQR classification (14.00). |
| **If you ran only on Mar 5** | 🏆 **Normal** | Despite `Symbolic` having a competitive mean on Mar 5 (1.48s), `Normal` is still recommended because `Symbolic`'s `🔴 SEVERE` risk on Mar 3 demonstrates that a single-date snapshot is insufficient. The format's behavior is inconsistent—what works today may fail catastrophically tomorrow. |
| **If core consistency (IQR) is your only metric** | ⚠️ **Symbolic** (with severe caveat) | Excellent IQR (0.06s on Mar 3) **masks catastrophic tail-risk** (P95=1.95s). This is a textbook example of IQR Deception. Do not use IQR as your primary decision metric without also monitoring P95. |
| **If you need JSON format** | 🔴 **NOT RECOMMENDED** | `DSL/JSON` is disqualified due to the **highest combined mean (1.43s)** among all formats, coupled with unacceptable temporal instability (+22% slower, 3.3x more variable). |

---

## 📁 Quick Reference Card

| If you want... | Use this format on gpt-4o-mini |
|:---|:---|
| **General production (SAFE CHOICE)** | 🏆 **Normal** (1.33s combined mean) | ✅ **Only format with `✅ SAFE` IQR classifications on all dates** (14.00 Mar 3, 7.12 Mar 5). The uniquely eligible format under the Two-Tier Eligibility Framework. |
| **Best single-day performance** | ⭐ **Normal** (1.21s on Mar 3 stable runs, σ=0.11s, CV=9%) |
| **Most stable across dates** | 📊 **Symbolic** (only 6.5% degradation between tests) | ❌ **But disqualified** due to `🔴 SEVERE` IQR Deception on Mar 3 (Index 32.50). |
| **Most improved format** | 📈 **Symbolic** (41% more consistent on Mar 5) | ❌ **But disqualified** due to `🔴 SEVERE` IQR risk on Mar 3. |
| **Maximum throughput with risk tolerance** | ⚠️ **Symbolic** (with caveats) | 🔴 **Not recommended for most use cases.** Competitive mean (1.40s) but `🔴 SEVERE` IQR Deception on Mar 3 (32.50) means 5% of requests exceeded **1.95s**. Only suitable with continuous P95 monitoring and automated fallback to `Normal`. |
| **JSON-native workflows** | 🔴 **NOT RECOMMENDED: DSL/JSON** | ❌ Disqualified due to highest combined mean (1.43s) and worst temporal instability (+22% slower, 3.3x more variable). |

---

> *"We don't ask you to trust our numbers. We give you the tools to verify them yourself."*

---
## 📊 Risk Legend - Quick Reference

| Symbol | Meaning | Production Implication |
|:---:|:---|:---|
| **✅ SAFE** | IQR Deception Index <20 | **Fully eligible for production.** Tight core and acceptable tails. |
| **🟡 MODERATE** | IQR Index 20-30 AND P95 < T (Dynamic Threshold) | **Eligible with monitoring.** Format name MUST be marked with `⚠️` in all tables. Requires ongoing P95 tracking. |
| **🔴 SEVERE** | IQR Index >30 OR (Index 20-30 AND P95 ≥ T) | **DISQUALIFIED** from production winner status. High tail-risk makes format unsuitable for strict SLAs. |
| **🚨 CRITICAL** | IQR Index >50 | **DISQUALIFIED.** Unusable for production—extreme tail-risk. |
| **🔄 WATCH LIST** | 🔴 Severe on anomalous date (documented) | **Retest pending.** Requires 24-48h retest before final determination. |
| **⭐ EXCELLENT** | Temporal Stability Score 0.95-1.00 | Virtually identical performance across test dates. Highly reliable. |
| **✅ GOOD** | Temporal Stability Score 0.85-0.94 | Minor variance, still reliable for most use cases. |
| **⚠️ MODERATE** | Temporal Stability Score 0.70-0.84 | Noticeable fluctuation between tests. Monitor closely. |
| **❌ POOR** | Temporal Stability Score <0.70 | Significant day-to-day variance. Format sensitive to backend changes. |

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
- Jesus Huerta aka <em><a href="https://github.com/mindhack03d" rel="nofollow">@(\_mindhack03d_)</a></em></br>

## Contributors
- Alex Hernandez aka <em><a href="https://twitter.com/_alt3kx_" rel="nofollow">@(\_alt3kx\_)</a></em></br>


[⬅️ Back to Home](../README.md) | [Methodology used](../Benchmark/benchmark_methodology.md)