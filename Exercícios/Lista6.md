# Lista 4 - Simplex base não disponível e Simplex revisado

**Universidade Federal do ABC**<br>
Prof.ª Geiza Cristina da Silva<br>
Programação Matemática


<br>

### Lista de conteúdos

- [Exercício 1](#exercício-1)
- [Exercício 2](#exercício-2) (incompleto)
- [Exercício 3](#exercício-3) (incompleto)
- [Exercício 4](#exercício-4) (incompleto)
- [Exercício 5](#exercício-5) (incompleto)

<br>

---

<br>

Uma fábrica de latas de alumínio deseja minimizar o custo de operação na fabricação, sujeito a atender a demanda de mercado e respeitar uma legislação que impõe um determinado volume de toneladas de alumínio reciclado. A fábrica produz dois tipos de latas: tipo A e tipo B. E, para tal, dispõe de três processos de produção, cada qual com seu volume de produção (número de latas/hora), quantidade de alumínio reciclado usado (ton/hora) e custo operacional (R$/hora).

<br>

| Processos | Volume Prod. A | Volume Prod. B | Alumínio Reciclado | Custo Operacional |
|-----------|----------------|----------------|--------------------|-------------------|
| 1         | 6              | 8              | 0                  | 65                |
| 2         | 12             | 12             | 2                  | 150               |
| 3         | 10             | 15             | 3                  | 200               |

<br>

A demanda de mercado é de, no mínimo, 2400 toneladas de lata do tipo A e 2800 toneladas de latas do tipo B. Órgãos ambientais estabelecem o uso de alumínio reciclado, em um mínimo, de 600 toneladas.

Considere que as variáveis naturais do problema são $x_j$, o número de horas de operação do processo $j = 1,2,3$ e $x_4,x_5,x_6$ são variáveis de folgas associadas à primeira, segunda e terceiras restrições.

<br>

# Exercício 1

Modele e resolva o problema pelo método dual simplex.

<br>

## Solução

**MODELAGEM**

```math
\text{min } z = 65x_1 + 150x_2 + 200x_3
```

Sujeito a:

```math
\displaylines{
    6x_1 + 12x_2 + 10x_3 \ge 2400 \\
    8x_1 + 12x_2 + 15x_3 \ge 2800 \\
    2x_2 + 3x_3 \ge 600 \\
    x_1,x_2,x_3 \ge 0
}
```

<br>

**PRIMAL**

```math
\text{min } z = 65x_1 + 150x_2 + 200x_3
```

Sujeito a:

```math
\displaylines{
    6x_1 + 12x_2 + 10x_3 - x_4 = 2400 \\
    8x_1 + 12x_2 + 15x_3 - x_5 = 2800 \\
    2x_2 + 3x_3 - x_6 = 600 \\
    x_1,x_2,x_3,x_4,x_5,x_6 \ge 0
}
```

<br>

**QUADRO INICIAL**

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $x_6$ | $b$   |
|-------|-------|-------|-------|-------|-------|-------|-------|
| $z$   | 65    | 150   | 200   | 0     | 0     | 0     | 0     |
| $x_4$ | -6    | -12   | -10   | 1     | 0     | 0     | -2400 |
| $x_5$ | -8    | -12   | -15   | 0     | 1     | 0     | -2800 |
| $x_6$ | 0     | -2    | -3    | 0     | 0     | 1     | -600  |

> As linhas das restrições foram multiplicadas por -1

<br>

#### ITERAÇÃO 1

**PASSO 1.1**

Como há coeficientes negativos na coluna $b$, ainda não chegamos na solução ótima.

<br>

**PASSO 1.2**

Variável que vai sair: $x_5$

<br>

**PASSO 1.3**

Variável que vai entrar: $\text{min } \\{ 65/-8, 150/-12, 200/-15 \\} \rightarrow x_1$

<br>

**PASSO 1.4**

- $L_3 \leftarrow L_3 * -1/8$
- $L_1 \leftarrow L_1 - 65L_3$
- $L_2 \leftarrow L_2 + 6L_3$

<br>

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $x_6$ | $b$    |
|-------|-------|-------|-------|-------|-------|-------|--------|
| z     | 0     | 105/2 | 625/8 | 0     | 65/8  | 0     | -22750 |
| $x_4$ | 0     | -3    | 5/4   | 1     | -3/4  | 0     | -300   |
| $x_1$ | 1     | 3/2   | 15/8  | 0     | -1/8  | 0     | 350    |
| $x_6$ | 0     | -2    | -3    | 0     | 0     | 1     | -600   |

<br>

#### ITERAÇÃO 2

**PASSO 2.1**

Como há coeficientes negativos na coluna $b$, ainda não chegamos na solução ótima.

<br>

**PASSO 2.2**

Variável que vai sair: $x_6$

<br>

**PASSO 2.3**

Variável que vai entrar: $\text{min } \\{ (105/2)/-2, (625/8)/-3 \\} \rightarrow x_3$

<br>

**PASSO 2.4**

- $L_4 \leftarrow L_4 * -1/3$
- $L_1 \leftarrow L_1 - 625/8 * L_4$
- $L_2 \leftarrow L_2 - 5/4 * L_4$
- $L_3 \leftarrow L_3 - 15/8 * L_4$

<br>

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $x_6$  | $b$    |
|-------|-------|-------|-------|-------|-------|--------|--------|
| z     | 0     | 5/12  | 0     | 0     | 65/8  | 625/24 | -38375 |
| $x_4$ | 0     | -23/6 | 0     | 1     | -3/4  | 5/12   | -550   |
| $x_1$ | 1     | 1/4   | 0     | 0     | -1/8  | 15/24  | -25    |
| $x_3$ | 0     | 2/3   | 1     | 0     | 0     | -1/3   | 200    |

<br>

#### ITERAÇÃO 3

**PASSO 3.1**

Como há coeficientes negativos na coluna $b$, ainda não chegamos na solução ótima.

<br>

**PASSO 3.2**

Variável que vai sair: $x_4$

<br>

**PASSO 3.3**

Variável que vai entrar: $\text{min } \\{ (5/12)/(-23/6), (65/8)/(-3/4) \\} \rightarrow x_2$

<br>

**PASSO 3.4**

- $L_2 \leftarrow L_2 * (-6/23)$
- $L_1 \leftarrow L_1 - 5/12L_2$
- $L_3 \leftarrow L_3 - 1/4L_3$
- $L_4 \leftarrow L_4 - 2/3L_3$

<br>



---

<br>
<br>

# Exercício 2

Dê uma interpretação econômica baseado na solução do problema, isto é, discuta a solução em termos de preço dual e custo reduzido.

<br>

## Solução

SOLUÇÃO

---

<br>
<br>

# Exercício 3

De quanto o custo operacional do processo 1 pode variar sem alterar a base da solução ótima? (calcular faixa de valores de custo de $x_1$ que mantém a solução ótima).

<br>

## Solução

SOLUÇÃO

---

<br>
<br>

# Exercício 4

De quanto o custo operacional do processo 2 pode variar sem que se altere a base da solução ótima?

<br>

## Solução

SOLUÇÃO

---

<br>
<br>

# Exercício 5

Uma nova regulamentação aumentou em 28% a quantidade usada de alumínio reciclado (de 600 para 768 toneladas). Qual será a nova solução obtida e qual seu valor (alteração no vetor $b$)?

<br>

## Solução

SOLUÇÃO
