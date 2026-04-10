# 02_Study_Selection — Study Selection and Quality Assessment Process

This folder documents the complete **five-stage study selection process** that narrowed an initial pool of 10,678 research articles down to **19 primary studies** included in the SLR.

## Selection Pipeline Overview

| Stage | Description | Criteria Applied | Before | After |
|-------|-------------|-----------------|--------|-------|
| STAGE 1 | Automatic filtering in digital libraries | EX1, EX2, EX3, EX6 | 10,678 | 5,364 |
| STAGE 2 | Semi-automatic filtering (consolidation, deduplication) | EX2, EX3, EX5, EX6, EX7 | 5,364 | 637 |
| STAGE 3 | Title, abstract, and introduction screening | EX2–EX9 | 637 | 144 |
| STAGE 4 | Full-text analysis | EX1–EX10 | 144 | 11 (+ 4 seeds) |
| STAGE 5 | Forward and backward snowballing | All criteria | 838 candidates | 11 + 8 = **19** |

## Folder Structure

```
02_Study_Selection/
├── README.md
├── STAGE1/                  # Automatic filtering — one xlsx per database
├── STAGE2/                  # Deduplication and consolidation
├── STAGE3/                  # Title, abstract, and introduction screening
├── STAGE4/                  # Full-text analysis
├── STAGE5/                  # Forward and backward snowballing
└── Included_and_Excluded_Research_Articles_recap.xlsx
```

Each STAGE subfolder contains its own README.md with detailed descriptions.

## Summary File

- **`Included_and_Excluded_Research_Articles_recap.xlsx`** — Complete recap with four sheets: Study Selection Summary, Exclusion Criteria (EX1–EX10), Inclusion Criteria (IN1–IN7), and the final list of 19 Included Primary Studies.
