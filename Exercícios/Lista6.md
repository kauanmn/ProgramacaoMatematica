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

**MODELAGEM - PRIMAL**

```math
\text{min } z = 65x_1 + 150x_2 + 200x_3
```

Sujeito a:

```math
\displaylines{
    6x_1 + 12x_2 + 10x_3 \ge 2400 \\
    8x_1 + 12x_2 + 15x_3 \ge 2800 \\
    2x_1 + 3x_3 \ge 600 \\
    x_1,x_2,x_3 \ge 0
}
```

<br>

**DUAL**

```math
\text{max } y = 2400w_1 + 2800w_2 + 600w_3
```

Sujeito a:

```math
\displaylines{
    6w_1 + 8w_2 \le 65 \\
    12w_1 + 12w_2 + 2w_3 \le 150 \\
    10w_1 + 15w_2 + 3w_3 \le 200 \\
    w_1,w_2,w_3 \ge 0
}
```

<br>

**PRIMAL - FORMA PADRÃO**

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

**PASSO 1.2**

Como há coeficientes negativos na coluna $b$, ainda não chegamos na solução ótima.

<br>

**PASSO 1.3**

Variável que vai sair:

<br>

**PASSO 1.4**

Variável que vai entrar:

<br>

**PASSO 1.5**

LINHAS

<br>

QUADRO

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
