
# Model Performance & Optimal Hyperparameters

## 1. Model Performance Comparison

The following results were obtained using 5-fold cross-validation.

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Random Forest | 0.09917 | 0.13493 | 0.36895 |
| CatBoost | 0.09997 | 0.13571 | 0.36157 |
| LightGBM | **0.09833** | **0.13345** | **0.38265** |
| XGBoost | 0.09954 | 0.13488 | 0.36934 |
| Extra Trees | 0.09837 | 0.13393 | 0.37818 |

**Best Overall Model: LightGBM**

- MAE: 0.09833
- RMSE: 0.13345
- R²: 0.38265

## 2. Optimal Hyperparameter Settings

The following hyperparameters were automatically selected through the respective optimization algorithms.

### Random Forest

```python
{
    "n_estimators": 500,
    "max_depth": 31,
    "min_samples_split": 4,
    "min_samples_leaf": 2,
    "max_features": 0.749798895
}
```

### CatBoost

```python
{
    "iterations": 900,
    "learning_rate": 0.099552898,
    "depth": 6,
    "l2_leaf_reg": 10.33716334,
    "border_count": 64
}
```

### LightGBM

```python
{
    "n_estimators": 900,
    "learning_rate": 0.021198330,
    "num_leaves": 149,
    "min_child_samples": 7,
    "subsample": 0.613231401,
    "colsample_bytree": 0.524336042,
    "reg_lambda": 1.625864145
}
```

### XGBoost

```python
{
    "n_estimators": 600,
    "learning_rate": 0.091226149,
    "max_depth": 7,
    "min_child_weight": 5.359530048,
    "subsample": 0.834203735,
    "colsample_bytree": 0.552402294,
    "reg_lambda": 18.412116238
}
```

### Extra Trees

```python
{
    "n_estimators": 500,
    "max_depth": 30,
    "min_samples_split": 12,
    "min_samples_leaf": 1,
    "max_features": 0.813623807
}
```

## 3. Evaluation Notes

- All reported metrics are based on 5-fold cross-validation.
- Hyperparameters were selected automatically using the respective optimization algorithms.
- The test dataset was not used during hyperparameter tuning or model selection.
- Reported metrics represent validation performance, not final test-set performance.
- LightGBM achieved the lowest MAE and RMSE and the highest R² among the five models.

