# 00_Queries — Search Queries

This folder contains the **search queries** used to retrieve candidate studies from each digital library.

## Contents

- **`Search_Queries_per_Database.xlsx`** — One sheet per digital library, documenting the exact search string, the fields searched, the date of execution, and the number of results returned.

## Base Query

The following base query was adapted to the syntax of each digital library:

```
((virtualiz* OR partition* OR isolat* OR hypervisor* OR container* OR separation kernel*
  OR microkernel* OR unikernel* OR TEE* OR trusted execution environment*)
AND
(microcontroller* OR micro controller* OR MCU* OR TrustZone-M
  OR ((resource constrained OR low end)
  AND (system* OR device* OR processor* OR core OR hardware OR HW OR platform))))
```

## Digital Libraries

| Library | Search Date | Raw Results | After Native Filters |
|---------|-------------|------------:|---------------------:|
| IEEE Xplore | 2025-07-28 | 2,107 | 1,526 |
| ACM Digital Library | 2025-07-28 | 441 | 312 |
| Scopus | 2025-07-28 | 3,769 | 1,672 |
| Web of Science | 2025-07-28 | 2,332 | 1,673 |
| ScienceDirect | 2025-08-20 | 2,029 | 181 |
| **Total** | | **10,678** | **5,364** |

## Notes

- Each digital library has its own query syntax. The spreadsheet documents the exact query string submitted to each platform.
- The ScienceDirect search was conducted on a later date (August 20, 2025) to ensure comprehensive coverage.
- The **Raw Results** column reports the number of articles returned by the query with no additional filter.
- The **After Native Filters** column reports the number of articles after applying the database-native filters described in STAGE 1 (see `../02_Study_Selection/STAGE1/README.md`). These filters implement a subset of the global exclusion criteria — mainly EX1 (years), EX3 (English), and EX6 (computer science subject area), plus EX2 (article type) where supported (ScienceDirect).
- The 5,364 articles obtained after native filters constitute the input of STAGE 1 / STAGE 2 of the study selection pipeline.
