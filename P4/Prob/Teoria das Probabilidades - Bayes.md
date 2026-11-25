---
tipo: anotacao
periodo: 4
disciplina: Prob
trilhas:
---
## Bayes:

### Teorema da Probabilidade Total:

Se $C_1,C_2,...,C_n$ é uma [[Partição do Espaço Amostral|partição do espaço amostral]], $\Omega$ tal que $P(C_j) > 0, \forall j=1,2,...,n$ então qualquer evento $A \subset \Omega$, tem-se
$$
P(A) = P(C_1)P(A \mid C_1) + P(C_2)P(A \mid C_2) + ... + P(C_n)P(A \mid C_n).
$$
Ou seja,
$$
P(A) = \sum_{j=1}^{n}P(C_j)P(A \mid C_j).
$$
*Comentário: O Teorema da Probabilidade Total nos mostra como obter a probabilidade a **priori** de um evento $A$ em termos das probabilidades a **posteriori** de $A$ dado a ocorrência dos eventos $C_1,C_2,...,C_n$ quando estes constituem uma partição do espaço amostral $\Omega$* 
### Teorema de Bayes:

Se $C_1,C_2,...,C_n$ é uma partição do espaço amostral $\Omega$ tal que $P(C_j) > 0, \forall j = 1,2,...,n$ e $A$ é um evento de $\Omega \mid P(A) > 0$, então 
$$P(C_i\mid A) = \frac{P(C_i)P(A\mid C_i)}{\sum_{j=1}^{n}P(C_j)P(A \mid C_j)},\forall i = 1,2,...,n$$

### Exercícios resolvidos

#### 1. Fábrica de parafusos

**Enunciado:** Em uma fábrica de parafusos, as máquinas $M_1$, $M_2$ e $M_3$ produzem, respectivamente, $25\%$, $35\%$ e $40\%$ do total. Da produção de cada máquina, $5\%$, $4\%$ e $2\%$, respectivamente, são parafusos defeituosos.

- **(a)** Escolhendo ao acaso um parafuso da produção total, qual é a probabilidade de ele ser defeituoso?
- **(b)** Sabendo que o parafuso escolhido é defeituoso, qual é a probabilidade de ele ter sido produzido pela máquina $M_1$?

**Definição dos eventos:**

- $M_i$: o parafuso foi produzido pela máquina $i$.
- $D$: o parafuso é defeituoso.

| Máquina | Participação na produção: $P(M_i)$ | Probabilidade de defeito: $P(D\mid M_i)$ |
| --- | --- | --- |
| $M_1$ | $25\%$ | $5\%$ |
| $M_2$ | $35\%$ | $4\%$ |
| $M_3$ | $40\%$ | $2\%$ |

##### (a) Probabilidade de um parafuso ser defeituoso

**Passo 1 — Aplicar o Teorema da Probabilidade Total.**

O parafuso pode ter vindo de qualquer uma das três máquinas. Como esses eventos formam uma [[Partição do Espaço Amostral|partição do espaço amostral]], somamos a contribuição de cada máquina:

$$
P(D)=P(M_1)P(D\mid M_1)+P(M_2)P(D\mid M_2)+P(M_3)P(D\mid M_3).
$$

**Passo 2 — Substituir os valores e calcular.**

$$
P(D)=0{,}25\cdot0{,}05+0{,}35\cdot0{,}04+0{,}40\cdot0{,}02
$$

$$
P(D)=0{,}0125+0{,}014+0{,}008=0{,}0345.
$$

**Resposta:**

$$
\boxed{P(D)=3{,}45\%}
$$

##### (b) Probabilidade de ter vindo de $M_1$, sabendo que é defeituoso

**Passo 1 — Identificar a probabilidade pedida.**

Queremos $P(M_1\mid D)$, e não $P(D\mid M_1)$: já sabemos que o parafuso é defeituoso e queremos descobrir sua origem.

Pelo Teorema de Bayes:

$$
P(M_1\mid D)=\frac{P(M_1)P(D\mid M_1)}{P(D)}.
$$

**Passo 2 — Usar a probabilidade calculada no item (a).**

$$
P(M_1\mid D)
=\frac{0{,}25\cdot0{,}05}{0{,}0345}
=\frac{0{,}0125}{0{,}0345}
=\frac{25}{69}.
$$

**Resposta:**

$$
\boxed{P(M_1\mid D)\approx36{,}23\%}
$$

**Interpretação:** Em uma produção de $10\,000$ parafusos, esperaríamos $125$ defeituosos de $M_1$, $140$ de $M_2$ e $80$ de $M_3$. Dos $345$ defeituosos, $125$ seriam de $M_1$, resultando em $125/345\approx36{,}23\%$.

#### 2. Dado honesto e dado viciado

**Enunciado:** Considere dois dados. Um é honesto, com probabilidade $1/6$ para cada face. O outro é viciado, com probabilidade $1/2$ para a face $1$ e $1/10$ para cada uma das demais faces. Escolhe-se aleatoriamente um dos dados e realizam-se dois lançamentos com esse mesmo dado, obtendo-se dois resultados iguais a $1$. Qual é a probabilidade de o dado escolhido ter sido o viciado?

**Definição dos eventos:**

- $H$: foi escolhido o dado honesto.
- $V$: foi escolhido o dado viciado.
- $A$: saiu $1$ nos dois lançamentos.

**Passo 1 — Determinar a probabilidade de escolher cada dado.**

Como a escolha entre os dois dados é aleatória, com chances iguais:

$$
P(H)=P(V)=\frac12.
$$

**Passo 2 — Calcular a probabilidade de dois resultados iguais a $1$ para cada dado.**

Os lançamentos são independentes quando o dado escolhido está fixado.

Para o dado honesto:

$$
P(A\mid H)=\frac16\cdot\frac16=\frac1{36}.
$$

Para o dado viciado:

$$
P(A\mid V)=\frac12\cdot\frac12=\frac14.
$$

**Passo 3 — Calcular a probabilidade total de observar dois resultados iguais a $1$.**

$$
P(A)=P(H)P(A\mid H)+P(V)P(A\mid V)
$$

$$
P(A)=\frac12\cdot\frac1{36}+\frac12\cdot\frac14
=\frac1{72}+\frac18
=\frac{10}{72}
=\frac5{36}.
$$

**Passo 4 — Aplicar o Teorema de Bayes.**

Queremos a probabilidade de ter escolhido o dado viciado, sabendo que saiu $1$ duas vezes:

$$
P(V\mid A)=\frac{P(V)P(A\mid V)}{P(A)}.
$$

Substituindo:

$$
P(V\mid A)
=\frac{\frac12\cdot\frac14}{\frac5{36}}
=\frac18\cdot\frac{36}{5}
=\frac9{10}.
$$

**Resposta:**

$$
\boxed{P(V\mid A)=90\%}
$$

**Interpretação:** Dois resultados iguais a $1$ são $9$ vezes mais prováveis com o dado viciado do que com o honesto, pois $(1/4)/(1/36)=9$. Como os dados tinham a mesma chance inicial de serem escolhidos, a probabilidade final do viciado é $9/(9+1)=90\%$.
