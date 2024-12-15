# Задача о распределении инвестиций между проектами

## Начальная матрица (Вариант 2):

| $   | A   | B   | С   | D   | 
|-----|-----|-----|-----|-----|
| 10  | 3   | 6   | 5   | 5   | 
| 20  | 9   | 7   | 9   | 10  | 
| 30  | 10  | 13  | 12  | 12  | 
| 40  | 15  | 15  | 15  | 15  | 
| 50  | 20  | 19  | 21  | 17  | 

Основной идеей решения является последовательное вычисление максимальной прибыли для двух проектов, их объединения в один и дальнейшее вычисление с прибылями последующих проектов. 

## Ход решения

### Шаг 1

Для первой пары AB максимизируем прибыль, то есть берем максимальную прибыль из двух возможных для первого значения инвестиций. Максимальное из 3(A) и 6(B) является 6. То есть распределение A0B1.

Для второго значения инвестиций есть несколько вариантов распределения. Представим их в таблице ниже.

| Пары     | "AB"       |
|--------  |------------|
| (02)     | 7          |
| (11)     | 3 + 6 = 9  |
| (20)     | 9          |

Из полученных пар необходимо выбрать ту, которая дает максимальную прибыль. Условимся, что при одинаковых значениях будем брать первое из возможных распределение. Таким образом, максимальную прибыль дает распределение A1B1.

Повторяем алгоритм для оставшихся значений инвестиций.

| $      | "AB"                                                                                                                                  | Max       |
|--------|---------------------------------------------------------------------------------------------------------------------------------------|-----------|
| 30     | (03) - **13**<br>(12) - 3 + 7 = **10**<br>(21) - 9 + 6 = **15**<br>(30) - **10**                                                      | 15 (A2B1) |
| 40     | (04) - **15**<br>(13) - 3 + 13 = **16**<br>(22) - 9 + 7 = **16**<br>(31) - 10 + 6 = **16**<br>(40) - **15**                           | 16 (A1B3) |
| 50     | (05) - **19**<br>(14) - 3 + 15 = **18**<br>(23) - 9 + 13 = **22**<br>(32) - 10 + 7 = **17**<br>(41) - 15 + 6 = **21**<br>(50) - **20**| 22 (A2B3) |

Таким образом, новый столбец "AB" выглядит следующим образом.

| $   | "AB" |       | 
|-----|------|-------|
| 10  | 6    | A0B1  | 
| 20  | 9    | A1B1  |
| 30  | 15   | A2B1  |
| 40  | 16   | A1B3  |
| 50  | 22   | A2B3  | 

### Шаг 2

Повторить алгоритм следует теперь для столбцов "AB" и C. В совокупности данные столбцы выглядят следующим образом. 

| $   | "AB" | C   | 
|-----|------|-----|
| 10  | 6    | 5   | 
| 20  | 9    | 9   |
| 30  | 15   | 12  |
| 40  | 16   | 15  |
| 50  | 22   | 21  | 

Проделаем аналогичную шагу 1 работу.

| $      | "ABC"                                                                                                                                 | Max        |
|--------|---------------------------------------------------------------------------------------------------------------------------------------|------------|
| 10     | (01) - **5**<br>(10) - **6**                                                                                                          | 6 (AB1C0)  |
| 20     | (02) - **9**<br>(11) - 6 + 5 = **11**<br>(20) - **9**                                                                                 | 11 (AB1C1) |
| 30     | (03) - **12**<br>(12) - 6 + 9 = **15**<br>(21) - 9 + 5 = **14**<br>(30) - **15**                                                      | 15 (AB1C2) |
| 40     | (04) - **15**<br>(13) - 6 + 12 = **18**<br>(22) - 9 + 9 = **18**<br>(31) - 15 + 5 = **20**<br>(40) - **16**                           | 20 (AB3C1) |
| 50     | (05) - **21**<br>(14) - 6 + 15 = **21**<br>(23) - 9 + 12 = **21**<br>(32) - 15 + 9 = **24**<br>(41) - 16 + 5 = **21**<br>(50) - **22**| 24 (AB3C2) |

### Шаг 3

Повторить алгоритм следует теперь для столбцов "ABC" и D. В совокупности данные столбцы выглядят следующим образом. 

| $   | "ABC" | D   | 
|-----|-------|-----|
| 10  | 6     | 5   | 
| 20  | 11    | 10  |
| 30  | 15    | 12  |
| 40  | 20    | 15  |
| 50  | 24    | 17  | 

Проделаем аналогичную шагу 2 работу.

| $      | "ABCD"                                                                                                                                   | Max         |
|--------|------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| 10     | (01) - **5**<br>(10) - **6**                                                                                                             | 6 (ABС1D0)  |
| 20     | (02) - **10**<br>(11) - 6 + 5 = **11**<br>(20) - **11**                                                                                  | 11 (ABC1D1) |
| 30     | (03) - **12**<br>(12) - 6 + 10 = **16**<br>(21) - 11 + 5 = **16**<br>(30) - **15**                                                       | 16 (ABС1D2) |
| 40     | (04) - **15**<br>(13) - 6 + 12 = **18**<br>(22) - 11 + 10 = **21**<br>(31) - 15 + 5 = **20**<br>(40) - **20**                            | 21 (ABC2D2) |
| 50     | (05) - **17**<br>(14) - 6 + 15 = **21**<br>(23) - 11 + 12 = **23**<br>(32) - 15 + 10 = **25**<br>(41) - 20 + 5 = **25**<br>(50) - **24** | 25 (ABC3D2) |

### Шаг 4

Таким образом, получаем, что максимальная прибыль составит 25. В этом случае распределение по проектам:

* **ABC3D2** - вкладываем 2 части в проект D, возвращаемся к строке 3 таблицы "ABC";
* **AB1C2** - вкладываем 2 части в проект C, возвращаемся к строке 1 таблицы "AB";
* **A0B1** - вкладываем 1 часть в проект B.

### Ответ 
Максимальная прибыль: 25.
Распределение инвестиций: A - 0, B - 10, C - 20, D - 20.
