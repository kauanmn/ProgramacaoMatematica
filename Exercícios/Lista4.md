# Lista 4 - Simplex base não disponível e Simplex revisado

**Universidade Federal do ABC**<br>
Prof.ª Geiza Cristina da Silva<br>
Programação Matemática


<br>

### Lista de conteúdos

- [Exercício 1](#exercício-1)
    - [Exercício 1A](#exercício-1a) (incompleto)
    - [Exercício 1B](#exercício-1b) (incompleto)
- [Exercício 2](#exercício-2) (incompleto)
- [Exercício 3](#exercício-3) (incompleto)
- [Exercício 4](#exercício-4)
    - [Exercício 4A](#exercício-4a) (incompleto)
    - [Exercício 4B](#exercício-4b) (incompleto)
    - [Exercício 4C](#exercício-4c) (incompleto)
    - [Exercício 4D](#exercício-4d) (incompleto)
- [Exercício 5](#exercício-5)
    - [Exercício 5A](#exercício-5a) (incompleto)
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

SOLUÇÃO

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

SOLUÇÃO

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

SOLUÇÃO

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
