# Project overview

## Question and data

I used my own virtual Rubik’s Cube history to explore which features accompany faster solves, how performance changes with practice, and how solve frequency and time differ by weekday or time of day. csTimer’s virtual cube is controlled with a keyboard. Its nested export records duration, timestamps, scrambles and timed movement events. These analyses extract `session36`, not WCA results or physical solves.

## Two stages

**STAT 303-1, Fall 2025:** 16,856 observations before cleaning; 80 removed using pause and rotation thresholds after the initial learning period; 16,776 rows and 14 variables retained. The analysis examined numeric associations, progression across solve index/calendar time, and 28 weekday/time-of-day combinations.

**STAT 303-2, Winter 2026:** an expanded snapshot with 22,442 observations and 15 variables. A random 80/20 split produced 17,953 training and 4,489 test observations. Eight linear specifications progressively added predictors; the ninth used degree-2 polynomial terms and Ridge with five-fold cross-validation. The saved run selected alpha 10. Separate OLS explored conditional associations.

The snapshots overlap and should not be counted as independent additional datasets.

## Interpretation

The exploratory report shows an early learning curve followed by slower, uneven progress. The regression extension demonstrates model specification, categorical encoding, polynomial features, regularization, comparison and coefficient interpretation.

The findings are descriptive. Longer pauses accompanying longer solve times is not proof that a specific training intervention improves future performance. Temporal comparisons may also reflect practice selection and learning stage.

The original prediction section uses a target-derived turning-speed feature. Its reported scores cannot establish forecasting ability. Course artifacts retain their original outputs; [validation notes](methods-and-limitations.md) supersede stronger predictive or causal interpretations in the original prose. A corrected experiment remains future work.
