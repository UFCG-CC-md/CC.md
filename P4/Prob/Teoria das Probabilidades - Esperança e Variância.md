---
tipo: anotacao
periodo: 4
disciplina: Prob
trilhas:
---


## Esperança e Variância:

### Introdução:

Algumas características numéricas, chamadas de **parâmetros**, ajudam a descrever o comportamento de uma distribuição de probabilidades.

- **Esperança (ou valor médio):** indica o valor médio associado à distribuição.
- **Variância:** indica a dispersão dos valores da variável em torno da esperança.
- **Desvio padrão:** é a raiz quadrada da variância.

Nesta anotação, consideramos **variáveis aleatórias discretas**, conforme os slides.

### Valor Médio (Valor Esperado, Esperança):

Seja $X$ uma variável aleatória discreta que assume os valores $x_1,x_2,\ldots$, com probabilidades $p(x_1),p(x_2),\ldots$, respectivamente, em que $p(x_i)=P(X=x_i)$.

Definimos o **valor médio**, também chamado de **valor esperado** ou **esperança** de $X$, por:

$$\mu = E(X) = \sum_{i=1}^{\infty} x_i \cdot p(x_i).$$

- **Caso finito:** se $X$ assume apenas $n$ valores, a esperança existe e a soma se reduz a:
	$$E(X) = \sum_{i=1}^{n} x_i \cdot p(x_i).$$
- **Caso infinito:** a convergência absoluta da série garante a existência de uma esperança finita:
	$$\sum_{i=1}^{\infty} |x_i \cdot p(x_i)| < \infty.$$
- **Observações:**
	- A esperança **não é necessariamente um dos valores possíveis** de $X$.
	- Não confunda a esperança com o **valor modal**, que é o valor mais provável.
	- Em geral, $E(X)$ é diferente da média aritmética $\bar{x}$: a esperança está associada à distribuição da variável, enquanto a média aritmética está associada aos valores observados em uma amostra.

### Propriedades da Esperança:

Considerando que as esperanças envolvidas existem:

- **Esperança de uma função de $X$:**
	$$E[h(X)] = \sum_{i=1}^{\infty} h(x_i) \cdot p(x_i).$$
	- Aplicamos a função $h$ a cada valor de $X$ e mantemos as probabilidades correspondentes.
- **Transformação linear:** se $a$ e $b$ são constantes reais:
	$$E(aX+b) = aE(X)+b.$$
	- Em particular:
		$$E(aX) = aE(X).$$
		$$E(b) = b.$$
- **Desvio em relação à esperança:** sendo $\mu=E(X)$:
	$$E(X-\mu) = 0.$$
- **Esperança de uma soma:**
	$$E(X_1+X_2+\cdots+X_n) = E(X_1)+E(X_2)+\cdots+E(X_n).$$

### Variância:

Seja $X$ uma variável aleatória cujo valor médio $\mu=E(X)$ existe. Definimos a **variância** de $X$ por:

$$\operatorname{Var}(X) = E[(X-\mu)^2].$$

A variância traz informações sobre a **dispersão dos possíveis valores de $X$ em torno de sua esperança**.

- **Não negatividade:** como $(X-\mu)^2 \geq 0$, temos:
	$$\operatorname{Var}(X) \geq 0.$$
- **Fórmula alternativa para o cálculo:**
	$$\operatorname{Var}(X) = E(X^2)-\mu^2.$$
	- Para uma variável aleatória discreta:
		$$E(X^2) = \sum_{i=1}^{\infty} x_i^2 \cdot p(x_i).$$
	- Quando há apenas $n$ valores possíveis, usamos a soma finita.

### Desvio Padrão:

Como a variância é não negativa, definimos o **desvio padrão** de $X$ por:

$$\operatorname{DP}(X) = \sqrt{\operatorname{Var}(X)}.$$

### Propriedade da Variância:

Se a variância de $X$ existe e $a$ e $b$ são constantes reais, então:

$$\operatorname{Var}(aX+b) = a^2 \cdot \operatorname{Var}(X).$$

- **Observação:** a constante somada não altera a variância; a multiplicação por $a$ faz a variância ser multiplicada por $a^2$.

### Exemplo Resolvido:

Os cálculos abaixo reúnem os Exemplos 1, 3, 4 e 6 dos slides.

Considere $X$: número de peças produzidas por minuto, com a seguinte função de probabilidade:

| $X=x_i$ | $1$ | $2$ | $3$ | $4$ |
| --- | --- | --- | --- | --- |
| $p(x_i)=P(X=x_i)$ | $0{,}10$ | $0{,}50$ | $0{,}25$ | $0{,}15$ |

- **(a) Calcular $E(X)$:**
	$$E(X) = 1\cdot0{,}10+2\cdot0{,}50+3\cdot0{,}25+4\cdot0{,}15 = 2{,}45.$$
	- A esperança é de $2{,}45$ peças por minuto, embora esse não seja um dos valores possíveis de $X$.
- **(b) Calcular $E(X^2)$:**
	$$E(X^2) = 1^2\cdot0{,}10+2^2\cdot0{,}50+3^2\cdot0{,}25+4^2\cdot0{,}15 = 6{,}75.$$
- **(c) Calcular $E(3X+1)$:**
	$$E(3X+1) = 3E(X)+1 = 3\cdot2{,}45+1 = 8{,}35.$$
- **(d) Calcular $\operatorname{Var}(X)$ e $\operatorname{DP}(X)$:**
	$$\operatorname{Var}(X) = E(X^2)-\mu^2 = 6{,}75-(2{,}45)^2 = 0{,}7475.$$
	$$\operatorname{DP}(X) = \sqrt{0{,}7475} \simeq 0{,}86.$$
	- A variância é medida em $(\text{peças/minuto})^2$ e o desvio padrão em peças por minuto.
- **(e) Calcular a variância de transformações de $X$:**
	$$\operatorname{Var}(3X+1) = 3^2\operatorname{Var}(X) = 9\cdot0{,}7475 = 6{,}7275.$$
	$$\operatorname{Var}(\sqrt{5}X-1) = (\sqrt{5})^2\operatorname{Var}(X) = 5\cdot0{,}7475 = 3{,}7375.$$

>[!cite] Fontes:
> **Slides de Variáveis Aleatórias Discretas — Esperança e Variância** (`Esperanca_variancia_vad_1.pdf`).
