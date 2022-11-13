# Programação Matemática - Aula 3

## Alocação de Recursos

A Capitão Caverna S.A., localizada em Pedra Lascada, aluga 3 tipos de barcos para passeios marítimos: jangadas, supercanoas e arcas com cabine. A companhia fornece juntamente com o barco um capitão para navegá-lo e uma tripulação que varia de acordo com a embarcação: uma para jangadas, duas para supercanoas e três para arcas.

A companhia tem 4 jangadas, 8 supercanoas e 3 arcas e sem seu corpo de funcionários: 10 capitães e 18 tripulantes. O aluguel é por diárias e a Capitão Caverna lucra $50 por jangada, $70 por supercanoa e $100 por arca.

Faça um modelo de programação matemática que determine o esquema de alguel que maximiza o lucro.

<br>

Variáveis de decisão:

- $emb$: conjunto dos diferentes tipos de embarcação = $\\{ \text{Jangada, Supercanoa, Arca} \\}$
- $l_i$: lucro proporcionado pelo aluguel da embarcação do tipo $i$
- $cap_i$: número de capitães necessários para comandar a em
- $trip_i$: número de tripulantes necessários para trabalhar na embarcação do tipo $i$
- $disp_i$: número disponível de embarcações do tipo $i$
- $ntrips$: número de tripulações disponíveis
- $ncapitaes$: número de capitães disponíveis

<br>

| Tipo de embarcação | Min. tripulantes | Min. capitães | Embarcações disp. | Lucro ($) |
|--------------------|------------------|---------------|-------------------|-----------|
| Jangada            | 1                | 1             | 4                 | 50        |
| Supercanoa         | 2                | 1             | 8                 | 70        |
| Arca               | 3                | 1             | 3                 | 100       |
| Funcionários disp. | 18               | 10            |                   |           |

<br>

O modelo genérico relativo ao problema em questão pode ser assim formulado:

```math
\displaylines{
    \text{max } \sum_{i \in emb} l_{i}x_{i} \\
    \sum_{i \in emb} cap_{i}x_{i} \le ncapitaes \\
    \sum_{i \in emb} trip_{i}x_{i} \le ntrips \\
    x_i \le disp_i, \forall i \in emb \\
    x_i \in \mathbb{Z}^{+}, \forall i \in emb
}
```




<br>

## Problema da Mochila 0-1 (Knapsack Problem)

Um excursionista planeja fazer uma viagem acampando. Há 5 itens que ele deseja levar consigo, mas estes, juntos, excedem o limite de 60 quilos que ele supõe ser capaz de carregar. Para ajudar a si próprio na seleção, ele atribui valores, por ordem crescente de importância a cada um dos itens conforme a tabela a seguir:

| Item | Peso (kg) | Valor |
|------|-----------|-------|
| 1    | 52        | 100   |
| 2    | 23        | 60    |
| 3    | 35        | 70    |
| 4    | 15        | 15    |
| 5    | 7         | 8     |

<br>

Suponha a existência de uma unidade de cada item, faça um modelo de programação inteira que maximize o valor total sem exceder as restrições de peso.

<br>

- $itens$: conjunto dos itens = $\\{ 1,2,3,4,5 \\}$
- $cap$: capacidade da mochila
- $w_j$: peso relativo ao item $j$
- $p_j$: valor de retorno proporcionado pelo item $j$

<br>

O problema da mochila 0-1 pode ser formulado como:

```math
\displaylines{
    \text{max } \sum_{j \in itens} p_{j}x_{j} \\
    \sum_{j \in itens} w_{j}x_{j} \le cap \\
    x_j \in \{ 0,1 \} \forall j \in itens
}
```




<br>

## Problema da Mochila 0-1 Múltipla

Este problema difere do anterior no sentido de que neste problema pode haver mais de uma unidade de cada item; no caso, há $u_j$ unidades disponíveis de cada item $j$.

A modelagem de programação inteira deste problema é

```math
\displaylines{
    \text{max } \sum_{i \in mochilas} \sum_{j \in itens} p_{j}x_{ij} \\
    \sum_{j \in itens} w_{j}x_{ij} \le cap_i \\
    \sum_{i \in mochilas} x_{ij} \le u_j \\
    x_{ij} \in \mathbb{Z}^{+} \\
    \forall i \in mochilas, \forall j \in itens
}
```



<br>

## Fluxo máximo em redes

A figura a seguir representa uma rede de comunicação de dados entre computadores. Os números representam a capacidade máxima em MBytes por segundo que pode ser transmitido de um computador para outro. Admita que a transmissão só é possível no sentido especificado pela seta. Qual é o fluxo máximo que pode passar entre A e G através da rede?

![image](https://user-images.githubusercontent.com/23441506/201501043-10d149ee-36ac-4f6b-bd5d-6d803c7383d4.png)

<br>

- $V$: conjunto de nós
- $cap_{ij}$: capacidade do arco $(i,j)$
- $n$: cardinalidade do conjunto de nós $(n = \vert V \vert)$

<br>

Assim, o modelo genérico pode ser escrito como:

```math
\displaylines{
    \text{max } \sum_{j \in V} x_{1j} \\
    \sum_{j \in V} x_{ij} - \sum_{j \in V} x_{ji} = 0 \\
    \sum_{j \in V} x_{1j} - \sum_{i \in V} x_{in} = 0 \\
    x_{ij} \le cap_{ij} \\
    x_{ij} \in \mathbb{Z}^{+}, \forall i,j \in V
}
```

Neste modelo, considera-se que o nó 1 é a origem e o nó $n$ é o destino.




<br>

## Caminho mínimo

Uma fábrica de artigos de decoração, localizada em Lambari, MG, deve entregar uma grande quantidade de peças na cidade de Baependi, MG. A empresa quer saber qual o caminho que seu caminhão de entregas deve fazer para minimizar a distância total percorrida.

A figura a seguir representa, na forma de rede, as ligações entre as cidades da região.

![image](https://user-images.githubusercontent.com/23441506/201502778-7ccf1581-8675-4765-a30b-3cee5153432d.png)

<br>

- $V$: conjunto dos vértices (nós)
- $d_{ij}$ distância do vértice $i$ ao vértice $j$
- $n$: cardinalidade do conjunto de vértices $(n = \lvert V \rvert)$

<br>

Considerando o nó 1 como a origem e o no $n$ como destino, pode-se modelar o poblema de caminho mínimo genericamente como:

```math
\displaylines{
    \text{min } \sum_{i \in V} \sum_{j \in V} d_{ij}x_{ij} \\
    \sum_{j \in V} x_{ij} - \sum_{j \in V} x_{ji} = 0, i \neq 1, i \neq n \\
    \sum_{j \in V} x_{1j} = 1 \\
    \sum_{i \in V} x_{in} = 1 \\
    x_{ij} \in \{ 0,1 \}, \forall i,j \in V
}
```










































