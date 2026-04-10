# STAGE 3 — Title, Abstract, and Introduction Screening

**Input**: 637 articles (from STAGE 2)
**Output**: 144 articles (input of STAGE 4)
**Criteria applied**: EX2, EX3, EX4, EX5, EX8, EX9

## Description

STAGE 3 consists of a manual screening in which each paper is evaluated by reading its **title, abstract, and (when needed) introduction**. The goal is to apply the exclusion criteria that cannot be enforced automatically but that can already be evaluated without reading the full text.

### Exclusion criteria applied at this stage

- **EX2** (article type): research articles of the following types: secondary studies (surveys, reviews, systematic reviews, systematization of knowledge), tutorials, editorials, newsletters, dissertations, technical reports, posters, and other non-peer-reviewed articles.
- **EX3** (English): non-English articles.
- **EX4** (full text): articles whose full text is neither available nor obtainable after a precise request to the authors.
- **EX5** (duplicates): residual duplicates missed by the automatic deduplication in STAGE 2.
- **EX8** (no virtualization): articles that do not focus on virtualization, in terms of implementation or management.
- **EX9** (no microcontroller-based systems): articles that do not focus on microcontroller-based systems.

## Two-reviewer process

Each paper is independently evaluated by **two reviewers** (Leonardo and Giacomo). Each reviewer assigns one of the following labels:

| Label | Meaning |
|-------|---------|
| **EXC** | The paper should clearly be excluded based on one of the applied exclusion criteria. |
| **INC** | The paper should clearly be included and proceed to the next stage. |
| **MB**  | *Maybe* — the reviewer is not sure: the title/abstract/introduction is not conclusive. |

### Rules for combining the two reviewers' decisions

The two independent evaluations are combined according to the following rules (which apply from STAGE 3 onwards):

| Reviewer 1 | Reviewer 2 | Combined | Action |
|------------|------------|----------|--------|
| EXC | EXC | **EXC** | Paper discarded |
| INC | INC | **INC** | Paper kept, proceeds to the next stage |
| MB  | MB  | **MB**  | Paper kept (to be re-evaluated in the next stage) |
| EXC | MB  | **MB**  | Paper kept (conservative: in doubt, keep) |
| INC | MB  | **MB**  | Paper kept |
| INC | EXC | **MB**  | **Disagreement** — paper kept and re-discussed |

**Conservative principle**: a paper is discarded **only if both reviewers independently mark it as EXC**. In any other configuration — including the explicit disagreement case INC vs EXC — the paper is kept for the next stage, so that no potentially relevant study is lost at this point.

### Disagreement resolution

When the two reviewers disagree (`INC + EXC`) or when both are uncertain (`MB + MB`, `EXC + MB`, `INC + MB`), the paper is kept and its final fate is recorded in the **`Final Opinion after discussion`** column of `STAGE3.xlsx`. This column reflects the outcome of a dedicated discussion between the two reviewers in which the paper is re-examined together and a joint decision (EXC, INC, or MB) is taken. All papers whose final opinion is INC or MB proceed to STAGE 4.

## Color Legend

The same three-color convention introduced in STAGE 2 is used throughout `STAGE3.xlsx` in the three decision columns (Reviewer 1, Reviewer 2, Final Opinion after discussion).

| Color | Label | Meaning | Action (from Final Opinion) |
|-------|-------|---------|------|
| 🟢 **Green** (`#00B050`) | **INC** | The paper is clearly relevant and proceeds to the next stage. | Keep → STAGE 4 |
| 🟡 **Yellow** (`#FFFF00`) | **MB** | The paper is borderline: it might be excluded for EX8 or EX9, but title/abstract/introduction are not conclusive. It is kept so the full text can be read in STAGE 4. | Keep → STAGE 4 (re-evaluation) |
| 🔴 **Red** (`#FF0000`) | **EXC** | The paper is excluded at this stage based on one of the applied exclusion criteria (EX2, EX3, EX4, EX5, EX8, EX9). | Discard |

## Results

The table below summarizes the number of papers assigned to each label by each reviewer and the **Final Opinion** after the joint discussion.

| Evaluation | 🔴 EXC (Red) | 🟡 MB (Yellow) | 🟢 INC (Green) | Total |
|------------|-----------:|---------------:|---------------:|------:|
| Reviewer 1 | 524 | 86 | 27 | 637 |
| Reviewer 2 | 468 | 151 | 18 | 637 |
| **Final Opinion after discussion** | **493** | **129** | **15** | **637** |

**Output of STAGE 3** = green + yellow rows in the `Final Opinion after discussion` column = **15 + 129 = 144 papers** → input of STAGE 4.

## Contents

| File | Description |
|------|-------------|
| `STAGE3.xlsx` | Screening results, with three color-coded decision columns: `Title and Abstract Filtering Reviewer 1`, `Title and Abstract Reviewer 2`, and `Final Opinion after discussion`. |

## Related Documents

- `../STAGE2/README.md` — previous stage (semi-automatic filtering and consolidation).
- `../STAGE4/README.md` — next stage (full-text analysis).
- `../README.md` — overview of the full selection pipeline and exclusion/inclusion criteria.
- `../../README.md` — main repository README, including the full SR Protocol.

## Next Step

The **144 papers** kept at the end of STAGE 3 (green + yellow in the Final Opinion column) are the input of **STAGE 4**, where each paper is read in full and the full set of exclusion criteria (EX2–EX10) is applied.
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          
