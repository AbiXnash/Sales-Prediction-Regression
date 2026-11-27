# Sales-Prediction-Regression

Forecasts monthly sales with a Random Forest regressor, in one Jupyter notebook. (This is a separate project from
[Big-Mart-Sales-Prediction](https://github.com/AbiXnash/Big-Mart-Sales-Prediction).)

## What the notebook does

1. Loads `train.csv` (daily sales by `date`, `store` and `item`, as in Kaggle's
   [Store Item Demand Forecasting](https://www.kaggle.com/competitions/demand-forecasting-kernels-only) data),
   drops store and item, and sums sales per month.
2. Makes the series stationary with month-to-month differences, and builds supervised features from the previous
   12 months' differences.
3. Holds out the last 12 months, scales to [-1, 1], and trains scikit-learn's `RandomForestRegressor`.
4. Turns the predicted differences back into sales, plots predictions against actual sales, and prints RMSE, MAE
   and R².

In the saved run: RMSE ≈ 20,024, MAE ≈ 17,355, R² ≈ **0.985**.

## Run it

```bash
pip install pandas numpy scikit-learn matplotlib jupyter
jupyter notebook Sales_Prediction_Regression.ipynb
```

Put `train.csv` next to the notebook first. It isn't included in this repository.

## Licence

MIT, see [LICENSE](LICENSE).
