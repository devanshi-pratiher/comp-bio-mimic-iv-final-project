# ICU Device-Associated Infection & Survival Prediction

Replication and extension of Su et al. (2024) using MIMIC-IV v2.2 data.

## Project Overview

This project replicates and extends a machine learning study predicting:
1. Device-associated infections (VAP, CLABSI, CAUTI)
2. 30-day survival after invasive device placement

**Key Improvements:**
- 4x larger cohort (35,921 vs 8,574 patients)
- +9% infection AUC (0.886 vs 0.812)
- +8.5% survival C-index (0.843 vs 0.777)
- Novel temporal validation (proves generalization to future patients)

## Data Access

**Large datasets are stored on One Drive:**

**Required MIMIC-IV Access:**
- This project uses MIMIC-IV v2.2 from PhysioNet
- Complete CITI training: https://physionet.org/content/mimiciv/
- Access via BigQuery: https://console.cloud.google.com/bigquery

## Installation
```bash
pip install -r requirements.txt
```

## Usage

1. Extract data from BigQuery using SQL scripts in `sql/`
2. Run notebooks in order: `01_bigquery_data_extraction.ipynb` → `08_figure_generation.ipynb`
3. Trained models are in `models/` directory

## Results

| Task | Metric | Paper | My Work | Improvement |
|------|--------|-------|---------|-------------|
| Infection | AUC | 0.812 | **0.886** | +9.1% |
| Survival | C-index | 0.777 | **0.843** | +8.5% |
| Temporal Drop | AUC | N/A | **0.8680** | Novel |

## Citation

Original Paper:
```
Su, X., Sun, L., Sun, X., & Zhao, Q. (2024). Machine learning for predicting 
device-associated infection and 30-day survival outcomes after invasive device 
procedure in intensive care unit patients. Scientific Reports, 14, 24585.
```

## License

This project is for academic/research purposes only. MIMIC-IV data usage must 
comply with PhysioNet Data Use Agreement.

## Contact

Devanshi Pratiher
```
