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




## Problema do Transporte

[imagem]


### Modelagem

Dados conhecidos:

- Dados conhecidos:
	- $a_{i}, i = 1, ..., m$ é a quantidade de determinado bem produzido por $m$ fábricas
	- $b_{j}, j = 1, ..., n$ é a quantidade da mercadoria consumida em $n$ destinos

- Variáveis de decisão: $x_{ij}$ é a quantidade de mercadoria a ser transportada de $i$ para $j$, $x_{ij} \ge 0, \forall i, j$

- Função objetivo: [fórmula]