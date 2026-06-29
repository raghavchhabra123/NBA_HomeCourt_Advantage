# NBA Home Court Advantage Prediction
[![View Notebook](https://img.shields.io/badge/Open%20in%20nbviewer-orange?logo=jupyter)](https://nbviewer.org/github/raghavchhabra123/NBA_HomeCourt_Advantage/blob/main/PredictNBAHomeGamesProject.ipynb)

**Goal:**  
Build a **leak-free machine learning pipeline** that predicts the **probability of an NBA home team winning** using only **pre-game data** such as recent form, rest days, and standings.

---

## Project Overview
This project demonstrates how time-aware feature engineering and leak-free modeling can simulate realistic NBA forecasting.  
All features are created using only data available *before tipoff*, ensuring the model never "cheats" with post-game stats.

---

## Results

| Model | Accuracy | ROC-AUC | PR-AUC | Brier Score |
|---|---|---|---|---|
| XGBoost | **77.9%** | **0.852** | **0.873** | 0.157 |
| Random Forest | 75.9% | 0.844 | 0.862 | 0.162 |
| Logistic Regression | 76.4% | 0.844 | 0.861 | 0.163 |
| Dummy Baseline | 55.0% | 0.500 | 0.550 | 0.450 |

---

## Methods
- Data cleaning and merging (`games.csv`, `ranking.csv`, `teams.csv`)
- Rolling win rates, rest-day, and home-frequency feature engineering
- Chronological train/test split to prevent data leakage
- Classification models: Logistic Regression, Random Forest, XGBoost
- Metrics: Accuracy, ROC-AUC, PR-AUC, Brier Score, and Calibration

---

## Key Insights
- Teams with stronger **recent form** and higher **pre-game win %** are most likely to win at home  
- **Rest advantage** has a measurable but smaller effect  
- XGBoost achieved the best performance with **77.9% accuracy** and **ROC-AUC of 0.852**  
- The most predictive feature was `diff_rank_W_PCT_pre` (difference in pre-game win percentage)

---

## Skills Demonstrated
`Python` · `Machine Learning` · `Feature Engineering` · `Scikit-Learn` · `XGBoost` · `Sports Analytics` · `Data Visualization`

---

## Files
- `PredictNBAHomeGamesProject.ipynb` — main notebook  
- `NBA_Project_Data/` — data sources  
- `requirements.txt` — dependencies  
- `README.md` — project overview and documentation

---

## Next Steps
- Incorporate Elo ratings or Vegas odds for richer pre-game context  
- Add player-level features (injuries, travel fatigue)  
- Explore rolling-origin cross-validation for time-series tuning
