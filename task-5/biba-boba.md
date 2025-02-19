### Вариант 4:
Имеется 9 независимых заданий, каждое из которых состоит из двух последовательных этапов, и 2 исполнителя, исполнитель 1 выполняет только первый этап задания, исполнитель 2 - только второй. Длительность заданий (по этапам): (3, 2), (11, 10), (7, 6), (15, 16), (2, 1), (13, 14), (4, 8), (2, 2), (3, 4)  

## Решение

Изначально мы имеем вот такую таблицу работ:  
|  | A | B | C | D | E | F | G | H | I |
|--|---|---|---|---|---|---|---|---|---|
| Ⅰ |3 | 11 | 7 | 15 | 2 | 13 | 4 | 2 | 3 |
| ⅠⅠ | 2 | 10 | 6 | 16 | 1 | 14 | 8 | 2 | 4 |

**Шаг №1**  
Разобьем все работы на две группы:  
первая группа - где первый этап <= второй этап  
вторая группа - где первый этап > второй этап

Первая группа: D, F, G, H, I  
Вторая группа: A, B, C, E 

**Шаг №2**  
Отсортировать работы из первой группы по возрастанию времени первого этапа:
| Работа | 1 | 2 |
|--------|---|---|
| H | 2 | 2 |
| I | 3 | 4 |
| G | 4 | 8 |
| F | 13 | 14 |
| D | 15 | 16 |

**Шаг №3**  
Отсортировать работы из второй группы по убыванию времени второго этапа:
| Работа | 1 | 2 |
|--------|---|---|
| B | 11 | 10 |
| C | 7 | 6 |
| A | 3 | 2 |
| E | 2 | 1 |

**Шаг №4**  
Соединить две таблицы
|Работы| H | I | G | F | D | B | C | A | E |
|--|---|---|---|---|---|---|---|---|---|
| Ⅰ | 0-2  | 2-5 | 5-9 | 9-22 | 22-37 | 37-48 | 48-55 | 55-58 | 58-60 |
| ⅠⅠ | 2-4 | 5-9 | 9-17 | 22-36 | 37-53 | 53-63 | 63-69 | 69-71 | 71-72 |

### Ответ:  
![image](https://github.com/user-attachments/assets/75963b32-fc2c-408a-ba54-7a8aa0cbbac9)

