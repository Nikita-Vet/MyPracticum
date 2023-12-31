**Отток клиентов**

Из «Бета-Банка» стали уходить клиенты. Каждый месяц. Немного, но заметно. Банковские маркетологи посчитали: сохранять текущих клиентов дешевле, чем привлекать новых.

**Цель:**

Спрогнозировать, уйдёт клиент из банка в ближайшее время или нет

**Выводы проекта:**

На этапе предобработки данных обнаружены пропуски в колонке Tenure. Произведена замена пропусков на медианное значение. Удалены колонки RowNumber, Surname и CustomerId.

В первоначальные данных наблюдался значительный дисбаланс (80% ответов целевого признака были негативными и только 20% позитивными). Все модели на первоначальных данных характеризовались высокой степенью ложноотрицательных прогнозов и низким качеством взвешенной величины (F1).

Устранен дисбаланс классов двумя методами upsampling и downsampling.

Самое высокие показатели качества достигаются на модели случайный лес **grid_model_rforest.best_estimator_**. На тестовой выборке модель случайного леса, обученная на данных с увеличенным миноритарным классом, дает показатель метрику F1 равный **0.6028**. У нее относительно низкое количество ложноотрицательных прогнозов и высокое положительных и ложноположительных. К сожалению свойства такой модели будут приводить к повышенным издержкам за счет дополнительных трат на лояльных клиентов, зато будет способствовать решению бизнес задачи: выявлять клиентов готовых уйти, что позволит предпринять в отношении их удерживающие мероприятия.

**Стек:**

pandas, numpy, math, matplotlib, pyplot, scipy, seaborn, sklearn, time
