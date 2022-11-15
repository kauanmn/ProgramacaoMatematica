# Programação Matemática - Aula 07

<br>

## Vértices e Soluções Básicas Viáveis

### Teorema

Uma solução básica viável é um vértice do conjunto de soluções viáveis $M$ de um PPL.




<br>

### Teorema

Dado um PPL com um conjunto de soluções viáveis $M$, $x$ é vértice de $M$ se, e somente se, for solução básica viável (SBV).




<br>

### Teorema

O número de SBVs de um PPL é finito.




### Teorema

Toda combinação convexa de soluções ótimas de um PPL é também uma solução ótima do problema.




<br>

### Corolário

Se um PPL admitir mais de uma solução ótima então admite infinitas soluções ótimas.




<br>

## Ideia do Método Simplex

Foi visto que:

- As soluções básicas viáveis são aquelas que se situam em vértices da região limitadora do PPL.
- A solução de um PPL é com certeza uma SBV

<br>

O que se necessita para resolver um PPL é um algoritmo que percorra as diferentes soluções básicas do problema e que otimize a procura $\Rightarrow$ Simplex.




<br>

## Exemplo do Método Simplex

```math
\text{max } z = 20x_1 + 24x_2
```

Sujeito a:

```math
\displaylines{
    3x_1 + 6x_2 \le 60 \\
    4x_1 + 2x_2 \le 32 \\
    x_1,x_2 \ge 0
}
```

<br>

#### Forma padrão:

```math
-\text{min } z = -20x_1 - 24x_2
```

Sujeito a:

```math
\displaylines{
    3x_1 + 6x_2 + x_3 = 60 \\
    4x_1 + 2x_2 + x_4 = 32 \\
    x_1,x_2,x_3,x_4 \ge 0
}
```

<br>

- Variáveis básicas: $x_3, x_4$
- Variáveis não-básicas: $x_1,x_2$
- Solução básica viável: $(x_1,x_2,x_3,x_4) = (0,0,60,32)$, com $z = 0$

<br>

Uma vez definida uma SBV, devemos determinar se ela é ótima. Caso não seja, tentaremos achar uma outra SBV adjacente que retorne um valor de $z$ menor.

Para cada variável não básica, usaremos a função objetivo para avaliar a melhoria ocorrida com o acréscimo de uma unidade desta variável.

Por exemplo, a função objetivo $-20x_1 - 24x_2$ pode diminuir em 20 unidades caso aumente uma unidade da VNB $x_1$, e 24 com $x_2$. Como $x_2$ causa um maior impacto na função objetivo, ela será escolhida para entrar na base.

<br>

---

Vimos que a variável escolhida para entrar na base é a mais negativa na função objetivo. Isto pode fazer com que alguma variável básica se torne negativa.

Então, qual é o limite do crescimento da variável que entra na base? Devemos verificar como o acréscimo de unidades à variável muda os valores no conjunto das variáveis básicas.

<br>

---

Para assegurar-se de que $x_3 \ge 0$, devemos ter $60 - 6x_2 \ge 0$ OU $x_2 \le 60/6 = 10$, usando a restrição $3x_1 + 6x_2 + x_3 = 60$, lembrando que $x_1 = 0$.

Para $4x_1 + 2x_2 + x_4 = 32$, temos $x_4 = 32 - 2x_2$. Podemos crescer $x_1$ enquanto $32 - 2x_2 \ge 0 \rightarrow x_2 \le 16$.

Isto significa que, para deixar todas as variáveis básicas não negativas, o maior valor que pode ser dado a $x_2$ é $\text{min } = \\{ 60/6, 32/2 \\} = 10$.

Com isso, a variável $x_3$ deve deixar a base para a entrada de $x_2$. Para encontrar a nova solução básica viável, usaremos as operações elementares sobre as equações de forma a termos o coeficiente 1 na linha da variável que entra na base (linha pivô) e zero nas demais.

<br>

---

Linha pivô (linha 2): $3x_1 + 6x_2 + x_3 = 60$.

Multiplicando-se toda a linha por 1/6, temos: $1/2x_1 + x_2 + 1/6x_3 + 0x_4 = 10$

Na terceira equação $(4x_1 + 2x_2 + x_4 = 32)$, devemos encontrar 0 no coeficiente relativo a $x_2$. Assim, deve-se fazer $(L3') = (L3) - 2(L2')$: $(L3') 3x_1 + 0x_2 - 1/3x_3 + x_4 = 12$

Na primeira equação $(-20x_1 - 24x_2)$ faz-se $(L1') = (L1) + 24(L2')$, obtendo-se: $(L1') -8x_1 + 0x_2 + 4x_3 + 0x_4 = 240$.

Colocando as linhas juntas, temos:

```math
\begin{aligned}

    &(L1') &-8x_1 + 0x_2 + 4x_3 + 0x_4 &= 240 \\
    &(L2') &1/2x_1 + 1x_2 + 1/6x_3 + 0x_4 &= 10 \\
    &(L3') &3x_1 + 0x_2 - 1/3x_3 + x_4 &= 12

\end{aligned}
```

<br>

Com $VB = x_2,x_4$ e $VNB = x_3, x_1$ que dá a seguinte solução viável:

- $(x_2,x_4) = (10, 12), z = 240$, com as demais variáveis nulas.

<br>

---

Tentaremos agora encontrar uma SBV que melhore ainda mais o valor de $z$. Vemos na linha $(L1')$ que cada unidade acrescentada da variável $x_1$ pode decrescer o valor de $z$ em 8 unidades. Assim, uma nova iteração começa.

Dizemos que uma solução obtida é ótima quando nenhuma das variáveis não básicas tem coeficiente negativo na linha da função objetivo.




<br>

## Algoritmo Simplex

1. Achar uma forma canônica inicial para o sistema de equações. Isto é, achar uma solução básica inicial.
2. Avaliar a função objetivo. Se todos os coeficientes forem positivos (ou zero), a solução é ótima (minimização). Fim.
3. Escolher a variável que entrará na base: variável que tem o coeficiente mais negativo na função objetivo.
4. Escolher a variável que deixará a base: variável que se anula mais rapidamente quando a variável que entrar for aumentada e valor.
5. Manipular o sistema de forma a encontrar a nova forma canônica que corresponda aos passos 3 e 4.
6. Voltar ao passo 2.
