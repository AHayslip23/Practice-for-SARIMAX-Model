# Practice for SARIMAX Model

Time-series forecasting practice with seasonal ARIMA models that include outside variables (SARIMAX), using daily Delhi climate data.

## Repository Contents

| File | Description |
|---|---|
| `SARIMAX practice .ipynb` | SARIMAX modeling notebook (28 charts) |
| `Delhi Climate Data 2013.csv` | Daily Delhi climate data (1,462 days): mean temperature, humidity, wind speed and mean pressure |

## Commit History

### `b452771`: Upload of the SARIMAX notebook and dataset (2023-03-26)
- **Train/test split:** the first 1,097 days for training and the remaining 365 days for testing.
- **Model selection:** used `pmdarima.auto_arima` (stepwise search minimizing AIC) with weekly seasonality (m = 7, D = 1) to choose model orders. The other climate variables were included as outside predictors.
- **Fitted `statsmodels` SARIMAX models over several rounds,** e.g. `(3,0,2)(2,1,0)[7]` with outside predictors, `(1,0,0)(2,1,0)[7]`, `(0,0,2)(0,1,1)[7]` for wind speed, and `(0,0,0)(2,1,0)[7]` for mean pressure.
- **Evaluation:** RMSE on the test set for each round, with forecast vs. actual plots. The largest error was on mean pressure (RMSE ≈ 360), whose data contains extreme outliers.

## Tools
Python, pandas, NumPy, statsmodels, pmdarima, scikit-learn, matplotlib, seaborn, Jupyter Notebook
