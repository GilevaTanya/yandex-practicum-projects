## *Модель рекомендации тарифа для оператора мобильной связи*

## *Стек:*  
Python, Pandas, Numpy,  matplotlib, SciPy.
  
## *Описание:*
Предоставлены данные о поведении клиентов, которые уже перешли на новые тарифы.  
Нужно построить модель для задачи классификации, которая выберет подходящий тариф. 

*Метрика качества *F1* не меньше 0.75.* 

**План выполнения проекта:**  
1.Открыть файл с данными и изучите его.
2.Разделите исходные данные на обучающую, валидационную и тестовую выборки.
3.Исследуйте качество разных моделей, меняя гиперпараметры.
4.Проверьте качество модели на тестовой выборке, достичь показателя accuracy не менее 0,75.
5.Проверьте модели на адекватность.

**Описание данных**

**сalls** — количество звонков  
**minutes** — суммарная длительность звонков в минутах  
**messages** — количество sms-сообщений  
**mb_used** — израсходованный интернет-трафик в Мб  
**is_ultra** — каким тарифом пользовался в течение месяца («Ультра» — 1, «Смарт» — 0) 

## **Вывод:**  

Из полученных данных, видно что пользователи "Ульта" пользуются связью на 20%-48% больше чем пользователи "Смарт", это касается всех направлений: количество звонков, продолжительность звонков, количество сообщений и объема израсходованного интернет-трафика в Мб. При этом пользователи "Ультра" составляют всего 31% от всего датафрейма. 

Так как перед нами стоит задача классификации, а именно построить модель которая предложит новый подходящий тариф для пользователя «Ультра» или «Смарт», построим  модели: дерево решений, случайный лес, логистическая регрессия.

При обучении, наилучшее качество показала модель `Случайный лес` Accuracy = 81%, при 10 деревьях с 9 ветвями. 
`Дерево решений` на втором месте, тоже с высоким Accuracy = 80%, количество ветвей -7.  
`Логистическая регрессия` показала наихудший результат Accuracy = 68%.

На тестовой выборке модель `Случайный лес` показала Accuracy -  89%

Модель `Случайный лес` показывает наилучшее качество, при том что задействовано всего 10 деревьев, что относительно немного, и не должно приводить к значительным временным издержкам.  
В связи с этим, для построения системы рекомендации для пользователей, которая будет предлагать переход на один из новых тарифов оператора мобильной связи «Мегалайн»: «Смарт» или «Ультра» - я предлагаю использовать модель `Случайный лес`.

*Оценка адекватности:* 
Среднее по таргету  и по `DummyClassifier` тестовой выборки дает результат - 0,70.  
Accuracy модели `Случайный лес` на тестовой выборке  дает результат - 0.89.  
Таким образом можно утверждать что обученная  модель `Случайный лес` предсказывает результат лучше чем  обычное усреднение на 19%.

