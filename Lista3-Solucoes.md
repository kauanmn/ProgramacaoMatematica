# Lista 3 - Simplex

**Universidade Federal do ABC**<br>
Prof.ª Geiza Cristina da Silva<br>
Programação Matemática


<br>


## Lista de conteúdos

- [Revisão](#revisão)
- [Exercício 1](#exercício-1)
    - [Exercício 1A](#exercício-1A)
    - [Exercício 1B](#exercício-1B) (incompleto)
    - [Exercício 1C](#exercício-1C) (incompleto)
    - [Exercício 1D](#exercício-1D) (incompleto)
    - [Exercício 1E](#exercício-1E) (incompleto)


<br>


# Revisão

**ALGORITMO SIMPLEX**

1. Achar uma forma canônica inicial para o sistema de equações (i.e., achar uma solução básica inicial)
2. Avaliar a função objetivo. Se todos os coeficientes forem $\ge 0$, a solução é ótima (minimização). Fim.
3. Escolher a variável que entrará na base: variável que tem o coeficiente mais negativo na função objetivo
4. Escolher a variável que deixará a base: variável que se anula mais rapidamente quando a variável que entrar for aumentada de valor
5. Manipular o sistema de forma a encontrar a nova forma canônica que corresponda aos passos 3 e 4
6. Voltar ao passo 2




<br>


# Exercício 1

Solucione pelo método simplex os seguintes problemas de programação linear. Descreva a solução encontrada e/ou comente a ocorrência de casos particulares.


<br>


## Exercício 1A

Função objetivo:

```math
    \text{max } z = 2x_{1} - 4x_{2} + 5x_{3} - 6x_{4}
```

Sujeito a:

```math
    \displaylines{
        x_{1} + 4x_{2} - 2x_{3} + 8x_{4} \le 2 \\
        -x_{1} + 2x_{2} + 3x_{3} + 4x_{4} \le 1 \\
        x_{1}, x_{2}, x_{3}, x_{4} \ge 0
    }
```


<br>


### Solução

#### PASSO 1 - FORMA CANÔNICA

Função objetivo:

```math
    \text{max } z = 2x_{1} - 4x_{2} + 5x_{3} - 6x_{4}
```

Sujeito a:

```math
    \displaylines{
        x_{1} + 4x_{2} - 2x_{3} + 8x_{4} \le 2 \\
        -x_{1} + 2x_{2} + 3x_{3} + 4x_{4} \le 1 \\
        x_{1}, x_{2}, x_{3}, x_{4} \ge 0
    }
```

<br>

Forma canônica:

```math
    - \text{min } z = -2x_{1} + 4x_{2} - 5x_{3} + 6x_{4}
```

Sujeito a:

```math
    \displaylines{
        x_{1} + 4x_{2} - 2x_{3} + 8x_{4} + x_{5} = 2 \\
        -x_{1} + 2x_{2} + 3x_{3} + 4x_{4} + x_{6} = 1 \\
        x_{1}, x_{2}, x_{3}, x_{4}, x_{5}, x_{6} \ge 0
    }
```

<br>

Quadro inicial:

|         | $x_{1}$ | $x_{2}$ | $x_{3}$ | $x_{4}$ | $x_{5}$ | $x_{6}$ | $b$ |
|---------|---------|---------|---------|---------|---------|---------|-----|
| $z$     | -2      | 4       | -5      | 6       | 0       | 0       | 0   |
| $x_{5}$ | 1       | 4       | -2      | 8       | 1       | 0       | 2   |
| $x_{6}$ | -1      | 2       | 3       | 4       | 0       | 1       | 1   |


<br>


#### ITERAÇÃO 1

#### Passo 2

Como ainda existem coeficientes negativos, então ainda não chegamos na solução ótima e, portanto, devemos continuar.


<br>


#### Passo 3

Escolher a variável que entrará na base.

A variável que tem o coeficiente mais negativo na função objetivo é $x_{3}$


<br>


#### Passo 4

Escolher a variável que deixará a base.

A variável que se anula mais rapidamente quando a variável que entrar for aumentada de valor é dada a seguir:

- $x_{5} \rightarrow 2/(-2) = -1$
- $x_{6} \rightarrow 1/3  = 0.33$

Assim, a variável que deixará a base é $x_{6}$.


<br>


#### Passo 5

Manipular o sistema de forma a encontrar a nova forma canônica que corresponda aos passos 3 e 4

$L_{3}' = L_{3} / 3$

|         | $x_{1}$ | $x_{2}$ | $x_{3}$ | $x_{4}$ | $x_{5}$ | $x_{6}$ | $b$   |
|---------|---------|---------|---------|---------|---------|---------|-------|
| $z$     | -2      | 4       | -5      | 6       | 0       | 0       | 0     |
| $x_{5}$ | 1       | 4       | -2      | 8       | 1       | 0       | 2     |
| $x_{3}$ | $-1/3$  | $2/3$   | $1$     | $4/3$   | $0$     | $1/3$   | $1/3$ |


<br>


$L_{2}' = L_{2} + 2L_{3}'$

|         | $x_{1}$ | $x_{2}$ | $x_{3}$ | $x_{4}$ | $x_{5}$ | $x_{6}$ | $b$   |
|---------|---------|---------|---------|---------|---------|---------|-------|
| $z$     | -2      | 4       | -5      | 6       | 0       | 0       | 0     |
| $x_{5}$ | $1/3$   | $16/3$  | $0$     | $32/3$  | $1$     | $2/3$   | $8/3$ |
| $x_{3}$ | $-1/3$  | $2/3$   | $1$     | $4/3$   | $0$     | $1/3$   | $1/3$ |


<br>


$L_{1}' = L_{1} + 5L_{3}'$

|         | $x_{1}$ | $x_{2}$ | $x_{3}$ | $x_{4}$ | $x_{5}$ | $x_{6}$ | $b$   |
|---------|---------|---------|---------|---------|---------|---------|-------|
| $z$     | $-11/3$ | $22/3$  | $0$     | $38/3$  | $0$     | $5/3$   | $5/3$ |
| $x_{5}$ | $1/3$   | $16/3$  | $0$     | $32/3$  | $1$     | $2/3$   | $8/3$ |
| $x_{3}$ | $-1/3$  | $2/3$   | $1$     | $4/3$   | $0$     | $1/3$   | $1/3$ |


<br>

#### ITERAÇÃO 2

#### Passo 2

Como ainda existem coeficientes negativos, então ainda não chegamos na solução ótima e, portanto, devemos continuar.


<br>


#### Passo 3

Escolher a variável que entrará na base.

A variável que tem o coeficiente mais negativo na função objetivo é $x_{1}$


<br>


#### Passo 4

Escolher a variável que deixará a base.

A variável que se anula mais rapidamente quando a variável que entrar for aumentada de valor é dada a seguir:

- $x_{5} \rightarrow (8/3) /  (1/3) =  8$
- $x_{3} \rightarrow (1/3) / -(1/3) = -1$

Assim, a variável que deixará a base é $x_{5}$.


<br>


#### Passo 5

Manipular o sistema de forma a encontrar a nova forma canônica que corresponda aos passos 3 e 4


<br>


$L_{2}' = L_{2}/(1/3) = 3L_{2}$

|         | $x_{1}$ | $x_{2}$ | $x_{3}$ | $x_{4}$ | $x_{5}$ | $x_{6}$ | $b$   |
|---------|---------|---------|---------|---------|---------|---------|-------|
| $z$     | $-11/3$ | $22/3$  | $0$     | $38/3$  | $0$     | $5/3$   | $5/3$ |
| $x_{1}$ | $1$     | $16$    | $0$     | $32$    | $3$     | $2$     | $8$   |
| $x_{3}$ | $-1/3$  | $2/3$   | $1$     | $4/3$   | $0$     | $1/3$   | $1/3$ |


<br>


$L_{1}' = L_{1} + (11/3)(L_{2})$

|         | $x_{1}$ | $x_{2}$ | $x_{3}$ | $x_{4}$ | $x_{5}$ | $x_{6}$ | $b$   |
|---------|---------|---------|---------|---------|---------|---------|-------|
| $z$     | $0$     | $66$    | $0$     | $130$   | $11$    | $9$     | $31$  |
| $x_{1}$ | $1$     | $16$    | $0$     | $32$    | $3$     | $2$     | $8$   |
| $x_{3}$ | $-1/3$  | $2/3$   | $1$     | $4/3$   | $0$     | $1/3$   | $1/3$ |


<br>


$L_{3}' = L_{3} + (1/3)L_{2}$

|         | $x_{1}$ | $x_{2}$ | $x_{3}$ | $x_{4}$ | $x_{5}$ | $x_{6}$ | $b$  |
|---------|---------|---------|---------|---------|---------|---------|------|
| $z$     | $0$     | $66$    | $0$     | $130$   | $11$    | $9$     | $31$ |
| $x_{1}$ | $1$     | $16$    | $0$     | $32$    | $3$     | $2$     | $8$  |
| $x_{3}$ | $0$     | $6$     | $1$     | $12$    | $1$     | $1$     | $3$  |


<br>

#### ITERAÇÃO 2

#### Passo 2

Como não há variáveis com coeficientes negativos, o algoritmo para aqui com a seguinte solução:

- $(x_{1}, x_{2}, x_{3}, x_{4}) = (8,0,3,0)$
- $z = 31$




<br>


## Exercício 1B

Função objetivo:

```math
    \text{max } z = 7x_{1} + 9x_{2}
```

Sujeito a:

```math
    \displaylines{
        x_{1} - x_{2} \ge -2 \\
        3x_{1} + 5x_{2} \le 15 \\
        5x_{1} + 4x_{2} \le 20 \\
        x_{1}, x_{2} \ge 0
    }
```


<br>


### Solução

SOLUÇÃO


<br>


## Exercício 1C

Função objetivo:

```math
    \text{min } z = -x_{1} - 2x_{2} + x_{3}
```

Sujeito a:

```math
    \displaylines{
        -2x_{1} - x_{2} + x_{3} \ge -2 \\
        2x_{1} - x_{2} + 5x_{3} \le 6 \\
        -4x_{1} - x_{2} - x_{3} \ge -6 \\
        x_{1}, x_{3} \ge 0, x_{2} \text{ livre}
    }
```


<br>


### Solução

SOLUÇÃO


<br>


## Exercício 1D

Função objetivo:

```math
    \text{max } z = x_{1} + 3x_{2}
```

Sujeito a:

```math
    \displaylines{
        -x_{1} + 2x_{2} \le 4 \\
        x_{1} + x_{2} \le 6 \\
        x_{1} + 3x_{2} \le 9 \\
        x_{1}, x_{2} \ge 0
    }
```


<br>


### Solução

SOLUÇÃO


<br>


## Exercício 1E

Função objetivo:

```math
    \text{max } z = x_{1} + x_{2}
```

Sujeito a:

```math
    \displaylines{
        x_{2} \le 2 \\
        -x_{1} + 2x_{2} \le 4 \\
        x_{1}, x_{2} \ge 0
    }
```


<br>


### Solução

SOLUÇÃO


<br>
