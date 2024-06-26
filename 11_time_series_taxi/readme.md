#  Прогнозирование заказов такси

## Цели работы:
Для компании-такси на основе предоставленных заказчиком данных сделать модель машинного обучения которая предсказывает количество заказов такси в следующий час. Значение метрики rmse не должно превышать 48

## Этапы работы:
* загрузить данные и выполнить ресемплирование по одному часу
* изучить данные
* обучить модели с разными гиперпараметрами
* проверить лучшую модель на тестовой выборка(размер тестовой выборки 10% от общих данных)
* подготовить выводы

## Выводы:

Мы обучили и проверили модель машинного обучения которая предсказывает количество заказов такси в следующий час. Значение метрики rmse не превышает 48. В ходе работы мы:

* провели ресемплирование заказов по одному часу
* изучили данные, обнаружили сезонность
* создали дополнительные признаки (час в дне, день в неделе, день в месяце, месяц в году, значения прошлых 168 часов)
* обучили модели с разными гиперпараметрами
* проверили лучшую модель на тестовой выборке(размер тестовой выборки 10% от общих данных)

Все модели показали достаточно близкие результаты. Самую большую рост эффективности для предсказаний мы получили не подбором моделей и их гиперпараметров, а ручным созданием признаков. Если нам важна интерпретируемось то мы можем слегка пожертвовать качеством у пользу интерпретируемости, например выбрав модель решающего дерева или линейной регрессии которые показали неплохие результаты.

Наилучшие результаты мы получили с помощью модели CatBoost, проверили на тестовой выборке что
* результат соотествует заданию, rmse 44.98 на тестовой выборке для CatBoostRegressor(loss_function="RMSE", iterations=250, depth=3), Learning rate 0.149255
* модель прошла проверку на адекватность
* графики ихсодного и предсказанного рядов довольно похожи
