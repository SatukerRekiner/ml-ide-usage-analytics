# Analytics of ML Features Usage in IDEs

End-to-end analysis of anonymized IDE usage for ML features (Mar–May 2025).  
Stack: **Python · Pandas · Matplotlib**. One-click run via notebook.

> 👀 Recruiter shortcut:
> - Open the self-contained notebook (context + analysis + findings):
>   - [`notebooks/01_analysis_selfcontained.ipynb`](notebooks/01_analysis_selfcontained.ipynb)
>   - or quick preview: exported HTML → `notebooks/01_analysis_selfcontained.html` (if present)
> - Core notebook used during development:
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
