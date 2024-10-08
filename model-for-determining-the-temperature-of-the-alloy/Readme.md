# Модель предсказания температуры сплава, для оптимизации процесса производства стали.

## *Стек:*
pandas, numpy, seaborn, matplotlib, scipy, math, scikit-learn, catboost.
## *Описание:*
Чтобы оптимизировать производственные расходы, металлургический комбинат решил уменьшить потребление электроэнергии на этапе обработки стали. Для этого комбинату нужно контролировать температуру сплава. Заказчик хочет использовать разработанную модель для имитации технологического процесса.   
*Задача* — построить модель, которая будет предсказывать финальную температуру сплава в ковше.**  
*Целевая метрика МАЕ* <= 6,8.**

## **План работы:**
1. Загрузка данных.
2. Исследовательский анализ и предобработка данных.
3. Объединение данных.
4. Исследовательский анализ и предобработка данных объединённого датафрейма.
5. Подготовка данных для обучения модели.
6. Обучение моделей машинного обучения: Линейная регрессия, Случайный лес, CatBoost.
7. Выбор лучшей модели.
8. Общий вывод и рекомендации заказчику.

## *Общий вывод:*

Для целей моделирования были выбраны следующие алгоритмы: Линейная регрессия, Случайный лес, CatBoost.

Налиучший показатель по метрики качества МАЕ показал алгоритм CatBoost: 
- на обучающей выборке - 6,1852,  
- на тестовой выборке - 6,06. 
Целевой уровень МАЕ <=6,8 достигнут.
  
**Гиперпараметры лучшей модели CatBoost: depth': 4, 'iterations': 1500, 'l2_leaf_reg': 1e-20, 'logging_level': 'Silent', 'loss_function': 'MAE', 'random_state': 290124.**
  
**ТОП-5 Параметров, оказавших наибольшее влияние на работу модели:**
- Время затраченное на нагрев - 24%
- Входая температура ковша - 21%
- Объем добавленной проволоки `wire_1` - 8%
- Объем добавленной проволоки `wire_2` - 7%
- Объем добавленных сыпучих материалов `bulk_6` - 6%

**ИТОГО:** чтобы наилучшим образом контролировать температуру ковша, нужно исходить из первичной температуры. Затраченное время на работу нагрева тесно связано с объемом добавленных материалов и имеет отрицательную корреляцию с финальной температурой.  
Чем выше будет качество изначально поданного сырья в ковш, тем меньше будут затраты производителя на электроэнергию и амортизацию.  
Предлагаю также рассмотреть введение на производстве коридора температур, колебания внутри которого будут считаться нормальными. В случае выхода  за пределы коридора оптимальных температур проводить тщательную проверку причин по каждому ковшу: где добыта руда, кем доставлена, какая смена работала, проверка исправности оборудования в период литья этого ковша и т.д. Таким образом можно будет выработать конкретные мероприятия, которые позволят сохранить ресурсы компании.


