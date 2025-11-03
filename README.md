# Analytics of ML Features Usage in IDEs

Repozytorium zawiera analizę danych użycia funkcji ML w IDE (Mar–Maj 2025).  
Zrobione w **Python + Pandas + Matplotlib**. Opcjonalnie (w drugim etapie) dorzucimy SQL/SQLite.

## Struktura
```
ml-ide-usage-analytics/
├── data/
│   └── data.csv              # źródłowy dataset (anonymized, daily agg)
├── figures/                  # automatycznie generowane wykresy
├── outputs/                  # tabele pośrednie/eksporty
├── notebooks/
│   └── 01_analysis.ipynb     # główna analiza (Python)
├── requirements.txt
├── .gitignore
└── README.md
```

## Jak uruchomić
1. (Opcjonalnie) utwórz wirtualne środowisko i aktywuj:
   ```bash
   python -m venv .venv
   # Windows: .venv\Scripts\activate
   # macOS/Linux:
   source .venv/bin/activate
   ```
2. Zainstaluj zależności:
   ```bash
   pip install -r requirements.txt
   ```
3. Uruchom Jupyter:
   ```bash
   jupyter notebook
   ```
4. Otwórz `notebooks/01_analysis.ipynb` i uruchom wszystkie komórki.

## Eksporty
- Wybrane agregacje zapisują się do `outputs/` (CSV).
- Wykresy zapisują się do `figures/` (PNG).

## Git & publikacja na GitHub
```bash
git init
git add .
git commit -m "Initial analysis: Python EDA, trends, CPR, pivots"
git branch -M main
git remote add origin <YOUR_REPO_URL>
git push -u origin main
```
