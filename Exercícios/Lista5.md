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
    - [Exercício 3A](#exercício-3a) (incompleto)
    - [Exercício 3B](#exercício-3b) (incompleto)
    - [Exercício 3C](#exercício-3c) (incompleto)

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

SOLUÇÃO

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

SOLUÇÃO

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

SOLUÇÃO
