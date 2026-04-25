[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/kOqwghv0)
# Предсказание суммы месячных трат клиента

**Студент:** Мурадханов Самурхан Мурадович

**Группа:** БИВ236


## Оглавление

1. [Описание задачи](#описание-задачи)
2. [Структура репозитория](#структура-репозитория)
3. [Запуски](#быстрый-старт)
4. [Данные](#данные)
5. [Результаты](#результаты)
7. [Отчёт](#отчёт)


## Описание задачи


**Задача:** Регрессия — предсказание суммы месячных трат клиента (Customer Lifetime Value)

**Датасет:** nline Retail (транзакции интернет-магазина)  https://www.kaggle.com/datasets/carrie1/ecommerce-data

**Целевая метрика:** MAE (Mean Absolute Error) — основная, RMSE, R² — дополнительные.


## Структура репозитория
Опишите структуру проекта, сохранив при этом верхнеуровневые папки. Можно добавить новые при необходимости.
```
.
├── data
│   ├── processed               # Очищенные и обработанные данные
│   └── raw                     # Исходные файлы
├── models                      # Сохранённые модели 
├── notebooks
│   ├── 01_eda.ipynb            # EDA
│   ├── 02_baseline.ipynb       # Baseline-модель
│   └── 03_experiments.ipynb    # Эксперименты и ablation study
├── presentation                # Презентация для защиты
├── report
│   ├── images                  # Изображения для отчёта
│   └── report.md               # Финальный отчёт
├── src
│   ├── preprocessing.py        # Предобработка данных
│   └── modeling.py             # Обучение и оценка моделей
├── tests
│   └── test.py                 # Тесты пайплайна
├── requirements.txt
└── README.md
```

## Запуск


```bash
# 1. Клонировать репозиторий
git clone https://github.com/hsemlcourse/hseml-group-project-22samur22.git
cd hseml-group-project-22samur22

# 2. Создать виртуальное окружение
python -m venv .venv
# Windows:
.venv\Scripts\activate
# Linux/macOS:
# source .venv/bin/activate

# 3. Установить зависимости
pip install -r requirements.txt

# 4. Открыть ноутбук с проектом
jupyter notebook notebooks/Мурадханов_Самурхан_CP1.ipynb
```

## Данные
- `data/raw/` — исходные файлы
- `data/processed/` — предобработанные данные


## Результаты
Здесь коротко выпишите результаты.

Модель |	MAE	| R² |	Примечание
|--------|-------------|-------------|------------|
Baseline |	£816.76 |	-0.03	| Предсказание медианой
Lasso	| £373.03 |	0.68 |	Линейная модель с регуляризацией
Random Forest |	£276.64 |	0.76 |	Ансамбль деревьев
XGBoost	| £256.29 |	0.79	| Лучшая модель (градиентный бустинг)



## Отчёт

Финальный отчёт: [`report/report.md`](report/report.md)
