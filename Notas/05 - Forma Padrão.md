# Programação Matemática - Aula 05

<br>

## Forma Padrão

```math
\text{min } z = \sum^{n}_{j=1} c_{j}x_{j}
```

Sujeito a:

```math
\displaylines{
    \sum^{n}_{j=1} a_{ij}x_{j} = b_{i} \\
    x_{j}, b_{i} \ge 0 \\
    \forall i = 1,...,m \\
    \forall j = 1,...,n
}
```




<br>

## Forma Canônica

- Um sistema de equações lineares em que cada equação tem uma variável com coeficiente 1 e 0 nas demais equações é dito estar na **FORMA CANÔNICA**.
- Se o PPL está na forma padrão e existe uma sequência $S$ tal que a matriz $A$ de $S$, $A_S = I$ e $C_S = 0$, então o PPL está na forma canônica em relação à sequência $S$. $I$ representa a matriz identidade.

<br>

Outras definições:

- Uma variável que tem coeficiente 1 em uma única equação e 0 em todas as outras equações é chamada **VARIÁVEL BÁSICA**
- Uma variável que não é básica é chamada de **VARIÁVEL NÃO BÁSICA**.




<br>

## Forma Canônica - Exemplo

```math
    \text{min } 2x_1 + x_3 - x_5 + x_6
```

Sujeito a:

```math
\begin{aligned}

    3x_1 - 2x_3 + x_5 + x_7 &= 1 \\
    2x_1 + x_2 - 3x_5 &= 8 \\
    3x_1 + 17x_3 + x_4 + x_6 &= 2 \\
    x_j &\ge 0, \forall j

\end{aligned}
```

<br>

| $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $x_6$ | $x_7$ | $b$ |
|-------|-------|-------|-------|-------|-------|-------|-----|
| 2     | 0     | 1     | 0     | -1    | 1     | 0     | 0   |
| 3     | 0     | -2    | 0     | 1     | 0     | 1     | 1   |
| 2     | 1     | 0     | 0     | -3    | 0     | 0     | 8   |
| 3     | 0     | 17    | 1     | 0     | 1     | 0     | 2   |

<br>

Verifica-se que o PPL está na forma padrão e a sequência $S = \\{ 7,2,4 \\}$ é tal que $A_S = I$ e $C_S = 0$. Portanto, o PPL está na forma canônica em relação à sequência $S = \\{ 7,2,4 \\}$.

Neste exemplo, verifica-se que as variáveis básicas são: $x_7, x_2, x_4$. As não básicas são todas as outras.

Quando um PPL está na forma canônica, temos uma solução viável e básica imediata. Por esse motivo, é importante o estudo de equivalência entre PPLs.




<br>

## Equivalência entre PPLs

### Operação 1

```math
\text{max } Q(x) \equiv -\text{min }\{ -Q(x) \}
```

<br>
<br>

Considere $M$ o conjunto das soluções viáveis e $x^\ast$ é solução ótima do PPL.

Então, podemos dizer que $\text{max }Q(x) = Q(x^\ast)$ tal que $Q(x^\ast) \ge Q(x), \forall x \in M$.

Se multiplicarmos esta inequação por -1, temos $-Q(x^\ast) \le -Q(x), \forall x \in M$. E, como $-Q(x^\ast) = \text{min }\\{-Q(x)\\}$, logo $Q(x^\ast) = -\text{min }\\{ -Q(x) \\}$.

No método simplex, através da minimização, encontra-se o resultado ótimo com sinal contrário. Portanto, é necessário inverter o sinal para encontrar a resposta correta.

<br>


### Operação 2

**Variáveis livres e sem restrição de sinal.**

Quando $x_k \in \mathbb{R}$, faz-se: $x_k = y_k - z_k$ e $y_k, z_k \ge 0$. Assim, tem-se:

```math
\begin{aligned}
    y_k > z_k &\rightarrow x_k > 0 \\
    y_k = z_k &\rightarrow x_k = 0 \\
    y_k < z_k &\rightarrow x_k < 0 \\
\end{aligned}
```

<br>

### Operação 3

**Desigualdades**

```math
\begin{aligned}

    \sum_j a_{ij}x_{j} \le b_i &\equiv \sum a_{ij}x_{j} + x_{n+1} = b_i \\
    \sum_j a_{ij}x_{j} \ge b_i &\equiv \sum a_{ij}x_{j} - x_{n+1} = b_i \\
    x_{n+1} &\ge 0

\end{aligned}
```

<br>

### Operação 4

**Variáveis negativas**

```math
x_k \le 0 = -y_k, y_k \ge 0
```

<br>

### Operação 5

$b_i$ **negativo**

Multiplicar a restrição $i$ por $-1$




<br>

## Exemplo

Reduzir o PPL à forma padrão:

```math
\text{max } x_1 - x_3
```

Sujeito a:

```math
\begin{aligned}
    x_1 + 2x_2 - x_3 &\ge 2\\
    x_1 - x_2 - 3x_3 &= 1\\
    x_2 + x_3 &\le 5
\end{aligned}
```

```math
x_1 \text{ irrestrito}, x_2 \ge 0, x_3 \le 0
```

<br>

### Passo 1

```math
-\text{min } -x_1 + x_3
```

Sujeito a:

```math
\begin{aligned}
    x_1 + 2x_2 - x_3 - x_4 &= 2 \\
    x_1 - x_2 - 3x_3 &= 1 \\
    x_2 + x_3 + x_5 &= 5
\end{aligned}
```

```math
x_1 \text{ irrestrito}, x_2,x_4,x_5 \ge 0, x_3 \le 0
```

<br>

### Forma padrão

```math
-\text{min } -(y_1 - z_1) - y_3
```

Sujeito a:

```math
\begin{aligned}
    y_1 - z_1 + 2x_2 + y_3 - x_4 &= 2 \\
    y_1 - z_1 - x_2 + 3y_3 &= 1 \\
    x_2 - y_3 + x_5 &= 5 \\
    y_1, z_1, x_2, y_3, x_4, x_5 &\ge 0
\end{aligned}
```
