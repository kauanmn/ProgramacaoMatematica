# Programação Matemática - Aula 01

## Pesquisa Operacional

**PESQUISA OPERACIONAL** é o conjunto de técnicas e métodos matemáticos empregados para auxiliar a tomada de decisões em organizações.

- É uma abordagem científica para tomada de decisão em que se busca determinar uma condição ótima de operação de um sistema que, usualmente, requer a alocação de recursos escassos

- A natureza da organização (sistema) pode ser fincanceira, industrial, militar, governamental etc.

- Os métodos de PO podem ser divididos em:
	- **Programação Matemática:** programação linear, programação não-linear, programação inteira, programação dinâmica, otimização em redes
	- **Métodos estatísticos:** teoria de filas, teoria de estoques, teoria de jogos, teoria de decisão e simulação
	- **Métodos Heurísticos**

- As técnicas e algoritmos destinam-se a estruturar e a solucionar os modelos quantitativos que podem ser expressos matematicamente

- O termo "programação" diz respeito a planejamento, programação de atividades



## Breve Histórico

Segundo Lins e Calôba (2004):

- O desenvolvimento concomitante de duas técnicas motivaram o desenvolvimento da PL
- John von Neumann em 1928: publicou o teorema central da teoria dos
 jogos, mais tarde formulado por meio da PL interpretado à luz da teoria da dualidade

- Análise de insumo-produto, publicado por Leontief, em 1936, "_Quantitative input and output relations in the economic systems of the United States_".

- Ambas tinham interesse central na interação entre jogos e economia

- Em 1939, o matemático e economista Kantorovitch formulou um PPL para organização e planejamento de produção. Em 1941, Hitchock fomulou o PPL do transporte. Em 1945, Stigler formulou o PPL da dieta.

- Um grupo de cientistas (entre eles George Dantizig) foi chamado pela força aérea americana, durante a Segunda Guerra, a fim de integrar os objetivos e necessidades das atividades militares. Em 1947, a equipe desenvolveu o método simplex.

- Em 1951, Trucker obteve os primeiros resultados no desenvolvimento da teoria da dualidade

- Em 1952 Charnes e Lemke desenvolveram o simplex revisado

- O desenvolvimento dos computadores potentes foi essencial para uma disseminação da PL e da PO




## Tomada de Decisão

- A programação matemática, na prática, é direcionada ao apoio da tomada de decisão no gerenciamento de grande porte.

- A técnica permite a modelagem de inter-relações entre variáveis que dificilmente seriam visíveis de forma intuitiva

- Com a utilização de programas de computadores, as técnicas podem examinar inúmeras configurações viáveis do problema proposto e selecionar, dentro de certos critérios, as melhores

A tomada de decisão frequentemente envolve os seguintes passos:

1. Identificação do problema
2. Formulação do problema
3. Representação adequada das variáveis e restrições do problema
4. Levantamento das alternativas viáveis
5. Estabelecimento de critérios de avaliação das alternativas
6. Comparação das alternativas
7. Análise de impacto da tomada de decisão




## Construção de modelos

**MODELO** pode ser definido como a esquematização (geralmente simplificada) de um sistema complexo

Processo:

- Passo 1: Definição do problema
- Passo 2: Formulação e Construção do Modelo
- Passo 3: Validação do Modelo (se satisfatório, ir para o passo 5)
- Passo 4: Reformulação do Modelo (ir para o passo 3)
- Passo 5: Aplicação do modelo




## Características dos modelos

Consiste nos seguintes elementos:

- **VARIÁVEIS DE DECISÃO:** são as variáveis consideradas relevantes ao problema, passíveis de quantificação e disponíveis.

- **FUNÇÃO OBJETIVO:** é uma função, produto de coeficientes pelas variáveis de decisão, que descreve as relações que se deseja otimizar no problema, como maximização do lucro ou minimização dos custos.

- **RESTRIÇÕES:** correspondem aos elementos restritivos que todo problema possui, como limitação de disponibilidade de matéria-prima ou de recursos de capital para investimento.




## Definição de Problema de Programação Linear

