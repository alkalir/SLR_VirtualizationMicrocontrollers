# Virtualization for Microcontroller-based Mixed-Criticality Systems: A Systematic Literature Review

## Repository Overview

This repository contains all the documentation and supporting materials related to the Systematic Literature Review (SLR) presented in the paper:

> L. Fazzini, G. Valente, F. Caruso, L. Pomante, and T. Di Mascio. **"Virtualization for Microcontroller-based Mixed-Criticality Systems: A Systematic Literature Review."** *Manuscript submitted to ACM*, 2026.

The SLR investigates how virtualization is implemented and managed in microcontroller-based mixed-criticality systems, covering the period 2015–2025. It follows the Kitchenham guidelines for systematic literature reviews in software engineering and identifies **19 primary studies** from an initial pool of **10,678 research articles** retrieved across five digital libraries.

The repository is organized to ensure **transparency**, **reliability**, and **replicability** of the review process.

---

## Repository Structure

```
SLR_Database/
│
├── README.md                              # This file (repository overview + SR Protocol)
│
├── 00_Background Articles/                # Full-text PDFs of related secondary studies
│   └── README.md
│
├── 01_Queries/                            # Search strings applied to each digital library
│   ├── README.md
│   └── Search_Queries_per_Database.xlsx
│
├── 02_Study_Selection/                    # Complete five-stage study selection process
│   ├── README.md
│   ├── STAGE1/                            # Automatic filtering in digital libraries (10,678 → 5,364)
│   │   └── README.md
│   ├── STAGE2/                            # Semi-automatic deduplication and consolidation (5,364 → 637)
│   │   └── README.md
│   ├── STAGE3/                            # Title, abstract, and introduction screening (637 → 144)
│   │   └── README.md
│   ├── STAGE4/                            # Full-text analysis (144 → 11 + 4 snowballing seeds)
│   │   └── README.md
│   ├── STAGE5/                            # Forward and backward snowballing (838 candidates → +8 = 19)
│   │   └── README.md
│   └── Included_and_Excluded_Research_Articles_recap.xlsx
│
├── 03_Included_PaPers/                    # Full-text PDFs of the 19 included primary studies
│   └── README.md
│
└── 04_Data Extraction/                    # Data extraction form and completed extraction
    ├── README.md
    ├── Data_Extraction_Form.xlsx
    └── Extracted_Data.xlsx
```

Each subfolder contains its own `README.md` with a detailed description of the content and of the activities performed at that stage of the review.

---

## Study Selection Process

The study selection followed a five-stage filtering procedure:

| Stage | Description | Criteria | Articles Before | Articles After |
|-------|-------------|----------|-----------------|----------------|
| STAGE 1 | Automatic filtering in digital libraries | EX1, EX2, EX3, EX6 | 10,678 | 5,364 |
| STAGE 2 | Semi-automatic filtering (consolidation, deduplication) | EX2, EX3, EX5, EX6, EX7 | 5,364 | 637 |
| STAGE 3 | Title, abstract, and introduction screening | EX2–EX9 | 637 | 144 |
| STAGE 4 | Full-text analysis | EX1–EX10 | 144 | 11 (+ 4 seeds) |
| STAGE 5 | Forward and backward snowballing | All criteria | 838 candidates | 11 + 8 = **19** |

---

## Research Questions

The SLR addresses the following overall research question:

> **How is virtualization implemented and managed in microcontroller-based mixed-criticality systems?**

This is decomposed into five specific research questions:

- **RQ1**: What virtualization solutions have been proposed and how do they differ across virtualization dimensions?
- **RQ2**: What hardware platforms are targeted and which architectural features enable or constrain virtualization?
- **RQ3**: How are memory partitioning, trap handling, and I/O virtualization implemented?
- **RQ4**: How is virtualization configured and managed across the system life cycle?
- **RQ5**: What is the impact of virtualization in terms of performance?

---

## Data Extraction Form

The data extraction form comprises **42 parameters** organized into **9 colour-coded groups**:

