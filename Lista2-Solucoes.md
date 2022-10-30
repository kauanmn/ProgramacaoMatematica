# Lista 2 - Resolução Gráfica

**Universidade Federal do ABC**<br>
Prof.ª Geiza Cristina da Silva<br>
Programação Matemática


<br>


## Lista de conteúdos

[**Exercício 1**](#exercício-1)
- [Exercício 1A](#exercício-1A)
- [Exercício 1B](#exercício-1B)
- [Exercício 1C](#exercício-1C)
- [Exercício 1D](#exercício-1D)
- [Exercício 1E](#exercício-1E)

<br>

[**Exercício 2**](#exercício-2)
- [Exercício 2A](#exercício-2A)
- [Exercício 2B](#exercício-2B)
- [Exercício 2C](#exercício-2C)
- [Exercício 2D](#exercício-2D)
- [Exercício 2E](#exercício-2E)

<br>

# Exercício 1

Solucione graficamente os seguintes problemas de programação linear. Apresente a solução ótima e/ou identifique os casos especiais.


<br>


## Exercício 1A

Maximizar $z = x_{1} + 3x_{2}$

Sujeito a:

- $x_{1} + x_{2} \le 5$
- $-x_{1} + x_{2} \le 4$
- $x_{1} \text{ irrestrita }, x_{2} \ge 0$



<br>


### Solução

Plotando as restrições, temos a seguinte área viável:

![image](https://user-images.githubusercontent.com/23441506/198855403-e5b4c828-c6f2-438c-b630-61bff67b3142.png)

<br>

Para os pontos extremos, temos os seguintes valores para a função objetivo:

- $(x_{1}, x_{2}) = (0.5, 4.5) \rightarrow z = x_{1} + 3x_{2} = 0.5 + 3 \times 4.5 = 14$
- $(x_{1}, x_{2}) = (-2, 2)    \rightarrow z = x_{1} + 3x_{2} = -2  + 3 \times 2   = 4$
- $(x_{1}, x_{2}) = (3, 2)     \rightarrow z = x_{1} + 3x_{2} = 3   + 3 \times 2   = 9$

<br>

Portanto, a solução ótima é:

- $x_{1} = 0.5$
- $x_{2} = 4.5$
- $z     = 14$



<br>


## Exercício 1B

Maximizar $z = x_{1} + 2x_{2}$

Sujeito a:

- $x_{1} \le 3$
- $x_{2} \le 4$
- $x_{1} + 2x_{2} \le 9$
- $x_{1}, x_{2} \ge 0$


<br>


### Solução

Plotando as restrições, temos a seguinte área viável:

![image](https://user-images.githubusercontent.com/23441506/198856568-6233d338-6e2c-425c-8f11-c6a3a600586f.png)

<br>

Para os pontos extremos, temos os seguintes valores para a função objetivo:

- $(x_{1}, x_{2}) = (0,0) \rightarrow z = x_{1} + 2x_{2} = 0 + 2 \times 0 = 0$
- $(x_{1}, x_{2}) = (0,4) \rightarrow z = x_{1} + 2x_{2} = 0 + 2 \times 4 = 8$
- $(x_{1}, x_{2}) = (1,4) \rightarrow z = x_{1} + 2x_{2} = 1 + 2 \times 4 = 9$
- $(x_{1}, x_{2}) = (3,0) \rightarrow z = x_{1} + 2x_{2} = 3 + 2 \times 0 = 3$
- $(x_{1}, x_{2}) = (3,3) \rightarrow z = x_{1} + 2x_{2} = 3 + 2 \times 3 = 9$

<br>

Portanto, a solução ótima é:

- $x_{1} = 1$
- $x_{2} = 4$
- $z = 9$

OU

- $x_{1} = 3$
- $x_{2} = 3$
- $z = 9$


<br>


## Exercício 1C

Minimizar

```math
    z = 3x_{1} + 2x_{2}
```

Sujeito a:

```math
\displaylines{
    x_{1} \le 3 \\
    x_{2} \le 4 \\
    x_{1} + 2x_{2} \le 9 \\
    x_{1}, x_{2} \ge 0
}
```


<br>


### Solução

Plotando as restrições, temos a seguinte área viável:

![image](https://user-images.githubusercontent.com/23441506/198856916-5df080ad-4d40-4cc7-be29-8690ed5a3a1d.png)

<br>

Para os pontos extremos, temos os seguintes valores para a função objetivo:

- $(x_{1}, x_{2}) = (0,0) \rightarrow z = 3x_{1} + 2x_{2} = 3 \times 0 + 2 \times 0 = 0$
- $(x_{1}, x_{2}) = (0,4) \rightarrow z = 3x_{1} + 2x_{2} = 3 \times 0 + 2 \times 4 = 8$
- $(x_{1}, x_{2}) = (1,4) \rightarrow z = 3x_{1} + 2x_{2} = 3 \times 1 + 2 \times 4 = 11$
- $(x_{1}, x_{2}) = (3,0) \rightarrow z = 3x_{1} + 2x_{2} = 3 \times 3 + 2 \times 0 = 9$
- $(x_{1}, x_{2}) = (3,3) \rightarrow z = 3x_{1} + 2x_{2} = 3 \times 3 + 2 \times 3 = 15$

<br>

Portanto, a solução ótima é:

- $x_{1} = 0$
- $x_{2} = 0$
- $z = 0$


<br>


## Exercício 1D

Maximizar

```math
    z = x_{1} - 4x_{2}
```

Sujeito a:

```math
\displaylines{
    -2x_{1} + x_{2} \le -1 \\
    -x_{1} - 2x_{2} \le -2 \\
    x_{2} \le 5 \\
    x_{1} \ge 0, x_{2} \text{ irrestrita }
    
}
```


<br>


### Solução

Plotando as restrições, temos a seguinte área viável:

![image](https://user-images.githubusercontent.com/23441506/198859244-5589420b-3321-4a81-b376-3ed68dea77f8.png)

Analisando a área viável, é possível perceber que podemos aumentar o $x_1$ e diminuir o $x_2$ indefinidamente. Isso caracteriza um problema **ILIMITADO**.


<br>


## Exercício 1E

Minimizar

```math
    z = 5x_{1} + 4x_{2}
```

Sujeito a:

```math
\displaylines{
    x_{1} + x_{2} \le 1 \\
    -2x_{1} - 2x_{2} \le -9 \\
    x_{1}, x_{2} \ge 0
}
```


<br>


### Solução

Plotando as restrições, temos a seguinte área viável:

![image](https://user-images.githubusercontent.com/23441506/198859674-57216815-5a6a-40f1-81bb-0f6a607d1ec9.png)


Como é possível ver, não existem soluções que satisfaçam todas as restrições simultaneamente. Portanto, temos um problema **INVIÁVEL**.


<br>


# Exercício 2

Considere as funções objetivos e, utilizando a representação gráfica, ache os valores ótimos dessas funções, sabendo que o conjunto de restrições é o seguinte:

```math
\displaylines{
    2x_{1} - x_{2} \ge -2 \\
    x_{1} + 2x_{2} \le 8 \\
    x_{1}, x_{2} \ge 0
}
```


<br>


### Restrições

Como as restrições são iguais para todos os subitens, será plotada a área viável comum entre eles:

![image](https://user-images.githubusercontent.com/23441506/198860190-5150ebca-589f-466c-ab23-24a07067b49c.png)

<br>

Os pontos extremos são:

- $(0.0, 0.0)$
- $(0.0, 2.0)$
- $(0.8, 3.6)$
- $(8.0, 0.0)$


<br>


## Exercício 2A

Função objetivo:

```math
    \text{max } z = x_{2}
```


<br>


### Solução

- $(x_{1}, x_{2}) = (0.0, 0.0) \rightarrow z = x_{2} = 0.0$
- $(x_{1}, x_{2}) = (0.0, 2.0) \rightarrow z = x_{2} = 2.0$
- $(x_{1}, x_{2}) = (0.8, 3.6) \rightarrow z = x_{2} = 3.6$
- $(x_{1}, x_{2}) = (8.0, 0.0) \rightarrow z = x_{2} = 0.0$

<br>

Portanto, a solução ótima é 

- $(x_{1}, x_{2}) = (0.8, 3.6)$
- $z = 3.6$


<br>


## Exercício 2B

Função objetivo:

```math
    \text{max } z = 3x_{1} + 2x_{2}
```


<br>

### Solução

- $(x_{1}, x_{2}) = (0.0, 0.0) \rightarrow z = 3x_{1} + 2x_{2} = 3 \times 0.0 + 2 \times 0.0 = 0$
- $(x_{1}, x_{2}) = (0.0, 2.0) \rightarrow z = 3x_{1} + 2x_{2} = 3 \times 0.0 + 2 \times 2.0 = 4$
- $(x_{1}, x_{2}) = (0.8, 3.6) \rightarrow z = 3x_{1} + 2x_{2} = 3 \times 0.8 + 2 \times 3.6 = 9.6$
- $(x_{1}, x_{2}) = (8.0, 0.0) \rightarrow z = 3x_{1} + 2x_{2} = 3 \times 8.0 + 2 \times 0.0 = 24$

<br>

Portanto, a solução ótima é 

- $(x_{1}, x_{2}) = (8.0, 0.0)$
- $z = 24$


<br>


## Exercício 2C

Função objetivo:

```math
    \text{min } z = 2x_{1} - 2x_{2}
```


<br>


### Solução

- $(x_{1}, x_{2}) = (0.0, 0.0) \rightarrow z = 2x_{1} + 2x_{2} = 2 \times 0.0 - 2 \times 0.0 = 0$
- $(x_{1}, x_{2}) = (0.0, 2.0) \rightarrow z = 2x_{1} + 2x_{2} = 2 \times 0.0 - 2 \times 2.0 = -4$
- $(x_{1}, x_{2}) = (0.8, 3.6) \rightarrow z = 2x_{1} + 2x_{2} = 2 \times 0.8 - 2 \times 3.6 = -5.6$
- $(x_{1}, x_{2}) = (8.0, 0.0) \rightarrow z = 2x_{1} + 2x_{2} = 2 \times 8.0 - 2 \times 0.0 = 16$

<br>

Portanto, a solução ótima é 

- $(x_{1}, x_{2}) = (0.8, 3.6)$
- $z = -5.6$


<br>


## Exercício 2D

Função objetivo:

```math
    \text{max } z = 2x_{1} + 4x_{2}
```


<br>

### Solução

- $(x_{1}, x_{2}) = (0.0, 0.0) \rightarrow z = 2x_{1} + 4x_{2} = 2 \times 0.0 + 4 \times 0.0 = 0$
- $(x_{1}, x_{2}) = (0.0, 2.0) \rightarrow z = 2x_{1} + 4x_{2} = 2 \times 0.0 + 4 \times 2.0 = 8$
- $(x_{1}, x_{2}) = (0.8, 3.6) \rightarrow z = 2x_{1} + 4x_{2} = 2 \times 0.8 + 4 \times 3.6 = 16$
- $(x_{1}, x_{2}) = (8.0, 0.0) \rightarrow z = 2x_{1} + 4x_{2} = 2 \times 8.0 + 4 \times 0.0 = 16$

<br>

Portanto, a solução ótima é 

- $(x_{1}, x_{2}) = (8.0, 0.0)$
- $z = 16$

OU

- $(x_{1}, x_{2}) = (0.8, 3.6)$
- $z = 16$


<br>


## Exercício 2E

Função objetivo:

```math
    \text{min } z = -3x_{1} - 2x_{2}
```

<br>

### Solução

- $(x_{1}, x_{2}) = (0.0, 0.0) \rightarrow z = -3x_{1} + 2x_{2} = -3 \times 0.0 - 2 \times 0.0 = 0$
- $(x_{1}, x_{2}) = (0.0, 2.0) \rightarrow z = -3x_{1} + 2x_{2} = -3 \times 0.0 - 2 \times 2.0 = -4$
- $(x_{1}, x_{2}) = (0.8, 3.6) \rightarrow z = -3x_{1} + 2x_{2} = -3 \times 0.8 - 2 \times 3.6 = -9.6$
- $(x_{1}, x_{2}) = (8.0, 0.0) \rightarrow z = -3x_{1} + 2x_{2} = -3 \times 8.0 - 2 \times 0.0 = -24$

Portanto, a solução ótima é 

- $(x_{1}, x_{2}) = (8.0, 0.0)$
- $z = -24$
