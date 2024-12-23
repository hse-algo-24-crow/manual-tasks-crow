## Вариант 2
Условие: указана трехдиагональная матрица порядка n. Для решения задачи требуется:
1.	Вывести рекуррентное соотношение для предложенной матрицы.
2.	Составить и решить характеристическое уравнение.
3.	Вывести формулу общего решения.
4.	Рассчитать на основе полученной формулы значение определителя матрицы порядка n.
   

**1. Найдем рекурентное соотношение**

$$\begin{vmatrix}
12 & 1 & 0 & ⋯ & 0 & 0\\
20 & 12 & 1 & ⋯ & 0 & 0\\
0 & 20 & 12 & ⋯ & 0 & 0\\
⋮ & ⋮ & ⋮ & ⋱ & ⋮ & ⋮\\
0 & 0 & 0 & ⋯ & 12 & 1\\
0 & 0 & 0 & ⋯ & 20 & 12\\
\end{vmatrix} = 
12 * \begin{vmatrix}
12 & 1 & ⋯ & 0 & 0\\
20 & 12 & ⋯ & 0 & 0\\
⋮ & ⋮ & ⋱ & ⋮ & ⋮\\
0 & 0 & ⋯ & 12 & 1\\
0 & 0 & ⋯ & 20 & 12\\
\end{vmatrix} - 1 * \begin{vmatrix}
20 & 1 & ⋯ & 0 & 0\\
0 & 12 & ⋯ & 0 & 0\\
⋮ & ⋮ & ⋱ & ⋮ & ⋮\\
0 & 0 & ⋯ & 12 & 1\\
0 & 0 & ⋯ & 20 & 12\\
\end{vmatrix} = $$
$$ = 12*x_{n-1} - 1 * \Biggl(20 * \begin{vmatrix}
12 & ⋯ & 0 & 0\\
⋮ & ⋱ & ⋮ & ⋮\\
0 & ⋯ & 12 & 1\\
0 & ⋯ & 20 & 12\\
\end{vmatrix} - 1 * \begin{vmatrix}
0 & ⋯ & 0 & 0\\
⋮ & ⋱ & ⋮ & ⋮\\
0 & ⋯ & 12 & 1\\
0 & ⋯ & 20 & 12\\
\end{vmatrix}\Biggl) = 12 * x_{n-1} - 20 * x_{n-2}$$ 

**2. Составим и решим характеристическое уравнение**

$$ λ^n = 12 * λ ^ {n-1} - 20 λ^{n-2}$$
$$ λ^2 - 12 * λ + 20 = 0$$

По т. Виета: 

$$ λ_1 = 10; λ_2 = 2 $$

**3. Выведем формулу общего решения**  

Формула общего решения:

>$$ x_n = a * 10^n + b * 2^n$$

$$ x_1 = \begin{vmatrix}
12\\
\end{vmatrix} = 12$$
$$ x_2 = \begin{vmatrix}
12 & 1\\
20 & 12\\
\end{vmatrix} = 144 - 20 = 124$$

Учитывая, что 

$$ x_n = a * 10^n + b * 2 ^ n $$

То 

$$x_1 = a * 10 + b * 2$$
$$x_2 = a * 100 + b * 4 $$

В итоге:
```math
\left\{
\begin{aligned}
    12 = 10 * a + 2 * b, \\
    124 = 100 * a + 4 * b.
\end{aligned}
\right. \to
\left\{
\begin{aligned}
    6 = 5 * a + b, \\
    31 = 25 * a + b.
\end{aligned}
\right. \to
\left\{
\begin{aligned}
    b = 6 - 5 * a, \\
    b = 31 - 25 * a.
\end{aligned}
\right.
```

$$ 6 - 5 * a = 31 - 25 * a $$
$$ 20 * a = 25$$
$$ a = 1.25$$
$$ b = 6 - 5 * 1.25 = -0.25$$

Формула частного решения:

>$$ x_n = 1.25 * 10^n - 0.25 * 2^n$$

**4. Найдем определитель матрицы порядка 10**

Но перед этим выполним небольшую проверку:

$$x_3 = 1.25 * 10^3 - 0.25 * 2^3 = 1250 - 2 = 1248$$
$$ x_3 = \begin{vmatrix}
12 & 1 & 0\\
20 & 12 & 1\\
0 & 20 & 12\\
\end{vmatrix} = 12^3 - 2 * 12 * 20 = 1728 - 480 = 1248$$

Как мы видим, результат сошелся.

Определитель для всей матрицы:
$$x_{10} = 1.25 * 10^{10} - 0.25 * 2^{10} = 125 * 10^8 - 2^8 = 12499999744$$

**Ответ:** 12499999744
