## Summary

### Boundaries

#### Standard Error Metrics (MAE, MSE, RMSE) Categorization

| Category           | Normalized Error Range  |
|--------------------|-------------------------|
| Perfect            | Exactly 0               |
| Very Acceptable    | $0 < x \leq 0.05$     |
| Acceptable         | $0.05 < x \leq 0.1$   |
| Moderate           | $0.1 < x \leq 0.2$    |
| High               | $0.2 < x \leq 0.3$    |
| Very High          | $0.3 < x \leq 1.0$    |
| Exceedingly High   | $x > 1.0$             |

#### Percentage Error (PE) Categorization

| Category          | Error Magnitude (%) | Direction |
|-------------------|-----------------------|-----------|
| Perfect           | Exactly 0%            | -         |
| Very Acceptable   | $0 < x \leq 5$    | Over/Under|
| Acceptable        | $5 < x \leq 10$   | Over/Under|
| Moderate          | $10 < x \leq 20$  | Over/Under|
| High              | $20 < x \leq 30$  | Over/Under|
| Very High         | $30 < x \leq 100$ | Over/Under|
| Exceedingly High  | $x > 100$           | Over/Under|

#### R2 Score Categorization

| Category                           | R2 Value Range    |
|------------------------------------|-------------------|
| Perfect                            | Exactly 1         |
| Very Acceptable                    | $0.95 \leq x < 1$|
| Acceptable                         | $0.9 \leq x < 0.95$|
| Moderate                           | $0.8 \leq x < 0.9$|
| High                               | $0.7 \leq x < 0.8$|
| Very High                          | $0.5 \leq x < 0.7$|
| Exceedingly High                   | $0 < x < 0.5$   |
| Doesn't Explain Variability        | Exactly 0         |
| Worse Than Simple Mean Model       | $x < 0$         |

#### MASE Categorization

| Category           | MASE Value Range  |
|--------------------|-------------------|
| Perfect            | Exactly 0         |
| Very Acceptable    | $0 < x \leq 0.05$|
| Acceptable         | $0.05 < x \leq 0.1$|
| Moderate           | $0.1 < x \leq 0.2$|
| High               | $0.2 < x \leq 0.3$|
| Very High          | $0.3 < x \leq 1.0$|
| Worse Than Naive Forecast Model | $x > 1.0$ |

### Severity Emojis:

| Metric | Emoji |
|--------|-------|
| PERFECT | 💯 |
| VERY_ACCEPTABLE | 👌 |
| ACCEPTABLE | ✔️ |
| MODERATE | ❗ |
| HIGH | ❌ |
| VERY_HIGH | 💀 |
| EXCEEDINGLY_HIGH | ☠ |
| R2_NO_FIT | 🚫 |
| R2_POOR_FIT | 🛑 |
| MASE_WORST | 🤬 |

### Directional Emojis:

| Metric | Emoji |
|--------|-------|
| OVERESTIMATION | 📈 |
| UNDERESTIMATION | 📉 |
| Nan / None | 🙅‍♂️ |

### Summary Table

> **Disclaimer:** Metrics are calculated using `sklearn.metrics`, with the exception of `MASE`, `sMAPE`, and `MBD`. Results may vary based on different implementations.

| Based on | Variant | Dataset | Model | R2 | MAE | MSE | RMSE | MASE | MAPE | sMAPE | MBD |
|--|--|--|--|--|--|--|--|--|--|--|--|
| Test Size | Small=1 | Sin | AutoReg |🙅‍♂️|👌|👌|👌|🤬|👌📈|👌📈|👌📈|
| | | | OffsetModel |--|--|--|--|--|--|--|--|
| | | Cos | AutoReg |--|--|--|--|--|--|--|--|
| | | | OffsetModel |--|--|--|--|--|--|--|--|
| Test Size | Small=2 | Sin | AutoReg |🛑|👌|👌|👌|🤬|👌📈|👌📈|👌📈|
| | | | OffsetModel |--|--|--|--|--|--|--|--|
| | | Cos | AutoReg |--|--|--|--|--|--|--|--|
| | | | OffsetModel |--|--|--|--|--|--|--|--|
| Test Size | Mid | Sin | AutoReg |🛑|👌|👌|👌|🤬|👌📈|👌📈|👌📈|
| | | | OffsetModel |--|--|--|--|--|--|--|--|
| | | Cos | AutoReg |--|--|--|--|--|--|--|--|
| | | | OffsetModel |--|--|--|--|--|--|--|--|
| Test Size | Large | Sin | AutoReg |🛑|❗|✔️|❌|🤬|👌📈|❌📈|💀📈|
| | | | OffsetModel |--|--|--|--|--|--|--|--|
| | | Cos | AutoReg |--|--|--|--|--|--|--|--|
| | | | OffsetModel |--|--|--|--|--|--|--|--|