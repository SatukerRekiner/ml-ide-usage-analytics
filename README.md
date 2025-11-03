# Analytics of ML Features Usage in IDEs

Repozytorium zawiera analizę danych użycia funkcji ML w IDE (Mar–Maj 2025).  
Zrobione w **Python + Pandas + Matplotlib**.

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

