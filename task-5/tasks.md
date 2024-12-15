## Оптимальное расписание. Конвейерная задача / Стратегия разделения процессоров

В задании часть вариантов представляют конвейерную задачу, другая задачу о разделении процессоров. Для каждой задачи необходимо: 
1. Выбрать алгоритм решения задачи и обосновать свой выбор.
2. Применить выбранный алгоритм, в решении отобразить ход выполнения алгоритма с подробными комментариями.
3. В ответе указать длительность полученного расписания.
4. В ответе вывести полученное расписание **в виде диаграммы Ганта**.

**Решение должно содержать номер варианта и подробное пошаговое описание.**


### Вариант 1:
Имеется 4 независимых задания и 2 исполнителя, исполнитель 1 с производительностью 6 и исполнитель 2 производительностью 4. Длительность заданий составляет 34, 26, 18, 12.

### Вариант 2:
Имеется 11 независимых заданий, каждое из которых состоит из двух последовательных этапов, и 2 исполнителя, исполнитель 1 выполняет только первый этап задания, исполнитель 2 - только второй. Длительность заданий (по этапам): (4, 3), (9, 12), (3, 2), (6, 5), (3, 6), (9, 8), (3, 5), (8, 7), (2, 2), (7, 8), (14, 15).

### Вариант 3:
Имеется 4 независимых задания и 2 исполнителя, исполнитель 1 с производительностью 10 и исполнитель 2 производительностью 6. Длительность заданий составляет 66, 40, 22, 16.

### Вариант 4:
Имеется 9 независимых заданий, каждое из которых состоит из двух последовательных этапов, и 2 исполнителя, исполнитель 1 выполняет только первый этап задания, исполнитель 2 - только второй. Длительность заданий (по этапам): (3, 2), (11, 10), (7, 6), (15, 16), (2, 1), (13, 14), (4, 8), (2, 2), (3, 4)

### Вариант 5:
Имеется 8 независимых заданий, каждое из которых состоит из двух последовательных этапов, и 2 исполнителя, исполнитель 1 выполняет только первый этап задания, исполнитель 2 - только второй. Длительность заданий (по этапам): (5, 7), (12, 13), (1, 1), (9, 8), (10, 11), (2, 5), (4, 3), (10, 9)

### Вариант 6:
Имеется 10 независимых заданий, каждое из которых состоит из двух последовательных этапов, и 2 исполнителя, исполнитель 1 выполняет только первый этап задания, исполнитель 2 - только второй. Длительность заданий (по этапам): (14, 15), (1, 1), (10, 9), (15, 18), (1, 4), (1, 5), (4, 3), (10, 9), (10, 9), (8, 12).

### Вариант 7:
Имеется 4 независимых задания и 2 исполнителя, исполнитель 1 с производительностью 6 и исполнитель 2 производительностью 2. Длительность заданий составляет 35, 22, 13, 10.

### Вариант 8:
Имеется 4 независимых задания и 2 исполнителя, исполнитель 1 с производительностью 4 и исполнитель 2 производительностью 2. Длительность заданий составляет 21, 14, 10, 9.

### Вариант 9:
Имеется 10 независимых заданий, каждое из которых состоит из двух последовательных этапов, и 2 исполнителя, исполнитель 1 выполняет только первый этап задания, исполнитель 2 - только второй. Длительность заданий (по этапам): (7, 6), (9, 8), (5, 4), (7, 8), (4, 4), (1, 5), (10, 9), (11, 12), (12, 15), (15, 18).

### Вариант 10:
Имеется 4 независимых задания и 2 исполнителя, исполнитель 1 с производительностью 6 и исполнитель 2 производительностью 2. Длительность заданий составляет 40, 28, 14, 14.

### Вариант 11:
Имеется 4 независимых задания и 2 исполнителя, исполнитель 1 с производительностью 7 и исполнитель 2 производительностью 3. Длительность заданий составляет 45, 19, 16, 10.