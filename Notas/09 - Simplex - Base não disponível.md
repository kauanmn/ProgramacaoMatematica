# Programação Matemática - Aula 09

<br>

## Quando a base não está disponível

- O PPL na forma padrão nem sempre equivale a forma padrão.
- Se não possuir uma SBV inicial, é preciso transformar o problema e buscar esta solução.
- Isto ocorre normalmente quando a região de viabilidade não inclui a origem


<br>

### Exemplo

```math
\text{min } -3x_1 - 5x_2
```

Sujeito a:

```math
\displaylines{
    x_1 \le 4 \\
    x_2 \le 6 \\
    3x_1 + 2x_2 \ge 18 \\
    x_1, x_2 \ge 0
}
```

<br>

#### Forma padrão

```math
\text{min } -3x_1 - 5x_2
```

Sujeito a:

```math
\displaylines{
    x_1 + x_3 = 4 \\
    x_2 + x_4 = 6 \\
    3x_1 + 2x_2 - x_5 = 18 \\
    x_1, x_2, x_3, x_4, x_5 \ge 0
}
```

<br>

Obviamente, não há nenhuma sequência em que o problema esteja na forma canônica.




<br>

## Métodos

Temos dois caminhos a adotar: descobrir uma base viável por um outro método qualqur e aplicar o simplex a partir desta base OU usar o próprio simplex da seguinte maneira:

- **Primeira fase**: o procedimento usa o simplex para buscar uma base viável
- **Segunda fase**: a partir da base calculada, o método simplex é aplicado tradicionalmente.

Existem dois métodos, ambos usando a ideia de "variáveis artificiais".

<br>
<br>

**VARIÁVEIS ARTIFICIAIS** são variáveis introduzidas na resolução do problema para que tenhamos a base viável inicial. Estas variáveis não possuem necessariamente ligação com a modelagem do problema.

O objetivo é eliminar as variáveis artificiais da base, chegando a uma primeira SBV do problema original.


<br>


### Exemplo

```math
\text{min } -3x_1 - 5x_2
```

Sujeito a:

```math
\displaylines{
    x_1 + x_3 = 4 \\
    x_2 + x_4 = 6 \\
    3x_1 + 2x_2 - x_5 + x^{a}_{1} = 18 \\
    x_1, x_2, x_3, x_4, x_5, x^{a}_{1} \ge 0
}
```

<br>

Agora a sequência de índices $\\{ 3,4,1^a \\}$ é uma base para o problema.




<br>

## Método Big M

Neste método, é adicionada uma penalidade grane às variáveis artificiais na função objetivo, colocando para elas um enorme coeficiente, representado por $M$.

Quando usamos o simplex para minimizar um problema em que existem variáveis extraordinariamente grandes na base, o método terá prioridade em trocá-las por outras com coeficientes menores.

<br>

Qual o valor de $M$ que devemos usar?

- $M$ deve ser suficientemente grande em relação aos coeficientes da função objetivo original.
- Ao mesmo tempo, visto que computadores são a principal ferramenta para resolver problemas de PL, não queremos que $M$ seja demasiadamente grande devido ao grave erro de arredondamento que pode resultar quando valores muito grandes são manipulados com valores muito pequenos
- No último exemplo, parece razoável estabelecer $M = 10$




<br>

### Exemplo de tableau simples

