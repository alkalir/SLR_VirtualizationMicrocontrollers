# STAGE 5 — Forward and Backward Snowballing

**Input**: 15 seed papers (11 primary studies from STAGE 4 + 4 papers kept for snowballing) → 838 raw snowballing candidates
**Output**: **11 + 8 = 19 primary studies** (final set of included papers for the SLR)
**Criteria applied**: All criteria (EX1–EX10, IN1–IN7)

## Description

STAGE 5 applies **forward and backward snowballing**, as recommended by Wohlin's guidelines, starting from the 15 seeds produced by STAGE 4:

- **11 primary studies** included by the full-text analysis of STAGE 4.2, and
- **4 papers that were excluded but flagged "keep for snowballing"** in STAGE 4.2 (see `../STAGE4/README.md`). These four papers are not counted as primary studies, but their bibliographies and citation graphs are considered valuable enough to be used as snowballing seeds.

For each seed paper, two activities are performed:

- **Backward snowballing** — inspecting the reference list of the seed and adding referenced papers that are potentially relevant to the candidate pool.
- **Forward snowballing** — inspecting the papers that cite the seed (via Google Scholar / Scopus / IEEE / Web of Science citation indexes) and adding citing papers that are potentially relevant to the candidate pool.

The resulting candidate papers are then filtered through a three-step process conceptually mirroring STAGE 3 + STAGE 4:

| Sub-step | Activity | File | Input | Output |
|----------|----------|------|------:|-------:|
| STAGE 5.1 | Forward + backward snowballing collection and title/abstract screening | `STAGE5_1_Snowballing.xlsx` | 838 raw (≈ 693 unique after dedup) | 22 |
| STAGE 5.2 | EX10 keyword pre-screening on the full text | `STAGE5_2_EX10.xlsx` | 22 | 18 |
| STAGE 5.3 | Full-text analysis against EX1–EX10 | `STAGE5_3_FullText.xlsx` | 18 | **8** |

As in STAGE 3 and STAGE 4, each sub-step is carried out by two reviewers (Leonardo and Giacomo) working independently, with disagreements reconciled through discussion as described in the SR Protocol section of the main `../../README.md`.

## STAGE 5.1 — Snowballing Candidate Collection

`STAGE5_1_Snowballing.xlsx` is organised as **one block per seed paper**: each block starts with the seed metadata (ID, year, authors, title, DOI) followed by the list of papers obtained from its forward + backward snowballing. For every candidate paper the two reviewers apply a title + abstract screening against all exclusion criteria (EX1, EX2, EX5, EX7, EX8, EX9) and mark the row with a decision (included/excluded + reason) and a colour.

### Per-seed candidate breakdown

| Seed ID | Year | Seed type | Title (short) | Candidates |
|--------:|------|-----------|---------------|-----------:|
| 82 | 2025 | Primary | FVM: Practical Feather-Weight Virtualization on Commodity Microcontrollers | 39 |
| 108 | 2022 | Primary | iSotEE: A Hypervisor Middleware for IoT-Enabled Resource-Constrained Devices | 42 |
| 167 | 2022 | Primary | SBIs: Application Access to Safe, Baremetal Interrupt Latencies | 60 |
| 226 | 2019 | Primary | Virtualization on TrustZone-Enabled Microcontrollers? Voilà! | 106 |
| 24 | 2020 | Primary | Applying reservation-based scheduling to a μC-based hypervisor | 12 |
| 26 | 2015 | Primary | AUTOBEST: a united AUTOSAR-OS and ARINC 653 kernel | 53 |
| 99 | 2025 | Primary | HiRTOS: A Multi-core RTOS Written in SPARK Ada | 8 |
| 152 | 2018 | Primary | Predictable Virtualization on Memory Protection Unit-Based Microcontrollers | 60 |
| 194 | 2024 | Primary | The Omnivisor: A Real-Time Static Partitioning Hypervisor Extension | 96 |
| 138 | 2019 | Primary | MxU: Towards Predictable, Flexible, and Efficient Memory Access | 30 |
| 135 | 2025 | Primary | Multi-Context Execution on a RISC-V Core for Mixed-Criticality | 14 |
| 120 | 2017 | Kept for snowballing | LTZVisor: TrustZone is the key | 118 |
| 200 | 2017 | Kept for snowballing | Towards a TrustZone-Assisted Hypervisor for Real-Time Embedded Systems | 66 |
| 223 | 2022 | Kept for snowballing | uTango: An Open-Source TEE for IoT Devices | 95 |
| 227 | 2021 | Kept for snowballing | Virtualizing an Automotive State-of-the-Art Microcontroller: Techniques and Its Evaluation | 39 |
| **Total** | | | | **838** |

