# PUF-Based 8T SRAM Circuit Design for In-Memory Computing Applications

[![Thesis](https://img.shields.io/badge/Nemertes-Institutional%20Repository-005596.svg)]([https://nemertes.library.upatras.gr/](https://nemertes.library.upatras.gr/items/33239f5f-763d-4461-9c4c-8cba7e36190b)
[![Presentation](https://img.shields.io/badge/Slides-Presentation%20PDF-red.svg)](PROJECT_PRESENTATION.pdf)

> **Author:** Odysseas Zachos  
> **Degree:** B.Sc. / M.Eng. Thesis, Department of Computer Engineering and Informatics (CEID), University of Patras  
> **Official Repository Link:** [Read Published Thesis on Nemertes](https://nemertes.library.upatras.gr/)  
> **Presentation Deck:** [Project Presentation (PDF)](PROJECT_PRESENTATION.pdf)

---

## 📌 Executive Summary & Impact
This repository showcases the implementation, simulation, and hardware security evaluation of a novel **Physical Unclonable Function (PUF)** architecture seamlessly integrated into an **8T SRAM** memory array. Designed using **UMC 28nm CMOS technology**, this work solves a critical trade-off in resource-constrained IoT security: **delivering silicon-level hardware authentication and cryptographic key generation without dedicated non-volatile memory or significant area overhead.**

By exploiting intrinsic process variations during read operations, the circuit generates unique, reproducible digital fingerprints on-demand while preserving full **In-Memory Computing (IMC)** operational capabilities.

---

## 🚀 Key Innovations & Architectural Value

* **Zero-Storage Cryptographic Security:** Traditional hardware keys stored in EEPROM/Flash are vulnerable to side-channel and physical reverse-engineering attacks. This design generates cryptographic keys **dynamically from silicon device mismatch**, leaving no permanent key trace in memory.
* **Dual-Functional 8T Substrate:** Operates as high-density RAM for memory/IMC tasks and transforms into a security primitive on-demand, maximizing area efficiency for edge-AI and IoT SoCs.
* **Disturb-Free Read Architecture:** Capitalizes on the 8T cell's isolated read path (separate read transistor decoupling the internal storage nodes) to eliminate read-disturb vulnerabilities during high-frequency PUF evaluations.
* **Ultra-Low Overhead Comparison:** Implements column-shared voltage differential comparators to digitize subtle discharge rate mismatches on Bitlines (`RBL`), minimizing active area and power consumption.
* **Comprehensive PVT Robustness:** Rigorously proven to maintain output integrity under severe supply voltage fluctuations and wide thermal gradients (process, voltage, temperature corner sweeps).

---

## 📊 Rigorous Verification & Monte Carlo Performance

Evaluation across **6,300 Monte Carlo simulation runs** per corner in Cadence Virtuoso Spectre confirms industrial-grade reliability, uniqueness, and tamper resistance metrics:

| Security Metric | Value | Ideal / Standard | Engineering Insight |
|---|---|---|---|
| **Temperature Reliability** | **98.46%** | 100% | Exceptional output consistency across thermal variations |
| **Voltage Reliability** | **93.94%** | 100% | Stable key generation under supply voltage droop conditions |
| **Mean Overall Reliability** | **95.60%** | 100% | High bit reproducibility for key extraction |
| **Uniqueness** | **46.50%** | 50.00% | Near-ideal inter-chip variation across fabricated instances |
| **Uniformity** | **55.00%** | 50.00% | Well-balanced 0/1 bit hamming weight distribution |
| **Tamper Resistance** | **51.92%** | 50.00% | Resilient against invasive probing and environmental bias |

---

## 🛠️ Design Environment & Toolchain
* **CAD & EDA Tools:** Cadence Virtuoso IC design suite, Spectre Circuit Simulator
* **CMOS Technology Node:** UMC 28nm planar CMOS PDK
* **Simulation Paradigms:** High-yield Monte Carlo analysis, multi-corner PVT analysis, transient voltage differential timing
* **Core Domains:** Hardware Security, VLSI Mixed-Signal Design, Digital Memory Architecture, In-Memory Computing (IMC)

---

## 🏗️ Architecture & Mechanism Overview
1. **8T Storage Cell Array:** Dual-port configuration separating write nodes from read evaluation paths.
2. **Precharge & Timing Logic:** Pre-charges `RBL` nodes before challenge-response evaluation cycles.
3. **Differential Sensing Unit:** High-gain voltage comparator sensing threshold voltage ($V_{th}$) mismatch between differential discharge paths.

---

## 📂 Publications & Documentation
* 📜 **Full Thesis Document:** Available officially on the [University of Patras Nemertes Repository](https://nemertes.library.upatras.gr/).
* 📊 **Slide Deck:** Access the presentation slides directly via [Thesis Presentation PDF](docs/presentation.pdf).

---

## 📬 Contact & Portfolio
Designed and developed by **Odysseas Zachos**. Feel free to connect for discussions on Hardware Security, VLSI Design, or Software Engineering opportunities.
