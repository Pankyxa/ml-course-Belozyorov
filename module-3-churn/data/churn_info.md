# Telco Customer Churn

**Источник:** [Kaggle, BlastChar](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)  
**Файл:** `telco_churn.csv` — 7043 клиента, 21 столбец

## Задача

Бинарная классификация: уйдёт клиент (`Churn = Yes`) или останется (`No`).

## Баланс классов

| Класс | Клиентов | Доля |
|-------|----------:|-----:|
| No, остался | 5174 | 73.5% |
| Yes, ушёл | 1869 | 26.5% |

Ушедших меньше, поэтому accuracy легко завысить. Рядом смотрим F1 и ROC-AUC.

## Столбцы

| Столбец | Смысл |
|---------|--------|
| customerID | идентификатор, в модель не входит |
| gender, SeniorCitizen, Partner, Dependents | демография |
| tenure | сколько месяцев клиент с компанией |
| PhoneService, MultipleLines, InternetService | связь |
| OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, StreamingMovies | дополнительные услуги |
| Contract | месяц, год или два года |
| PaperlessBilling, PaymentMethod | счёт и оплата |
| MonthlyCharges, TotalCharges | платежи. `TotalCharges` записан текстом, у новых клиентов бывает пустым |
| Churn | целевая метка |

## Что уже видно без модели

- Месячный контракт: отток 42.7%. Год: 11.3%. Два года: 2.8%.
- Fiber optic: отток 41.9%. DSL: 19.0%. Без интернета: 7.4%.
- Среди клиентов с tenure не больше 6 месяцев уходит 52.9%.
