# Programação Matemática - Aula 11

<br>

## Motivação

- Para cada problema de PL, existe um outro, denominado **DUAL** do problema original, que por sua vez é chamado de **PRIMAL**.
- Os dois guardam uma relação tão estreita que a solução ótima de um problema fornce automaticamente a solução ótima do outro.
- Os estudos de dualidade possibilitam uma melhor compreensão dos problemas de PL, a interpretação econômica de alguns parâmetros, o desenvolvimento de outras teorias como o dual-simplex.




<br>

## Problema Dual

- Uma **VARIÁVEL DUAL** é definida para cada restrição do primal
- Uma **RESTRIÇÃO DUAL** é definida para cada variável primal
- Os coeficientes da restrição de uma variável primal definem os coeficientes do lado esquerdo da restrição dual (matriz transposta), e seus coeficientes na função objetivo definem os coeficientes do lado direito.
- Os coeficientes da função objetivo do problema dual são iguais aos coeficientes do lado direito das equações das restrições do problema primal

<br>

### Correspondência entre pares primal-dual

![image](https://user-images.githubusercontent.com/23441506/202852976-8bf9726c-900e-4479-9d6a-56e121776b71.png)




<br>

## Exemplo 1

### Primal

```math
\text{max } z = 5x_1 + 12x_2 + 4x_3
```

Sujeito a:

```math
\displaylines{
    x_1 + 2x_2 + x_3 \le 10 \\
    2x_1 - x_2 + 3x_3 = 8 \\
    2x_1 + 8x_2 + 4x_3 \ge 30 \\
    x_1,x_2,x_3 \ge 0
}
```

<br>

### Dual

```math
\text{min } y = 10w_1 + 8w_2 + 30w_3
```

Sujeito a:

```math
\displaylines{
    w_1 + 2w_2 + 2w_3 \ge 5 \\
    2w_1 - w_2 + 8w_3 \ge 12 \\
    w_1 + 3w_2 + 4w_3 \ge 4 \\
    w_1 \ge 0, w_2 \text{ irrestrita }, w_3 \le 0
}
```




<br>

## Exemplo 2

### Primal

```math
\text{min } z = 15x_1 + 12x_2
```

Sujeito a:

```math
\displaylines{
    x_1 + 2x_2 \ge 3 \\
    2x_1 - 4x_2 \le 5 \\
    x_1,x_2 \ge 0
}
```




<br>

### Dual

```math
\text{max } y = 3w_1 + 5w_2
```

Sujeito a:

```math
\displaylines{
    w_1 + 2w_2 \le 15 \\
    2w_1 - 4w_2 \le 12 \\
    w_1 \ge 0, w_2 \le 0
}
```




<br>

## Exemplo 3

### Primal

```math
\text{min } z = 5x_1 + 6x_2
```

Sujeito a:

```math
\displaylines{
    x_1 + 2x_2 = 5 \\
    -x_1 + 5x_2 \ge 3 \\
    4x_1 + 7x_2 \le 8 \\
    x_1 \text{ irrestrita }, x_2 \ge 0
}
```




<br>

### Dual

```math
\text{max } y = 5w_1 + 3w_2 + 8w_3
```

Sujeito a:

```math
\displaylines{
    w_1 - w_2 + 4w_3 = 5 \\
    2w_1 + 5w_2 + 7w_3 \le 6 \\
    w_1 \text{ irrestrita }, w_2 \ge 0, w_3 \le 0
}
```




<br>

## Teorema da Dualidade Fraca

O valor da função objetivo $z$ de qualquer solução viável do problema primal $P : \text{max } z$ sujeito a $Ax \le b, x \ge 0$ é sempre menor ou igual ao valor da função objetivo $y$, de qualquer solução viável do seu problema dual $D : \text{min } y$ sujeito $Aw \ge C, w \ge 0$.

<br>

### Consequência

- O valor da função objetivo do Primal é um limite inferior para a função objetivo do Dual
- O valor da função objetivo do Dual é um limite superior para a função objetivo do Primal




<br>

## Teorema da Dualidade Forte

Seja $x^\ast$ e $w^\ast$ soluções viáveis dos problemas Primal e Dual, respectivamente, tais que $cx^\ast = bw^\ast$. Então, $x^\ast, w^\ast$ são soluções ótimas dos problemas Primal e Dual.




<br>

## PPL Ilimitado

- Se o Primal é ilimitado, então o Dual é inviável
- Se o Dual é ilimitado, então o Primal é inviável




<br>

## Teorema Fundamental da Dualidade

Considere os problemas primal $P$ e dual $D$. Uma, e somente uma, das seguintes alternativas é verdadeira:

- Se $P$ tem uma solução ótima, então $D$ também tem, e os valores das funções objetivos de ambos são iguais. A recíproco é verdadeira.
- Se $P$ é ilimitado, então $D$ é inviável. A recíproca é verdadeira. Além disso, ambos os problemas podem ser inviáveis.




<br>

## Interpretação Econômica do Dual

### PPL da Manufatura

Uma manufatura produz mesas e bancos, sendo capaz de vender toda a sua produção no período. O único recurso restrito é a mão-de-obra, cuja produtividade, juntamente com os lucros, são dados:

![image](https://user-images.githubusercontent.com/23441506/202870646-aa73a917-748f-4fa1-b809-1c15812e6a28.png)

<br>

```math
\text{max } z = 20x_1 + 24x_2
```

Sujeito a:

```math
\displaylines{
    3x_1 + 6x_2 \le 60 \\
    4x_1 + 2x_2 \le 32 \\
    x_1, x_2 \ge 0
}
```

<br>


#### Dual

```math
\text{max } y = 60w_1 + 32w_2
```

Sujeito a:

```math
\displaylines{
    3w_1 + 4w_2 \ge 20 \\
    6w_1 + 2w_2 \ge 24 \\
    w_1,w_2 \ge 0
}
```

<br>

---

#### Forma Padrão

#### Primal

```math
\text{min } z = -20x_1 - 24x_2
```

Sujeito a:

```math
\displaylines{
    3x_1 + 6x_2 + x_3 = 60 \\
    4x_1 + 2x_2 + x_4 = 32 \\
    x_1, x_2, x_3, x_4 \ge 0
}
```

<br>

#### Dual

```math
\text{max } y = 60w_1 + 32w_2
```

Sujeito a:

```math
\displaylines{
    3w_1 + 4w_2 - w_3 = 20 \\
    6w_1 + 2w_2 - w_4 = 24 \\
    w_1,w_2,w_3,w_4 \ge 0
}
```

<br>

Multiplicamos por -1 as equações das restrições do dual e representamos o primal e o dual no quadro simplex.

![image](https://user-images.githubusercontent.com/23441506/202871584-25c0f096-20ca-4c65-91f7-3d222d512d97.png)

<br>

- A solução do dual aparece na linha da função objetivo (FO) do primal. O contrário também é verdade.
- A solução primal é viável enquanto a do dual não é.

<br>

Efetuando-se a primeira iteração do simplex, temos:

![image](https://user-images.githubusercontent.com/23441506/202871710-d6cde234-4139-4d00-9d5a-7f5b0e5f2fd8.png)

<br>

A partir da função objetivo do primal, temos $w = \\{ 4, 0, -8, 0 \\}$. A solução não é ótima, como pode ser visto no quadro primal e pelo dual ser inviável.

<br>

#### Quadro Final

|       | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $b$ |
|-------|-------|-------|-------|-------|-----|
| $z$   | 0     | 0     | 28/9  | 8/3   | 272 |
| $x_2$ | 0     | 1     | 2/9   | -1/6  | 8   |
| $x_1$ | 1     | 0     | -1/9  | 1/3   | 4   |

<br>

Solução ótima do primal $x^\ast = \\{4, 8, 0, 0 \\}$. A solução ótima do dual é $w^\ast = \\{ 28/9, 8/3, 0, 0 \\}$.

<br>

- A solução ótima da variável dual pode ser interpretada economicamente como o impacto marginal da variação do elemento do lado direito da restrição sobre a função objetivo.
- A primeira restrição do PPL da manufatura refere-se a homens-hora no setor de montagem. Logo, a solução ótima da primeira variável dual (28/9) indica o impacto da variação de um homem-hora de montagem sobre o lucro da manufatura.
- As variáveis de folga do primal são nulas. Se a primeira variável de folga fosse diferente de zero, então haveria sobre de homens-hora no setor de montagem e a primeira variável natural do dual seria necessariamente nula, indicando que um homem-hora adicional não acrescentaria em termos de lucro adicional, uma vez que este recurso está sobrando.




<br>

## Introdução às Condições Complementares de Folga (CCF)

Interpretação econômica do primeiro conjunto de condições complementares de folga:

- _Para cada restrição primal, ou a variável de folga é nula ou a variável natural do dual correspondente é nula._

<br>

### Relação de complementaridade

- O produto das variáveis de decisão do primal por suas variáveis de folga correspondentes no dual é zero.
- O produto das variáveis de decisão do dual por suas variáveis de folga correspondentes no primal é zero.

<br>

Se $\overline{x}, \overline{w}$ satisfazem as CCFs, então eiste a correspondência ilustrada abaixo:

![image](https://user-images.githubusercontent.com/23441506/202872249-c1ba500f-dc71-48bc-92ac-d7e0f9632e19.png)

<br>

- O número de soluções básicas no primal e dual devem ser exatamente o mesmo.
- Em um problema primal com $n$ variáveis e $m$ restrições, o número total de variáveis naturais e de folga será de $m+n$
- É válida a seguinte relação:


![image](https://user-images.githubusercontent.com/23441506/202872275-a9725e9e-da2a-4435-9f56-8b6c9c193d61.png)
