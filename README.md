# Analytics of ML Features Usage in IDEs

End-to-end analysis of anonymized IDE usage for ML features (Mar–May 2025).  
Stack: **Python · Pandas · Matplotlib**. One-click run via notebook.

> 👀 Recruiter shortcut:
> - Open the self-contained notebook (context + analysis + findings):
>   - [`notebooks/01_analysis.ipynb`](notebooks/01_analysis.ipynb)

---

## Repo structure
```bash
ml-ide-usage-analytics/
   ├─ data/
   │ └─ data.csv # anonymized, daily-aggregated dataset
   ├─ figures/ # charts auto-saved by notebook
   ├─ outputs/ # CSV exports / findings
   ├─ notebooks/
   │ └─ 01_analysis.ipynb # main analysis
   ├─ requirements.txt
   ├─ .gitignore
   └─ README.md
```
---

## Dataset (schema & assumptions)
Each row ≈ one user's **day** for a `(license, model, feature)` tuple:

| column         | type   | description                                  |
|----------------|--------|----------------------------------------------|
| `uuid`         | string | anonymized user id                           |
| `day_id`       | date   | day of activity                              |
| `license`      | string | Basic / Standard / Enterprise / Premium      |
| `model`        | string | Model_A … Model_E                            |
| `feature`      | string | Feature_1 … Feature_5                        |
| `requests_cnt` | number | requests issued that day (non-negative)      |
| `spent_amount` | number | spend for the same slice (non-negative)      |

Assumptions: already daily-aggregated, anonymized, consistent units across rows.

```
## What the notebook covers
1. **Sanity check (lite)** — types, numeric stats, compact distributions.
2. **Baseline aggregations** — by model / feature / license (+ CSV exports).
3. **Requests ↔ Spent** — Pearson/Spearman + scatter (PNG in `figures/`).
4. **Weekly trends** — sums, MA(3), week-over-week % (CSV + PNG).
5. **Combinations** — matrices for `model×feature` and `feature×license` (volumes + row shares).
6. **Feature mix per model** — 100% stacked bars + per-model bars with % labels.
7. **Efficiency (CPR)** — spent per request by model/feature/license (+ ranking and min-volume filter).

_All charts go to `figures/`, tables to `outputs/`._

## Key takeaways (short)
- **Usage ↔ Spend:** strong positive relationship — more requests → higher spend.
- **Concentration:** a few `(model, feature)` pairs drive a large share — prioritise reliability & UX there.
- **Feature mix:** Feature_1 & Feature_2 dominate across models; long tail may need contextual onboarding.
- **CPR:** some segments have materially higher *spent per request* → candidates for pricing/bundling tests.

See details in the self-contained notebook’s **Findings & Recommendations** section.

## How I approached this (methodology)
- **Frame the problem:** clarify metrics (`requests_cnt`, `spent_amount`) and grain (daily per `license × model × feature × user`).
- **Sanity & quality:** validate types, date range, non-negativity, outliers.
- **EDA first:** simple rollups + visual checks to form hypotheses.
- **Explain patterns:** correlation & trends, then segments (matrices) for crisp comparisons.
- **Prioritize by impact:** combine **volume** and **CPR** to surface high-leverage areas.
- **Make it reproducible:** relative paths, auto-exports, self-contained notebook with context.

## Repro & notes
- Paths are relative; the notebook auto-resolves `data/data.csv`.
- Outputs are re-generated on run; no manual steps required.
- Data uses anonymized IDs and daily-aggregated signals only.
- Stack: Python 3.x, Pandas, Matplotlib (no seaborn to keep deps minimal).

## Contact
If you have any questions or want a short walkthrough, feel free to reach out.


