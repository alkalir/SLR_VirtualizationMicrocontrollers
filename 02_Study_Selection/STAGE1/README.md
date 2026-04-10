# STAGE 1 — Database Query Execution and Automatic Filtering

**Goal**: Execute the base search query on each selected digital library and collect the full list of candidate articles after applying the database-native filters.

**Input**: base query defined in `../../01_Queries/`
**Output**: **5,364** articles across 5 digital libraries → input of STAGE 2

## Description

In STAGE 1, the base query (see `../../01_Queries/README.md`) was adapted to the specific syntax supported by each digital library and executed on their search interfaces. The query is structured as:

> `Virtualization_keywords` **AND** `Virtualized_components`

where `Virtualization_keywords` contains terms related to virtualization mechanisms (e.g., *Virtualiz\**, *Partition\**, *Isolat\**, *hypervisor\**, *container\**, *separation kernel\**, *unikernel\**, *microkernel\**, *TEE*) and `Virtualized_components` contains terms related to microcontroller-based / resource-constrained systems (e.g., *microcontroller\**, *MCU*, *TrustZone-M*, *low-end system\**, *resource-constrained device\**).

After running each query, a set of **database-native filters** was applied to reduce the initial result set. These filters correspond to a subset of the global exclusion criteria (see `../README.md` for the full list):

- **EX1 (years)** — published outside the window *2015 – end of July 2025*
- **EX2 (article type)** — secondary studies, tutorials, editorials, newsletters (applied only when the database filter supports it — e.g., ScienceDirect)
- **EX3 (English)** — non-English articles (applied only when the database filter supports it — e.g., Scopus)
- **EX6 (no CS)** — articles outside the computer science subject area (applied only when the database filter supports it — e.g., Scopus, ScienceDirect)

All remaining exclusion criteria are handled in later stages.

## Digital Libraries and Per-Database Pipeline

The five digital libraries used for the search, together with the filtering pipeline applied in each of them and the final number of articles exported, are summarized below. Full queries (native syntax) are available in `../../01_Queries/Search_Queries_per_Database.xlsx`.

| # | Digital Library | No filters | Filtering pipeline | Final (after filters) |
|---|-----------------|-----------:|--------------------|----------------------:|
| 1 | IEEE Xplore      | 2,107 | EX1 | **1,526** |
| 2 | ACM Digital Library | 441 | EX1 | **312** |
| 3 | Scopus           | 3,769 | EX1 (2,697) → EX6/subject area (1,693) → EX3/language (1,672) | **1,672** |
| 4 | Web of Science   | 2,332 | EX1 (1,690) → EX3/language (1,673) | **1,673** |
| 5 | ScienceDirect    | 2,029 | EX1 (2,015) → EX6/subject area (397) → EX2/article type (376) → additional EX6 refinement (181) | **181** |
|   | **TOTAL**        | **10,678** |  | **5,364** |

> **Note on criterion labels.** The per-database pipeline uses labels that match the global exclusion criteria defined in `../README.md`. Depending on the database, a single native filter may implement a different criterion: e.g., in Scopus the "subject area = Computer Science" filter corresponds to EX6, and the "language = English" filter corresponds to EX3.

## Dates of Execution

All queries on IEEE Xplore, ACM Digital Library, Scopus, and Web of Science were executed on **28/07/2025**. The ScienceDirect query was executed on **20/08/2025**.

## Contents

This folder contains the raw exports obtained from each digital library after applying the database-native filters. Each file is a direct export of the article list (bibliographic metadata: title, authors, year, venue, DOI, abstract, keywords) and constitutes the input of STAGE 2 (deduplication and consolidation).

| File | Digital Library | Articles |
|------|-----------------|---------:|
| `IEEE_Xplore_STAGE1_Results.csv` | IEEE Xplore | 1,526 |
| `ACM_STAGE1_Results.csv` | ACM Digital Library | 312 |
| `Scopus_STAGE1_Results.csv` | Scopus | 1,672 |
| `WebOfScience_STAGE1_Results.xls` | Web of Science | 1,673 |
| `ScienceDirect__STAGE1_Results.csv` | ScienceDirect | 181 |
|  | **Total** | **5,364** |

## Related Documents

- `../../01_Queries/README.md` — definition of the base query (groups, attributes, operators) and rationale.
- `../../01_Queries/Search_Queries_per_Database.xlsx` — native-syntax queries actually submitted to each digital library.
- `../README.md` — overview of the 5-stage selection pipeline and full list of inclusion/exclusion criteria.
- `../../README.md` — main repository README, including the full SR Protocol.

## Next Step

The 5,364 articles exported in this folder are the input of **STAGE 2**, where the separate per-database lists are consolidated, duplicates across databases are removed (EX5), and remaining non-CS / non-topical / non-English / non-primary-study records are filtered out (EX2, EX3, EX6, EX7).