**PROBLEMA DE PROGRAMAÇÃO LINEAR** é um problema de otimização que consiste em achar os valores das variáveis que minimizam (ou maximizam) a função objetivo sujeito a um conjunto de restrições




## Exemplo - Problema de Produção de Tintas

A empresa _Reddy Mikks_ produz tintas para interiores e exteriores com matérias-primas $M_1$ e $M_2$. Os valores são expressos em toneladas.


|               | Tintas p/ Exteriores | Tintas p/ Interiores | Disp. Máx. |
|---------------|----------------------|----------------------|------------|
| $M_1$         | 6                    | 4                    | 24         |
| $M_2$         | 1                    | 2                    | 6          |
| Lucro ($1000) | 5                    | 4                    |            |

Uma pesquisa de mercado indica que a demanda diária de tintas para interiores não pode ultrapassar a de tintas para exteriores por mais de 1 tonelada. Além disso, a demanda diária máxima de tintas para interiores é de 2 t.

A empresa deseja determinar o mix ótimo de produtos de tintas para interiores e exteriores que maximizem o lucro total diário.


### Modelagem

1. Escolha das variáveis de decisão:

- $x_{1}$: toneladas de tinta para exterior produzidas diariamente
- $x_{2}$: toneladas de tinta para interior produzidas diariamente

2. Elaboração da função objetivo:

```math
	\text{max } z = 5x_{1} + 4x_{2}
```

3. Formulação das restrições (limitações de matéria-prima e de demanda):

- Restrição associada ao limite de uso diário de $M_{1}$: $6x_{1} + 4x_{2} \le 24$
- Restrição associada ao limite de uso diário de $M_{2}$: $x_{1} + 2x_{2} \le 6$
- Restrição de demanda de tintas: $x_{2} - x_{1} \le 1$
- Restrição de demanda de mercado: $x_{2} \le 2$


4. Formulação das restrições de não negatividade: $x_{1} \ge 0, x_{2} \ge 0$




## Modelando Problemas Típicos de PL

- Definição das atividades: define-se as atividades que participam do processo
- Definição de recursos: determinação dos recursos usados ou produzidos em cada atividade
- Cálculo dos coeficientes de insumo/produção: deve-se estabelecer as relações entre as atividades e os recursos
- Determinação das condições externas: como os recursos são limitados, cumpre determinar a quantidade de cada recurso disponível ao processo
- Formalização do modelo




## Problema de Programação Linear

- A função objetivo é da forma $F(x) = c_{1}x_{1} + \cdots + c_{n}x_{n} = \text{c}x$, onde $\text{c}$ é o vetor linha de $n$ constantes dadas (coeficientes de custo), isto é, uma função linear, produto de coeficientes dos custos pelas variáveis de decisão, que descreve as relações que se deseja otimizar

- As restrições são desigualdades lineares que correspondem aos elementos restritivos que todo problema possui, como limitação de disponibilidade de matéria-prima ou de recursos de capital para investimento

- Há ainda restrições de não negatividade das variáveis




## Formulação Algébrica - Forma Geral

Otimizar

[completar fórmula]

sujeito a:

[completar fórmulas]

Onde:

- $x_{j}$ é o nível de atividade da alternativa $j$ a ser determinado pela solução do PPL
- $c_{j}$ é o custo unitário da alternativa $j$
- $b_{i}$ é o valor limitante referente à restrição $i$
- $a_{ij}$ é a contribuição unitária da alternativa $j$ à restrição $i$




## Propriedades do Modelo de PL

- **Proporcionalidade**: a contribuição de cada variável deve ser diretamente proporcional ao valor da variável. Não se considera, por exemplo, economia de escala e nem custos iniciais de implantação.

- **Aditividade**: a contribuição total de todas as atividades deve ser a soma direta das contribuições individuais de cada variável. Isto implica em que, por exmeplo, o preço unitário de um alimento não pode variar condicionado a uma maior demanda de outro

- **Determinismo**: todos os coeficientes da função objetivo e das restrições do modelo de PL são determinísticos, ou seja, constantes conhecidas. Em essência, os coeficientes em PL são aproximações do valor médio das contribuições de probabilidade