The 838 raw candidates include a significant amount of overlap (the same paper is often referenced by — or cites — multiple seeds): approximately **693 unique titles** remain after deduplication.

### Filtering outcome of STAGE 5.1

The title/abstract screening of STAGE 5.1 is the most selective step of snowballing, because snowballing candidates come from any research area (most backward/forward references are out of scope, pre-2013, duplicates of STAGE 1/2 papers, or already excluded in previous stages). The main exclusion reasons recorded by the reviewers are:

| Exclusion Criterion | Meaning | Approx. papers |
|---------------------|---------|---------------:|
| EX1 | Year out of range (pre-2013) | ~186 |
| EX5 | Duplicate of a paper already considered in STAGE 1/2/3/4 | ~142 |
| EX2 | Secondary studies, theses, surveys, editorials | ~129 |
| EX9 | Virtualization not targeted at microcontrollers | ~46 |
| EX7 | CS article out of the SLR topic | ~45 |
| EX8 | No virtualization mechanism defined | ~9 |

**Output of STAGE 5.1** = **22 papers** that survive the title/abstract screening and proceed to STAGE 5.2.

## STAGE 5.2 — EX10 Keyword Pre-Screening

`STAGE5_2_EX10.xlsx` applies the same EX10 keyword pre-screening used in STAGE 4.1 to the 22 papers coming out of STAGE 5.1:

- `Paper available in full text` — whether the full text could be retrieved (if not, the paper is excluded for EX4).
- `Paper discusses about MCS (EX10)` — green ✓ / red ⮾ decision on whether the paper addresses mixed-criticality aspects.

### Results

| Outcome | Meaning | Papers |
|---------|---------|-------:|
| 🟢 **Green ✓** | Paper discusses mixed-criticality → proceeds to STAGE 5.3 | 17 |
| 🔴 **Red ⮾** | Paper does not discuss mixed-criticality (EX10) or is not available in full text (EX4) | 4 |
| ⛔ Other | Full text not available (EX4), no EX10 decision recorded | 1 |
| **Total** | | **22** |

**Output of STAGE 5.2** = **18 papers** that proceed to STAGE 5.3 (17 green + 1 carried forward for full-text evaluation despite missing EX10 mark).

## STAGE 5.3 — Full-Text Analysis

`STAGE5_3_FullText.xlsx` contains the final full-text analysis of the 18 surviving snowballing candidates. The two reviewers independently read the full text and record their decision (included/excluded + reason) in the `Filtering Reviewer 1` / `Filtering Reviewer 2` columns, with the colour of the row reflecting the consensus decision.

### Results

| Final Opinion | Meaning | Papers |
|---------------|---------|-------:|
| 🟢 **Green** | **Included as new primary study** — the paper satisfies all inclusion criteria | **8** |
| 🔴 **Red** | Excluded (EX4, EX7, EX8, EX9) | 10 |
| **Total** | | **18** |

The 10 red papers are excluded for the following reasons recorded by the reviewers: not a complete virtualization solution (EX8), paper not available in full text (EX4), virtualization not targeted at MCUs (EX9), or out of the SLR topic (EX7).

