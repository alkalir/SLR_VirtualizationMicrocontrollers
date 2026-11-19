# 04_Data Extraction — Data Extraction Form and Extracted Data

**Input**: 19 primary studies (the final set produced by STAGE 5)
**Output**: Completed data-extraction table with **44 parameters × 19 papers**
**Goal**: Answering the 5 research questions (RQ1–RQ5) of the SLR by systematically extracting the same set of information from each primary study.

## Description

After the study selection process (STAGE 1 → STAGE 5) has produced the final set of **19 primary studies**, each of them is read in full and a fixed set of **44 data-extraction parameters** is filled in. The parameters are organised into **6 thematic groups**, each colour-coded in the spreadsheets and each addressing one or more of the Research Questions of the SLR:

- **RQ1** — What are the characteristics of virtualization solutions proposed for microcontroller-based mixed-criticality systems?
- **RQ2** — On which hardware platforms are these solutions implemented and evaluated?
- **RQ3** — How is isolation between partitions enforced (memory, traps/interrupts, I/O)?
- **RQ4** — How is the life-cycle of a partition managed (boot, creation, scheduling, communication)?
- **RQ5** — What is the impact of the proposed virtualization solution on system performance?

The extraction protocol and the taxonomy used to classify the answers are documented in the SR Protocol section of the main `../README.md`, in particular under *Data Extraction* and *Data Synthesis*.

## Contents

| File | Description |
|------|-------------|
| `Data_Extraction_Form.xlsx` | Template defining all 44 extraction parameters, organised in 6 colour-coded groups with the associated Research Question (sheet `Data Extraction Form`), plus a sheet `Allowed Values` with the description and the admitted values of each parameter. Each column is a parameter, each group is a coloured header spanning several columns. |
| `Extracted_Data.xlsx` | Completed data-extraction table — **one row per primary study (19 rows), one column per parameter (44 columns)**. The first three header rows reproduce the colour-coded group structure of the form. A second sheet, `Legend`, explains the abbreviations and symbols used in the cells (`n.r.` = not reported, `—` = not applicable/not evaluated, `●` = evaluated). |

## Extraction Parameters

The 44 parameters are organised into 6 groups, following Table *Data extraction parameters* of the paper. The colour of each group matches the fill colour used in the header row of `Data_Extraction_Form.xlsx` and `Extracted_Data.xlsx`.

| # | Group | Colour | RQ | #Params | Parameters |
|--:|-------|--------|----|--------:|------------|
| 1 | **General Paper Information** | 🔵 Blue (`4472C4`) | — | 6 | Year; Author; Title; Database; DOI; Venue |
| 2 | **Virtualization Dimensions** | 🟢 Green (`70AD47`) | RQ1 | 7 | Virtualized resource; Partitioned resource; VL origin; VL category; VL deployment; Guest interface approach; Guest privilege model |
| 3 | **Targeted HW Platforms** | 🟠 Orange (`ED7D31`) | RQ2 | 8 | Instruction-set architecture; Processor model; Clock frequency; Processor configuration; Privilege levels; Memory HW protection mechanisms; Additional HW protection mechanisms; SW protection mechanisms |
| 4 | **Virtualization Implementation** | 🟣 Purple (`7030A0`) | RQ3 | 6 | Tenant scheduling; Tenant privilege interface; Exception handling; Interrupt handling; I/O access method; I/O sharing |
| 5 | **Virtualization Configuration and Management** | 🩵 Cyan (`00B0F0`) | RQ4 | 9 | Tenant creation; Tenant configuration; Boot sequence; Max tenants; Service API; Task scheduling; Tenant shared memory; Tenant communication; Protection management |
| 6 | **Performance Impact** | ⬜ Gray (`7F7F7F`) | RQ5 | 8 | General execution time overhead; Context switch overhead; Hypercall overhead; Interrupt handling overhead; I/O access overhead; HW resource overhead; Power overhead; Memory footprint |
| | **Total** | | | **44** | |

## Structure of the Spreadsheets

Both `Data_Extraction_Form.xlsx` and `Extracted_Data.xlsx` share the same horizontal layout:

- **Row 1** — Group header: the cell is merged across the columns of the group and filled with the group colour (see table above). It contains the group name.
- **Row 2** — Parameter header: one cell per parameter, with a light-blue fill, containing the short name of the parameter.
- **Row 3** — RQ tag: the Research Question each parameter contributes to (RQ1–RQ5; `—` for the general information).
- **Rows 4–22** in `Extracted_Data.xlsx` — the 19 primary studies, one row per paper, ordered chronologically by year (from 2015 to 2025).

## Primary Studies Covered

The 19 primary studies extracted in `Extracted_Data.xlsx` are the ones identified by STAGE 5 (11 from STAGE 4 + 8 added by snowballing). They span from 2015 to 2025 and are listed chronologically in the spreadsheet:

1. Virtualized Communication Controllers in Safety-Related Automotive Embedded Systems (2015)
2. AUTOBEST: A United AUTOSAR-OS and ARINC 653 Kernel (2015)
3. Timing Analysis for Hypervisor-Based I/O Virtualization in Safety-Related Automotive Systems (2017)
4. Predictable Virtualization on Memory Protection Unit-Based Microcontrollers (2018)
5. Hypervisor for Consolidating Real-Time Automotive Control Units (2018)
6. Virtualization on TrustZone-Enabled Microcontrollers? Voilà! (2019)
7. BlueIO: A Scalable Real-Time Hardware I/O Virtualization System for Many-Core Embedded Systems (2019)
8. MCS-IOV: Real-Time I/O Virtualization for Mixed-Criticality Systems (2019)
9. MxU: Towards Predictable, Flexible, and Efficient Memory Access Control (2019)
10. Applying Reservation-Based Scheduling to a μC-Based Hypervisor (2020)
11. iSotEE: A Hypervisor Middleware for IoT-Enabled Resource-Constrained Devices (2022)
12. SBIs: Application Access to Safe, Baremetal Interrupt Latencies (2022)
13. Towards Hard Real-Time and Energy-Efficient Virtualization for Manycore Embedded Systems (2023)
14. Integrating Containers and Partitioning Hypervisors for Dependable Real-Time Industrial Clouds (2024)
15. The Omnivisor: A Real-Time Static Partitioning Hypervisor Extension (2024)
16. Multi-Context Execution on a RISC-V Core for Mixed-Criticality Systems (2025)
17. FVM: Practical Feather-Weight Virtualization on Commodity Microcontrollers (2025)
18. HiRTOS: A Multi-Core RTOS Written in SPARK Ada (2025)
19. Wasm-IO: Enabling Low-Level Device Interaction in WebAssembly for Industry Automation (2025)

The full-text PDFs of all 19 papers are stored in `../03_Included_PaPers/`.

## Related Documents

- `../02_Study_Selection/STAGE5/README.md` — previous step, describes how the 19 primary studies were obtained.
- `../03_Included_PaPers/` — full-text PDFs of the 19 primary studies that are the subjects of the extraction.
- `../README.md` — top-level overview of the reproducibility database.
