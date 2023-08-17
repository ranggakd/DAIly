## Summary

<details>
    <summary>
<h3>Boundaries</h3>
    </summary>

> **Disclaimer:** These boundaries are user-defined. They may vary based on different context.

#### Standard Error Metrics (MAE, MSE, RMSE) Categorization

| Category           | Normalized Error Range  |
|--------------------|-------------------------|
| Perfect            | Exactly 0               |
| Very Acceptable    | $0 < x \leq 0.05$     |
| Acceptable         | $0.05 < x \leq 0.1$   |
| Moderate           | $0.1 < x \leq 0.2$    |
| High               | $0.2 < x \leq 0.3$    |
| Very High          | $0.3 < x \leq 1$    |
| Exceedingly High   | $x > 1$             |

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
| Doesn't Explain Variability        | Exactly 0       |
| Worse Than Simple Mean Model       | $x < 0$         |

#### MASE Categorization

| Category           | MASE Value Range  |
|--------------------|-------------------|
| Perfect            | Exactly 0         |
| Very Acceptable    | $0 < x \leq 0.05$|
| Acceptable         | $0.05 < x \leq 0.1$|
| Moderate           | $0.1 < x \leq 0.2$|
| High               | $0.2 < x \leq 0.3$|
| Very High          | $0.3 < x \leq 1$|
| Worse Than Naive Forecast Model | $x > 1$ |
</details>

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

> **Disclaimer:** 
>
> 1. Metrics are calculated using `sklearn.metrics`, with the exception of `MASE`, `sMAPE`, and `MBD`. Results may vary based on different implementations.
> 1. The datasets utilized for these metrics were synthesized using mathematical formulas, particularly functions such as sine and cosine, to allow for controlled factors and predictable patterns.
> 1. The controlled models employed for this exploration include `statsmodels.tsa.ar_model.AutoReg` and `OffsetModel`. 
> 1. `AutoReg` was chosen for its fundamental nature in *time series forecasting*, while the `OffsetModel` was designed to produce predictions by simply shifting the actual test data by a specified offset, effectively *mimicking a model that performs well* in comparison to `AutoReg`.
> 1. This experiment specifically addresses **forecasting problems**, emphasizing that forecasting is a subset of regression tasks. In other words, while all forecasting problems are regressions, not all regression problems are forecasts. *Click 📊 for the plot*.
> 1. This experiment is not intended to serve as a rule of thumb or a best practice. Instead, it offers a glimpse into how different metrics behave on controlled models and datasets to foster a deeper understanding.
> 1. **Use insights from this exploration at your own risk.**

