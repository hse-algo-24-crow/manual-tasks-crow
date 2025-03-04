# Задание №9
# Задача о максимальном потоке.

## Задание
Для каждого варианта представлены условия задачи, в соответствии с которыми необходимо: 
1. Построить сеть с указанием пропускной способности дуг.
2. Построить остаточную сеть.
3. Определить максимальный поток методом поиска увеличивающих путей в остаточной сети.
4. Проверить величину максимального потока через поиск минимальной пропускной способности разрезов сети, то есть рассчитать пропускную способность всех разрезов сети.
5. Оформить решение задачи по шагам с подробными комментариями, таблицами и диаграммами.
6. В ответе указать максимальную величину потока и как это поток можно организовать, то есть изобразить сеть с указанием соответствующих локальных потоков.

## Постановка задачи
1. Дана сеть (взвешенный ориентированный граф) с источником s и стоком t.
2. Для каждой дуги определена ее пропускная способность.
3. Необходимо найти максимальный поток для указанной сети. 

## Вариант №1

Пропускная способность дуг сети указана в таблице.

|          Дуги          | sa | sc | ac | ba | cb | bt | at |
|:----------------------:|:--:|:--:|:--:|:--:|:--:|----|----|
| Пропускная способность | 7  | 8  | 8  | 5  | 11 | 5  | 10 |

### Построим сеть с источником **s**, стоком **t** и указанными пропускными способностями дуг.

```mermaid
graph LR
    s-->|7|a
    s-->|8|c
    a-->|8|c
    b-->|5|a
    c-->|11|b
    b-->|5|t
    a-->|10|t
```

Построим остаточную сеть. Так как изначально поток в сети не задан, все дуги сети являются пустыми (локальный поток равен нулю), соответственно в остаточную сеть необходимо вынести обратную дугу с весом равным пропускной способности. 

```mermaid
graph RL
    a-.->|7|s
    c-.->|8|s
    c-.->|8|a
    a-.->|5|b
    b-.->|11|c
    t-.->|5|b
    t-.->|10|a
```

### Проведем поиск увеличивающего пути в остаточной сети
В остаточной сети найден увеличивающий путь t -> a -> b -> c -> s.

Вес дуг в пути:
- ta: 10
- ab: 5
- bc: 11
- cs: 8

Минимальный вес дуг на этом пути равен 5.

Уменьшим вес дуг на найденном пути.
Дуги, для которых вес стал нулевым, в данном случае ab, удалим из остаточной сети.  

```mermaid
graph RL
    a-.->|7|s
    s--->|5|c
    c-.->|3|s
    c-.->|8|a
    b--->|5|a
    c--->|5|b
    b-.->|6|c
    t-.->|5|b
    a--->|5|t
    t-.->|5|a
```

Скорректируем соответствующим образом локальные потоки в исходной сети. 
Первым числом будем указывать локальный поток, вторым пропускную способность дуги. 

```mermaid
graph LR
    s-->|"(0, 7)"|a
    s-->|"(5, 8)"|c
    a-->|"(0, 8)"|c
    b-->|"(5, 5)"|a
    c-->|"(5, 11)"|b
    b-->|"(0, 5)"|t
    a-->|"(5, 10)"|t
```

### Продолжим поиск увеличивающего пути в остаточной сети

```mermaid
graph RL
    a-.->|7|s
    s--->|5|c
    c-.->|3|s
    c-.->|8|a
    b--->|5|a
    c--->|5|b
    b-.->|6|c
    t-.->|5|b
    a--->|5|t
    t-.->|5|a
```

В остаточной сети найден увеличивающий путь t -> a -> s. 

Вес дуг в пути:
- ta: 5
- as: 7

Минимальный вес дуг на этом пути равен 5.

Уменьшим вес дуг на найденном пути.
Дуги, для которых вес стал нулевым, в данном случае ta, удалим из остаточной сети.

```mermaid
graph LR
    s--->|5|a
    a-.->|2|s
    s--->|5|c
    c-.->|3|s
    c-.->|8|a
    b--->|5|a
    c--->|5|b
    b-.->|6|c
    t-.->|5|b
    a--->|10|t
```

Скорректируем соответствующим образом локальные потоки в исходной сети.

```mermaid
graph LR
    s-->|"(5, 7)"|a
    s-->|"(5, 8)"|c
    a-->|"(0, 8)"|c
    b-->|"(5, 5)"|a
    c-->|"(5, 11)"|b
    b-->|"(0, 5)"|t
    a-->|"(10, 10)"|t
```

### Продолжим поиск увеличивающего пути в остаточной сети

```mermaid
graph LR
    s--->|5|a
    a-.->|2|s
    s--->|5|c
    c-.->|3|s
    c-.->|8|a
    b--->|5|a
    c--->|5|b
    b-.->|6|c
    t-.->|5|b
    a--->|10|t
```

В остаточной сети найден увеличивающий путь t -> b -> c -> s. 

