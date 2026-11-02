# Module 2 — House Prices: предобработка и регрессия

**Автор:** Белозёров Константин Сергеевич, ПКТб-23-1  
**Дата обучения:** 2026-11-02  
**Отчёт:** [notebook.ipynb](./notebook.ipynb)

Задача — предсказать `SalePrice`. Обучение идёт на `log1p(SalePrice)`, метрики R² и RMSE в логарифмах считаются на отложенных 20%.

## Результаты

| Модель | RMSE (log) | MAE (log) | R² | RMSE ($) |
|--------|------------|-----------|-----|----------|
| Linear Regression | 0.1281 | 0.0863 | 0.9027 | 21 400 |
| Ridge | 0.1250 | 0.0851 | 0.9074 | 21 256 |
| Lasso | 0.1189 | 0.0813 | 0.9162 | 20 512 |
| ElasticNet | 0.1189 | 0.0812 | 0.9161 | 20 500 |
| Random Forest | 0.1444 | 0.0942 | 0.8762 | 24 276 |

**Лучшая модель:** Lasso. Она обнулила 57 из 225 признаков. Файл `models/best_model.pkl` — её копия.

## Быстрый старт

```python
import json
from pathlib import Path
import joblib

model = joblib.load('models/best_model.pkl')
scaler = joblib.load('models/scaler.pkl')
features = json.loads(Path('models/feature_cols.json').read_text())
```

## Структура

- `notebook.ipynb` — отчёт
- `data/train.csv`, `data/test.csv`, `data/house_prices_info.md`
- `models/` — четыре линейные модели, лучшая модель, scaler, признаки, метрики
- `examples/` — EDA, scatter прогноза, остатки
