# Programação Matemática - Aula 4

<br>

## Solução Viável e Região Viável

Dado um problema $\text{min }z = \text{c}^{\text{t}}\text{x}$

Sujeito a:

```math
\displaylines{
    A\text{x} = \text{b} \\
    \text{x} \ge 0
}
```

Uma solução $x = (x_1, ..., x_n)$ é dita **SOLUÇÃO VIÁVEL** se satisfaz todas as restrições $A\text{x} = \text{b}, \text{x} \ge 0$
 \\
O conjunto de todas as soluções viáveis $S = \\{ x \in \mathbb{R}_{+}^{n} : Ax=b \\}$ é chamado de **REGIÃO VIÁVEL**.




<br>

## Solução Ótima

Uma solução $x^\ast = (x^\ast_{1}, ..., x^\ast_{n})$ de um PL de minimização é uma **SOLUÇÃO ÓTIMA** se $f(x^\ast) \le f(x), \forall x \in S$.

Uma solução $x^\ast = (x^\ast_{1}, ..., x^\ast_{n})$ de um PL de maximização é uma **SOLUÇÃO ÓTIMA** se $f(x^\ast) \ge f(x), \forall x \in S$.




<br>

## Procedimento

Consiste em:

- Determinação da região de soluções viáveis
- Determinação da solução ótima entre todos os pontos viáveis da região de soluções

<br>

Etapa 1 - Determinar a região de soluções viáveis

- Restrições de não-negatividade: primeiro quadrante
- Demais restrições
    - Transformá-las em equações
    - Traçar no gráfico a reta resultante
    - Uma reta $ax + by = c$ divide o plano em dois semi-planos: $ax + by \le c$ e $ax + by \ge c$
    - Qualquer ponto que esteja dentro ou sobre o contorno da região viável é viável
    - A reta é traçada no gráfico locali

A reta é traçada no gráfico localizando-se dois pontos distintos nela. Considere agora o efeito da desigualdade. Somente uma das duas partes que a reta divide satisfaz a desigualdade. Para determinar o lado correto, tome um ponto qualquer como ponto de referência. Por exemplo, o ponto $(0,0)$: se ele satisfaz a desigualdade, então o lado que ele se encontra é a meia-região viável; caso contrário, é o outro lado.




<br>

## Exemplo - Problema da Dieta

Minimizar

```math
    z = 30x_1 + 20x_2
```

sujeito a:

```math
\displaylines{
    4x_1 + 2x_2 \ge 20 \\
    x_1 + 2x_2 \ge 10 \\
    x_1 \ge 2 \\
    x_1, x_2 \ge 0
}
```

<br>

![image](https://user-images.githubusercontent.com/23441506/201508785-b0a11ba3-1783-417e-be8f-8427e4cf2a73.png)

<br>

Etapa 2 - Determinar a solução ótima

- O lugar geométrico da função objetivo constitui-se de um conjunto de retas paralelas. Uma dessas retas pode ser encontrada igualando-se a função objetivo a uma constante qualquer.
- Em seguida, identifica-se a direção na qual a função objetivo é otimizada.
- A solução ótima ocorre em um ponto na região de soluções além do qual qualquer aumento adicional levará para fora dos contornos da região viável.

![image](https://user-images.githubusercontent.com/23441506/201533553-683ee013-fa8a-4521-97c2-53a6c99266cf.png)

- A solução ótima (se existir) está sempre relacionada a um **PONTO EXTREMO** da região de soluções (em que duas ou mais retas se cruzam).
- Isto faz com que possamos resolver o problema da enumeração de todos os pontos extremos.
- À medida que o número de restrições e variáveis aumenta, este procedimento de enumeração torna-se menos viável em termos de cálculo.
- Ainda sim, o conhecimento de que o número de infinitas soluções contidas dentro da região viável pode ser substituído por um número finito de soluções é fundamental para o método simplex.




<br>

## Casos Particulares

- **INFINITAS SOLUÇÕES**: se a função objetivo é paralela a alguma restrição $R_1$, qualquer ponto que se encontre sobre $R_1$ em região viável é ótimo. O número de soluções ótimas neste caso é infinito.
- **ILIMITADO**: ocorre quando o PPL não é fechado e a função objetivo melhora em uma direção sem jamais atingir uma fronteira da região.
- **INVIÁVEL**: ocorre quando os lugares geométricos definidos pelas restrições caracterizam um conjunto vazio. Não há nenhuma solução que satisfaça, simultaneamente, todas as restrições.
- **DEGENERAÇÃO**: uma das restrições é redundante, o que na prática corresponde a recursos supérfluos ou erro na formulação do modelo.

















