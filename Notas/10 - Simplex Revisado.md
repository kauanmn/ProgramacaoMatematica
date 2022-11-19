# Programação Matemática - Aula 10

<br>

## Motivação

- No método simplex revisado, são realizadas somente as operações de pivoteamento necessárias, enquanto no método tradicional são modificados todos os elementos da tabela, que não têm informações relevantes.
- Os cálculos partem dos dados originais do problema.
- Usado nos temas das próximas aulas: dualidade e pós-otimização.




<br>

## Estrutura matricial do Simplex

```math
\text{min } z = c^{T}x
```

Sujeito a:

```math
\displaylines{
    Ax = b \\
    x \ge 0
}
```

<br>

Onde:

- $A$ é a matriz de restrições $m \times n$
- $x$ é a matriz de variáveis com $n$ componentes
- $b$ é a matriz coluna $1 \times m$
- $c$ é a matriz coluna $n \times 1$ de custos. $c^T$ é a sua transposta.

<br>

Excluindo-se os casos de degeneração do problema, devem existir tantas variáveis básicas quanto restrições do problema, ou seja, $m$.

Divide-se a matriz $A$ do seguinte modo:

<br>

![image](https://user-images.githubusercontent.com/23441506/202065705-038055ae-1160-4645-bad5-9ceed8b20dfc.png)

^- VERIFICAR COM A PROFESSORA SE ESTÁ CORRETO




<br>

## Simplex Revisado

Seja o PPL $Ax = b, x \ge 0$. Considerando que a sequência ótima de variáveis para o problema seja conhecida, pode ser efetuada uma pré-multiplicação dos dois lados pela inversa da base da sequência ótima:

```math
\displaylines{
    (B^{-1}A)x = B^{-1}b \Rightarrow B^{-1} \begin{bmatrix}B & R \end{bmatrix} \begin{bmatrix} x_B \\ x_R \end{bmatrix} = B^{-1}b \\
    \Rightarrow \begin{bmatrix} B^{-1}B & B^{-1}R \end{bmatrix} \begin{bmatrix} x_B \\ x_R \end{bmatrix} = B^{-1}b \Rightarrow \begin{bmatrix} I & B^{-1}R \end{bmatrix}\begin{bmatrix} x_B \\ x_R \end{bmatrix} = B^{-1}
}
```

<br>

Então temos:

![image](https://user-images.githubusercontent.com/23441506/202822675-8d5e5f44-5650-443c-91fd-62d0179d4a77.png)

<br>

Para colocar a linha da função objetivo da mesma maneira, o objetivo é obter zeros nas variáveis básicas. Assim, multiplicamos a equação

```math
    \begin{bmatrix} B^{-1}B & B^{-1}R \end{bmatrix} \begin{bmatrix} x_B \\ x_R \end{bmatrix} = B^{-1}b \text{ por } c^{T}_B
```

de forma a obter $c^T_B$ nas colunas das variáveis básicas:

```math
    c^{T}_B\begin{bmatrix} B^{-1}B & B^{-1}R \end{bmatrix} \begin{bmatrix} x_B \\ x_R \end{bmatrix} = c^{T}_BB^{-1}b
```

Subtraímos esta linha daquela originalmente na funçao objetivo:

![image](https://user-images.githubusercontent.com/23441506/202828405-d98e5690-d1b5-4cca-b450-dcc56056cea4.png)

<br>

E temos:

![image](https://user-images.githubusercontent.com/23441506/202828417-202cba16-4c8f-4130-b64d-32c29eb39a39.png)

<br>

A solução do problema será $z = c^{T}_B B^{-1} b$ e $B^{-1}b$.



<br>

## [TODO]

COLOCAR EXEMPLOS 1 E 2
