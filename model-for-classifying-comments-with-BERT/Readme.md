# *Модель классификации комментариев на позитивные и негативные с BERT*

## *Стек:*  
Python, Pandas, BERT,  nltk, scikit-learn,  tf-idf.
  
## *Описание:*
Интернет-магазин  запускает новый сервис. Теперь пользователи могут редактировать и дополнять описания товаров, как в вики-сообществах. То есть клиенты предлагают свои правки и комментируют изменения других. Магазину нужен инструмент, который будет искать токсичные комментарии и отправлять их на модерацию. 

Нужно обучить модель классифицировать комментарии на позитивные и негативные. В распоряжении есть набор данных с разметкой о токсичности правок.
Метрика качества *F1* не меньше 0.75. 

**План выполнения проекта:**  
1. Загрузите и подготовьте данные.
2. Обучите разные модели. Целевая метрика *F1* не меньше 0.75.
3. Сделайте выводы.

**Описание данных**  
*text* содержит текст комментария
*toxic* — целевой признак.


## **ВЫВОД:**  
- Объем строк датафрейма 159 292.
- Дубликатов и пропусков нет.
- Дисбаланс классов - 90%(0)/10%(1)
- Проведена лемматицация теста в столбце text в столбец lemm_text.
- Слова векторизированы через TfidfVectorizer, удалены стоп слова.
- Выборка разделена на обучающую, валидационнную и тестовую в соотношении: 60/20/20. 
- Для модели BERT, данные были урезаны до 1000 строк, для экономии времени обучения.

По итогу обучения наилучший результат и целевой показатель при валидации достигла только модель LogisticRegression: F1- мера - 0,7539.
При тестировании модель LogisticRegression: F1- мера - 0,7606. Поставленная задача проекта выполнена.