| Group | Addressed RQ | Parameters |
|-------|-------------|------------|
| General Paper Information | RQ1 | Year, Author, Title, Database, DOI, Venue |
| Virtualization Dimensions | RQ1 | Virtualization layer, Deployment model, Interface model, Guest adaptation model, Virtualized resource, Partitioned resource |
| Know Your Hardware | RQ2 | ISA, Processor model, Core configuration, Clock frequency, Privilege levels, Protection units, Additional HW mechanisms |
| Partitioning Memory | RQ3 | HW-based isolation, SW-based isolation |
| Handling Traps and Interrupts | RQ3 | Interrupt handling, Privilege emulation, Exception handling |
| I/O Virtualization | RQ3 | Peripheral virtualization strategy, Support for shared peripherals |
| Start-Up Sequence and Partition Switch | RQ4 | Boot order, Partition creation, Partition switch, Partition scheduling |
| Services to Partitions | RQ4 | Task handling, Shared memory, IPC, Service interface |
| Impact on Performance | RQ5 | Total execution time, Context switch, Hypercall latency, Interrupt latency, I/O latency, HW resource, Power, Memory footprint |

---

## Data Sources

The search was conducted in **August 2025** across the following digital libraries:

- ACM Digital Library
- IEEE Xplore
- Scopus
- ScienceDirect
- Web of Science

---

## Search Query

```
((virtualiz* OR partition* OR isolat* OR hypervisor* OR container* OR separation kernel*
  OR microkernel* OR unikernel* OR TEE* OR trusted execution environment*)
AND
(microcontroller* OR micro controller* OR MCU* OR TrustZone-M
  OR ((resource constrained OR low end)
  AND (system* OR device* OR processor* OR core OR hardware OR HW OR platform))))
```

---

## 19 Included Primary Studies

| # | Reference | Year | Title |
|---|-----------|------|-------|
| 1 | Reinhardt et al. | 2015 | Virtualized Communication Controllers in Safety-Related Automotive Embedded Systems |
| 2 | Zuepke et al. | 2015 | AUTOBEST: A United AUTOSAR-OS and ARINC 653 Kernel |
| 3 | Kohn et al. | 2017 | Timing Analysis for Hypervisor-Based I/O Virtualization in Safety-Related Automotive Systems |
| 4 | Pan et al. | 2018 | Predictable Virtualization on Memory Protection Unit-Based Microcontrollers |
| 5 | Rajan et al. | 2018 | Hypervisor for Consolidating Real-Time Automotive Control Units |
| 6 | Jiang et al. | 2019 | BlueIO: A Scalable Real-Time Hardware I/O Virtualization System |
| 7 | Jiang et al. | 2019 | MCS-IOV: Real-Time I/O Virtualization for Mixed-Criticality Systems |
| 8 | Pan et al. | 2019 | MxU: Towards Predictable, Flexible, and Efficient Memory Access Control |
| 9 | Pinto et al. | 2019 | Virtualization on TrustZone-Enabled Microcontrollers? Voilà! |
| 10 | Dasari et al. | 2020 | Applying Reservation-Based Scheduling to a μC-Based Hypervisor |
| 11 | Li et al. | 2022 | iSotEE: A Hypervisor Middleware for IoT-Enabled Resource-Constrained Reliable Systems |
| 12 | Pan et al. | 2022 | SBIs: Application Access to Safe, Baremetal Interrupt Latencies |
| 13 | Jiang et al. | 2023 | Towards Hard Real-Time and Energy-Efficient Virtualization for Manycore Embedded Systems |
| 14 | Barletta et al. | 2024 | Integrating Containers and Partitioning Hypervisors for Dependable Real-Time Industrial Clouds |
| 15 | Ottaviano et al. | 2024 | The Omnivisor: A Real-Time Static Partitioning Hypervisor Extension |
| 16 | Fazzini et al. | 2025 | Multi-Context Execution on a RISC-V Core for Mixed-Criticality Systems |
| 17 | Li et al. | 2025 | FVM: Practical Feather-Weight Virtualization on Commodity Microcontrollers |
| 18 | Rivera et al. | 2025 | HiRTOS: A Multi-Core RTOS Written in SPARK Ada |
| 19 | Seidler et al. | 2025 | Wasm-IO: Enabling Low-Level Device Interaction in WebAssembly for Industry Automation |

---

# SR Protocol

Review protocol for **Virtualization for Microcontroller-based Mixed-Criticality Systems**.

## Team Information

| Field | Value |
|-------|-------|
| **Project Lead** | LF |
| **Research Team Members** | LF, GV, FC, LP, TDM |
| **Date** | August 2025 – April 2026 |
| **Institution** | Department of Information Engineering, Computer Science and Mathematics (DISIM), University of L'Aquila, Italy |

