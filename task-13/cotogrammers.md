# Задание 13. Вариант 6 #

## Условие задачи ##

|   **Вещи**  |  **A**  |  **B**  |  **C**  |  **D**  |  **E**  |  **F**  |  **G**  |
|-------------|:-------:|:-------:|:-------:|:-------:|:-------:|:-------:|:-------:|
|   **Вес**   |    3    |    5    |    7    |    4    |    2    |    6    |    1    |
|**Стоимость**|    10   |    15   |    20   |    12   |    8    |    18   |    5    |

Вместимость рюкзака V = 20.

Численность популяции N = 4 особи.

Для скрещивания выбираются сильнейшие, скрещивание - одноточечное.

Стратегия применения оператора мутации:
- если дети идентичны родителям;
- если фитнес-функция равна 0;
- мутации проводятся по любым генам, чтобы исключить ситуации, описанные в пунктах выше.

Как только сформируется 4 поколение, алгоритм завершается.

## Решение ##

### 1. Создадим 1 поколение. ###

Пусть

|    **x<sub>i</sub>**    | **f(x<sub>i</sub>)** | **Вес** |
|:-----------------------:|:--------------------:|:-------:|
|x<sub>1</sub> = (1010101)|          43          |    13   |
|x<sub>2</sub> = (0110010)|          53          |    18   |
|x<sub>3</sub> = (1100110)|          51          |    16   |
|x<sub>4</sub> = (1001110)|          48          |    15   |

Сильнейшие особи x<sub>2</sub> и x<sub>3</sub> - родители.

|  **Родители**  |     |     |     |     |     |     |     | **f(x<sub>i</sub>)** | **Вес** |
|:--------------:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:--------------------:|:-------:|
|  x<sub>2</sub> |**0**|**1**|**1**|  0  |  0  |  1  |  0  |                      |         |
|  x<sub>3</sub> |  1  |  1  |  0  |**0**|**1**|**1**|**0**|                      |         |
|    **Дети**    |     |     |     |     |     |     |     |                      |         |
|  x<sub>5</sub> |**0**|**1**|**1**|**0**|**1**|**1**|**0**|          61          |   20    |
|  x<sub>6</sub> |  1  |  1  |  0  |  0  |  0  |  1  |  0  |          43          |   14    |

Поводов для мутаций не обнаружено

### 2. Создадим 2 поколение. ###

|    **x<sub>i</sub>**    | **f(x<sub>i</sub>)** | **Вес** |
|:-----------------------:|:--------------------:|:-------:|
|x<sub>2</sub> = (0110010)|          53          |    18   |
|x<sub>3</sub> = (1100110)|          51          |    16   |
|x<sub>5</sub> = (0110110)|          61          |    20   |
|x<sub>6</sub> = (0110110)|          43          |    14   |

Сильнейшие особи x<sub>2</sub> и x<sub>5</sub> - родители.

|  **Родители**  |     |     |     |     |     |     |     | **f(x<sub>i</sub>)** | **Вес** |
|:--------------:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:--------------------:|:-------:|
|  x<sub>2</sub> |**0**|**1**|**1**|**0**|  0  |  1  |  0  |                      |         |
|  x<sub>5</sub> |  0  |  1  |  1  |  0  |**1**|**1**|**0**|                      |         |
|    **Дети**    |     |     |     |     |     |     |     |                      |         |
|  x<sub>7</sub> |**0**|**1**|**1**|**0**|**1**|**1**|**0**|          61          |   20    |
|  x<sub>8</sub> |  0  |  1  |  1  |  0  |  0  |  1  |  0  |          53          |   18    |

x<sub>7</sub> и x<sub>8</sub> - полученные особи совпадают с родительскими => мутация

|    **x<sub>i</sub>**    | **f(x<sub>i</sub>)** | **Вес** |
|:-----------------------:|:--------------------:|:-------:|
|x<sub>7</sub> = (0110100)|          43          |    14   |
|x<sub>8</sub> = (0010010)|          38          |    13   |

### 3. Создадим 3 поколение. ###

|    **x<sub>i</sub>**    | **f(x<sub>i</sub>)** | **Вес** |
|:-----------------------:|:--------------------:|:-------:|
|x<sub>2</sub> = (0110010)|          53          |    18   |
|x<sub>5</sub> = (0110110)|          61          |    20   |
|x<sub>7</sub> = (0110100)|          43          |    14   |
|x<sub>8</sub> = (0010010)|          38          |    13   |

Сильнейшие особи x<sub>2</sub> и x<sub>5</sub> - родители.

|  **Родители**  |     |     |     |     |     |     |     | **f(x<sub>i</sub>)** | **Вес** |
|:--------------:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:--------------------:|:-------:|
|  x<sub>2</sub> |**0**|**1**|**1**|**0**|**0**|  1  |  0  |                      |         |
|  x<sub>5</sub> |  0  |  1  |  1  |  0  |  1  |**1**|**0**|                      |         |
|    **Дети**    |     |     |     |     |     |     |     |                      |         |
|  x<sub>9</sub> |**0**|**1**|**1**|**0**|**0**|**1**|**0**|          61          |   20    |
|  x<sub>10</sub>|  0  |  1  |  1  |  0  |  1  |  1  |  0  |          53          |   18    |

x<sub>9</sub> и x<sub>10</sub> - полученные особи совпадают с родительскими => мутация

|    **x<sub>i</sub>**    | **f(x<sub>i</sub>)** | **Вес** |
|:-----------------------:|:--------------------:|:-------:|
|x<sub>9</sub> = (0111100)|          55          |    18   |
|x<sub>10</sub>= (1010010)|          48          |    16   |

### 4. Создадим 4 поколение. ###

|    **x<sub>i</sub>**    | **f(x<sub>i</sub>)** | **Вес** |
|:-----------------------:|:--------------------:|:-------:|
|x<sub>2</sub> = (0110010)|          53          |    18   |
|x<sub>5</sub> = (0110110)|          61          |    20   |
|x<sub>9</sub> = (0110100)|          55          |    18   |
|x<sub>10</sub>= (0010010)|          48          |    16   |

Лидер поколения - x<sub>5</sub> = (0110110)

## Ответ: ##

Максимальная найденная стоимость рюкзака: 61
Занятое место: 20
Пустое место: 0
Кодировка предметов в рюкзаке: 0110110
Предметы в рюкзаке: B, C, E, F.