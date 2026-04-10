# STAGE 4 — Full-Text Analysis

**Input**: 144 articles (from STAGE 3)
**Output**: 11 primary studies (input of STAGE 5) + 4 papers kept for snowballing
**Criteria applied**: EX1–EX10 

## Description

STAGE 4 consists of a comprehensive full-text analysis of the candidate articles against the **full set of exclusion criteria EX1–EX10**, with particular focus on **EX10 — "Does not address mixed-criticality aspects"**, which is applied here for the first time in the selection pipeline.

The process is divided into two sub-steps, both performed by two reviewers (Leonardo and Giacomo) working independently and reconciling disagreements through discussion, as described in the SR Protocol section of the main [`../../README.md`](../../README.md).

| Sub-step | Activity | File | Input | Output |
|----------|----------|------|------:|-------:|
| STAGE 4.1 | EX10 keyword pre-screening on the full text | `STAGE4_1_EX10_Check.xlsx` | 144 | 65 |
| STAGE 4.2 | Full-text analysis against EX1–EX10 | `STAGE4_2_FullText_Analysis.xlsx` | 65 | **11 + 4** |


## STAGE 4.1 — EX10 Screening

For each paper the full text is retrieved and the reviewers check whether the document contains any reference to mixed-criticality-related terminology. The `STAGE4_1_EX10_Check.xlsx` file reports, for each paper:

- `Paper available in full text` — whether the full text could be retrieved (if not, the paper is excluded for EX4).
- `Mentions mixed-criticality key words in the full text` — the occurrences (Yes/No) of the keywords `criticality`, `mixed-critical`, `safety-critical`, and `critical`.
- `Paper discusses about mixed-criticality` — final decision of the screening (green ✓ / red ⮾).

### Results

| Outcome | Meaning | Papers |
|---------|---------|-------:|
| 🟢 **Green ✓** | The paper discusses mixed-criticality aspects → proceeds to STAGE 4.2 | 62 |
| 🔴 **Red ⮾** | The paper does not discuss mixed-criticality (EX10) → excluded | 76 |
| ⛔ Other | Full text not available or excluded for EX1/EX4 (year out of range / no full text) | 6 |
| **Total** | | **144** |

Of the 6 papers outside the EX10 check, 3 are definitively excluded (EX1/EX4) while the remaining 3 are carried forward to STAGE 4.2 for further evaluation on the available material, giving **65 papers** as input of STAGE 4.2.

## STAGE 4.2 — Full-Text Analysis Against EX1–EX10

The 65 papers that survived the EX10 pre-screening are read in full and independently evaluated by the two reviewers against **all** exclusion criteria (EX1–EX10) and inclusion criteria (IN1–IN7). The final decision on each paper is reconciled through discussion and recorded in the `Final Opinion` column of `STAGE4_2_FullText_Analysis.xlsx`.

Each row is additionally annotated with the `Paper excluded, but keep it for snowballing` column: papers that are excluded from the primary-study set but are still considered relevant seed papers for the snowballing procedure of STAGE 5 are flagged with ✓ in this column.

### Results

| Final Opinion | Meaning | Papers |
|---------------|---------|-------:|
| 🟢 **Green** | **Included as primary study** — the paper satisfies all inclusion criteria and none of the exclusion criteria | **11** |
| 🔴 **Red** | **Excluded** — the paper fails one or more exclusion criteria | 54 |
| **Total** | | **65** |

### Exclusion breakdown for STAGE 4.2

The 54 red papers are excluded for the following reasons (a paper can be excluded by more than one criterion, so totals may exceed 54):

| Exclusion Criterion | Meaning | Papers |
|---------------------|---------|-------:|
| EX8 | Does not address virtualization  | 30 |
| EX9 | Virtualization not targets microcontrollers (e.g. MMU-based, cloud, application processors) | 16 |
| EX2 | Secondary studies, tutorials, editorials | 4 |
| EX7 | CS article out of the SLR topic | 3 |

## Papers Kept for Snowballing

Among the 54 papers excluded in STAGE 4.2, **4 papers are flagged with ✓ in the `Paper excluded, but keep it for snowballing` column**. These papers, although they do not satisfy all of our inclusion criteria (and therefore are not counted among the 11 primary studies from the database search), are considered particularly relevant to the research questions and are used as **additional seeds for the forward and backward snowballing** performed in STAGE 5. They are carried forward alongside the 11 primary studies and their reference lists / citing papers are inspected during snowballing.

| Paper ID | Year | Authors | Title | DOI |
|---------:|------|---------|-------|-----|
| 120 | 2017 | Pinto S.; Pereira J.; Gomes T.; Tavares A.; Cabral J. | LTZVisor: TrustZone is the key | [10.4230/LIPIcs.ECRTS.2017.4](https://doi.org/10.4230/LIPIcs.ECRTS.2017.4) |
| 200 | 2017 | S. Pinto; J. Pereira; T. Gomes; M. Ekpanyapong; A. Tavares | Towards a TrustZone-Assisted Hypervisor for Real-Time Embedded Systems | [10.1109/LCA.2016.2617308](https://doi.org/10.1109/LCA.2016.2617308) |
| 223 | 2022 | D. Oliveira; T. Gomes; S. Pinto | uTango: An Open-Source TEE for IoT Devices | [10.1109/ACCESS.2022.3152781](https://doi.org/10.1109/ACCESS.2022.3152781) |
| 227 | 2021 | Sundar Rajan A.K.; Nirmala Devi M. | Virtualizing an Automotive State-of-the-Art Microcontroller: Techniques and Its Evaluation | [10.1007/978-3-030-59897-6_2](https://doi.org/10.1007/978-3-030-59897-6_2) |

## Color Legend

The same convention used in STAGE 2 and STAGE 3 is applied to the `Paper discusses about mixed-criticality` column of `STAGE4_1_EX10_Check.xlsx` and to the `Final Opinion` column of `STAGE4_2_FullText_Analysis.xlsx`:

| Color | Meaning | Action |
|-------|---------|--------|
| 🟢 **Green** | The paper passes the criteria of the current sub-step | Keep → next sub-step / primary studies |
| 🔴 **Red** | The paper fails one or more exclusion criteria | Discard (or keep for snowballing if flagged in the dedicated column) |

## Contents

| File | Description |
|------|-------------|
| `STAGE4_1_EX10_Check.xlsx` | Full-text availability and EX10 keyword pre-screening for the 144 papers entering STAGE 4 |
| `STAGE4_2_FullText_Analysis.xlsx` | Complete full-text analysis against EX1–EX10 for the 65 papers that survived STAGE 4.1, including reviewer decisions, final opinion, and the snowballing flag |

## Related Documents

- `../STAGE3/README.md` — previous stage (title, abstract, and introduction screening).
- `../STAGE5/README.md` — next stage (forward and backward snowballing).
- `../README.md` — overview of the full selection pipeline and exclusion/inclusion criteria.
- `../../README.md` — main repository README, including the full SR Protocol.

## Next Step

STAGE 4 produces two sets of papers that are carried forward to **STAGE 5 (snowballing)**:

1. **11 primary studies** — the papers included by the full-text analysis. These form the authoritative seed set of the SLR and are the starting point of both forward and backward snowballing.
2. **4 additional snowballing seeds** — papers excluded from the primary-study set but flagged in the `Paper excluded, but keep it for snowballing` column because their bibliographies and citation graphs are still considered valuable sources of candidate primary studies.
