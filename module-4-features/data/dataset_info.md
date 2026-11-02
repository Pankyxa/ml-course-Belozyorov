# Online Shoppers Purchasing Intention

**Источник:** UCI Machine Learning Repository, запись 468.  
Файл на Kaggle: [Online Shoppers Intention](https://www.kaggle.com/datasets/roshansharma/online-shoppers-intention)  
**Файл:** `online_shoppers_intention.csv` — 12 330 сессий, 18 столбцов  
**Авторы:** Sakar, Polat, Katircioglu, Kastro (2018)

## Задача

Бинарная классификация: закончилась ли сессия покупкой (`Revenue = True`).

## Баланс классов

| Класс | Сессий | Доля |
|-------|-------:|-----:|
| False, без покупки | 10 422 | 84.5% |
| True, покупка | 1 908 | 15.5% |

Пропусков в таблице нет. Дисбаланс сильный, одной accuracy недостаточно.

## Признаки

10 числовых метрик поведения (`Administrative`, длительности, `BounceRates`, `ExitRates`, `PageValues`, `SpecialDay`) и категориальные поля `Month`, `OperatingSystems`, `Browser`, `Region`, `TrafficType`, `VisitorType`, `Weekend`.

`OperatingSystems`, `Browser`, `Region` и `TrafficType` записаны числами, но порядка у этих кодов нет: это идентификаторы, а не «чем больше, тем лучше».
