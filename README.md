# yandex-practicum-projects

Я начинающий специалист по Data Science. \
Мой путь в it начался с курсов Яндекс Практикум. \
В настоящий момент мое обучение на курсе завершено и я ищу свою первую работу!

> Используемый стек: \
Python, Pandas, Matplotlib, Seaborn, NumPy, SciPy, PyTorch, Keras, Scikit-learn, Bootstrap, Lightgbm, Catboost, BERT, Nltk, A/B tests, SQL, PostgreSQL.

За время учебы я решила 16 кейсов (банки, телеком, промышленность, интернет-сервисы и д.р.) \
Здесь представлены ссылки и краткое описание 6 наиболее интересных из них.


| #    | Наименование проекта                | Описание                                                     | Стек                                                         |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1.   | [Нейросеть для определения возраста покупателей по фотографии](https://github.com/GilevaTanya/yandex-practicum-projects/blob/main/model-fo-determining-age-on-a-photo/Readme.md) | Фотофиксация в прикассовой зоне поможет определять возраст клиентов, чтобы анализировать покупки и предлагать товары, которые могут заинтересовать покупателей этой возрастной группы и контролировать добросовестность кассиров при продаже алкоголя. (обработка изображения, нейронные сети, компьютерное зрение)  | Python, Pandas, Keras, PIL , matplotlib |
| 2.   | [Модель для классификации комментариев](https://github.com/GilevaTanya/yandex-practicum-projects/tree/main/model-for-classifying-comments-with-BERT) | Модель, которая будет искать токсичные комментарии и отправлять на модерацию. (обработка естественного языка, классификация) | Python, Pandas, Numpy, BERT, nltk, scikit-learn, tf-idf.      |
| 3.   | [Модель для предсказания температуры сплава, для оптимизации процесса производства стали.](https://github.com/GilevaTanya/yandex-practicum-projects/tree/main/model-for-determining-the-temperature-of-the-alloy) | Чтобы оптимизировать производственные расходы, металлургический комбинат решил уменьшить потребление электроэнергии на этапе обработки стали за счет контроля температуры сплава (градиентный бустинг, регрессия)| Python, Pandas, Numpy, seaborn, matplotlib, scipy, math, scikit-learn, CatBoost |
| 4.   | [Модель для прогнозирования оттока клиента Банка](https://github.com/GilevaTanya/yandex-practicum-projects/tree/main/model-for-predicting-customer-of-the-bank) | Модель которая поможет банку сохранять текущих клиентов и недопустить расторжения договора (классификация) | Python, Pandas, Numpy, scikit-learn matplotlib |
| 5.   | [Модель для прогнозирования количества заказов такси на следующий час](https://github.com/GilevaTanya/yandex-practicum-projects/tree/main/model-for-predicting-taxi-for-the-next-hour) | Чтобы привлекать больше водителей в период пиковой нагрузки, нужно спрогнозировать количество заказов такси на следующий час (временные ряды, регрессия, градиентный бустинг)  | Python, Pandas, Numpy, scikit-learn, statsmodels, RidgeCV |
| 6.   | [Модель для прогнозирования рыночной стоимости автомобиля](https://github.com/GilevaTanya/yandex-practicum-projects/tree/main/model-for-predicting-value-car) | Сервис по продаже автомобилей для привлечения новых клиентов предлагает быстро узнать рыночную стоимость автомобиля (градиентный бустинг, регрессия) | Python, Pandas, seaborn, matplotlib, scikit-learn, LightGBM |

####

#### 1. Проект: Нейросеть для определения возраста покупателей по фотографии (обработка изображения, нейронные сети, компьютерное зрение, Keras)
**- Что сделано:**  произвела исследовательский анализ набора фотографий, подготовила данные к обучению: нормировка, аугментация, привела к одной размерности. При обучении нейронной сеть, использовала архитектуру ResNet50, верхушка реализовала через 2 полносвязных слоя, активация через relu, оптимизатор: Adam. Оценка качества по MAE.\
**- Результат:** создала нейросеть на базе Keras.

####

#### 2. Проект: Модель для классификации комментариев (обработка естественного языка, NLP, классификация, BERT)
**- Что сделано:**  произвела предобработку данных, визуализацию, подготовила данных к обучению (лемматизация, векторизация, удаление стоп-слов), обучила нескольких моделей с автоматическим подбором гиперпараметров + предобрученная модель BERT2000. Выбрала наилучшую модель по значению F1-меры. \
**- Результат:** создала модель  на базе LinearRegression.

####

#### 3. Проект: Модель для предсказания температуры сплава, для оптимизации процесса производства стали (градиентный бустинг, регрессия).
**- Что сделано:**  произвела предобработку данных, визуализацию, подготовила данные к обучению,произвела масштабирование признаков, обучила несколько моделей с автоматическим подбором гиперпараметров. Выборала наилучшую модель по значению МАЕ <=6,8. Провела исследования важности признаков feature_importances_\
**- Результат:** создала модель на базе CatBoost.

####

#### 4. Проект: Модель для прогнозирования оттока клиента Банка (классификация).
**- Что сделано:**  произвела предобработку данных, визуализацию, подготовила данных к обучению, обучила нескольких моделей с автоматическим подбором гиперпараметров + измерение AUC-ROC. Выбрала наилучшую модель по значению F1-меры. Проверка на адекватность.\
**- Результат:** создала модель Случайного леса, при взвешивании классов.

####

#### 5. Проект: Модель для прогнозирования количества заказов такси на следующий час (временные ряды, регрессия, градиентный бустинг)
**- Что сделано:** ресемплировала данных по одному часу, проверила соблюдение хронологического порядка и границ временного интервала, произвела оценку стационарности ряда, тренда, сезонности и шума, произвела проверка автокорреляции. Создала дополнительные признаки, подготовила данные к обучению, обучила нескольких моделей с автоматическим подбором гиперпараметров. Выбрала наилучшую модель по RMSE. Проверка на адекватность. \
**- Результат:**  создана модель на базе LinearRegression.

####

#### 6. Проект: Модель для прогнозирования рыночной стоимости автомобиля (градиентный бустинг, регрессия).
**- Что сделано:** произвела предобработку данных, визуализацию, подготовила данных к обучению (прямое кодирование категориальных признаков в численные посредством OHE, масштабирование признаков. Для модели LightGBM кодировка через OHE не проводила), обучила нескольких моделей с автоматическим подбором гиперпараметров. Выбрала наилучшую модель по значению RMSE. \
**- Результат:** создала модель на базе LightGBM.