## New Primary Studies Added by Snowballing

The **8 papers included in STAGE 5.3** are the new primary studies added by the snowballing process. Together with the 11 primary studies from STAGE 4, they form the **final set of 19 primary studies** analysed in the SLR.

| # | Paper ID | Year | Authors | Title |
|--:|---------:|------|---------|-------|
| 1 | 638 | 2018 | Sundar Rajan A.K. et al. | Hypervisor for consolidating real-time automotive control units: Its procedure, implications and hidden pitfalls |
| 2 | 644 | 2023 | Z. Jiang et al. | Towards hard real-time and energy-efficient virtualization for manycore embedded systems | 
| 3 | 849 | 2025 | M. Seidler; A. Krause; P. Ulbrich | Wasm-IO: Enabling low-level device interaction in WebAssembly for industry automation | 
| 4 | 1101 | 2024 | M. Barletta; F. Boccola; M. Cinque; L. De Simone | Integrating Containers and Partitioning Hypervisors for Dependable Real-Time Industrial Clouds |
| 5 | 1155 | 2019 | Z. Jiang; N. Audsley; P. Dong; N. Guan; et al. | MCS-IOV: Real-time I/O virtualization for mixed-criticality systems |
| 6 | 1160 | 2019 | Z. Jiang; N. Audsley; P. Dong | BlueIO: A scalable real-time hardware I/O virtualization system for many-core embedded systems |
| 7 | 1411 | 2015 | D. Reinhardt; M. Güntner; S. Obermeier | Virtualized Communication Controllers in Safety-Related Automotive Embedded Systems | 
| 8 | 1414 | 2017 | A. Kohn; K. Schmidt; J. Decker; M. Sebastian; A. Züpke; A. Herkersdorf | Timing Analysis for Hypervisor-Based I/O Virtualization in Safety-Related Automotive Systems |

## Color Legend

The same convention used in STAGE 2, 3, and 4 is applied to the decision columns of all three STAGE 5 spreadsheets:

| Color | Meaning | Action |
|-------|---------|--------|
| 🟢 **Green** | The paper passes the criteria of the current sub-step | Keep → next sub-step / included primary study |
| 🟡 **Yellow** | Borderline —  the decision is postponed | Keep → next sub-step |
| 🔴 **Red** | The paper fails one or more exclusion criteria | Discard |

## Contents

| File | Description |
|------|-------------|
| `STAGE5_1_Snowballing.xlsx` | Forward + backward snowballing candidate pool, organised as one block per seed (15 seed blocks, 838 raw candidates ≈ 693 unique) with title/abstract screening decisions |
| `STAGE5_2_EX10.xlsx` | EX10 keyword pre-screening for the 22 papers that survived STAGE 5.1 |
| `STAGE5_3_FullText.xlsx` | Full-text analysis against EX1–EX10 for the 18 papers that survived STAGE 5.2; identifies the 8 new primary studies |

## Related Documents

- `../STAGE4/README.md` — previous stage (full-text analysis) and source of the 11 + 4 seeds used in STAGE 5.
- `../README.md` — overview of the full selection pipeline and exclusion/inclusion criteria.
- `../../README.md` — main repository README, including the full SR Protocol (inclusion/exclusion criteria, reviewer roles, reconciliation procedure).
- `../Included_and_Excluded_Research_Articles_recap.xlsx` — consolidated recap of all included and excluded articles across the 5 stages.

## Final Result

STAGE 5 is the last step of the study selection process. Its output is the **final set of 19 primary studies** used in the systematic literature review:

- **11 primary studies** identified by the database search + full-text analysis (STAGE 1 → STAGE 4), and
- **8 new primary studies** identified by snowballing starting from the 11 primary studies and the 4 additional "keep for snowballing" seeds (STAGE 5).

These 19 primary studies are the papers stored in `../../03_Included_PaPers/` and analysed during data extraction in `../../04_Data Extraction/`.
