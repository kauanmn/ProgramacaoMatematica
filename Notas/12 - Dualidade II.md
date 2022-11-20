# Programação Matemática - Aula 12

<br>

## Usando as CCF para resolver um PPL

#### Primal

$\text{min } z = 2x_1 + 3x_2 + 4x_3 + 2x_4$

Sujeito a:

```math
\displaylines{
    x_1 + x_2 - 2x_3 + 2x_4 \ge 1 \text{ } (w_1) \\
    2x_1 - 2x_2 - x_3 + x_4 \ge 1 \text{ } (w_2) \\
    x_1,x_2,x_3,x_4 \ge 0
}
```

<br>

#### Dual

$\text{max } w_1 + w_2$

Sujeito a:

```math
\displaylines{
    w_1 + 2w_2 \le 2 \text{ } (x_1) \\
    w_1 - 2w_2 \le 3 \text{ } (x_2) \\
    -2w_1 + w_2 \le 4 \text{ } (x_3) \\
    2w_1 + w_2 \le 2 \text{ } (x_4) \\
    w_1, w_2 \ge 0
}
```




<br>

#### Forma Padrão

#### Primal

$\text{min } z = 2x_1 + 3x_2 + 4x_3 + 2x_4$

Sujeito a:

```math
\displaylines{
    x_1 + x_2 - 2x_3 + 2x_4 - x_5 = 1 \text{ } (w_1) \\
    2x_1 - 2x_2 - x_3 + x_4 - x_6 = 1 \text{ } (w_2) \\
    x_1,x_2,x_3,x_4,x_5,x_6 \ge 0
}
```

<br>

#### Dual

$\text{max } w_1 + w_2$

Sujeito a:

```math
\displaylines{
    w_1 + 2w_2 + w_3 = 2 \text{ } (x_1) \\
    w_1 - 2w_2 + w_4 = 3 \text{ } (x_2) \\
    -2w_1 + w_2 + w_5 = 4 \text{ } (x_3) \\
    2w_1 + w_2 + w_6 = 2 \text{ } (x_4) \\
    w_1, w_2, w_3, w_4, w_5, w_6 \ge 0
}
```

<br>

A relação entre as variáveis primais e duais e a solução ótima do dual são:

- Variáveis naturais do primal: $\\{ x_1, x_2, x_3, x_4 \\}$
- Variáveis de folga do dual: $\\{ w_3, w_4, w_5, w_6 \\}$
- Variáveis de folga do primal: $\\{ x_5, x_6 \\}$
- Variáveis naturais do dual: $\\{ w_1, w_2 \\}$

<br>

Solução ótima do dual:

- $w^\ast = 4/3$
- $(w_1,w_2,w_3,w_4,w_5,w_6)=(2/3,2/3,0,11/3,14/3,0)$

<br>

![image](https://user-images.githubusercontent.com/23441506/202877836-5ae9620e-6cf4-411e-8417-ccff81c59f65.png)

<br>

A solução ótima do primal decorre do sistema:

```math
\displaylines{
    x_1 + 2x_4 = 1 \\
    2x_1 + x_4 = 1
}
```

Solução do sistema: $x_1 = x_4 = 1/3$

Solução ótima do primal:

- $z^\ast = 4/3$
- $(x_1,x_2,x_3,x_4,x_5,x_6) = (1/3,0,0,1/3,0,0)$




<br>

## Exercício

Seja o seguinte PPL correspondendo à produção de copos de vidro de 4 tipos diferentes:

$P : \text{max } z = 6x_1 + 10x_2 + 9x_3 + 20x_4$

Sujeito a:

1. $4x_1 + 9x_2 + 7x_3 + 10x_4 \le 600$ (horas no dep. modelagem)
2. $x_1 + x_2 + 3x_3 + 40x_4 \le 400$ (horas no dep. embalagem)
3. $3x_1 + 4x_2 + 2x_3 + x_4 \le 500$ (disponibilidade de vidro em kg)
4. $x_1,x_2,x_3,x_4 \ge 0$

Solução ótima:

- $z = 2800/3$
- $(x_1,x_2,x_3,x_4,x_5,x_6, x_7) = (400/3, 0, 0, 20/3, 0, 0, 280/3)$


#### Exercício:

- Encontre o dual do problema
- Use a solução ótima do primal dada e as CCF para encontrar a solução ótima do problema dual
- Interprete o problema dual e as folgas do primal e dual




<br>

## Algoritmo Dual Simplex

#### Primal
$\text{min } z = 10x_1 + 4x_2$

Sujeito a:

```math
\displaylines{
    3x_1 + 2x_2 \ge 60 \\
    6x_1 + 2x_2 \ge 84 \\
    3x_1 + 6x_2 \ge 72 \\
    x_1,x_2 \ge 0
}
```

<br>

#### Dual

$\text{max } y = 60w_1 + 84w_2 + 72w_3$

Sujeito a:

```math
\displaylines{
    3w_1 + 6w_2 + 3w_3 \le 10 \\
    2w_1 + 2w_2 + 6w_3 \le 4 \\
    w_1,w_2,w_3 \ge 0
}
```

<br>

Para representar o primal no quadro, formando a matriz identidade, as equações das restrições são multiplicadas por -1.

![image](https://user-images.githubusercontent.com/23441506/202879139-f8ee002d-d024-493b-9c28-28eee5572344.png)

<br>

- Escolhe-se o menor valor da coluna $b$. A variável correspondente sairá da base
- O teste da razão deve ser feito olhando a transposição da matriz. Deve-se dividir o valor das variáveis na linha da função objetivo pelo elemento correspondente na linha pivô
- Deve-se considerar os módulos das razões. Os coeficientes positivos da matriz são desconsiderados
- $x_4$ deixará a base e $x_1$ entrará

![image](https://user-images.githubusercontent.com/23441506/202879621-0bc744c0-b4da-470b-b348-10e75968244c.png)

<br>

$x_5$ deixará a base e $x_2$ entrará.

![image](https://user-images.githubusercontent.com/23441506/202879676-c8790ab5-5df6-481f-8134-6acbd19a6cb3.png)

<br>

$x_3$ deixará a base e $x_5$ entrará

![image](https://user-images.githubusercontent.com/23441506/202879703-3ad019b8-a558-4b48-aea0-8a12d6920d60.png)

<br>

- Pelas CCF, as relações entre as variáveis duais e primais são:
    - $x_1 \cdot w_4 = 0$
    - $x_2 \cdot w_5 = 0$
    - $x_3 \cdot w_1 = 0$
    - $x_4 \cdot w_2 = 0$
    - $x_5 \cdot w_3 = 0$
- Sabe-se que $w_3, w_4, w_5 = 0$, pois são complementares às VB da solução ótima do primal.
- As demais variáveis podem ser encontradas na linha da função objetivo e na coluna da variável primal correspondente:

$w_1 = 0.67, w_2 = 1.33$




<br>


## Exercício

Considere o seguinte PPL da dieta:

![image](https://user-images.githubusercontent.com/23441506/202880383-bc9ac07b-19fc-42c7-97e8-bb3dc5960c13.png)

<br>

- Modele o problema e ache as soluções primal e dual através do dual simplex
- Interprete as soluções
