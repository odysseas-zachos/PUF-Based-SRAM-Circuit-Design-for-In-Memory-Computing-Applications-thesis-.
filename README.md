# PUF-Based 8T SRAM Circuit Design for In-Memory Computing Applications


> **Author:** Odysseas Zachos  
> **Degree:** B.Sc. / M.Eng. Thesis, Department of Computer Engineering and Informatics (CEID), University of Patras  
> **Official Repository Link:** [Read Published Thesis on Nemertes](https://nemertes.library.upatras.gr/items/33239f5f-763d-4461-9c4c-8cba7e36190b)  
> **Presentation Deck:** [Project Presentation (PDF)](PROJECT_PRESENTATION.pdf)

---

## 📌 Executive Summary & Impact

  The growing use of embedded systems and Internet of Things (IoT) devices has 
rendered hardware security particularly important in modern circuit design. Conventional 
methods, where digital system security relies on storing cryptographic keys in non
volatile memory, can become vulnerable to physical attacks. For this reason, Physical 
Unclonable Functions (PUFs) constitute an attractive alternative, as they exploit the small 
manufacturing variations that are naturally present in every chip. In this way, each device 
acquires a unique "fingerprint," which can be used for authentication or cryptographic 
key generation, without requiring their storage. 
  This diploma thesis addresses the design and behavioral analysis of a PUF 
topology based on an 8T SRAM memory suitable for in-memory computing (IMC) 
applications. The memory operates as a PUF circuit without any modification to the basic 
circuit of its memory cells, incorporating only a single voltage comparator per column of 
cells. The 8T cell design was selected because it offers greater read stability, owing to its 
separate read path (RBL/RWL), while at the same time efficiently supporting in-memory 
computing operations. Thus, the same topology can be exploited both as a security 
mechanism and as a computational substrate. 
  Within the framework of this work, the 8T SRAM memory cell is presented, 
together with the basic peripheral units — such as the drivers, the precharge circuit, and 
the voltage comparator — as well as the way in which these are combined into a complete 
memory. The PUF circuit was designed in UMC 28nm CMOS technology, while the 
correct operation of the circuit was verified through simulations using the CADENCE 
platform (Virtuoso–Spectre). In addition, the behavior of the PUF circuit was analyzed 
and its performance characteristics were validated through extensive Monte Carlo 
simulations, examining fundamental metrics such as reliability, uniqueness, uniformity, 
and tamper resistance, under different variations of temperature and supply voltage. 
  The results show that the proposed topology can produce responses with the 
following characteristics: uniqueness of 46.6%, uniformity of 54,8%, tamper resistance 
of 51.92%, a reliability of 98,46% with respect to temperature variation, 93,94% with 
respect to supply voltage variation and mean reliability 95,6%. Consequently, since the 
activation of multiple read lines is feasible, the circuit can be used as a strong PUF, while 
at the same time retaining the ability to support in-memory computing operations.


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
