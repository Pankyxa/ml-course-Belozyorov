# House Prices — Advanced Regression Techniques

**Источник:** [Kaggle](https://www.kaggle.com/c/house-prices-advanced-regression-techniques)  
**Описание полей:** Dean De Cock, Ames Housing dataset  
**Файлы:** `train.csv` (1460 строк, 81 столбец), `test.csv` (1459 строк, 80 столбцов, без `SalePrice`)

## Задача

Регрессия: предсказать `SalePrice` — цену продажи дома в долларах.

## Целевая переменная

| Показатель | Значение |
|------------|----------|
| Среднее | $180 921 |
| Медиана | $163 000 |
| Минимум | $34 900 |
| Максимум | $755 000 |
| Асимметрия | 1.88 |
| Эксцесс | 6.54 |

Правый хвост — причина логарифмирования `log1p`.

## Группы признаков

| Группа | Примеры |
|--------|---------|
| Качество и состояние | `OverallQual`, `OverallCond`, `ExterQual`, `KitchenQual` |
| Площадь | `GrLivArea`, `TotalBsmtSF`, `1stFlrSF`, `2ndFlrSF`, `GarageArea` |
| Возраст | `YearBuilt`, `YearRemodAdd`, `YrSold` |
| Участок | `LotArea`, `LotFrontage`, `Neighborhood` |
| Гараж, подвал, бассейн | `GarageCars`, `BsmtQual`, `PoolQC` |

Числовых признаков 36, категориальных 43, плюс `Id` и цель.

## Пропуски, которые важны для чистки

| Столбец | Смысл пропуска |
|---------|----------------|
| `PoolQC`, `Alley`, `Fence`, `MiscFeature` | объекта обычно нет |
| `FireplaceQu` | нет камина |
| `Garage*` | нет гаража |
| `Bsmt*` | нет подвала |
| `LotFrontage` | длина фасада не указана, зависит от района |
| `Electrical` | единичный пропуск |
