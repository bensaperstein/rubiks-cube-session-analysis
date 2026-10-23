# Methods and validation notes

This note clarifies the original course submissions; it does not claim a revised model has been fitted.

## Target-derived turning speed

The parser computes `turn_speed_tps = number_of_turns / solve_time_s`. Models 2–9 then use this feature to model `solve_time_s`. A train/test split cannot remove that mathematical dependence. The final saved test R² of approximately 0.834 and MAE of approximately 1.24 seconds are not evidence of predicting an unknown future solve time.

Even without turning speed, longest pause, completed move counts and fastest burst describe a solve after it occurs. They can support retrospective description, but not a pre-solve forecast without changing the information available.

## Split and tuning

The random 80/20 split (`random_state=2`) mixes earlier and later practice. Test scores were examined across specifications, so this is not an untouched final evaluation of a fully prespecified process.

The original Ridge workflow expands polynomial features and scales the training matrix before `RidgeCV(cv=5)`. The scaler is fitted before the internal folds. A stronger workflow would fit preprocessing within each fold using a pipeline. A chronological holdout and time-aware tuning would better match future-performance prediction.

## Coefficients and inference

- Products of mutually exclusive weekday indicators are structurally zero; their zero coefficients are not learned evidence of irrelevance.
- Large standardized coefficients do not establish causal importance, particularly with correlated polynomial terms.
- Separate OLS R² describes the fitted sample, not independent test performance. Saved standard errors are nonrobust; repeated solves may also be time-dependent.
- The code and report differ in one saved Model 2 test-MAE entry. Neither is a portfolio headline. Resolve discrepancies by rerunning when the original data is available.
- One person’s keyboard-controlled solves cannot establish population-wide effects or physical speedcubing performance. Filtering, practice selection and learning stage affect interpretation.

## Proposed reanalysis — not yet completed

1. Define retrospective explanation versus prediction before a solve.
2. Inventory feature availability and remove target-derived or unavailable predictors.
3. Reserve a chronological test period; restrict preprocessing/selection to training data.
4. Compare simple baselines and a pipeline with time-aware tuning.
5. Evaluate once on the holdout, inspect drift, and report uncertainty.

The resume describes dataset size, compared specifications and tuning without using compromised prediction scores as headline achievements.