| Plot | Based on | Variant | Dataset | Model | R2 | MAE | MSE | RMSE | MASE | MAPE | sMAPE | MBDev |
|--|--|--|--|--|--|--|--|--|--|--|--|--|
|[📊]()| Test Size | Small=1 | $\cos(x)$ | AutoReg |🙅‍♂️|👌|👌|👌|🤬|👌📈|👌📈|👌📈|
|[📊]()| | | | OffsetModel |🙅‍♂️|👌|👌|👌|🤬|👌📈|👌📈|👌📈|
|[📊]()| | | $\sin(x)$ | AutoReg |🙅‍♂️|👌|👌|👌|🤬|☠📈|☠📈|☠📉|
|[📊]()| | | | OffsetModel |🙅‍♂️|👌|👌|👌|🤬|☠📈|☠📈|☠📈|
|[📊]()| Test Size | Small=2 | $\cos(x)$ | AutoReg |🛑|👌|👌|👌|🤬|👌📈|👌📈|👌📈|
|[📊]()| | | | OffsetModel |🛑|👌|👌|👌|🤬|👌📈|👌📈|👌📈|
|[📊]()| | | $\sin(x)$ | AutoReg |🛑|👌|👌|👌|🤬|☠📈|☠📈|☠📉|
|[📊]()| | | | OffsetModel |🛑|👌|👌|👌|🤬|☠📈|☠📈|☠📈|
|[📊]()| Test Size | Mid | $\cos(x)$ | AutoReg |🛑|👌|👌|👌|🤬|👌📈|👌📈|👌📈|
|[📊]()| | | | OffsetModel |🛑|👌|👌|👌|🤬|👌📈|👌📈|👌📈|
|[📊]()| | | $\sin(x)$ | AutoReg |🛑|👌|👌|👌|🤬|☠📈|💀📈|☠📉|
|[📊]()| | | | OffsetModel |🛑|👌|👌|👌|🤬|☠📈|☠📈|☠📈|
|[📊]()| Test Size | Large | $\cos(x)$ | AutoReg |🛑|❗|✔️|❌|🤬|👌📈|❌📈|💀📈|
|[📊]()| | | | OffsetModel |❗|👌|👌|👌|🤬|👌📈|👌📈|👌📈|
|[📊]()| | | $\sin(x)$ | AutoReg |🛑|❌|❗|❌|🤬|☠📈|💀📈|☠📉|
|[📊]()| | | | OffsetModel |👌|👌|👌|👌|🤬|☠📈|❗📈|☠📈|
|[📊]()| Number Nature | Non-zero Real Numbers | $10 \cdot \cos(x) + 1$ | AutoReg |🛑|☠|☠|☠|🤬|👌📈|☠📈|☠📈|
|[📊]()| | | | OffsetModel |👌|👌|👌|👌|💀|👌📈|✔️📈|👌📈|
|[📊]()| | | $10 \cdot \sin(x) + 1$ | AutoReg |🛑|💀|☠|💀|🤬|❗📈|💀📈|☠📈|
|[📊]()| | | | OffsetModel |👌|👌|👌|👌|💀|👌📈|❗📈|👌📉|
|[📊]()| | Real Numbers | $\text{int}(10 \cdot \cos(x))$ | AutoReg |||||||||
|[📊]()| | | | OffsetModel |||||||||
|[📊]()| | | $\text{int}(10 \cdot \sin(x))$ | AutoReg |||||||||
|[📊]()| | | | OffsetModel |||||||||
|[📊]()| | Negative Numbers Only | $10 \cdot \cos(x) - 11$ | AutoReg |||||||||
|[📊]()| | | | OffsetModel |||||||||
|[📊]()| | | $10 \cdot \sin(x) - 11$ | AutoReg |||||||||
|[📊]()| | | | OffsetModel |||||||||
|[📊]()| | Positive Numbers Only | $10 \cdot \cos(x) + 11$ | AutoReg |||||||||
|[📊]()| | | | OffsetModel |||||||||
|[📊]()| | | $10 \cdot \sin(x) + 11$ | AutoReg |||||||||
|[📊]()| | | | OffsetModel |||||||||
|[📊]()| | Very Small Numbers | $1 \times 10^{-6} \cdot \cos(x)$ | AutoReg |||||||||
|[📊]()| | | | OffsetModel |||||||||
|[📊]()| | | $1 \times 10^{-6} \cdot \sin(x)$ | AutoReg |||||||||
|[📊]()| | | | OffsetModel |||||||||
|[📊]()| | Very Large Numbers | $1 \times 10^{11} \cdot \cos(x)$ | AutoReg |||||||||
|[📊]()| | | | OffsetModel |||||||||
|[📊]()| | Very Large Numbers | $1 \times 10^{11} \cdot \sin(x)$ | AutoReg |||||||||
|[📊]()| | | | OffsetModel |||||||||
|[📊]()| Magnitude | Large | $10 \cdot \cos(x) + 1$ | AutoReg |||||||||
|[📊]()| | Small | $10 \cdot \cos(x) + 1$ | AutoReg |||||||||
|[📊]()| | Same Magnitude for $y \text{ and } \hat{y}$ | $10 \cdot \cos(x) + 1$ | AutoReg |||||||||
|[📊]()| | Different Magnitude for $y \text{ and } \hat{y}$ | $10 \cdot \cos(x) + 1$ | AutoReg |||||||||


https://ranggakd.github.io/DAIly/ideas/regression_forecasting_metrics/plots/testsize_s1_cos_ar.html
https://ranggakd.github.io/DAIly/ideas/regression_forecasting_metrics/plots/testsize_s1_cos_om.html
https://ranggakd.github.io/DAIly/ideas/regression_forecasting_metrics/plots/testsize_s1_sin_ar.html
https://ranggakd.github.io/DAIly/ideas/regression_forecasting_metrics/plots/testsize_s1_sin_om.html
https://ranggakd.github.io/DAIly/ideas/regression_forecasting_metrics/plots/testsize_s2_cos_ar.html
https://ranggakd.github.io/DAIly/ideas/regression_forecasting_metrics/plots/testsize_s2_cos_om.html
https://ranggakd.github.io/DAIly/ideas/regression_forecasting_metrics/plots/testsize_s2_sin_ar.html
https://ranggakd.github.io/DAIly/ideas/regression_forecasting_metrics/plots/testsize_s2_sin_om.html
https://ranggakd.github.io/DAIly/ideas/regression_forecasting_metrics/plots/testsize_mid_cos_ar.html
https://ranggakd.github.io/DAIly/ideas/regression_forecasting_metrics/plots/testsize_mid_cos_om.html
https://ranggakd.github.io/DAIly/ideas/regression_forecasting_metrics/plots/testsize_mid_sin_ar.html
https://ranggakd.github.io/DAIly/ideas/regression_forecasting_metrics/plots/testsize_mid_sin_om.html
https://ranggakd.github.io/DAIly/ideas/regression_forecasting_metrics/plots/testsize_l_cos_ar.html
https://ranggakd.github.io/DAIly/ideas/regression_forecasting_metrics/plots/testsize_l_cos_om.html
https://ranggakd.github.io/DAIly/ideas/regression_forecasting_metrics/plots/testsize_l_sin_ar.html
https://ranggakd.github.io/DAIly/ideas/regression_forecasting_metrics/plots/testsize_l_sin_om.html