## Review Research Question

**Full Review Question**

> How is virtualization implemented and managed in microcontroller-based mixed-criticality systems?

This overall question is decomposed into five specific research questions:

- **RQ1** — What are the characteristics of virtualization solutions proposed for microcontroller-based mixed-criticality systems?
- **RQ2** — On which hardware platforms are these solutions implemented and evaluated?
- **RQ3** — How is isolation between partitions enforced (memory, traps/interrupts, I/O)?
- **RQ4** — How is the life-cycle of a partition managed (boot, creation, scheduling, communication)?
- **RQ5** — What is the impact of the proposed virtualization solution on system performance?

## Search Strategy

### Search String

The full search string applied to the selected digital libraries is:

```
((virtualiz* OR partition* OR isolat* OR hypervisor* OR container* OR separation kernel*
  OR microkernel* OR unikernel* OR TEE* OR trusted execution environment*)
AND
(microcontroller* OR micro controller* OR MCU* OR TrustZone-M
  OR ((resource constrained OR low end)
  AND (system* OR device* OR processor* OR core OR hardware OR HW OR platform))))
```

The string was adapted to the syntax of each digital library; the exact queries effectively submitted are recorded in `01_Queries/Search_Queries_per_Database.xlsx`.

### Digital Resources

The following bibliographic databases were searched in August 2025:

1. Scopus — <https://www.scopus.com>
2. ACM Digital Library — <https://dl.acm.org>
3. IEEE Xplore Digital Library — <https://ieeexplore.ieee.org>
4. ScienceDirect — <https://www.sciencedirect.com>
5. Web of Science — <https://www.webofscience.com>

### Hand Searching

No manual journal-by-journal hand searching was performed: all candidate articles came either from the database searches listed above (STAGE 1) or from the snowballing procedure (STAGE 5).

### Reference Searches

Forward and backward snowballing, as recommended by Wohlin's guidelines, were performed in STAGE 5 starting from **15 seed papers** (the 11 primary studies identified in STAGE 4 plus 4 additional papers flagged as "kept for snowballing" in STAGE 4.2):

- **Backward snowballing** — inspection of the reference lists of each seed paper, to identify relevant older papers cited by the seeds.
- **Forward snowballing** — inspection of the papers citing each seed (via Google Scholar, Scopus, IEEE Xplore, Web of Science), to identify relevant newer papers that cite the seeds.

The snowballing process produced 838 raw candidates (≈ 693 unique titles after deduplication), from which 8 additional primary studies were identified. Details are reported in `02_Study_Selection/STAGE5/README.md`.

## Inclusion Factors

| Code | Description |
|------|-------------|
| **IN1** | Proposes or evaluates a virtualization solution |
| **IN2** | Targets microcontroller-based or resource-constrained platforms |
| **IN3** | Addresses mixed-criticality workloads |
| **IN4** | Published between January 2015 and July 2025 |
| **IN5** | Written in English |
| **IN6** | Primary study (journal article, conference paper, or workshop paper) |
| **IN7** | Full text available |

## Exclusion Factors

| Code | Description |
|------|-------------|
| **EX1** | Published before 2015 or after July 2025 |
| **EX2** | Not written in English |
| **EX3** | Not a journal article, conference paper, or workshop paper (e.g., editorial, poster, thesis, technical report) |
| **EX4** | Duplicate (within the same digital library) |
| **EX5** | Duplicate (cross-database) |
| **EX6** | Not related to computer science or engineering |
| **EX7** | Secondary or tertiary study (survey, review, systematic review, meta-analysis) |
| **EX8** | Does not address virtualization on embedded/constrained platforms |
| **EX9** | Focuses on high-end processors (e.g., Cortex-A, x86) or application-class/cloud virtualization |
| **EX10** | Does not address mixed-criticality aspects |

## Data Extraction

A dedicated data-extraction form was designed to systematically record the information needed to answer the five research questions. The form is implemented as an electronic spreadsheet (`04_Data Extraction/Data_Extraction_Form.xlsx`) and defines **42 parameters**, organised into **9 thematic colour-coded groups**:

