# Module 1 — Titanic: EDA + бинарная классификация

**Автор:** Белозёров Константин Сергеевич, ПКТб-23-1  
**Дата обучения:** 2026-11-02  
**Отчёт:** [notebook.ipynb](./notebook.ipynb)

Задача — предсказать, выжил ли пассажир «Титаника». Данные: `data/train.csv` (891 строка) и `data/test.csv` (418 строк). Описание столбцов — в `data/titanic_info.md`.

## Результаты

Метрики на отложенных 20% (`random_state=42`, стратификация по `Survived`).

| Модель | Accuracy | Precision | Recall | F1 | ROC-AUC |
|--------|----------|-----------|--------|-----|---------|
| Logistic Regression | 0.8045 | 0.7833 | 0.6812 | 0.7287 | 0.8486 |
| Decision Tree | 0.7821 | 0.7419 | 0.6667 | 0.7023 | 0.8132 |
| Random Forest | 0.8045 | 0.8400 | 0.6087 | 0.7059 | 0.8497 |

**Время обучения:** 0.004 с (LR), 0.002 с (DT), 0.12 с (RF).

Обе обязательные модели выше порога ROC-AUC 0.80. Среди них лучше логистическая регрессия. Случайный лес чуть выше по AUC и precision, но хуже по recall.

## Быстрый старт

Ноутбук запускается из этой папки, пути к данным относительные (`data/train.csv`).

```python
import joblib
import requests
from io import BytesIO

BASE_URL = "https://raw.githubusercontent.com/Pankyxa/ML_Spirin/main/module-1-titanic"
model = joblib.load(BytesIO(requests.get(f"{BASE_URL}/models/lr_model.pkl").content))
```

Пока репозиторий не опубликован, те же файлы лежат в `models/`.

## Структура

- `notebook.ipynb` — отчёт из 14 разделов
- `models/` — модели, scaler, кодировщик пола, список признаков, метрики
- `data/` — датасет и описание
- `examples/` — графики EDA, матрицы ошибок и ROC-кривые
- `requirements.txt` — версии пакетов, на которых ноутбук запускался
