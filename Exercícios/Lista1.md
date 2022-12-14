# Lista 1 - Modelagem

### Lista de conteúdos

- [Exercício 1](#exercício-1)
- [Exercício 2](#exercício-2)
- [Exercício 3](#exercício-3)
- [Exercício 4](#exercício-4) (incompleto)
- [Exercício 5](#exercício-5) (incompleto)
- [Exercício 6](#exercício-6)
- [Exercício 7](#exercício-7)

<br>

# Exercício 1

Uma empresa foi contratada para produzir dois produtos, A e B, nos meses de junho, julho e agosto. A capacidade total de produção (em horas) varia mensalmente, conforme apresentado a seguir:

|                        | Junho | Julho | Agosto |
|------------------------|-------|-------|--------|
| Demanda para A (unid.) | 500   | 500   | 750    |
| Demanda para B (unid.) | 1000  | 1200  | 1200   |
| Capacidade (horas)     | 3000  | 3500  | 3000   |

As taxas de produção em unidades por hora são 1,25 e 1 para os produtos A e B, respectivamente. Toda a demanda deve ser atendida. Contudo, a demanda para um mês posterior pode ser completada com a produção de um anterior. Para qualquer carregamento de um mês para o seguinte são cobrados custos de permanência no estoque de $0,90 e $0,75 por unidade por mês para os produtos A e B, respectivamente. Os custos unitários de produção para os dois produtos são $30 e $28 para A e B, respectivamente.

**Determine a programação ótima de produção dos dois produtos.**

<br>

## Solução

Variáveis de decisão:

- $x_{A1}$ (unid. do produto A produzidas em junho)
- $x_{A2}$ (unid. do produto A produzidas em julho)
- $x_{A3}$ (unid. do produto A produzidas em agosto)

<br>

- $x_{B1}$ (unid. do produto B produzidas em junho)
- $x_{B2}$ (unid. do produto B produzidas em julho)
- $x_{B3}$ (unid. do produto B produzidas em agosto)

<br>

- $I_{A1}$ (unid. do produto A no estoque em junho)
- $I_{A2}$ (unid. do produto A no estoque em julho)
- $I_{A3}$ (unid. do produto A no estoque em agosto)

<br>

- $I_{B1}$ (unid. do produto B no estoque em junho)
- $I_{B2}$ (unid. do produto B no estoque em julho)
- $I_{B3}$ (unid. do produto B no estoque em agosto)

<br>

Função objetivo:

- Custo de produção: $30*(x_{A1} + x_{A2} + x_{A3}) + 28*(x_{B1} + x_{B2} + x_{B3})$
- Custo de estoque: $0,9*(I_{A1} + I_{A2} + I_{A3}) + 0,75*(I_{B1} + I_{B2} + I_{B3})$
- Função objetivo:

```math
\displaylines{
    \text{min } z = & 30*(x_{A1} + x_{A2} + x_{A3}) + 28*(x_{B1} + x_{B2} + x_{B3})\\
    & + 0,9*(I_{A1} + I_{A2} + I_{A3}) + 0,75*(I_{B1} + I_{B2} + I_{B3})
}
```

<br>

Restrições:

| Restrição    | Junho                             | Julho                             | Agosto                         |
|--------------|-----------------------------------|-----------------------------------|--------------------------------|
| Demanda de A | $I_{A1} + x_{A1} - I_{A2} = 500$  | $I_{A2} + x_{A2} - I_{A3} = 500$  | $I_{A3} + x_{A3} = 750$        |
| Demanda de B | $I_{B1} + x_{B1} - I_{B2} = 1000$ | $I_{B2} + x_{B2} - I_{B3} = 1200$ | $I_{B3} + x_{B3} = 1200$       |
| Capacidade   | $1,25x_{A1} + x_{B1} \le 3000$    | $1,25x_{A2} + x_{B2} \le 3500$    | $1,25x_{A3} + x_{B3} \le 3000$ |

<br>

- $x_{jk} \ge 0$
- $I_{jk} \ge 0$


---

<br>
<br>

# Exercício 2

Em grande parte dos campuses universitários, os departamentos contratam alunos bolsistas para prestar alguns serviços. A necessidade destes serviços varia durante o horário normal de trabalho (8h às 17h).

Em um departamento, o número mínimo necessário de estudantes é dois entre 8h e 10h, três entre 10h01 e 11h, quatro entre 11h01 e 13h e três entre 13h01 e 17h.

Cada estudante trabalha por três horas consecutivas (exceto os que começam às 15h01 e às 16h01, que trabalham duas horas e uma hora, respectivamente).

Considere que nenhum dos estudantes deve começar a trabalhar na hora do almoço (meio-dia).

**Determine o número mínimo de estudantes que este departamento deve contratar e especifique a que hora do dia cada um deve se apresentar para trabalhar.**

<br>

## Solução

Variáveis de decisão:

- $x_{8}$: alunos que começaram a trabalhar 8h
- $x_{9}$: alunos que começaram a trabalhar 9h
- $x_{10}$: alunos que começaram a trabalhar 10h
- $x_{11}$: alunos que começaram a trabalhar 11h
- $x_{12}$: alunos que começaram a trabalhar 12h
- $x_{13}$: alunos que começaram a trabalhar 13h
- $x_{14}$: alunos que começaram a trabalhar 14h
- $x_{15}$: alunos que começaram a trabalhar 15h
- $x_{16}$: alunos que começaram a trabalhar 16h

<br>

Função objetivo:

```math
\displaylines{
    \text{min } z = x_{8} + x_{9} + x_{10} + x_{11} + x_{12} + x_{13} + x_{14} + x_{15} + x_{16}
}
```

<br>

Restrições:

| Restrição          | Fórmula                          |
|--------------------|----------------------------------|
| Meio-dia           | $x_{12} = 0$                     |
| Min. alunos às 8h  | $x_{8} \ge 2$                    |
| Min. alunos às 9h  | $x_{8} + x_{9} \ge 2$            |
| Min. alunos às 10h | $x_{8} + x_{9} + x_{10} \ge 3$   |
| Min. alunos às 11h | $x_{9} + x_{10} + x_{11} \ge 4$  |
| Min. alunos às 12h | $x_{10} + x_{11} \ge 4$          |
| Min. alunos às 13h | $x_{11} + x_{13} \ge 3$          |
| Min. alunos às 14h | $x_{13} + x_{14} \ge 3$          |
| Min. alunos às 15h | $x_{13} + x_{14} + x_{15} \ge 3$ |
| Min. alunos às 16h | $x_{14} + x_{15} + x_{16} \ge 3$ |

---

<br>
<br>

# Exercício 3

Uma empresa produz televisão em 3 fábricas: São Paulo, João Pessoa e Manaus. Os pontos principais de revenda, com as respectivas encomendas mensais são:

| Revenda        | Demanda (unid.) |
|----------------|-----------------|
| Rio de Janeiro | 6000            |
| Salvador       | 5000            |
| Aracajú        | 3000            |
| Maceió         | 4000            |
| Recife         | 3000            |

<br>

A produção máxima mensal em cada fábrica é:

| Fábrica     | Capacidade (unid.) |
|-------------|--------------------|
| São Paulo   | 10000              |
| João Pessoa | 5000               |
| Manaus      | 6000               |

<br>

O custo de transporte das fábricas até as revendas é dado pelo quadro abaixo:

| De \ Para         | (1) Rio de Janeiro | (2) Salvador | (3) Aracajú | (4) Maceió | (5) Recife |
|-------------------|--------------------|--------------|-------------|------------|------------|
| (1) São Paulo     | 1000               | 2000         | 3000        | 3500       | 4000       |
| (2) João Pessoa   | 4000               | 2000         | 1500        | 1200       | 1000       |
| (3) Manaus        | 6000               | 4000         | 3500        | 3000       | 2000       |

<br>

Determinar o número de unidades produzidas em cada fábrica e entregues a cada revenda, a fim de minimizar o custo de transporte.

<br>

## Solução

Variáveis de decisão:
- $x_{1i}$ = unidades que saem de São Paulo
- $x_{2i}$ = unidades que saem de João Pessoa
- $x_{3i}$ = unidades que saem de Manaus
- $x_{j1}$ = unidades que chegam no Rio de Janeiro
- $x_{j2}$ = unidades que chegam em Salvador
- $x_{j3}$ = unidades que chegam em Aracajú
- $x_{j4}$ = unidades que chegam em Maceió
- $x_{j5}$ = unidades que chegam em Recife

<br>

Função objetivo:

```math

 \displaylines{\text{min } z = 1000x_{11} + 2000x_{12} + 3000x_{13} + 3500x_{14} + 4000x_{15}\\
+ 4000x_{21} + 2000x_{22} + 1500x_{23} + 1200x_{24} + 1000x_{25}\\
+ 6000x_{31} + 4000x_{32} + 3500x_{33} + 3000x_{34} + 2000x_{35}}

```

<br>

Restrições:

| Restrição                | Fórmula                                                |
|--------------------------|--------------------------------------------------------|
| Capacidade (São Paulo)   | $x_{11} + x_{12} + x_{13} + x_{14} + x_{15} \le 10000$ |
| Capacidade (João Pessoa) | $x_{21} + x_{22} + x_{23} + x_{24} + x_{25} \le 5000$  |
| Capacidade (Manaus)      | $x_{31} + x_{32} + x_{33} + x_{34} + x_{35} \le 6000$  |
| Demanda (Rio de Janeiro) | $x_{11} + x_{21} + x_{31} \le 6000$                    |
| Demanda (Salvador)       | $x_{12} + x_{22} + x_{32} \le 5000$                    |
| Demanda (Aracajú)        | $x_{13} + x_{23} + x_{33} \le 3000$                    |
| Demanda (Maceió)         | $x_{14} + x_{24} + x_{34} \le 4000$                    |
| Demanda (Recife          | $x_{15} + x_{25} + x_{35} \le 3000$                    |

---

<br>
<br>

# Exercício 4

Uma empresa imobiliária está desenvolvendo um projeto habitacional de casas de aluguel e um espaço para o comércio varejista. O projeto habitacional consiste em apartamentos funcionais, apartamentos duplex e unidades residenciais simples.

A demanda máxima de inquilinos potenciais é estimada em 500 apartamentos funcionais, 300 apartamentos duplex e 250 unidades residenciais simples, mas o número de apartamentos duplex deve ser igual a no mínimo 50% do número de apartamentos funcionais e unidades residenciais simples.

O espaço para o comércio varejista é proporcional ao número de unidades residenciais à razão de no mínimo 10 pés², 15 pés² e 18 pés² para apartamentos funcionais, apartamentos duplex e unidades residenciais simples, respectivamente.

Contudo, a disponibilidade de terreno limita o espaço de comércio varejista a não mais do que 10.000 pés².

A receita mensal de aluguéis é estimada em $600, $750 e $1200 para apartamentos funcionais, apartamentos duplex e unidades residenciais simples, respectivamente.

O aluguel de espaços para comércio varejista é $100/pés².

**Determine a área ótima de espaço para comércio varejista e o número de unidades residenciais.**

<br>

## Solução

---

<br>
<br>

# Exercício 5

Um fabricante de tiras metálicas recebeu um pedido para produzir 2000 tiras de tamanho 2cm x 4cm e 1000 tiras de 4cm x 7cm.

As tiras podem ser produzidas a partir de chapas maiores disponíveis nos tamanhos de 10cm x 3000cm e 11cm x 2000cm.

O departamento técnico encarregado de planejar o atendimento ao pedido decidiu que os padrões de corte mostrados na figura a seguir são adequados para produzir as tiras encomendadas.

![image](https://user-images.githubusercontent.com/23441506/198317285-0a9c4aca-daf5-4ba6-b8de-4dc3f1a49a7f.png)

**Formule um modelo de programação linear que permita minimizar o material usado no atendimento à encomenda.**

<br>

## Solução

---

<br>
<br>

# Exercício 6

Um fabricante de rações quer determinar a fórmula mais econômica de certa ração. A composição nutritiva dos ingredientes disponíveis no mercado e os seus custos são descritos na Tabela 1. O fabricante deve entregar 1000 quilos de ração por dia e garantir que esta contenha no mínimo 0,8% e no máximo 1,2% de cálcio, não menos do que 22% de proteína e no máximo 20% de carboidratos.

| Nutrientes \ Ingredientes | Soja | Milho | Cana |
|---------------------------|------|-------|------|
| Cálcio                    | 0,2% | 1%    | 3%   |
| Proteína                  | 50%  | 9%    | -    |
| Carboidratos              | 0,8% | 2%    | 2%   |
| Custo (R$/kg)             | 15   | 20    | 8    |

Tabela 1. Composição de nutrientes por alimento.

<br>

## Solução

Variáveis de decisão:

- $x_{soja}$ (kg de soja)
- $x_{milho}$ (kg de milho)
- $x_{cana}$ (kg de cana)

<br>

Função objetivo:

```math
\displaylines{
    \text{min } z = 15x_{soja} + 20x_{milho} + 8x_{cana}
}
```

<br>

Restrições:

| Restrição            | Fórmula                                                     |
|----------------------|-------------------------------------------------------------|
| Demanda (kg)         | $x_{soja} + x_{milho} + x_{cana} = 1000$                    |
| Cálcio (por kg)      | $8 \le 0,002x_{soja} + 0,01x_{milho} + 0,03x_{cana} \le 12$ |
| Proteína (por kg)    | $0,5x_{soja} + 0,09x_{milho} \ge 22$                        |
| Carboidrato (por kg) | $0,008x_{soja} + 0,02x_{milho} + 0,02x_{cana} \le 200$      |



---

<br>
<br>

# Exercício 7

Uma determinada empresa está interessada em maximizar o lucro mensal proveniente de quatro de seus produtos, designados por I, II, III e IV. Para fabricar esses produtos, ela utiliza dois tipos de máquinas (M1 e M2) e dois tipos de mão-de-obra (MO1 e MO2), que têm as seguintes disponibilidades:

Tempo disponível das máquinas por mês:

| Máquina | Tempo (hora/mês) |
|---------|------------------|
| M1      | 80               |
| M2      | 20               |
| M3      | 40               |

<br>

Número de máquina-hora por unidade de cada produto:

| Máquina \ Produtos | I | II | III | IV |
|--------------------|---|----|-----|----|
| M1                 | 5 | 4  | 8   | 9  |
| M2                 | 2 | 6  | -   | 8  |
| M3                 | 3 | 4  | 6   | 2  |

<br>

Tempo disponível da mão de obra por mês:

| Mão de obra | Tempo (homens-hora/mês) |
|-------------|-------------------------|
| MO1         | 120                     |
| MO2         | 160                     |

<br>

Número de homens-hora por unidade de cada produto:

| MDO \ Produtos | I | II | III | IV |
|----------------|---|----|-----|----|
| MO1            | 2 | 4  | 2   | 8  |
| MO2            | 7 | 3  | -   | 7  |

<br>

Produtos:

| Descrição \ Produtos                 | I     | II   | III  | IV   |
|--------------------------------------|-------|------|------|------|
| Potencial máx. de vendas (unid./mês) | 70    | 60   | 40   | 20   |
| Lucro ($/unid.)                      | 10,00 | 8,00 | 9,00 | 7,00 |

<br>

**Faça o planejamento da produção mensal da empresa objetivando maximizar o lucro.**

<br>

## Solução

Variáveis de decisão:

- $x_{1}$: unidades do produto I
- $x_{2}$: unidades do produto II
- $x_{3}$: unidades do produto III
- $x_{4}$: unidades do produto IV

<br>

Função objetivo:

```math
\displaylines{
    \text{max } z = 10x_{1} + 8x_{2} + 9x_{3} + 7x_{4}
}
```

<br>

Restrições:

| Restrição           | Fórmula                                     |
|---------------------|---------------------------------------------|
| Potencial (prod. 1) | $x_{1} \le 70$                              |
| Potencial (prod. 2) | $x_{2} \le 60$                              |
| Potencial (prod. 3) | $x_{3} \le 40$                              |
| Potencial (prod. 4) | $x_{4} \le 20$                              |
| Tempo máq. 1        | $5x_{1} + 4x_{2} + 8x_{3} + 9x_{4} \le 80$  |
| Tempo máq. 2        | $2x_{1} + 6x_{2} + 8x_{4} \le 20$           |
| Tempo máq. 3        | $3x_{1} + 4x_{2} + 6x_{3} + 2x_{4} \le 40$  |
| Mão de obra 1       | $2x_{1} + 4x_{2} + 2x_{3} + 8x_{4} \le 120$ |
| Mão de obra 2       | $7x_{1} + 3x_{2} + 7x_{4} \le 160$          |
