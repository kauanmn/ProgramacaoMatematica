# Lista 4 - Simplex base não disponível e Simplex revisado

**Universidade Federal do ABC**<br>
Prof.ª Geiza Cristina da Silva<br>
Programação Matemática


<br>

### Lista de conteúdos

- [Exercício 1](#exercício-1)
    - [Exercício 1A](#exercício-1a) (incompleto)
    - [Exercício 1B](#exercício-1b) (incompleto)
- [Exercício 2](#exercício-2)
- [Exercício 3](#exercício-3) (incompleto)
- [Exercício 4](#exercício-4)
    - [Exercício 4A](#exercício-4a)
    - [Exercício 4B](#exercício-4b) (incompleto)
    - [Exercício 4C](#exercício-4c) (incompleto)
    - [Exercício 4D](#exercício-4d) (incompleto)
- [Exercício 5](#exercício-5)
    - [Exercício 5A](#exercício-5a)
    - [Exercício 5B](#exercício-5b) (incompleto)
- [Exercício 6](#exercício-6)
    - [Exercício 6A](#exercício-6a) (incompleto)
    - [Exercício 6B](#exercício-6b) (incompleto)
    - [Exercício 6C](#exercício-6c) (incompleto)
    - [Exercício 6D](#exercício-6d) (incompleto)

<br>

# Exercício 1

Considere o PPL da dieta abaixo:

|                  | Feijão | Ervilha | Lentilha | Soja | Trigo | Milho | Mínimo |
|------------------|--------|---------|----------|------|-------|-------|--------|
| Vitaminas        | 2      | 2       | 4        | 0    | 6     | 0     | 20     |
| Proteínas        | 10     | 0       | 5        | 4    | 2     | 2     | 30     |
| Minerais         | 4      | 0       | 2        | 0    | 4     | 4     | 40     |
| Custos Unitários | 6      | 1       | 5        | 1    | 4     | 1     |        |

Sabendo que o custo mínimo com alimentação para satisfazer às necessidades de nutrientes é atingido quando se consome apenas ervilha, soja e milho.

<br>

## Exercício 1A

Determine as quantidades a serem consumidas destes três alimentos.

<br>

### Solução

SOLUÇÃO

<br>

## Exercício 1B

É possível obter outra dieta de custo mínimo? Se for, com quais alimentos e em que quantidade?

<br>

### Solução

SOLUÇÃO

---

<br>
<br>

# Exercício 2

Mostre como o método Big-M vai indicar que o problema a seguir não tem nenhuma solução viável.

```math
    \text{max } z = 2x_1 + 5x_2
```

Sujeito a:

```math
\displaylines{
    3x_1 + 2x_2 \ge 6 \\
    2x_1 + x_2 \le 2 \\
    x_1, x_2 \ge 0
}
```

<br>

## Solução

Forma padrão

```math
-\text{min } -z = -2x_1 - 5x_2 + Mx_a
```

Sujeito a:

```math
\displaylines{
    3x_1 + 2x_2 - x_3 + x_a = 6 \\
    2x_1 + x_2 + x_4 = 2 \\
    x_1,x_2,x_3,x_4,x_a \ge 0
}
```

<br>

**QUADRO INICIAL**

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_a$ | $b$ |
|-------|-------|-------|-------|-------|-------|-----|
| $z$   | -2    | -5    | 0     | 0     | 10    | 0   |
| $x_a$ | 3     | 2     | -1    | 0     | 1     | 6   |
| $x_4$ | 2     | 1     | 0     | 1     | 0     | 2   |

<br>

- $x_2$ entra
- $x_4$ sai $(2/2 = 1)$

<br>

- $L_3 \leftarrow L_3$
- $L_2 \leftarrow L_2 - 2L_3$
- $L_1 \leftarrow L_1 + 5L_3$

<br>

**ITERAÇÃO 1**

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_a$ | $b$ |
|-------|-------|-------|-------|-------|-------|-----|
| $z$   | 8     | 0     | 0     | 5     | 10    | 10  |
| $x_a$ | -1    | 0     | -1    | -2    | 1     | 2   |
| $x_a$ | 2     | 1     | 0     | 1     | 0     | 2   |

<br>

Como não há mais variáveis com coeficientes negativos na linha da FO, então o algoritmo termina por aqui. No entanto, a solução ótima contém a variável artificial, o que não é possível. Este fato indica a inviabilidade do problema.

---

<br>
<br>

# Exercício 3

Mostre como o método das duas fases vai indicar que o problema a seguir não tem nenhuma solução viável:

```math
    \text{max } z = 2x_1 + 5x_2
```

Sujeito a:

```math
\displaylines{
    3x_1 + 2x_2 \ge 6 \\
    2x_1 + x_2 \le 2 \\
    x_1, x_2 \ge 0
}
```

<br>

## Solução

SOLUÇÃO

---

<br>
<br>

# Exercício 4

Resolva os seguintes problemas de PL. Em cada caso, caracterize o PPL original como inviável, ilimitado, degenerado, possui uma solução ótima ou múltiplas soluções ótimas. Quando for os dois últimos casos, explicite a solução.

<br>

## Exercício 4A

```math
\text{max } z = 3x_1 + 2x_2 + 3x_3
```

Sujeito a:

```math
\displaylines{
    2x_1 + x_2 + x_3 \ge 2 \\
    x_1 + 3x_2 + x_3 \le 6 \\
    3x_1 + 4x_2 + 2x_3 \le 8 \\
    x_1,x_2,x_3 \ge 0
}
```

<br>

### Solução

**FORMA PADRÃO (Big-M)**

```math
-\text{min } -z = -3x_1 - 2x_2 - 3x_3 + Mx_7 (M = 10)
```

Sujeito a:

```math
\displaylines{
    2x_1 + x_2 + x_3 - x_4 + x_7 = 2 \\
    x_1 + 3x_2 + x_3 + x_5 = 6 \\
    3x_1 + 4x_2 + 2x_3 + x_6 = 8 \\
    x_1,x_2,x_3,x_4,x_5,x_6 \ge 0
}
```

<br>

**QUADRO INICIAL**

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $x_6$ | $x_7$ | $b$ |
|-------|-------|-------|-------|-------|-------|-------|-------|-----|
| $z$   | -3    | -2    | -3    | 0     | 0     | 0     | 10    | 0   |
| $x_5$ | 1     | 3     | 1     | 0     | 1     | 0     | 0     | 6   |
| $x_6$ | 3     | 4     | 2     | 0     | 0     | 1     | 0     | 8   |
| $x_7$ | 2     | 1     | 1     | -1    | 0     | 0     | 1     | 2   |

<br>

#### ZERAR A VARIÁVEL ARTIFICIAL

$L_1 \leftarrow L_1 - 10L_4$

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $x_6$ | $x_7$ | $b$ |
|-------|-------|-------|-------|-------|-------|-------|-------|-----|
| $z$   | -23   | -12   | -13   | 10    | 0     | 0     | 0     | -20 |
| $x_5$ | 1     | 3     | 1     | 0     | 1     | 0     | 0     | 6   |
| $x_6$ | 3     | 4     | 2     | 0     | 0     | 1     | 0     | 8   |
| $x_7$ | 2     | 1     | 1     | -1    | 0     | 0     | 1     | 2   |

<br>

#### ITERAÇÃO 1

**PASSO 1.2**

Como há coeficientes negativos na linha da função objetivo, então a solução não é ótima.

<br>

**PASSO 1.3**

Variável que vai entrar: $x_1$

<br>

**PASSO 1.4**

Variável que vai sair: $\text{min } \\{ 6/1, 8/3, 2/2 \\} \rightarrow x_7$

<br>

**PASSO 1.5**

- $L_4 \leftarrow L_4/2$
- $L_1 \leftarrow L_1 + 23L_4$
- $L_2 \leftarrow L_2 - L_4$
- $L_3 \leftarrow L_3 - 3L_4$

<br>

**QUADRO**

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $x_6$ | $x_7$ | $b$ |
|-------|-------|-------|-------|-------|-------|-------|-------|-----|
| $z$   | 0     | -1/2  | -3/2  | -3/2  | 0     | 0     | 0     | 3   |
| $x_5$ | 0     | 5/2   | 1/2   | 1/2   | 1     | 0     | -1/2  | 5   |
| $x_6$ | 0     | 5/2   | 1/2   | 3/2   | 0     | 1     | -3/2  | 5   |
| $x_1$ | 1     | 1/2   | 1/2   | -1/2  | 0     | 0     | 1/2   | 1   |

<br>

#### ITERAÇÃO 2

**PASSO 2.2**

Como há coeficientes negativos na linha da função objetivo, então a solução não é ótima.

<br>

**PASSO 2.3**

Variável que vai entrar: $x_4$

<br>

**PASSO 2.4**

Variável que vai sair: $\text{min } \\{ 5/(1/2), 5/(3/2) \\} \rightarrow x_6$

<br>

**PASSO 2.5**

- $L_3 \leftarrow 2/3L_3$
- $L_1 \leftarrow L_1 + 3/2 L_3$
- $L_2 \leftarrow L_2 - 1/2 L_3$
- $L_4 \leftarrow L_4 + 1/2 L_3$

<br>

**QUADRO**

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $x_6$ | $x_7$ | $b$  |
|-------|-------|-------|-------|-------|-------|-------|-------|------|
| $z$   | 0     | 2     | -1    | 0     | 0     | 1     | -3/2  | 8    |
| $x_5$ | 0     | 5/3   | 1/3   | 0     | 1     | -1/3  | 0     | 10/3 |
| $x_4$ | 0     | 5/3   | 1/3   | 1     | 0     | 2/3   | -1    | 10/3 |
| $x_1$ | 1     | 4/3   | 2/3   | 0     | 0     | 1/3   | 0     | 8/3  |

<br>

#### ITERAÇÃO 3

**PASSO 3.2**

Como há coeficientes negativos na linha da função objetivo, então a solução não é ótima.

<br>

**PASSO 3.3**

Variável que vai entrar: $x_3$

<br>

**PASSO 3.4**

Variável que vai sair: $\text{min } \\{ (10/3)/(1/3), (8/3)/(2/3) \\} \rightarrow x_1$

<br>

**PASSO 3.5**

- $L_4 \leftarrow 3/2 L_4$
- $L_1 \leftarrow L_1 + L_4$
- $L_2 \leftarrow L_2 - 1/3 L_4$
- $L_3 \leftarrow L_3 - 1/3 L_4$

<br>

**QUADRO**

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $x_6$ | $x_7$ | $b$ |
|-------|-------|-------|-------|-------|-------|-------|-------|-----|
| $z$   | 3/2   | 4     | 0     | 0     | 0     | 3/2   | -3/2  | 12  |
| $x_5$ | -1/2  | 3/3   | 0     | 0     | 1     | -1/2  | 0     | 2   |
| $x_4$ | -1/2  | 3/3   | 0     | 1     | 0     | 1/2   | -1    | 2   |
| $x_3$ | 3/2   | 2     | 1     | 0     | 0     | 1/2   | 0     | 4   |

<br>

#### ITERAÇÃO 4

**PASSO 4.2**

Como não há mais coeficientes negativos, a solução ótima foi encontrada:

- $x^\ast = (x_1,x_2,x_3,x_4,x_5,x_6) = (0,0,4,2,2,0)$
- $z = 12$

<br>

## Exercício 4B

```math
\text{max } z = 3x_1 + 2x_2 + 3x_3
```

Sujeito a:

```math
\displaylines{
    2x_1 + x_2 + x_3 \le 2 \\
    3x_1 + 4x_2 + 2x_3 \ge 8 \\
    x_1, x_2, x_3 \ge 0
}
```

<br>

### Solução

SOLUÇÃO

<br>

## Exercício 4C

```math
\text{max } z = 2x_1 + 5x_2 + x_3
```

Sujeito a:

```math
\displaylines{
    x_1 + x_2 \ge 6 \\
    x_2 - x_3 \ge 4 \\
    4x_1 + 2x_2 + x_3 \le 15 \\
    x_1,x_2,x_3 \ge 0
}
```

<br>

### Solução

SOLUÇÃO

<br>

## Exercício 4D

```math
\text{min } z = x_1 - 3x_2 + x_3
```

Sujeito a:

```math
\displaylines{
    x_1 + x_2 \ge 6 \\
    x_2 - x_3 \ge 4 \\
    4x_1 + 2x_2 + x_3 \le 15 \\
    x_1, x_2, x_3 \ge 0
}
```

<br>

### Solução

SOLUÇÃO

---

<br>
<br>

# Exercício 5

Resolva os seguintes problemas usando o simplex revisado.

<br>

## Exercício 5A

```math
\text{max } z = 2x_1 + 4x_2
```

Sujeito a:

```math
\displaylines{
    x_1 + 2x_2 \le 5 \\
    x_1 + x_2 \le 4 \\
    x_1,x_2 \ge 0
}
```

<br>

### Solução

**FORMA PADRÃO**

```math
-\text{min } -z = -2x_1 - 4x_2
```

Sujeito a:

```math
\displaylines{
    x_1 + 2x_2 + x_3 = 5 \\
    x_1 + x_2 + x_4 = 4 \\
    x_1,x_2,x_3,x_4 \ge 0
}
```

<br>

**MATRIZES**

```math
A = \begin{bmatrix} 1 & 2 & 1 & 0 \\ 1 & 1 & 0 & 1 \end{bmatrix},
b = \begin{bmatrix} 5 \\ 4 \end{bmatrix}, 
c^T = \begin{bmatrix} -2 & -4 & 0 & 0 \end{bmatrix}
```

<br>

**SOLUÇÃO INICIAL**

```math
\displaylines{
    B = \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}, R = \begin{bmatrix} 1 & 2 \\ 1 & 1 \end{bmatrix} \\
    c^T_B = \begin{bmatrix} 0 & 0 \end{bmatrix}, c^T_R = \begin{bmatrix} -2 & -4 \end{bmatrix} \\
    s_B = \{ 3,4 \}, s_R = \{ 1,2 \}
}
```

<br>

**ITERAÇÃO 1**

1. Variável que entra na base é a que possui coeficiente mais negativo: $x_2$

2. Variável que sai da base usa o teste da razão (entre $b$ e $R$): $\text{min }\\{ 5/2, 4/1 \\} \rightarrow x_3$

3. Recalcular $s_B, s_R, B, R, c^T_B, c^T_R$:

```math
s_B = \{ 2,4 \}, s_R = \{ 1,3 \}
```

Assim:

```math
\displaylines{
    B = \begin{bmatrix} 2 & 0 \\ 1 & 1 \end{bmatrix}, R = \begin{bmatrix} 1 & 1 \\ 1 & 0 \end{bmatrix} \\
    c^T_B = \begin{bmatrix} -4 & 0 \end{bmatrix}, c^T_R = \begin{bmatrix} -2 & 0 \end{bmatrix}
}
```

<br>

4. Calcular $B^{-1}$:

```math
B \cdot B^{-1} = I \rightarrow B^{-1} = \begin{bmatrix} 1/2 & 0 \\ -1/2 & 1 \end{bmatrix}
```

<br>

5. Calcular $x_B = B^{-1}b$:

```math
\begin{bmatrix} 1/2 & 0 \\ -1/2 & 1 \end{bmatrix}\begin{bmatrix} 5 \\ 4 \end{bmatrix} = \begin{bmatrix} 5/2 \\ 3/2 \end{bmatrix}
```

<br>

Para avaliar a variável que vai entrar na base, deve-se calcular a matriz de coeficientes da função objetivo das variáveis não básicas por meio da equação $c^T_R - c^T_{B}B^{-1}R$.

<br>

6. Calcular $c^T_R - c^T_{B}B^{-1}R$:

```math
B^{-1}R = \begin{bmatrix} 1/2 & 0 \\ -1/2 & 1 \end{bmatrix}\begin{bmatrix} 1 & 1 \\ 1 & 0 \end{bmatrix} =
\begin{bmatrix} 1/2 & 1/2 \\ 1/2 & -1/2 \end{bmatrix}
```

```math
C^T_{B}B^{-1}R = \begin{bmatrix} -4 & 0 \end{bmatrix} \begin{bmatrix} 1/2 & 1/2 \\ 1/2 & -1/2 \end{bmatrix} =
\begin{bmatrix} -2 & -2 \end{bmatrix}
```

```math
c^T_R - c^T_{B}B^{-1}R = \begin{bmatrix} -2 & 0 \end{bmatrix} - \begin{bmatrix} -2 & -2 \end{bmatrix} =
\begin{bmatrix} 0 & 2 \end{bmatrix}
```

<br>

Como não há nenhum coeficiente negativo em $c^T_R - c^T_{B}B^{-1}R$, constata-se que a solução ótima foi alcançada. A solução ótima, para $s_B = \\{ 2,4 \\}$:

```math
\displaylines{
    x^\ast = B^{-1}b = \begin{bmatrix} 5/2 \\ 3/2 \end{bmatrix} \rightarrow \{0, 5/2, 0, 3/2 \} \\
    z = 4 * 5/2 = 10
}
```

<br>

## Exercício 5B

```math
\text{max } z = 3x_1 + 2x_2 - 2x_3 + 5x_4
```

Sujeito a:

```math
\displaylines{
    x_1 + x_2 + 3x_3 + x_4 \le 8 \\
    3x_1 - x_2 + x_3 + 2x_4 \le 10 \\
    x_1 - x_3 \le 6 \\
    x_1,x_2,x_3,x_4 \ge 0
}
```

<br>

### Solução

**FORMA PADRÃO**

```math
- \text{min } - z = - 3x_1 - 2x_2 + 2x_3 - 5x_4
```

Sujeito a:

```math
\displaylines{
    x_1 + x_2 + 3x_3 + x_4 + x_5 = 8 \\
    3x_1 - x_2 + x_3 + 2x_4 + x_6 = 10 \\
    x_1 - x_3 + x_7 = 6 \\
    x_1,x_2,x_3,x_4,x_5,x_6,x_7 \ge 0
}
```

<br>

**MATRIZES**

```math
\displaylines{
    A = \begin{bmatrix} 1 & 1 & 3 & 1 & 1 & 0 & 0 \\ 3 & -1 & 1 & 2 & 0 & 1 & 0 \\ 1 & 0 & -1 & 0 & 0 & 0 & 1 \end{bmatrix} \\ \\
    b = \begin{bmatrix} 8 \\ 10 \\ 6 \end{bmatrix} \\ \\
    c^T = \begin{bmatrix} -3 & -2 & 2 & -5 & 0 & 0 & 0 \end{bmatrix}
}
```

<br>

**SOLUÇÃO INICIAL**

```math
\displaylines{
    B = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix} \\ \\
    R = \begin{bmatrix} 1 & 1 & 3 & 1 \\ 3 & -1 & 1 & 2 \\ 1 & 0 & -1 & 0 \end{bmatrix} \\ \\
    c^T_B = \begin{bmatrix} 0 & 0 & 0 \end{bmatrix}   \\ \\
    c^T_R = \begin{bmatrix} -3 & -2 & 2 & -5 \end{bmatrix} \\ \\
    s_B = \{ 5,6,7 \} \\ \\
    s_R = \{ 1,2,3,4 \}
}
```

<br>

**ITERAÇÃO 1**

1. Variável que entra na base é a que possui coeficiente mais negativo: $x_4$

2. Variável que sai da base usa o teste da razão (entre $b$ e $R$): $\text{min }\\{ 8/1, 10/2 \\} \rightarrow x_6$

3. Recalcular $s_B, s_R, B, R, c^T_B, c^T_R$:

```math
\displaylines{
    s_B = \{ 5,4,7 \} \\ \\
    s_R = \{ 1,2,3,6 \}
}
```

<br>

Assim, temos:

```math
\displaylines{
    B = \begin{bmatrix} 1 & 1 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 1 \end{bmatrix} \\ \\
    R = \begin{bmatrix} 1 & 0 & 3 & 0 \\ 3 & -1 & 1 & 1 \\ 1 & 0 & -1 & 0 \end{bmatrix} \\ \\
    c^T_B = \begin{bmatrix} 0 & -5 & 0 \end{bmatrix} \\ \\
    c^T_R = \begin{bmatrix} -3 & -2 & 2 & 0 \end{bmatrix}
}
```

<br>

4. Calcular $B^{-1}$:

```math
\displaylines{
    B = \begin{bmatrix} 1 & 1 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 1 \end{bmatrix} \\ \\
    B^{-1} = \begin{bmatrix} 1 & -1/2 & 0 \\ 0 & 1/2 & 0 \\ 0 & 0 & 1 \end{bmatrix}
}
```

<br>

5. Calcular $x_B = B^{-1}b$:

```math
x_B = \begin{bmatrix} 1 & -1/2 & 0 \\ 0 & 1/2 & 0 \\ 0 & 0 & 1 \end{bmatrix} \cdot \begin{bmatrix} 8 \\ 10 \\ 6 \end{bmatrix} = \begin{bmatrix} 3 \\ 5 \\ 6 \end{bmatrix}
```

<br>

Para avaliar a variável que vai entrar na base, deve-se calcular a matriz de coeficientes da função objetivo das variáveis não básicas por meio da equação $c^T_R - c^T_{B}B^{-1}R$.

<br>

6. Calcular $c^T_R - c^T_{B}B^{-1}R$:

```math
B^{-1}R = \begin{bmatrix} 1 & -1/2 & 0 \\ 0 & 1/2 & 0 \\ 0 & 0 & 1 \end{bmatrix} \cdot \begin{bmatrix} 1 & 0 & 3 & 0 \\ 3 & -1 & 1 & 1 \\ 1 & 0 & -1 & 0 \end{bmatrix} = \begin{bmatrix} -1/2 & 1/2 & 5/2 & -1/2 \\ 3/2 & -1/2 & 1/2 & 1/2 \\ 1 & 0 & -1 & 0 \end{bmatrix}
```

<br>

```math

```



















<br>

---

<br>
<br>

# Exercício 6

Resolva os problemas do exercício 4 usando o simplex revisado.

<br>

## Exercício 6A

```math
\text{max } z = 3x_1 + 2x_2 + 3x_3
```

Sujeito a:

```math
\displaylines{
    2x_1 + x_2 + x_3 \ge 2 \\
    x_1 + 3x_2 + x_3 \le 6 \\
    3x_1 + 4x_2 + 2x_3 \le 8 \\
    x_1,x_2,x_3 \ge 0
}
```

<br>

### Solução

SOLUÇÃO

<br>

## Exercício 6B

```math
\text{max } z = 3x_1 + 2x_2 + 3x_3
```

Sujeito a:

```math
\displaylines{
    2x_1 + x_2 + x_3 \le 2 \\
    3x_1 + 4x_2 + 2x_3 \ge 8 \\
    x_1, x_2, x_3 \ge 0
}
```

<br>

### Solução

SOLUÇÃO

<br>

## Exercício 6C

```math
\text{max } z = 2x_1 + 5x_2 + x_3
```

Sujeito a:

```math
\displaylines{
    x_1 + x_2 \ge 6 \\
    x_2 - x_3 \ge 4 \\
    4x_1 + 2x_2 + x_3 \le 15 \\
    x_1,x_2,x_3 \ge 0
}
```

<br>

### Solução

SOLUÇÃO

<br>

## Exercício 6D

```math
\text{min } z = x_1 - 3x_2 + x_3
```

Sujeito a:

```math
\displaylines{
    x_1 + x_2 \ge 6 \\
    x_2 - x_3 \ge 4 \\
    4x_1 + 2x_2 + x_3 \le 15 \\
    x_1, x_2, x_3 \ge 0
}
```

<br>

### Solução

SOLUÇÃO
