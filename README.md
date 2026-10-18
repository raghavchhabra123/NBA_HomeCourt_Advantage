# NBA Home Court Advantage — historical experiment

**This notebook is retained for learning and historical context. Its reported 77.9% accuracy is contaminated by target leakage and must not be presented as pre-game forecasting performance.**

Use the maintained [NBA Matchup Predictor](https://github.com/raghavchhabra123/nba-matchup-predictor) for the current project and its reproducible chronological evaluation. These are different experiments, not directly comparable model scores.

## What the audit found

- The standings join uses `allow_exact_matches=True`, so a game can receive its own end-of-day standings. In the committed CSVs, after game-ID and team/date standings deduplication, 24,770 home games had a one-game standings change from the preceding day. Every one of those changes matched that day's result. This directly exposes target information through `W_PCT`.
- Missing feature values are filled with medians computed before the train/test split, allowing future data to influence training inputs.
- The notebook chooses the best model using its test results and inspects feature importance on that same test set. It therefore lacks an untouched final evaluation.
- A chronological split alone does not repair these feature-level leakage paths.

The notebook and its outputs are preserved as an archival experiment, **not a validated benchmark**. The original “leak-free” characterization is withdrawn. A corrected run would need strictly prior-day standings, training-only imputation, temporal model selection and newly generated metrics. No corrected 77.9% result is claimed.

## Historical contents

- `PredictNBAHomeGamesProject.ipynb`: cleaning, feature construction, exploratory model comparisons and plots.
- `NBA_Project_Data/`: original data snapshots.
- `requirements.txt`: broad historical dependencies, not a locked reproduction environment.

[View the archived notebook](https://nbviewer.org/github/raghavchhabra123/NBA_HomeCourt_Advantage/blob/main/PredictNBAHomeGamesProject.ipynb)

The maintained project replaces this headline with training-only evaluation, explicit baselines, per-season scores, rolling development folds, regression tests and documented data limitations.
