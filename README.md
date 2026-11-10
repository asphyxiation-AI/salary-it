# Зарплата.IT

Система оценивает условную зарплатную премию за отдельные цифровые компетенции с учетом региона и отрасли.

## Визуализация

<img width="1919" height="1079" alt="изображение" src="https://github.com/user-attachments/assets/445dc1e4-f376-4a28-97ac-32b958a0f8b8" />

## Основные возможности (Features)

- **Сбор данных из трёх источников:**
  - `trudvsem.ru` — открытый API, ~3 000 IT-вакансий с полным текстом описания;
  - `hh.ru IT 2026` (Kaggle) — 6 968 IT-вакансий, 42 признака;
  - `hh.ru 2026` (Kaggle) — 129 464 вакансии, фильтруются до IT-категории (~5 850).
- **Очистка и унификация:** приведение зарплат к «месяц, net», нормализация регионов и опыта, фильтрация выбросов.
- **NLP на тексте описания:** TF-IDF + Ridge, CatBoost native text features, лемматизация через `pymorphy3`.
- **11 моделей:** от тривиального baseline до CatBoost с полным набором признаков (R² = 0.711).
- **Quantile Regression:** прогноз диапазона зарплаты (10–90 перцентиль), coverage 73.1%.
- **Интерпретация:** топ-30 слов, повышающих/понижающих зарплату; важность признаков.
- **Сравнительный анализ:** госсектор vs частный сектор (медианы 55k vs 130k).

## Установка (Installation)

```bash
git clone https://github.com/asphyxiation-AI/salary-it.git
cd salary-it
```

## Использование (Usage)
```
# 1. Парсинг trudvsem (~30 минут)
jupyter notebook 01_parsing_trudvsem.ipynb

# 2. Загрузка датасетов hh.ru с Kaggle
jupyter notebook 02_loading_kaggle.ipynb

# 3. Объединение и очистка
jupyter notebook 03_merge_clean.ipynb
```
## Структура проекта (Project Structure)

-

## Разработка и вклад (Contributing)

-

## Лицензия (License)

-
