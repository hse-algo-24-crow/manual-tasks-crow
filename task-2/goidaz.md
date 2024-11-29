# Вариант 3 команда GOIDAZ

## Условие

Дана трехдиагональная матрица порядка n = 8:

$$
A =
\begin{pmatrix}
6 & 2 & 0 & \cdots & 0 & 0\\
4 & 6 & 2 & \cdots & 0 & 0\\
0 & 4 & 6 & \cdots & 0 & 0\\
\vdots & \vdots & \vdots & \ddots & \vdots & \vdots\\
0 & 0 & 0 & \cdots & 6 & 2\\
0 & 0 & 0 & \cdots & 4 & 6\\
\end{pmatrix}
$$

## 1. Найдем рекурентное соотношение

Для ленточной матрицы определитель выражается через определители меньшего порядка:

$$
x_n = 6 \cdot x_{n-1} - 8 \cdot x_{n-2}
$$

## 2. Составим и решим характеристическое уравнение

Характеристическое уравнение:

$$
\lambda^n = 6 \cdot \lambda^{n-1} - 8 \cdot \lambda^{n-2}
$$

Квадратное уравнение:

$$
\lambda^2 - 6\lambda + 8 = 0
$$

Решение уравнения:

$$
\lambda_1 = 4; \quad \lambda_2 = 2
$$

## 3. Выведем формулу общего решения

Общее решение:

$$
x_n = a \cdot 4^n + b \cdot 2^n
$$


Система уравнений:

$$
2a + b = 3
$$

$$
8a + 2b = 14
$$

Решение системы:

- a = 2
- b = -1

Таким образом, частное решение:

$$
x_n = 2 \cdot 4^n - 1 \cdot 2^n
$$

## 4. Найдем определитель матрицы порядка 8

Вычисляем:

$$
x_8 = 2 \cdot 4^8 - 1 \cdot 2^8
$$

- 4^8 = 65536
- 2^8 = 256

Итак, определитель:

$$
x_8 = 2 \cdot 65536 - 256 = 131072 - 256 = 130816
$$

**Ответ:** 130816