1. **General Paper Information** (RQ1) — 6 parameters: Year, Authors, Title, Database/Library, DOI, Venue.
2. **Virtualization Dimensions** (RQ1) — 6 parameters: Virtualization layer, Deployment model, Interface model, Guest adaptation model, Virtualized resource, Partitioned resource.
3. **Know Your Hardware** (RQ2) — 7 parameters: Instruction-set architecture, Processor model, Core configuration, Clock frequency, Privilege levels, Protection units, Additional HW mechanisms.
4. **Partitioning Memory** (RQ3) — 2 parameters: HW-based isolation, SW-based isolation.
5. **Handling Traps and Interrupts** (RQ3) — 3 parameters: Interrupt handling, Privilege emulation, Exception handling.
6. **I/O Virtualization** (RQ3) — 2 parameters: Peripheral virtualization strategy, Support for shared peripherals.
7. **Start-Up Sequence and Partition Switch** (RQ4) — 4 parameters: Boot order, Partition creation, Partition switch, Partition scheduling.
8. **Services to Partitions** (RQ4) — 4 parameters: Task handling inside partitions, Shared memory regions, Inter-partition communication, Service interface.
9. **Impact on Performance** (RQ5) — 8 parameters: Total execution time overhead, Context switch overhead, Hypercall latency, Interrupt handling latency, I/O access latency, HW resource overhead, Power overhead, Memory footprint.

Data extraction was performed **independently by two reviewers** (Leonardo Fazzini and Giacomo Valente) reading the full text of each of the 19 primary studies. Disagreements were resolved through discussion and consensus with the other authors, obtaining a single completed row per paper in the final extraction table (`04_Data Extraction/Extracted_Data.xlsx`).

## Study Quality Assessment

Following Kitchenham's guidelines, the main quality criterion adopted is the **availability of a concrete implementation and evaluation** of the proposed virtualization mechanism. This requirement is embedded in the inclusion/exclusion criteria themselves — specifically in IN1 (proposes or evaluates a virtualization solution) and in EX8 (does not address virtualization). Papers surviving STAGE 4 (full-text analysis) are considered to have met this minimum-quality bar.

In addition, for each included primary study the reviewers recorded whether:

- the paper clearly identifies the hardware platform and protection mechanisms used;
- the paper reports quantitative performance measurements (overheads, latencies, memory footprint);
- the paper provides a reproducible description of the isolation and scheduling strategies.

These quality indicators are reflected in the extracted data and are used in the discussion of results to weight the contribution of each primary study.

## Data Synthesis

The extracted data were analysed and summarised through **descriptive analysis** (frequency analysis) and **taxonomy-based classification**. For each research question, the answers recorded in the extraction form were aggregated and classified according to the taxonomy of virtualization dimensions adopted in the SLR. The results of the synthesis are reported in the manuscript as tables, charts and narrative discussion addressing each research question (RQ1–RQ5).

## Research Team Member Roles

| Task | Description | Responsible |
|------|-------------|-------------|
| **DATABASE SEARCH** | Search in selected databases | LF |
| **STAGE 1** | Automatic filtering on the selected digital libraries | LF|
| **STAGE 2** | Semi-automatic consolidation and deduplication of the results | LF|
| **STAGE 3** | Screening of title, abstract, and introduction against EX2–EX9 | LF, GV |
| **STAGE 4** | Full-text analysis against EX1–EX10 (including EX10 keyword pre-screening) | LF, GV |
| **STAGE 5** | Forward and backward snowballing + full-text analysis of candidates | LF, GV, LP |
| **Study Quality Assessment** | Assessment of the quality of each included primary study | LF, GV, FC |
| **Data Extraction** | Extraction of the 42 parameters from the 19 included primary studies | LF, GV |
| **Data Synthesis** | Aggregation, classification, and narrative synthesis of the extracted data | LF, GV, FC, LP, TDM |
| **Review Supervision** | Overall review direction, methodology, and final validation | LP, TDM |

**Legend** — LF: Leonardo Fazzini; GV: Giacomo Valente; FC: Federica Caruso; LP: Luigi Pomante; TDM: Tania Di Mascio.

## References

- Kitchenham, B., Charters, S. (2007). *Guidelines for performing Systematic Literature Reviews in Software Engineering*. EBSE Technical Report EBSE-2007-01.
- Wohlin, C. (2014). *Guidelines for snowballing in systematic literature studies and a replication in software engineering*. In Proceedings of the 18th International Conference on Evaluation and Assessment in Software Engineering (EASE '14), ACM.
