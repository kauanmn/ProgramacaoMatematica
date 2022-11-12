# Programação Matemática - Aula 02

## Exemplo - Problema da Dieta

O objetivo é determinar, em uma dieta para redução calórica, as quantidades de certos alimentos que deverão ser ingeridos diariamente, de modo que determinados requisitos nutricionais sejam satisfeitos a custo mínimo.

Suponha que certa dieta esteja restrita a leite desnatado, carne magra de boi, carne de peixe e salada de composição conhecida. Sabendo-se que os requisitos nutricionais serão expressos em termos de vitaminas A, C e D, e controlados por suas quantidades mínimas (em miligramas), uma vez que são indispensáveis à preservação da saúde da pessoa que está se submetendo à dieta.

A tabela a seguir resume a quantidade de cada vitamina em disponibilidade nos alimentos e necessidade diária.

| Vitaminas  | Leite (l) | Carne (kg) | Peixe (kg) | Salada (100g) | Mínimo |
|------------|-----------|------------|------------|---------------|--------|
| A          | 2ml       | 2ml        | 10ml       | 20ml          | 11ml   |
| B          | 50ml      | 20ml       | 10ml       | 30ml          | 70ml   |
| Custo (R$) | 2         | 4          | 6,5        | 2             |        |


### Modelagem

1. Escolha das variáveis de decisão:

$x_{i}$: quantidade do alimento $i$ a ser usado na dieta, $i = (l, c, p, s)$ (leite, carne, peixe, salada)

2. Elaboração da função objetivo: $\text{min } z = 2x_{l} + 4x_{c} + 6.5x_{p} + 2x_{s}$

3. Formulação das restrições (requisitos nutricionais):

- Restrição de demanda de vitamina A: $2x_{l}  + 2x_{c}  + 10x_{p} + 20x_{s} \ge 11$
- Restrição de demanda de vitamina C: $50x_{l} + 20x_{c} + 10x_{p} + 30x_{s} \ge 70$
- Restrição de demanda de vitamina D: $80x_{l} + 70x_{c} + 10x_{p} + 80x_{s} \ge 250$

4. Formulação das restrições de não negatividade: $x_{l}, x_{c}, x_{p}, x_{s} \ge 0$




<br>

## Problema do Transporte

