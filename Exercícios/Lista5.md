# Lista 5 - Dualidade e Dual-Simplex

**Universidade Federal do ABC**<br>
Prof.ª Geiza Cristina da Silva<br>
Programação Matemática


<br>

### Lista de conteúdos

- [Exercício 1](#exercício-1)
- [Exercício 2](#exercício-2)
    - [Exercício 2A](#exercício-2a)
    - [Exercício 2B](#exercício-2b)
- [Exercício 3](#exercício-3)
    - [Exercício 3A](#exercício-3a)
    - [Exercício 3B](#exercício-3b)
    - [Exercício 3C](#exercício-3c)

<br>

# Exercício 1

Considere o seguinte PPL:

```math
\text{min } z = 5x_1 + 2x_2 + 4x_3
```

Sujeito a:

```math
\displaylines{
    3x_1 + x_2 + 2x_3 \ge 4\\
    6x_1 + 3x_2 + 5x_3 \ge 10 \\
    x_1,x_2,x_3 \ge 0
}
```

<br>

Resolva o problema dual pelo método gráfico e, usando as Condições Complementares de Folga, descreva a relação entre as variáveis primais e duais do problema e a solução do problema primal.

<br>

## Solução

<br>

**PRIMAL**

```math
\text{min } z = 5x_1 + 2x_2 + 4x_3
```

Sujeito a:

```math
\displaylines{
    3x_1 + x_2 + 2x_3 \ge 4\\
    6x_1 + 3x_2 + 5x_3 \ge 10 \\
    x_1,x_2,x_3 \ge 0
}
```

<br>

**DUAL**

```math
\text{max } y = 4w_1 + 10w_2$
```

Sujeito a:

```math
\displaylines{
    3w_1 + 6w_2 \le 5 \\
    w_1 + 3w_2 \le 2 \\
    2w_1 + 5w_2 \le 4 \\
    w_1,w_2 \ge 0
}
```

<br>

**SOLUÇÃO GRÁFICA**

![image](https://user-images.githubusercontent.com/23441506/205517262-f2c1ca45-79f8-43a0-8618-83dd1b7a850e.png)

<br>

1. $w = (0, 0.667) \rightarrow z = 6.67$
2. $w = (1, 0.333) \rightarrow z = 7.33$
3. $w = (1.667, 0) \rightarrow z = 6.67$

Portanto, a solução ótima do problema dual é $w^\ast = (1, 0.333)$ com $z = 7.33$.

<br>

Se fizermos a forma padrão do problema dual, acharemos três variáveis de folga dual que estão relacionadas com as variáveis naturais do problema primal, conforme veremos a seguir:

<br>

**DUAL - FORMA PADRÃO**

```math
\text{max } y = 4w_1 + 10w_2$
```

Sujeito a:

```math
\displaylines{
    3w_1 + 6w_2 + w_3 = 5 \\
    w_1 + 3w_2 + w_4 = 2 \\
    2w_1 + 5w_2 + w_5 = 4 \\
    w_1,w_2,w_3,w_4,w_5 \ge 0
}
```

<br>

Com a solução do problema dual, é possível calcular os valores das variáveis de folga do problema dual:

Lembrete: a solução ótima do dual é $x^\ast = (1, 0.333)$:

- $w_3 = 5 - 3w_1 - 6w_2 = 5 - 3*1 - 6*0.333 = 0$
- $w_4 = 2 - w_1 - 3w_2 = 2 - 1 - 3*0.333 = 0$
- $w_5 = 4 - 2w_1 - 5w_2 = 4 - 2*1 - 5*0.333 = 0.333$

<br>

As Condições Complementares de Folga dizem a respeito da relação entre as variáveis primais e duais. Assim, temos:

| Primal | Valor    | Dual  | Valor    |
|--------|----------|-------|----------|
| $x_1$  | $\neq 0$ | $w_3$ | $= 0$    |
| $x_2$  | $\neq 0$ | $w_4$ | $= 0$    |
| $x_3$  | $= 0$    | $w_5$ | $\neq 0$ |
| $x_4$  | $= 0$    | $w_1$ | $\neq 0$ |
| $x_5$  | $= 0$    | $w_2$ | $\neq 0$ |

<br>

A interpretação das variáveis de folga é a seguinte:

- As variáveis de folga do dual $(w_3, w_4, w_5)$ dizem respeito ao custo reduzido, ou seja, o custo de incluir a respectiva variável na solução. Neste caso, $x_3$ deveria melhorar seu coeficiente em $w_5 = 0.333$.
- As variáveis naturais do dual $(w_1, w_2)$ dizem respeito ao preço sombra, ou seja, a variação da função objetivo com o relaxamento de uma restrição.

<br>

É possível também calcular a solução ótima do problema primal já que sabemos que $x_3 = x_4 = x_5 = 0$:

```math
\displaylines{
    3x_1 + x_2 + 2x_3 - x_4 = 4 \\
    6x_1 + 3x_2 + 5x_3 - x_5 = 10 \\
    x_1,x_2,x_3,x_4,x_5 \ge 0
}
```


```math
\displaylines{
    3x_1 + x_2 = 4 \\
    6x_1 + 3x_2 = 10 \\
}
```


```math
\displaylines{
    x_1 = 2/3 \\
    x_2 = 2
}
```

<br>

Logo, a solução ótima do problema primal é $x^\ast = (0.667, 2, 0)$


---

<br>
<br>

# Exercício 2

Seja o seguinte quadro ótimo obtido ao final do método simplex para um problema de PL:

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $b$  |
|-------|-------|-------|-------|-------|------|
| $z$   | 0     | 0     | 4/3   | 1/6   | 50/3 |
| $x_2$ | 0     | 1     | 2/3   | -1/6  | 10/3 |
| $x_1$ | 1     | 0     | 1/3   | 1/6   | 20/3 |

<br>

## Exercício 2A

Indique as soluções ótimas do primal e do dual.

<br>

### Solução

Primal:

- $x^\ast = \\{ 20/3, 10/3, 0, 0 \\}$
- $z = 50/3$

Dual:

- $x^\ast = \\{ 0, 0, 4/3 , 1/6 \\}$
- $z = 50/3$

<br>

## Exercício 2B

Explique o significado das variáveis duais sobre o problema original.

<br>

### Solução

As variáveis duais têm significado de custo reduzido, que é o custo de incluir as variáveis na solução.

---

<br>
<br>

# Exercício 3

Resolva os seguintes problemas pelo método dual simplex:

<br>

## Exercício 3A

```math
\text{min } z = 3x_1 + 2x_2 + 3x_3
```

Sujeito a:

```math
\displaylines{
    2x_1 + x_2 + x_3 \le 2 \\
    3x_1 + 4x_2 + 2x_3 \ge 8 \\
    x_1,x_2,x_3 \ge 0
}
```

<br>

### Solução

**FORMA PADRÃO**

```math
\text{min } z = 3x_1 + 2x_2 + 3x_3
```

Sujeito a:

```math
\displaylines{
    2x_1 + x_2 + x_3 + x_4 = 2 \\
    3x_1 + 4x_2 + 2x_3 - x_5 = 8 \\
    x_1,x_2,x_3,x_4,x_5 \ge 0
}
```

<br>

**QUADRO INICIAL**

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $b$ |
|-------|-------|-------|-------|-------|-------|-----|
| z     | 3     | 2     | 3     | 0     | 0     | 0   |
| $x_4$ | 2     | 1     | 1     | 1     | 0     | 2   |
| $x_5$ | -3    | -4    | -2    | 0     | 1     | -8  |

> Pelo menos uma restrição foi multiplicada por $-1$ para formar a base inicial.

<br>

**ITERAÇÃO 1**

<br>

**Passo 1.1**

Como há coeficientes negativos na coluna de $b$, ainda não chegamos na solução ótima e devemos continuar.

<br>

**Passo 1.2**

Variável que vai sair: $x_5$

<br>

**Passo 1.3**

Variável que vai entrar: $\text{min } \\{ \vert 3/-3 \vert, \vert 2/-4 \vert, \vert 3/-2 \vert \\} \rightarrow x_2$

<br>

**Passo 1.4**

- $L_3 \leftarrow L_3 / -4$
- $L_1 \leftarrow L_1 - 2L_3$
- $L_2 \leftarrow L_2 - L_3$

<br>

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $b$ |
|-------|-------|-------|-------|-------|-------|-----|
| z     | 3/2   | 0     | 2     | 0     | 1/2   | -4  |
| $x_4$ | 5/4   | 0     | 1/2   | 1     | 1/4   | 0   |
| $x_2$ | 3/4   | 1     | 1/2   | 0     | -1/4  | 2   |

<br>

**ITERAÇÃO 2**

<br>

**Passo 2.1**

Como não há mais valores negativos na coluna de $b$, então o algoritmo para e temos a seguinte solução ótima:

- $x^\ast = (0,2,0)$
- $z = 4$

<br>

## Exercício 3B

```math
\text{max } z = 2x_1 + 5x_2 + x_3
```

Sujeito a:

```math
\displaylines{
    x_1 + x_2 \le 6 \\
    x_2 - x_3 \ge 8 \\
    x_1,x_2,x_3 \ge 0
}
```

<br>

### Solução

**FORMA PADRÃO**

```math
\text{max } z = 2x_1 + 5x_2 + x_3
```

Sujeito a:

```math
\displaylines{
    x_1 + x_2 + x_4 = 6 \\
    x_2 - x_3 - x_5 = 8 \\
    x_1,x_2,x_3,x_4,x_5 \ge 0
}
```

<br>

**QUADRO INICIAL**

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $b$ |
|-------|-------|-------|-------|-------|-------|-----|
| z     | 2     | 5     | 1     | 0     | 0     | 0   |
| $x_4$ | 1     | 1     | 0     | 1     | 0     | 6   |
| $x_5$ | 0     | -1    | 1     | 0     | 1     | -8  |

> Pelo menos uma restrição foi multiplicada por $-1$ para formar a base inicial.

<br>

**ITERAÇÃO 1**

<br>

**Passo 1.1**

Como há coeficientes negativos na coluna de $b$, ainda não chegamos na solução ótima e devemos continuar.

<br>

**Passo 1.2**

Variável que vai sair: $x_5$

<br>

**Passo 1.3**

Variável que vai entrar: $\text{min } \\{ \vert 5/-1 \vert \\} \rightarrow x_2$

<br>

**Passo 1.4**

- $L_3 \leftarrow L_3 * -1$
- $L_1 \leftarrow L_1 - 5L_3$
- $L_2 \leftarrow L_2 - L_3$

<br>

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $b$ |
|-------|-------|-------|-------|-------|-------|-----|
| z     | 2     | 0     | 6     | 0     | 5     | -40 |
| $x_4$ | 1     | 0     | 1     | 1     | 1     | -2  |
| $x_2$ | 0     | 1     | -1    | 0     | -1    | 8   |

<br>

**ITERAÇÃO 2**

<br>

**Passo 2.1**

Como há coeficientes negativos na coluna de $b$, ainda não chegamos na solução ótima e devemos continuar.

<br>

**Passo 2.2**

Variável que vai sair: $x_4$

<br>

**Passo 2.3**

Não há opções para a variável que vai entrar. Portanto, este problema é inviável.

<br>

## Exercício 3C

```math
\text{min } z = x_1 - 3x_2 + x_3
```

Sujeito a:

```math
\displaylines{
    x_1 + x_2 \le 2 \\
    x_2 - 2x_3 \ge 8 \\
    4x_1 + 2x_2 + x_3 \le 15 \\
    x_1, x_2, x_3 \ge 0
}
```

<br>

### Solução

**FORMA PADRÃO**

```math
\text{min } z = x_1 - 3x_2 + x_3
```

Sujeito a:

```math
\displaylines{
    x_1 + x_2 + x_4 = 2 \\
    x_2 - 2x_3 - x_5 = 8 \\
    4x_1 + 2x_2 + x_3 - x_6 = 15 \\
    x_1, x_2, x_3, x_4, x_5, x_6 \ge 0
}
```

<br>

**QUADRO INICIAL**

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $x_6$ | $b$ |
|-------|-------|-------|-------|-------|-------|-------|-----|
| z     | 1     | -3    | 1     | 0     | 0     | 0     | 0   |
| $x_4$ | 1     | 1     | 0     | 1     | 0     | 0     | 2   |
| $x_5$ | 0     | -1    | 2     | 0     | 1     | 0     | -8  |
| $x_6$ | -4    | -2    | -1    | 0     | 0     | 1     | -15 |

> Pelo menos uma restrição foi multiplicada por $-1$ para formar a base inicial.

<br>

**ITERAÇÃO 1**

<br>

**Passo 1.1**

Como há coeficientes negativos na coluna de $b$, ainda não chegamos na solução ótima e devemos continuar.

<br>

**Passo 1.2**

Variável que vai sair: $x_6$

<br>

**Passo 1.3**

Variável que vai entrar: $\text{min } \\{ \vert 1/-4 \vert, \vert -3/-2 \vert, \vert 1/-1 \vert \\} \rightarrow x_1$

<br>

**Passo 1.4**

- $L_4 \leftarrow L_4 * 1/-4$
- $L_1 \leftarrow L_1 - L_4$
- $L_2 \leftarrow L_2 - L_4$

<br>

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $x_6$ | $b$   |
|-------|-------|-------|-------|-------|-------|-------|-------|
| z     | 0     | -7/2  | 3/4   | 0     | 0     | 1/4   | -15/4 |
| $x_4$ | 0     | 1/2   | -1/4  | 1     | 0     | 1/4   | -7/4  |
| $x_5$ | 0     | -1    | 2     | 0     | 1     | 0     | -8    |
| $x_1$ | 1     | 1/2   | 1/4   | 0     | 0     | -1/4  | 15/4  |

<br>

**ITERAÇÃO 2**

<br>

**Passo 2.1**

Como há coeficientes negativos na coluna de $b$, ainda não chegamos na solução ótima e devemos continuar.

<br>

**Passo 2.2**

Variável que vai sair: $x_5$

<br>

**Passo 2.3**

Variável que vai entrar: $\text{min } \\{ \vert (-7/2)/-1 \vert \\} \rightarrow x_2$

<br>

**Passo 2.4**

- $L_3 \leftarrow L_3 * -1$
- $L_1 \leftarrow L_1 + 7/2 L_3$
- $L_2 \leftarrow L_2 - 1/2 L_3$
- $L_4 \leftarrow L_4 - 1/2 L_3$

<br>

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $x_6$ | $b$   |
|-------|-------|-------|-------|-------|-------|-------|-------|
| z     | 0     | 0     | -25/4 | 0     | -7/2  | 1/4   | 97/4  |
| $x_4$ | 0     | 0     | 3/4   | 1     | 1/2   | 1/4   | -23/4 |
| $x_2$ | 0     | 1     | -2    | 0     | -1    | 0     | 8     |
| $x_1$ | 1     | 0     | 5/4   | 0     | 1/2   | -1/4  | -1/4  |

<br>

**ITERAÇÃO 3**

<br>

**Passo 3.1**

Como há coeficientes negativos na coluna de $b$, ainda não chegamos na solução ótima e devemos continuar.

<br>

**Passo 3.2**

Variável que vai sair: $x_4$

<br>

**Passo 3.3**

Não há nenhum valor negativo na linha da variável $x_4$ para que seja feito o teste da razão. Portanto, este solução é inviável.
