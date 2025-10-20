# 🏀 NBA Home Court Advantage Prediction

**Goal:**  
Build a **leak-free machine learning pipeline** that predicts the **probability of an NBA home team winning** using only **pre-game data** such as recent form, rest days, and standings.

---

## 📊 Project Overview
This project demonstrates how time-aware feature engineering and leak-free modeling can simulate realistic NBA forecasting.  
All features are created using only data available *before tipoff*, ensuring the model never “cheats” with post-game stats.

---

## ⚙️ Methods
- Data cleaning and merging (`games.csv`, `ranking.csv`, `teams.csv`)
- Rolling win rates, rest-day, and home-frequency feature engineering
- Chronological train/test split to prevent data leakage
- Classification models: Logistic Regression, Decision Tree, Random Forest, XGBoost
- Metrics: Accuracy, ROC-AUC, PR-AUC, Brier Score, and Calibration

---

## 🧠 Key Insights
- Teams with stronger **recent form** and higher **pre-game win %** are most likely to win at home  
- **Rest advantage** has a measurable but smaller effect  
- The model achieved strong **ROC-AUC (~0.70)** with realistic calibration  

---

## 💡 Skills Demonstrated
`Python` · `Machine Learning` · `Feature Engineering` · `Scikit-Learn` · `Sports Analytics` · `Data Visualization`

---

## 🗂️ Files
- `PredictNBAGamesProject.ipynb` — main notebook  
- `NBA_Project_Data/` — data sources  
- `README.md` — project overview and documentation

---

## 🚀 Next Steps
- Incorporate Elo ratings or Vegas odds for richer pre-game context  
- Add player-level features (injuries, travel fatigue)  
- Explore rolling-origin cross-validation for time-series tuning
