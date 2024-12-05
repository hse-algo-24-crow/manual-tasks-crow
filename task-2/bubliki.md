# Задание №2. Вариант 1
## Вычисление ленточного определителя (трехдиагональной матрицы)
Для выполнения задания необходимо по условиям, указанным для команды в файле task-2/tasks.md:
1. Вывести рекуррентное соотношение для предложенной матрицы.
2. Составить и решить характеристическое уравнение.
3. Вывести формулу общего решения.
4. Рассчитать на основе полученной формулы значение определителя матрицы заданного порядка.

## Условие

Дана трехдиагональная матрица:

$$
A =
\begin{pmatrix}
4 & 3 & 0 & \cdots & 0 & 0\\
-4 & 4 & 3 & \cdots & 0 & 0\\
0 & -4 & 4 & \cdots & 0 & 0\\
\vdots & \vdots & \vdots & \ddots & \vdots & \vdots\\
0 & 0 & 0 & \cdots & 4 & 3\\
0 & 0 & 0 & \cdots & -4 & 4\\
\end{pmatrix}
$$

## 1. Найдем рекуррентное соотношение

Чтобы найти определитель ленточной матрицы, выразим его через определители меньшего порядка. Сделаем это путём удаление первой строки, первого столбца; первой строки, второго столбца.

$$
A =
\begin{pmatrix}
4 & 3 & 0 & \cdots & 0 & 0\\
-4 & 4 & 3 & \cdots & 0 & 0\\
0 & -4 & 4 & \cdots & 0 & 0\\
\vdots & \vdots & \vdots & \ddots & \vdots & \vdots\\
0 & 0 & 0 & \cdots & 4 & 3\\
0 & 0 & 0 & \cdots & -4 & 4\\
\end{pmatrix} =
4 * \begin{pmatrix}
4 & 3 & \cdots & 0 & 0\\
-4 & 4 & \cdots & 0 & 0\\
\vdots & \vdots & \ddots & \vdots & \vdots\\
0 & 0 & \cdots & 4 & 3\\
0 & 0 & \cdots & -4 & 4\\
\end{pmatrix} - 3 * \begin{pmatrix}
-4 & 3 & \cdots & 0 & 0\\
0 & 4 & \cdots & 0 & 0\\
\vdots & \vdots & \ddots & \vdots & \vdots\\
0 & 0 & \cdots & 4 & 3\\
0 & 0 & \cdots & -4 & 4\\
\end{pmatrix}
$$

Уже из матрицы порядка n - 1 также удалим первую строку, первый столбец для получения однородного рекуррентного соотношения:

$$
B =
-4 * \begin{pmatrix}
4 & \cdots & 0 & 0\\
\vdots & \ddots & \vdots & \vdots\\
0 & \cdots & 4 & 3\\
0 & \cdots & -4 & 4\\
\end{pmatrix}
$$

По итогу, однородное реккурентное соотношение имеет вид:

$$
x_n = 4 \cdot x_{n-1} + 3 * 4 \cdot x_{n-2} = 4 \cdot x_{n-1} + 12 \cdot x_{n-2} 
$$

## 2. Составим и решим характеристическое уравнение

Характеристическое уравнение:

$$
\lambda^n = 4 \cdot \lambda^{n-1} + 12 \cdot \lambda^{n-2}
$$

Чтобы решить характеристическое уравнение, решим квадратное уравнение:

$$
\lambda^2 - 4\lambda - 12 = 0
$$

По теореме Виета:

$$
\lambda_1 = 6; 
\lambda_2 = -2
$$

## 3. Выведем формулу общего решения

Общее решение:

$$
x_n = a \cdot 6^n + b \cdot (-2)^n
$$

Подставим в решение начальные условия и решим систему уравнений:

- x1 = 4 
- x2 = 28 

$$
6a - 2b = 4
$$
$$
36a + 4b = 28
$$

Выразим b, приравняем и найдём коэффициенты a и b:

$$
3a - b = 2
$$
$$
9a + b = 7
$$

$$
3a - b = 9a + b
$$

Получим:

- a = 0.75 
- b = 0.25

$$
x_n = 0.75 \cdot 6^n + 0.25 \cdot (-2)^n
$$

## 4. Найдем определитель матрицы порядка 9

Для начала проверим правильность выведенного уравнения

$$
С = 
\begin{pmatrix}
4 & 3 & 0\\
-4 & 4 & 3\\
0 & -4 & 4\\ 
\end{pmatrix}  
$$

$$
С = 4^3 - 2*((-4) * 4 * 3) = 160
$$

$$
x_3 = 0.75 \cdot 6^3 + 0.25 \cdot (-2)^3 = 162 - 2 = 160
$$

Так как результаты совпали, можем с уверенностью считать определитель 9 порядка

$$
x_9 = 0.75 \cdot 6^9 + 0.25 \cdot (-2)^9 = 7558272 - 128 = 7558144
$$

**Ответ:** 7558144