![image](https://user-images.githubusercontent.com/23441506/201389443-7793c73a-f06e-4f62-810c-754069fe99c3.png)


### Modelagem

Dados conhecidos:

- Dados conhecidos:
	- $a_{i}, i = 1, ..., m$ é a quantidade de determinado bem produzido por $m$ fábricas
	- $b_{j}, j = 1, ..., n$ é a quantidade da mercadoria consumida em $n$ destinos

- Variáveis de decisão: $x_{ij}$ é a quantidade de mercadoria a ser transportada de $i$ para $j$, $x_{ij} \ge 0, \forall i, j$

- Função objetivo:

```math
	\text{min } \sum_{i=1}^{m}\sum_{j=1}^{n} c_{ij}x_{ij}
```




<br>

## Um caso do Problema do Transporte

Peças Automotivas - Indústria MG Auto

| Fábricas     | Centros de Distribuição |
|--------------|-------------------------|
| Los Angeles  | Denver                  |
| Detroit      | Miami                   |
| Nova Orleans |                         |

<br>

| Fábricas     | Capacidade de Prod. |
|--------------|---------------------|
| Los Angeles  | 1000                |
| Detroit      | 1500                |
| Nova Orleans | 1200                |

<br>

| Centros de Distribuição | Demanda |
|-------------------------|---------|
| Denver                  | 2300    |
| Miami                   | 1400    |

<br>

Custos de Transporte

| Fábricas\Centros de Dist. | Denver | Miami |
|---------------------------|--------|-------|
| Los Angeles               | 80     | 215   |
| Detroit                   | 100    | 108   |
| Nova Orleans              | 102    | 68    |

<br>

### Modelagem

1. Função objetivo: $\text{min } z = 80x_{11} + 215x_{12} + 100x_{21} + 108x_{22} + 102x_{31} + 68x_{32}$
2. Restrições de capacidade/demanda das unidades:

    - Restrições associadas à capacidade de produção das fábricas:

    ```math
    \begin{aligned}
        &x_{11} + x_{12} = 1000 \text{ (Los Angeles)} \\
        &x_{21} + x_{22} = 1500 \text{ (Detroit)} \\
        &x_{31} + x_{32} = 1200 \text{ (Nova Orleans)}
    \end{aligned}
    ```

    - Restrições associadas às demandas dos centros de distribuição:


    ```math
    \begin{aligned}
        &x_{11} + x_{21} + x_{31} = 2300 \text{ (Denver)} \\
        &x_{12} + x_{22} + x_{32} = 1400 \text{ (Miami)}
    \end{aligned}
    ```

3. Restrições de não-negatividade: $x_{11}, x_{12}, x_{21}, x_{22}, x_{31}, x_{32} \ge 0$


<br>


- As restrições podem ser escritas genericamente da forma:
    - Capacidade das fábricas: $\sum{x_{ij}} = a_{i}$
    - Demanda dos centros: $\sum{x_{ij}} = b_{j}$
    - $\forall i = 1,...,m, \forall j = 1,...,n$
- O sinal das restrições podem variar dependendo do caso:
    - No caso acima, a quantidade total disponível nas fábricas é exatamente igual à quantidade de bens demandados nos centros de consumo
    - Se a demanda é menor do que a quantidade disponível nas fábricas, temos:
        - Capacidade das fábricas: $\sum{x_{ij}} \le a_{i}$
        - Demanda dos centros: $\sum{x_{ij}} = b_{j}$ OU $\sum{x_{ij}} \ge b_{j}$




<br>

## Planejamento de produção e controle de estoque

Esta classe de problemas consiste em determinar o mix ótimo de produtos a serem produzidos, em um ou mais períodos de tempo, que maximize o ganho e respeite as restrições de demanda, matéria-prima, armazenamento e outras.




<br>

## PPL Planejamento - Único período

Produção: parcas, casacos com enchimento, calças com isolamento térmico e luvas. Todos os produtos são fabricados em quatro departamentos. A empresa recebeu pedidos fechados para seus produtos. O contrato estipula uma multa para itens não entregues. Elabore um plano ótimo de produção para a empresa.

| Departamento  | Parca | Casacos | Calças | Luvas | Capacidade |
|---------------|-------|---------|--------|-------|------------|
| Corte         | 0,30  | 0,30    | 0,25   | 0,15  | 1000       |
| Isolamento    | 0,25  | 0,35    | 0,30   | 0,10  | 1000       |
| Costura       | 0,45  | 0,50    | 0,40   | 0,22  | 1000       |
| Embalagem     | 0,15  | 0,15    | 0,10   | 0,05  | 1000       |
| Demanda       | 800   | 750     | 600    | 500   |            |
| Lucro (unid.) | 30    | 40      | 20     | 10    |            |
| Multa (unid.) | 15    | 20      | 10     | 8     |            |

<br>

1. Variáveis de decisão

    - $x_{1}$: quantidade de parcas
    - $x_{2}$: quantidade de casacos com enchimento
    - $x_{3}$: quantidade de calças
    - $x_{4}$: quantidade de pares de luvas

2. Função objetivo: receita = lucro - multa

    - Lucro: $30x_{1} + 40x_{2} + 20x_{3} + 10x_{4}$
    - Seja $s_{j}$ o número de unidades faltantes do produto $j = 1,2,3,4$
    - Multa: $15s_{1} + 20s_{2} + 10s_{3} + 8s_{4}$
    - Função objetivo: $\text{max } 30x_1 + 40x_2 + 20x_3 + 10x_4 - (15s_1 + 20s_2 + 10s_3 + 8s_4)$

3. Restrições

Restrições por departamento:

| Departamento | Restrição                                        |
|--------------|--------------------------------------------------|
| Corte        | $0.30x_1 + 0.30x_2 + 0.25x_3 + 0.15x_4 \le 1000$ |
| Isolamento   | $0.25x_1 + 0.35x_2 + 0.30x_3 + 0.10x_4 \le 1000$ |
| Costura      | $0.45x_1 + 0.50x_2 + 0.40x_3 + 0.22x_4 \le 1000$ |
| Embalagem    | $0.15x_1 + 0.15x_2 + 0.10x_3 + 0.05x_4 \le 1000$ |

<br>

Restrições de demanda:

- $x_1 + s_1 = 800$
- $x_2 + s_2 = 750$
- $x_3 + s_3 = 600$
- $x_4 + s_4 = 500$

<br>

Restrições de não-negatividade: $x_j \ge 0, s_j \ge 0, j = 1,2,3,4$

<br>
<br>

Maximizar

```math
    z = 30x_1 + 40x_2 + 20x_3 + 10x_4 - (15s_1 + 20s_2 + 10s_3 + 8s_4)
```

sujeito a:

```math

\displaylines{
    0.30x_1 + 0.30x_2 + 0.25x_3 + 0.15x_4 \le 1000 \\
    0.25x_1 + 0.35x_2 + 0.30x_3 + 0.10x_4 \le 1000 \\
    0.45x_1 + 0.50x_2 + 0.40x_3 + 0.22x_4 \le 1000 \\
    0.15x_1 + 0.15x_2 + 0.10x_3 + 0.05x_4 \le 1000 \\
    x_1 + s_1 = 800 \\
    x_2 + s_2 = 750 \\
    x_3 + s_3 = 600 \\
    x_4 + s_4 = 500 \\
    x_j \ge 0, s_j \ge 0, j = 1,2,3,4
}
```




<br>

## PPL Planejamento - Múltiplos períodos

A Acme Manufacturing Company firmou um contrato para entrega de janelas de casa para os próximos seis meses. As demandas para cada mês são 100, 250, 190, 140, 220 e 110 unidades, respectivamente.

O custo de produção por janela varia de mês para mês, dependendo do custo da mão-de-obra, do material e de utilidades. A Acme estima que o custo de produção por janela nos próximos seis meses seja 50, 45, 55, 48, 52 e 50 unidades monetárias, respectivamente.

Para aproveitar a vantagem das variações no custo de fabricação, a Acme pode optar por produzir mais do que o necessário em determinado mês e reter as unidades excedentes para entregar em meses posteriores. Entretanto, isso incorrerá em custos de armazenagem de 8 u.m. por janela, por mês, considerando o estoque no final do mês.

Desenvolva um modelo de PL para determinar a programação ótima de produção.

<br>

- Variáveis de decisão:
    - $x_i$: unidades produzidas no mês $i$
    - $I_i$: unidades deixadas em estoque no final do mês $i$
    - $i = 1,...,6$
- Função objetivo: minimizar o custo de produção e estoque
    - Custo total de produção: $50x_1 + 45x_2 + 55x_3 + 48x_4 + 52x_5 + 50x_6$
    - Custo total de estoque: $8(I_1 + I_2 + I_3 + I_4 + I_5 + I_6)$
    - Função objetivo:

```math
    \text{min } 50x_1 + 45x_2 + 55x_3 + 48x_4 + 52x_5 + 50x_6 + 8(I_1 + I_2 + I_3 + I_4 + I_5 + I_6)
```

- Restrições: para cada período temos: estoque inicial + quantidade produzida - estoque final = demanda
    - Demanda mês 1: $I_0 + x_1 - I_1 = 100$
    - Demanda mês 2: $I_1 + x_2 - I_2 = 250$
    - Demanda mês 3: $I_2 + x_3 - I_3 = 190$
    - Demanda mês 4: $I_3 + x_4 - I_4 = 140$
    - Demanda mês 5: $I_4 + x_5 - I_5 = 220$
    - Demanda mês 6: $I_5 + x_6 - I_6 = 110$
- Para o problema, $I_0 = 0$ porque a situação parte de zero de estoque inicial
- Para qualquer solução ótima, $I_6 = 0$
- Restrições de não-negatividade: $x_i, I_i \ge 0, i=1,...,6$


<br>
<br>

Minimizar

```math
    z = 50x_1 + 45x_2 + 55x_3 + 48x_4 + 52x_5 + 50x_6 + 8(I_1 + I_2 + I_3 + I_4 + I_5 + I_6)
```

sujeito a:
```math
\displaylines{
    I_0 + x_1 - I_1 = 100 \\
    I_1 + x_2 - I_2 = 250 \\
    I_2 + x_3 - I_3 = 190 \\
    I_3 + x_4 - I_4 = 140 \\
    I_4 + x_5 - I_5 = 220 \\
    I_5 + x_6 - I_6 = 110 \\
    x_i, I_i \ge 0, i=1,...,6 \\
    I_0 = 0
}
```

A solução ótima deste problema é: $z = 49980, (x_1, x_2, x_3, x_4, x_5, x_6) = (100, 440, 0, 140, 220, 110), I_2 = 190$

Isto é, somente no mês 2, a quantidade produzida de 440 unidades abrange a demanda para ambos os meses, 2 e 3




<br>

## Problemas de Alocação de Recursos

- Esta classe trata dos problemas de programação de atividades das empresas
- Aqui o objetivo é determinar como os recursos serão alocados de maneira a atender ao planejamento da empresa, minimizando a quantidade de recursos usados e observando as restrições de uso destes recursos
- Os recursos considerados podem ser funcionários, máquinas, ônibus, aeronaves etc.




<br>

## PPL Alocação de Pessoal

Um hospital trabalha com um atendimento variável em demanda durante as 24 horas do dia. O número mínimo de enfermeiros necessários em cada turno é apresentado abaixo:

| Turno | Horário       | Mín. Enfermeiros |
|-------|---------------|------------------|
| 1     | 08:00 - 12:00 | 50               |
| 2     | 12:00 - 16:00 | 60               |
| 3     | 16:00 - 20:00 | 50               |
| 4     | 20:00 - 00:00 | 40               |
| 5     | 00:00 - 04:00 | 30               |
| 6     | 04:00 - 08:00 | 20               |

<br>

O horário de trabalho de um enfermeiro é de 8 horas quando ele entra nos turnos 1, 2, 3, 4 e 6. O enfermeiro que entra no turno 4 recebe uma graticação de 50% sobre o salário e o enfermeiro que entra no turno 5 trabalha quatro horas.

Elabore um modelo de programação linear que minimiza o gasto com a mão-de-obra.

<br>

Variáveis de decisão:

- $x_i$: número de enfermeiros que entram em serviço no início do turno $i = 1, ..., 6$

<br>

Função objetivo:

- O objetivo é minimizar o número total de trabalhadores
- Minimizar $z = x_1 + x_2 + x_3 + 1.5x_4 + 2x_5 + x_6$

<br>

Restrições por turno:

| Turno | Restrição          |
|-------|--------------------|
| 1     | $x_6 + x_1 \ge 50$ |
| 2     | $x_1 + x_2 \ge 60$ |
| 3     | $x_2 + x_3 \ge 50$ |
| 4     | $x_3 + x_4 \ge 40$ |
| 5     | $x_4 + x_5 \ge 30$ |
| 6     | $x_6 \ge 20$       |

<br>

Restrição de integralidade e não-negatividade: $x_i \in \mathbb{Z}^{+}, i = 1,...,6$

<br>
<br>

Minimizar

```math
    z = x_1 + x_2 + x_3 + 1.5x_4 + 2x_5 + x_6
```

sujeito a

```math
\displaylines{
    x_6 + x_1 \ge 50 \\
    x_1 + x_2 \ge 60 \\
    x_2 + x_3 \ge 50 \\
    x_3 + x_4 \ge 40 \\
    x_4 + x_5 \ge 30 \\
    x_6 \ge 20 \\
    x_i \in \mathbb{Z}^{+}, i = 1,...,6
}
```

<br>

A solução ótima é:

- $z = 145$
- $(x_1, x_2, x_3, x_4, x_5, x_6) = (20, 40, 10, 30, 0, 30)$




<br>


## PPL Corte

Trata do corte de peças padronizadas como rolos de papel, barras de metal etc. em tamanhos especificados pelos clientes. O objetivo é atender a demanda de maneira a minimizar o número de barras necessárias ou a perda de material.

<br>


### Exemplo

Uma fábrica de papel produz rolos de papel com largura de 10 a 20 m. Pedidos especiais de clientes com larguras diferentes são produzidos pelo corte padronizado de rolos. Um pedido está expresso na tabela abaixo:

| Pedido | Largura Desejada | Qtd. de Rolos |
|--------|------------------|---------------|
| 1      | 5                | 10000         |
| 2      | 7                | 30000         |
| 3      | 9                | 20000         |

Deseja-se determinar o esquema de corte com perda mínima.

<br>

A formulação do PPL requer a identificação dos possíveis padrões de corte.

| Largura | $x_1$ | $x_2$ | $x_3$ | $x_4$ | $x_5$ | $x_6$ | $x_7$ | $x_8$ | $x_9$ |
|---------|-------|-------|-------|-------|-------|-------|-------|-------|-------|
| 5       | 2     | 0     | 0     | 4     | 2     | 2     | 1     | 0     | 0     |
| 7       | 0     | 1     | 0     | 0     | 1     | 0     | 2     | 1     | 0     |
| 9       | 0     | 0     | 1     | 0     | 0     | 1     | 0     | 1     | 2     |
| Perda   | 0     | 3     | 1     | 0     | 3     | 1     | 1     | 4     | 2     |

- $x_1, x_2, x_3$ - rolo de 10 m
- restante - rolo de 20 m

<br>

Variáveis de decisão:

- $x_i$: quantidades de rolo cortado segundo o padrão $i = 1,2,...,9$

<br>

Restrições:

- Demanda 5m: $2x_1 + 4x_4 + 2x_5 + 2x_6 + x_7 \ge 10000$
- Demanda 7m: $x_2 + x_5 + 2x_7 + x_8 \ge 30000$
- Demanda 9m: $x_3 + x_6 + x_8 + 2x_9 \ge 20000$

<br>

Função objetivo:

- O objetivo é minimizar a quantidade em papel (em área)
- Minimizar $z = 10(x_1 + x_2 + x_3) + 20(x_4 + x_5 + x_6 + x_7 + x_8 + x_9)$
- Outro objetivo é minimizar a perda de papel na largura
- Minimizar $z = 3x_2 + x_3 + 3x_5 + x_6 + x_7 + 4x_8 + 2x_9$

<br>

Solução:

- $x_3 = 20000$
- $x_7 = 15000$




<br>

## PPL Empacotamento

Há um conjunto de contêineres e outro de itens a serem alocados a esses contêineres. Sabe-se que cada contêiner $i$ tem capacidade $cap_i$ e que cada item $j$ tem um peso $w_j$. O objetivo é determinar o número mínimo de contêineres necessário para empacotar todos os itens.

Considere:

- $C$: conjunto de contêineres
- $I$: conjunto dos itens
- $w_j$: peso do item $j$
- $cap_i$: capacidade do contêiner $i$

<br>

Minimizar

```math
\displaylines{
    \text{min } \sum_{i \in C} y_i
}
```

sujeito a:

```math
\displaylines{
    \sum_{i \in C} x_{ij} = 1, \forall j \in I \\
    \sum_{i \in C} w_{j}x_{ij} \le cap_{i}y_{i}, \forall i \in C \\
    x_{ij} \in \{ 0,1 \}, \forall i \in C, \forall j \in I \\
    y_i \in \{ 0,1 \}, \forall i \in C
    
    
}
```




<br>

## PPL Planejamento Urbano

Uma cidade aprovou uma melhoria da base de cobrança de impostos que prevê a condenação de uma área habitacional do centro da cidade e sua substituição por um conjunto habitacional moderno. O projeto envolve duas fases: demolição das casas aqué do padrão e construção do novo conjunto urbano.

- Um total de 300 casas podem ser demolidas. Cada casa ocupa 0,25 acres. O custo de demolição é de $2000.
- Os tamanhos dos lotes para unidades simples, duplas, triplas e quádruplas são de 0.18, 0.28, 0.4 e 0.5 acres, respectivamente. Ruas e espaços reservados ocupam 15% da área disponível.
- As unidades triplas e quádruplas devem somar, no mínimo, 25% do total, as simples e duplas devem representar 20% e 10%, no mínimo, respectivamente.
- O imposto cobrado por unidade domiciliar simples, duplas, triplas e quádruplas é de $1000, $1900, $2700 e $3400, respectivamente.
- O custo de construção por unidade domiciliar simples, dupla, tripla e quádruplas é de $50K, $70K, $130K e $160K, respectivamente.
- O financiamento acordado com o banco é de, no máximo, $15M

Quantas unidades de cada tipo devem ser construídas para maximizar a arrecadação de impostos?

<br>

Variáveis de decisão:

- $x_1$ - nº unid. simples
- $x_2$ - nº unid. duplas
- $x_3$ - nº unid. triplas
- $x_4$ - nº unid. quádruplas
- $x_5$ - nº casas antigas a demolir

<br>

Função objetivo: maximizar o ganho com impostos:

```math
    \text{max } z = 1000x_1 + 1900x_2 + 2700x_3 + 3400x_4
```

<br>

Restrição de disponibilidade do terreno

- Disponibilidade do terreno: área para novas casas $\le$ área disponível
- Área para novas casas: $0.18x_1 + 0.28x_2 + 0.4x_3 + 0.5x_4$
- Área disponível: $0.85(0.25x_5) = 0.2125x_5$
- Restrição: $0.18x_1 + 0.28x_2 + 0.4x_3 + 0.5x_4 \le 0.2125x_5$
- Número de casas disponíveis para demolição: $x_5 \le 300$

Restrições de limitação do número de unidades de cada tipo:

- Unidades simples: $x_1 \ge 0.2(x_1 + x_2 + x_3 + x_4)$
- Unidades duplas: $x_2 \ge 0.1(x_1 + x_2 + x_3 + x_4)$
- Unidades triplas e quádruplas: $x_3 + x_4 \ge 0.25(x_1 + x_2 + x_3 + x_4)$

Restrições de custos: $50x_1 + 70x_2 + 130x_3 + 160x_4 + 2x_5 \le 15000$

Não-negatividade: $x_1,x_2,x_3,x_4,x_4 \ge 0$

<br>

Solução:

- $z = 343,965$
- $(x_1,x_2,x_3,x_4,x_5) = (35.83, 98.53, 44.79, 0, 244.49)$


























