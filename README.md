# Решение задачи классификации временных рядов

Это репозиторий содержит решение задачи классификации временных рядов. Решение основано на модели XGBoost и включает в себя этапы анализа данных, создание признаков, обучения модели и предсказания.

## Структура репозитория

```
├── train.parquet # Обучающая выборка
├── test.parquet # Тестовая выборка
├── xgb_model.pkl # Сохраненная обученная модель XGBoost
├── predict.ipynb # Jupyter Notebook с кодом предсказания
├── modeltrain.ipynb # Jupyter Notebook с кодом обучения модели и генерации признаков
├── submission.csv # Файл с предсказаниями на тестовой выборке
├── requirements.txt # Список необходимых библиотек
└── README.md # Этот файл
```

## Описание файлов

* **train.parquet & test.parquet:** Исходные данные в формате parquet. Содержат временные ряды, которые необходимо классифицировать.

* **xgb_model.pkl:** Обученная модель XGBoost, сохраненная с помощью библиотеки `pickle`. Этот файл используется для предсказаний на тестовой выборке.

* **predict.ipynb:** Jupyter Notebook, содержащий код для:
  - загрузки тестовых данных
  - генерации признаков
  - загрузки обученной модели 
  - создания файла `submission.csv` с предсказаниями

* **train.ipynb:** Jupyter Notebook, содержащий:
  - код для анализа данных (EDA)
  - генерацию признаков из обучающей выборки
  - обучение модели XGBoost
  - оценку качества на валидационной выборке
  - визуализации и анализ распределения классов
  - анализ временных рядов

* **submission.csv:** CSV файл, содержащий предсказания.

## Инструкция по запуску

1. Установка библиотек:
```bash
pip install -r requirements.txt
```

2. Клонируйте репозиторий:
```bash
git clone <(https://github.com/den1ksk/Time-series-vk)>
```

3. Перейдите в директорию репозитория:
```bash
cd <Time-series-vk>
```

4. Для получения предсказаний на тестовой выборке, запустите `predict.ipynb`. Скрипт создаст файл `submission.csv` с предсказаниями.

5. Для воспроизведения обучения модели и анализа данных, запустите `train.ipynb`.

## Дополнительная информация

* Обучение модели выполнено с использованием GPU (Nvidia RTX 3050 8GB) для ускорения процесса. Если у вас нет GPU, удалите параметр `device='cuda'` и `tree_method='hist'`, из кода обучения модели в `train.ipynb`.
