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














































































































































































































