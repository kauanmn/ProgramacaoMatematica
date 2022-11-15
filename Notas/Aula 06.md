# Programação Matemática - Aula 06

<br>

## Combinação Linear

Um vetor $\text{x}$ é chamado de **COMBINAÇÃO LINEAR** dos vetores $\text{x}_1, ..., \text{x}_k$ se $\text{x}$ pode ser expresso na forma:

```math
\text{x} = \alpha_1\text{x}_1 + \cdots + \alpha_k\text{x}_k
```

Onde $\alpha_i$ são escalares.




<br>

## Combinação Linear Convexa (CLC)

Um vetor $\text{x}$ é chamado de **COMBINAÇÃO LINEAR CONVEXA** dos vetores $\text{x}_1, ..., \text{x}_k$ se $\text{x}$ pode ser expresso na forma:

```math
\text{x} = \alpha_1\text{x}_1 + \cdots + \alpha_k\text{x}_k
```

Tal que:

- $\alpha_i \ge 0$
- $\sum \alpha_i = 1$




<br>

### Exemplo

Sejam:

```math
\text{x}_1 = \begin{bmatrix} 3\\1\\0 \end{bmatrix},
\text{x}_2 = \begin{bmatrix} 0\\1\\3 \end{bmatrix},
\text{x}_3 = \begin{bmatrix} 1\\1\\2 \end{bmatrix}
```

Então:

```math
\displaylines{
    \begin{bmatrix} 3\\1\\0 \end{bmatrix} \alpha_1 +
    \begin{bmatrix} 0\\1\\3 \end{bmatrix} \alpha_2 =
    \begin{bmatrix} 1\\1\\2 \end{bmatrix} \\
    3\alpha_1 = 1 \rightarrow \alpha_1 = 1/3 \\
    \alpha_1 + \alpha_2 = 1 \rightarrow 3\alpha_2 = 2 \rightarrow \alpha_2 = 2/3
}
```

<br>

Portanto, é CLC.




<br>

## Conjunto Convexo

Um conjunto $X \subset \mathbb{R}^n$ é um **CONJUNTO CONVEXO** se, para quaisquer $\text{x}_1, \text{x}_2 \in X$ e $\alpha \in [0,1]$, temos que:

```math
\alpha\text{x}_1 + (1-\alpha)\text{x}_2 \in X
```

<br>

![image](https://user-images.githubusercontent.com/23441506/201974156-94d31fdb-6c76-40fe-9935-a159a6e13a63.png)




<br>

## Hiperplano

Seja $X \subset \mathbb{R}^n$ um conjunto de pontos tal que, $\forall x \in X$, existem $a_i, b$, com pelo menos um $a_i \neq 0$ tal que

```math
a_{1}x_{1} + \cdots + a_{n}x_{n} = b
```

Então, $X$ é um **HIPERPLANO** em $\mathbb{R}^n$.




<br>

## Semiplano

Em $\mathbb{R}^n$, um **SEMIESPAÇO** é a região de um dos lados de um hiperplano.

Em outras palavras, são os pontos $x$ tais que $a_{1}x_{1} + \cdots + a_{n}x_{n} \le b$, para alguns $a_i, b \in \mathbb{R}$.




<br>

## Convexidade e Programação Linear

### Teorema

O conjunto $M$ das soluções viáveis de um PPL $\text{min } Q(x)$ tal que $Ax = b, x \ge 0$ é um conjunto convexo.

<br>

#### Ideia

Por definição, se um conjunto é convexo, para quaisquer dois pontos distintos, a CLC desses pontos também pertencem ao conjunto.

A ideia é provar que, dados dois vetores $x_1, x_2 \in M$, a CLC desses pontos também pertencem a $M$.

<br>

#### Prova

Como $x_1,x_2$ são soluções viáveis do PPL devem satisfazer $Ax_1 = b, Ax_2 = b$, tal que $x_1,x_2 \ge 0$.

Seja $x$ uma CLC de $x_1,x_2$. Então $x = \alpha_1x_1 + \alpha_2x_2$ e $\alpha_1 + \alpha_2 = 1$. Logo, $x \ge 0$ porque $x_1, x_2, \alpha_1, \alpha_2$ também são.

Como $Ax = A(\alpha_1x_1 + \alpha_2x_2) = \alpha_1Ax_1 + \alpha_2Ax_2 = \alpha_1b + \alpha_2b = b$, então a CLC de qualquer $x_1,x_2 \in M$ também pertence a $M$. Logo, o conjunto de soluções viáveis de um PPL é convexo.




<br>

## Vértices

Um ponto $x$ de um conjunto convexo $M$ é chamado de **VÉRTICE** (ou **PONTO EXTREMO**) de $M$, quando ele não pode ser obtido como CLC de nenhum par de pontos distintos de $M$.




<br>

## Bases

Seja um conjunto de vetores não nulos $A_1, ..., A_n \in \mathbb{R}^n$ e $x_1,...,x_n \in \mathbb{R}$.

Se a equação $A_1x_1 + \cdots + A_nx_n = 0$ só for satisfeita para $x_1 = \cdots = x_n = 0$, então os vetores $A_1, ..., A_n$ são **LINEARMENTE INDEPENDENTES**.

<br>

Se uma matriz $(m \times n)$ tem $n$ colunas e $m$ linhas linearmente independentes, então a matriz quadrada $B$ de ordem $m$ formadas por elas é uma **BASE** em $A$.

Se existir uma matriz base para a matriz $A$, então o sistema de equações lineares $Ax = b$ tem uma solução $x, \forall b \in \mathbb{R}^m$.

- As variáveis associadas à submatriz $B$ são chamadas de **VARIÁVEIS BÁSICAS** $(x_B)$.

As $(n-m)$ colunas restantes formam a submatriz não base $R$.

- As variáveis associadas à submatriz $R$ são as **VARIÁVEIS NÃO BÁSICAS** $(x_R)$

<br>

Seja $Ax = b$. Então, são válidas as partições:

```math
\displaylines{
    A = [B \vert R] \\
    x = \begin{bmatrix} x_B \\ x_R \end{bmatrix}
}
```

<br>

Assim,

```math
\displaylines{
    Ax = b \Leftrightarrow [B \vert R]\begin{bmatrix} x_B \\ x_R \end{bmatrix} = b \\ \\
    x_B = B^{-1}b-B^{-1}Rx_{R}
}
```

<br>

Define-se como **SOLUÇÃO BÁSICA** para $Ax = [Bx_B + Rx_R]$, $b$ tal que $x_R = 0$ e $x_B = B^{-1}b$

Se além disso $x_B \ge 0$, então a solução é uma **SOLUÇÃO BÁSICA VIÁVEL**.








































































































