Вес дуг в пути:
- tb: 5
- bc: 6
- cs: 3

Минимальный вес дуг на этом пути равен 3.

Уменьшим вес дуг на найденном пути.
Дуги, для которых вес стал нулевым, в данном случае cs, удалим из остаточной сети.

```mermaid
graph LR
    s--->|5|a
    a-.->|2|s
    s--->|8|c
    c-.->|8|a
    b--->|5|a
    c--->|8|b
    b-.->|3|c
    b--->|3|t
    t-.->|2|b
    a--->|10|t
```

Скорректируем соответствующим образом локальные потоки в исходной сети.

```mermaid
graph LR
    s-->|"(5, 7)"|a
    s-->|"(8, 8)"|c
    a-->|"(0, 8)"|c
    b-->|"(5, 5)"|a
    c-->|"(8, 11)"|b
    b-->|"(3, 5)"|t
    a-->|"(10, 10)"|t
```

### Продолжим поиск увеличивающего пути в остаточной сети

```mermaid
graph LR
    s--->|5|a
    a-.->|2|s
    s--->|8|c
    c-.->|8|a
    b--->|5|a
    c--->|8|b
    b-.->|3|c
    b--->|3|t
    t-.->|2|b
    a--->|10|t
```

В остаточной сети найден увеличивающий путь t -> b -> c -> a -> s. 

Вес дуг в пути:
- tb: 2
- bc: 3
- ca: 8
- as: 2

Минимальный вес дуг на этом пути равен 2.

Уменьшим вес дуг на найденном пути.
Дуги, для которых вес стал нулевым, в данном случае tb и as, удалим из остаточной сети.

```mermaid
graph LR
    s--->|7|a
    s--->|8|c
    a--->|2|c
    c-.->|6|a
    b--->|5|a
    c--->|10|b
    b-.->|1|c
    b--->|5|t
    a--->|10|t
```

Скорректируем соответствующим образом локальные потоки в исходной сети.

```mermaid
graph LR
    s-->|"(7, 7)"|a
    s-->|"(8, 8)"|c
    a-->|"(2, 8)"|c
    b-->|"(5, 5)"|a
    c-->|"(10, 11)"|b
    b-->|"(5, 5)"|t
    a-->|"(10, 10)"|t
```

### Продолжим поиск увеличивающего пути в остаточной сети
В остаточной сети не найдено увеличивающих путей, следовательно, алгоритм завершил работу.
Найденный поток величиной 15 является максимальным для данной сети.

### Проверим значение максимального потока перебором всех разрезов сети.
Разрез сети - разбиение множества всех узлов в сети на два непересекающихся подмножества V<sub>1</sub> и V<sub>2</sub>, причём во множество V<sub>1</sub> входит источник (s), а в V<sub>2</sub> входит сток (t).

Пропускная способность разреза - сумма пропускных способностей всех дуг, которые начинаются в вершинах из множества V<sub>1</sub> и оканчиваются в вершинах из V<sub>2</sub>.

Для сети из _n_ вершин существует 2<sup>n - 2</sup> различных разрезов, так как две вершины из множества (источник и сток) "зафиксированы" в V<sub>1</sub> и V<sub>2</sub>, остальные вершины можно различными способами распределять между множествами V<sub>1</sub> и V<sub>2</sub>.

Для сети из 5 вершин нужно найти 2<sup>5 - 2</sup> = 2<sup>3</sup> = 8 разрезов. 

| № | V<sub>1</sub>                   | V<sub>2</sub> | Пропускная способность разреза |
|---|:--------------------------------|:--------------|:------------------------------:|
| 1 | s                               | a, b, c, t    |           7 + 8 = 15           |
|   | **s + одна вершина из a, b, c** |               |                                |
| 2 | s, a                            | b, c, t       |         8 + 8 + 10 = 26        |
| 3 | s, b                            | a, c, t       |         8 + 7 + 5 + 5 = 25     |
| 4 | s, c                            | a, b, t       |         7 + 11 = 18            |
|   | **s + пара вершин из a, b, c**  |               |                                |
| 5 | s, a, b                         | c, t          |         8 + 8 + 10 + 5 = 31    |
| 6 | s, b, c                         | a, t          |         7 + 5 + 5 = 17         |
| 7 | s, a, c                         | b, t          |         10 + 11 = 21           |
|   | **s + три вершины из a, b, c**  |               |                                |
| 8 | s, a, b, c                      | t             |           10 + 5 = 15          |

Минимальная пропускная способность разреза равна 15 ( {s} / {t, a, b, c} ), что совпадает с найденной величиной максимального потока в сети.

### Ответ:
Максимальный поток в сети равен 15, он реализуется следующим локальными потоками:

```mermaid
graph LR
    s-->|"(7, 7)"|a
    s-->|"(8, 8)"|c
    a-->|"(2, 8)"|c
    b-->|"(5, 5)"|a
    c-->|"(10, 11)"|b
    b-->|"(5, 5)"|t
    a-->|"(10, 10)"|t
```