![image](https://user-images.githubusercontent.com/23441506/202055126-66ef2d64-77fe-4e5e-a516-5d380f6209c1.png)

Devem ser feitas transformações na linha $z$ para que o problema fique na forma canônica, ou seja, zerar o coeficiente de $x^{a}_{1}$.

Para isto, devemos somar as linhas das variáveis artificiais à linha da função objetivo: $L1' = L1 - 10L4$.

![image](https://user-images.githubusercontent.com/23441506/202057908-febe1eb7-83fa-4521-8187-3df320d4ed15.png)

$x_1$ entra na base e $x_3$ sai.

<br>

![image](https://user-images.githubusercontent.com/23441506/202058046-b93bafa8-3d15-4e31-8348-600320cb7545.png)

$x_2$ entra na base e $x^{a}_1$ sai.

<br>

![image](https://user-images.githubusercontent.com/23441506/202058129-bd65f5cd-b68a-409c-b2a4-206aa1b097d1.png)

As variáveis foram eliminadas da base!

$x_3$ entra na base e $x_4$ sai.

<br>

![image](https://user-images.githubusercontent.com/23441506/202058230-c9513b20-513e-4722-a1e0-347474482272.png)

$x_5$ entra na base e $x_3$ sai.

<br>

#### Quadro final

![image](https://user-images.githubusercontent.com/23441506/202058290-d652eeb8-810b-4a34-b89c-85a611be1c3d.png)




<br>

## Método das Duas Fases

Aqui é introduzida uma nova função objetivo que minimiza o número de variáveis artificiais existentes na base.

Como uma base real não possui qualquer variável artificial não nula, concluída a primeira fase, prosseguiremos normalmente com os cálculos com a função objetivo original do problema.

O nome do método está vinculado à existência de duas funções objetivo, uma para cada fase.

O novo PPL a ser criado terá mais uma função objetivo: $\text{min } q = x^{a}_{1} + x^{a}_{2} + \cdots$, correspondente à soma das variáveis artificiais incluídas no problema.

Se a solução deste problema for zero, terá sido obtida uma SBV do problema original e as variáveis artificiais podem ser eliminadas.




### Exemplo

```math
\text{min } z = -3x_1 - 5x_2
```

Sujeito a:

```math
\displaylines{
    x_1 + x_3 = 4 \\
    x_2 + x_4 = 6 \\
    3x_1 + 2x_2 - x_5 = 18 \\
    x_1, x_2, x_3, x_4, x_5 \ge 0
}
```

<br>

Na primeira fase, o problema será:

```math
\text{min } q = x^{a}_{1}
```

Sujeito a:

```math
\displaylines{
    x_1 + x_3 = 4 \\
    x_2 + x_4 = 6 \\
    3x_1 + 2x_2 - x_5 + x^{a}_{1} = 18 \\
    x_1, x_2, x_3, x_4, x_5, x^{a}_{1} \ge 0
}
```

<br>

#### Quadro inicial

![image](https://user-images.githubusercontent.com/23441506/202059403-8df2f55b-3308-4a6f-a62f-438948bdc1d7.png)

Devem ser feitas transformações na linha $q$ para que o problema fique na forma canônica. Ou seja, zerar os coeficientes de $x^{a}_{1}$. Para isto, devemos somar as linhas das variáveis artificiais à linha da função objetivo: $L1' = L1 - L5$.

<br>

![image](https://user-images.githubusercontent.com/23441506/202059966-b38be219-58e6-4d8a-91fa-4db0efba4bfd.png)

$x_1$ entra na base e $x_3$ sai.

<br>

![image](https://user-images.githubusercontent.com/23441506/202060009-ef4f6dc8-8cda-4764-9f53-635f80e3ed68.png)

$x_2$ entra na base e $x^{a}_{1}$.

<br>

Quadro final:

![image](https://user-images.githubusercontent.com/23441506/202060134-2aabfda3-95f3-4bf0-a394-26907c6f9ca9.png)

As variáveis artificiais são nulas e saíram da base. Assim, podemos retirá-las do problema.

Se for necessário, a função objetivo do PPL original deve ser colocada na forma canônica.

<br>

#### Início da segunda fase

![image](https://user-images.githubusercontent.com/23441506/202060396-a82a5acf-50d5-46dc-aaf2-433ed50aad47.png)

Este tableau é exatamente igual ao obtido pelo método Big M quando da eliminação das variáveis artificiais.




<br>

### Teorema

Considere PPL um problema de programação linear e PPL2 seu problema acessório, acrescido das variáveis artificiais necessárias e seja $(x^\ast, x^{a^\ast})$ solução ótima do PPL2:

- Se $\sum x^{a^\ast}_{i} > 0$, então o PPL original é inviável.
- Se $\sum x^{a^\ast}_{i} = 0$, então o PPL é viável e o PPL2 fornece a primeira SBV do PPL original.
