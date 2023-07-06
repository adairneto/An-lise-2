---
title: MA602 Análise 2 - Exercícios P2
author: Adair Neto
date: \today
header-includes:
   - \usepackage[brazilian]{babel}
   - \usepackage[left=2cm,right=2cm,top=2cm,bottom=2cm]{geometry}
   - \setlength{\parindent}{1.5em}
   - \setlength{\parskip}{0.5em}
   - \usepackage{indentfirst}
   - \usepackage{helvet}
   - \usepackage[bitstream-charter]{mathdesign}
   - \usepackage[T1]{fontenc}
   - \usepackage{textcomp}
   - \usepackage[frenchmath]{mathastext}
---

## Os teoremas clássicos do Cálculo Integral

### Capítulo 11, Seção 1, Exercício 1 

**Questão:**  Seja $f : [a, b] \longrightarrow \mathbb{R}$ integrável, contínua à direita no ponto $x_0 \in [a,b)$. Prove que $F:[a,b] \longrightarrow \mathbb{R}$, dada por $$ F(x) = \int_a^x f(t)~dt $$ é derivável à direita no ponto $x_0$ com $F_{+}'(x_0) = f(x_0)$.

Dê exemplos com $f$ integrável, descontínua no ponto $x_0$, nos quais:

1. Existe $F'(x_0)$.

2. Não existe $F'(x_0)$.

**Resolução:** 

- Por definição,
$$
   F(x) - F(x_0) = \int_a^x f(t)~dt - \int_a^a f(t)~dt = \int_a^x f(t)~dt
$$
- Note que $F$ é contínua em $[a, x]$ e diferenciável em $(a,x)$. 
- Pelo Teorema do Valor Médio, para cada $x \in [x_0, x]$, existe $c_x \in (x_0, x)$ tal que 
$$
   \frac{F(x) - F(x_0)}{x - x_0} = f(c_x)
$$
- Logo,
$$
   F_{+}'(x_0) = \lim_{x \to x_0^+} \frac{F(x) - F(x_0)}{x - x_0} = \lim_{x \to x_0^+} f(c_x) = f(x_0)
$$
- Existe $F'(x_0)$.:
   - Considere
   $$
      f(x) = 2 x \sin \left(\frac{1}{x^2} \right) - \frac{2 \cos \left(\frac{1}{x^2} \right)}{x}
   $$
   para $x \neq 0$ e $f(0) = 0$.
   - Então 
   $$
      F(x) = x^2 \sin (x^{-2}), \quad F(0) = 0
   $$
   - E $f$ é descontínua em $0$.
- Não existe $F'(x_0)$.
   - Considere
   $$
      f(x) = \begin{cases}
         0, & 0 < x \le 1 \\
         1, & x = 0
      \end{cases}
   $$
   - Temos que $\int_0^1 f = 0$, $f$ é descontínua em $x = 0$ e não existe $F'$.

### Capítulo 11, Seção 1, Exercício 2

**Questão:** Seja $f :[a,b] \longrightarrow \mathbb{R}$ derivável com $f'$ integrável. Mostre que, para quaisquer $x, c \in [a,b]$ tem-se 
$$
f(x) = f(c) + \int_c^x f'(t)~dt
$$

**Resolução:** 

- Seja $P = \{ a = t_0 < t_1 < \ldots < t_n = c \}$ uma partição de $[a,c]$.
- Temos que
$$
   f(c) - f(a) = \sum_{i=1}^n [f(t_i) - f(t_{i-1})]
$$
- Pelo Teorema do Valor Médio, para todo $i = 0, 1, \ldots, n$, existe $\xi_i \in (t_{i-1}, t_i)$ tal que
$$
   f'(\xi_i)(t_i - t_{i-1}) = f(t_i) - f(t_{i-1})
$$
- Substituindo,
$$
   f(c) - f(a) = \sum_{i=1}^n f'(\xi_i) \Delta t_i
$$
- Como $f'$ é integrável, 
$$
   m_i' \leq f'(\xi_i) \le M_i' \implies s(f', P) \le f(c) - f(a) \le S(f', P)
$$
- Como $P$ é arbitrário, 
$$
   f(c) = f(a) + \int_a^c f'(t) ~dt
$$

### Capítulo 11, Seção 1, Exercício 5

**Questão:** Sejam $f :[a,b] \longrightarrow \mathbb{R}$ contínua $\alpha, \beta : I \longrightarrow \mathbb{R}$ deriváveis. Defina $\varphi : I \longrightarrow \mathbb{R}$ pondo 
$$
\varphi(x) = \int_{\alpha(x)}^{\beta(x)} f(t) ~dt, \quad \forall~x \in I
$$
Prove que $\varphi$ é derivável e 
$$
\varphi'(x) = f(\beta(x))\beta'(x) - f(\alpha(x)) \alpha'(x)
$$

**Resolução:** 

- Como $f$ é contínua, pelo Teorema Fundamental do Cálculo, $f$ possui primitiva $F$:
$$
   \varphi(x) = \int_{\alpha(x)}^{\beta(x)} f(t) ~dt = F(\beta(t)) - F(\alpha(t))
$$
- Como $F$ é primitiva, $F$ é derivável com $F' = f$. Pela regra da cadeia,
$$
   \varphi'(x) = f(\beta(x))\beta'(x) - f(\alpha(x)) \alpha'(x)
$$

### Capítulo 11, Seção 1, Exercício 6

**Questão:** Sejam $f : [0, 1] \longrightarrow \mathbb{R}$ dada por 
$$
f(x) = \begin{cases}
0, & \text{ se } x \in \mathbb{R} \setminus \mathbb{Q} \\ 
\frac{1}{q}, & \text{ se } x = \frac{p}{q} \text{ é fração irredutível }, ~q>0 
\\
1, & \text{ se } x = 0
\end{cases}
$$
e $g : [0, 1] \longrightarrow \mathbb{R}$ dada por 
$$
g(x) = \begin{cases}
0, & x = 0 \\
1, & x > 0
\end{cases}
$$
Mostre que $f$ e $g$ são integráveis, porém $g \circ f : [0, 1] \longrightarrow \mathbb{R}$ não é integrável.

**Resolução:** 

- Vimos que $f$ é integrável (de fato, o conjunto de seus pontos de descontinuidade são os racionais, que têm medida nula). 
- Como $g$ tem apenas um ponto de descontinuidade e $g$ é limitada, $g$ é integrável. 
- Temos que 
$$
g \circ f(x) = \begin{cases}
1, & x = 0 \\
0, & x \in \mathbb{R} \setminus \mathbb{Q} \\
1, & x = p/q 
\end{cases}
$$
- Portanto, dada uma partição $P$ de $[0,1]$ qualquer, 
$$
   s(g \circ f, P) = 0 \quad \text{ e } \quad S(g \circ f, P) = 1
$$
- Logo, $g \circ f$ não é integrável.

### Questão 3 (P1 2020)

**Questão:** Enuncie a Fórmula do Valor Médio para Integrais e o Teorema do Valor Médio de Lagrange. Utilize a Fórmula do Valor Médio para Integrais para provar o Teorema do Valor Médio de Lagrange no caso em que $f : [a, b] \longrightarrow \mathbb{R}$ é de classe $C^1$.

**Resolução:** 

1. Fórmula do Valor Médio para Integrais.
   - Seja $f : [a, b] \longrightarrow \mathbb{R}$ contínua.
   - Existe $c \in (a,b)$ tal que
   $$
   \int_a^b f(x)~dx = f(c)(b-a)
   $$

2. Teorema do Valor Médio de Lagrange.
   - Seja $f : [a, b] \longrightarrow \mathbb{R}$ contínua em $[a,b]$ e derivável em $(a,b)$. 
   - Existe $c \in (a,b)$ tal que
   $$
   f'(c)(b-a) = f(b) - f(a)
   $$

3. Demonstrar Teorema do Valor Médio de Lagrange.
   - Pela fórmula do valor médio para integrais, $c \in (a,b)$ tal que
   $$
   \int_a^b f(x)~dx = f(c)(b-a)
   $$
   - Pelo Teorema Fundamental do Cálculo, 
   $$
   \int_a^b f(x)~dx = F(b) - F(a)
   $$
   - em que $F' = f$.
   - Assim, temos a seguinte identidade:
   $$
   f(c)(b-a) = F(b) - F(a)
   $$
   - Derivando-se a expressão acima,
   $$
   f'(c)(b-a) = f(b) - f(a)
   $$

## Integrais Impróprias

### Capítulo 11, Seção 4, Exercício 4

**Questão:** Mostre que
$$
\int_0^{+ \infty} x \sin(x^4)~dx 
$$
converge, embora a função $x \sin(x^4)$ seja ilimitada.

**Resolução:** 

0. Ideia: analisar a série $\sum_{n=0}^\infty (-1)^n a_n$, em que $a_n = \int_{\sqrt{n\pi}}^{\sqrt{(n+1)\pi}} |x \sin(x^4)|~dx$, e aplicar o Teorema de Leibniz.
1. Estimar a área da integral.
   - Tome $a = \sqrt[4]{n \pi}$ e $b = \sqrt[4]{(n+1) \pi}$
   - Então 
   $$
      \int_a^b |x \sin(x^4)|~dx
   $$ 
   - é menor do que a área do retângulo de base $(b-a)$ e altura $b$.
   - Para calcular a área $b(b-a)$, note que 
   $$
      b^4 - a^4 = \pi = (b-a)(a^3 + a^2b + ab^2 + b^3)
   $$
   - Isso nos dá
   $$
      b(b-a) = \frac{b \pi}{a^3 + a^2b + ab^2 + b^3} \overset{n \to \infty}{\longrightarrow} 0
   $$
2. Mostrar que a sequência é decrescente.
   - Seja $c = \sqrt[4]{(n+2) \pi}$.
   - Fazemos a mudança de variáveis $x = \sqrt[4]{u^4 + \pi}$.
   - Assim, 
   $$
      a_{n+1} = \int_b^c |x \sin(x^4)|~dx = \int_a^b |u \sin(u^4)| \frac{u^2}{\sqrt[4]{(u^4 + \pi)^2}} ~du
   $$
   - O que implica que $a_{n+1} < a_n$.
3. Aplicar Teorema de Leibniz.
   - Ou seja, $(a_n)$ é uma sequência decrescente que tende para zero.
   - Pelo Teorema de Leibniz, 
   $$
      \sum_{n=0}^\infty (-1)^n a_n
   $$
   - converge para a integral desejada.

### Capítulo 11, Seção 4, Exercício 5

**Questão:** Seja $f:[a, +\infty) \longrightarrow \mathbb{R}$ contínua, positiva, monótona não-crescente. Prove que se $\int_a^\infty f(x)~dx$ converge, então $\lim_{x \to \infty} xf(x) = 0$.

**Resolução:** 

- Defina 
$$
F(x) = \int_a^x f(x)~dx
$$
- Por hipótese, existe $L = \lim_{x \to \infty} F(x)$.
- Assim, dado $\varepsilon > 0$, temos que existe $N \in \mathbb{N}$ tal que 
$$
x > N \implies |F(x) - L| < \varepsilon \iff L-\varepsilon < F(x) < L+\varepsilon
$$
- Particularmente, se $x > 2N$,
$$
x/2 > N \implies L-\varepsilon < F(x/2) < L+\varepsilon
$$
- Como $f$ é positiva não-crescente,
$$
x/2 > N \implies L-\varepsilon < F(x/2) \le F(x) < L+\varepsilon
$$
- Portanto, 
$$
x/2 > N \implies F(x) - F(x/2) = \int_{x/2}^x f(x)~dx < 2 \varepsilon
$$
- Por outro lado, como a função é não-crescente, sua área é maior ou igual do que a do retângulo de base $x - x/2$ e altura $f(x)$, i.e.,
$$
\int_{x/2}^x f(x)~dx \ge \frac{x}{2} f(x)
$$
- Dessa forma,
$$
   \frac{x}{2} f(x) < 2 \varepsilon \iff xf(x) < \varepsilon
$$
- Logo, 
$$
   \lim_{x \to \infty} x f(x) = 0
$$

### Capítulo 11, Seção 4, Exercício 6 (Critério de Cauchy para Integrais)

**Questão:** Seja $f:[a, +\infty) \longrightarrow \mathbb{R}$ integrável em cada intervalo limitado $[a,x]$. Prove que a integral imprópria 
$$
\int_a^\infty f(x)~dx = \lim_{x \to \infty} \int_a^x f(t)~dt
$$
existe sse. para todo $\varepsilon > 0$, existe $A > 0$ tal que
$$
A < x < y \implies \left| \int_x^y f(t)~dt \right| < \varepsilon
$$

**Resolução:** 

1. $(\Rightarrow)$ Suponha que a integral existe.
   - Tome $F(x)$ e $L$ como no exercício 11.4.5. 
   - Dado $\varepsilon > 0$, existe $A > 0$ tal que 
   $$
     x > A \implies |F(x) - L| < \varepsilon/2
   $$
   - Então
   $$
      y > x > A \implies \left| \int_x^y f \right| = \left| \int_a^y f - \int_a^x f \right| = \left| \left( \int_a^y f - L \right) - \left( \int_a^x f - L \right) \right| < \varepsilon
   $$

2. $(\Leftarrow)$
   - Seja $n \in \mathbb{N}$ e defina 
   $$
      a_n = \int_a^n f(x) ~dx
   $$
   - Dado $\varepsilon > 0$, existe $A>0$ tal que 
   $$
      n > m > A \implies |a_n - a_m| = \left| \int_m^n f(x)~dx \right| < \varepsilon
   $$
   - Isso mostra que $(a_n)$ é de Cauchy.
   - Seja $L = \lim a_n$.
   - Assim, existe $B > 0$ tal que 
   $$
      n > m > B \implies |a_m - L| < \varepsilon/2 \quad \text{ e } \quad \left| \int_m^n f(x)~dx \right| < \varepsilon /2
   $$
   - Dessa forma, 
   $$
   \begin{aligned}
      \left| \int_a^n f(t)~dt - L \right| &= \left| \left( \int_a^m f(t)~dt - L \right) + \int_m^n f(t)~dt \right| \\
      &\le \left| \int_a^m f(t)~dt - L \right| + \left| \int_m^n f(t)~dt \right| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon
   \end{aligned}
   $$
   - Logo, 
   $$
      \lim_{x \to \infty} \int_a^x f(t)~dt = L
   $$

# Sequências e Séries de Funções

## Convergência Simples e Convergência Uniforme 

### Capítulo 12, Seção 1, Exercício 1

**Questão:** Mostre que a sequência de funções $f_n : [0, +\infty) \longrightarrow \mathbb{R}$, dadas por $f_n(x) = x^n/(1+x^n)$, converge simplesmente. Determine a função limite e mostre que a convergência não é uniforme.

**Resolução:** 

1. $(f_n)$ converge simplesmente.
   - Observe que
   $$
      f_n(x) = \frac{x^n}{1+x^n} = \frac{x^n}{x^n(1+1/x^n)} = \frac{1}{1+1/x^n}
   $$
   - Se $x \in[0,1)$, temos que $f_n(x) \to 0$. 
   - Se $x > 1$, então $f_n(x) \to 1$.
   - Se $x = 1$, então $f_n(x) = 1/2$.

2. Função limite $f$.
   $$
   f_n(x) \to f(x) = \begin{cases}
   0, & x \in [0,1) \\
   1/2, & x = 1 \\
   1, & x > 1
   \end{cases}
   $$

3. A convergência não é uniforme.
   - Note que cada $f_n$ é contínua, mas $f$ não é contínua. 

### Capítulo 12, Seção 1, Exercício 2

**Questão:** Prove que a sequência de funções $f_n : [0, +\infty] \longrightarrow \mathbb{R}$, dadas por $f_n(x) = x^n/(1+x^n)$ converge uniformemente em todos os intervalos do tipo $[0, 1-\delta]$ e $[1+\delta, +\infty)$, $0 < \delta < 1$.

**Resolução:** 

1. Intervalos $[0, 1-\delta]$.
   - Como $[0, 1-\delta] \subseteq [0,1)$, temos que $f_n(x) \to f(x) \equiv 0$ (pelo ex. 12.1.1).
   - Como $[0,1-\delta]$ é compacto, cada $f_n$ é contínua e $(f_n)$ é monótona ($f_1 \ge f_2 \ge \cdots \ge f_n \ge \cdots$), segue do Teorema de Dini que $f_n \to f$ uniformemente. 

2. Intervalos $[1+\delta, +\infty)$.
   - Pelo ex. 12.1.1, temos que $f_n(x) \to f(x) \equiv 1$.
   - Como $(f_n)$ é crescente ($f_{n+1} \ge f_n$), temos
   $$
      x \ge 1+\delta \implies f(x) \ge f(1+\delta)
   $$
   - Por outro lado, dado $\varepsilon > 0$, 
   $$
      |f_n(1+\delta) - 1| < \varepsilon \implies 1 - f_n(1+\delta) < \varepsilon \implies f_n(1+\delta) > 1-\varepsilon
   $$
   - Assim,
   $$
      f_n(x) \ge 1-\varepsilon \implies 1 - f_n(x) \le \varepsilon \implies |f_n(x) - 1| \le \varepsilon
   $$
   - para todo $x \in [1+\delta, +\infty)$.
   - Logo, a convergência é uniforme.

### Capítulo 12, Seção 1, Exercício 3

**Questão:** Prove que a série $\sum_{n=1}^\infty x^n(1-x^n)$ converge quando $x$ pertence ao intervalo $(-1, 1]$. Mostre que a convergência é uniforme em todos os intervalos do tipo $[-1+\delta, 1-\delta]$, onde $0 < \delta < 1/2$.

**Resolução:** 

- Defina $a = 1-\delta$.
- Então $x \in [-1+\delta, 1-\delta]$ significa que $|x| \le a < 1$. 
- Assim, $|x|^k \le a^k < 1$ implica $|1-x^k| \le 1 + |x^k| \le 2$.
- Portanto,
$$
\sum_{n=1}^\infty |x^n(1-x^n)| \le 2 \sum_{n=1}^\infty |x^n| \le 2 \sum_{n=1}^\infty a^n = \frac{2a}{1-a}
$$
- Assim, para todo $\varepsilon > 0$, existe $N \in \mathbb{N}$ tal que
$$
n \ge N \implies \sum_{n=N}^\infty |x^n(1-x^n)| = \frac{2a^N}{1-a} < \varepsilon
$$
- Ou seja, a convergência é uniforme.
- Por fim, note que para $x = 1$, temos
$$
\sum_{n=1}^\infty 1^n(1-1^n) = 0
$$
- Logo, a série converge para todo $x \in (-1, 1]$.

### Capítulo 12, Seção 1, Exercício 4 (Critério de Cauchy)

**Questão:** A fim de que a sequência de funções $f_n : X \longrightarrow \mathbb{R}$ convirja uniformemente, é necessário e suficiente que, para todo $\varepsilon > 0$ dado, exista $n_0 \in \mathbb{N}$ tal que
$$
m, n > n_0 \implies |f_m (x) - f_n (x)| < \varepsilon 
$$
qualquer que seja $x \in X$.

**Resolução:** 

1. $(\Rightarrow)$ Suponha que $f_n \to f$ uniformemente.
   - Dado $\varepsilon > 0$, existe $n_0 \in \mathbb{N}$ tal que, para todo $x \in X$, 
   $$
      n > n_0 \implies |f_n(x) - f(x)| < \varepsilon/2
   $$
   - Assim, para todo $x \in X$,
   $$
      n, m > n_0 \implies |f_m(x) - f_n(x)| \le |f_m(x) - f(x)| + |f_n(x) - f(x)| < \varepsilon
   $$

2. $(\Leftarrow)$ Suponha que $(f_n)$ é de Cauchy.
   - Como $(f_n)$ é de Cauchy, para todo $x \in X$, temos que $f_n(x) \to f(x)$.
   - Dado $\varepsilon > 0$, existe $n_0 \in \mathbb{N}$ tal que, para todo $x \in X$,
   $$
   m, n > n_0 \implies |f_m (x) - f_n (x)| < \varepsilon 
   $$
   - Tomando $m \to \infty$,
   $$
   \lim_{m \to \infty} |f_m (x) - f_n (x)| = |f_n(x) - f(x)| \le \varepsilon
   $$
   - Logo, $f_n \to f$ uniformemente.

### Capítulo 12, Seção 1, Exercício 5

**Questão:** Se a sequência de funções $f_n : X \longrightarrow \mathbb{R}$ converge uniformemente para $f : X \longrightarrow \mathbb{R}$, prove que $f$ é limitada se, e somente se, existem $K > 0$ e $n_0 \in \mathbb{N}$ tais que
$$
n > n_0 \implies |f_n (x)| \le K
$$
para todo $x \in X$.

**Resolução:** 

0. Preparo.
   - Como $f_n \to f$ uniformemente, dado $\varepsilon = 1$, existe $n_0 \in \mathbb{N}$ tal que, para todo $x \in X$,
   $$
      n > n_0 \implies ||f_n(x)| - |f(x)|| \le |f_n (x) - f(x)| \le 1
   $$

1. $(\Rightarrow)$ Suponha que $f$ é limitada. 
   - Então existe $K > 0$ tal que $|f(x)| \le K$.
   - Assim, 
   $$
      |f_n(x)| \le ||f_n(x)| - |f(x)|| + |f(x)| \le 1 + |f(x)| \le 1+K
   $$
   - Logo, a $f_n$ é limitada para $n \ge n_0$.

2. $(\Leftarrow)$ Suponha que, se $n \ge n_0$, então $|f_n (x)| \le K$.
   - Note que 
   $$
      |f(x)| \le ||f_n(x)| - |f(x)|| + |f_n(x)| \le 1 + |f_n(x)| \le 1 + K
   $$
   - Logo, $f$ é limitada.

### Capítulo 12, Seção 1, Exercício 6

**Questão:** Se a sequência de funções $f_n : X \longrightarrow \mathbb{R}$ é tal que $f_1 \ge f_2 \ge \ldots \ge f_n \ge \ldots$ e $f_n \to 0$ uniformemente em $X$, mostre que a série $\sum (-1)^n f_n$ converge uniformemente em $X$.

**Resolução:** 

- Seja $S_N$ a soma parcial $S_N = \sum_{n=1}^N (-1)^n f_n$.
- E seja $F_N$ a soma parcial $F_N = \sum_{n=1}^N (-1)^n$.
- Note que $|F_n| \le 1 =: K$ pois
$$ 
   \sum_{i=1}^n (-1)^i = \begin{cases} 0, & n \text{ par } \\ -1, & n \text{ ímpar } \end{cases} \implies \left| \sum_{i=1}^n (-1)^i \right| \le 1
$$
- Com isso, se $N >M$, 
$$
   \begin{aligned}
      |S_N(x) - S_M(x)| &= \left| \sum_{n=M+1}^N [F_n(x) - F_{n-1}(x)] f_n(x) \right| \\
      &= |F_N(x) f_N(x) - F_M(x) f_{M+1}(x)| + \left| \sum_{n = M+1}^{N-1} F_n(x) [f_n(x) - f_{n+1}(x)] \right| \\ 
      &\le K \left( |f_N(x)| + |f_{M+1}(x)| + \sum_{n=M+1}^{N-1} [f_n(x) - f_{n+1}(x)] \right) \\
      &= K \left( |f_N(x)| + |f_{M+1}(x)| + f_{M+1}(x) - f_N(x) \right)
   \end{aligned}
$$
- Tomando $M$ suficientemente grande (o que é possível, já que $f_n \to 0$), essa expressão pode ser tomada uniformemente pequena.
- Logo, $\sum (-1)^n f_n$ converge uniformemente em $X$.
- Obs: o argumento acima funciona para $\sum g_n$ com somas parciais uniformemente limitadas no lugar de $(-1)^n$.
<!-- $$
   \begin{aligned}
      S_m &= (-1)f_1 + f_2 + (-1)f_3 + \cdots + (-1)^m f_m \\
      &= (-1)(f_1 - f_2) + (-1 + 1)(f_2 - f_3) + (-1 + 1 - 1)(f_3 - f_4) + \cdots + (-1 + \ldots + (-1)^m)f_m \\
      &= s_1 (f_1 - f_2) + s_3 (f_2 - f_3) + s_3 (f_3 - f_4) + \cdots + s_m f_m \\
      &= \sum_{n=2}^m s_{n-1}(f_{n-1} - f_n) + s_m f_m
   \end{aligned}
- Como $|s_m| \le 1$ para todo $m$ e $\sum_{n=2}^\infty (f_{n-1} - f_n) \to f_1$, temos que a série $\sum_{n=2}^\infty s_{n-1}(f_{n-1} - f_n)$ é absolutamente convergente.
- E como $\lim_{m \to \infty} (s_m f_m) = 0$, temos que o limite $\lim_{m \to \infty} S_m$ existe.
- Logo, $\sum (-1)^n f_n$ converge.
$$ -->

### Capítulo 12, Seção 1, Exercício 7

**Questão:** Se $\sum |f_n(x)|$ converge uniformemente em $X$, prove que $\sum f_n(x)$ também converge uniformemente em $X$.

**Resolução:** 

- Pelo Critério de Cauchy, como $\sum |f_n(x)|$ converge uniformemente em $X$, para todo $\varepsilon > 0$, existe $n_0 \in \mathbb{N}$ tal que, para todo $x \in X$,
$$
n, m > n_0 \implies \left| \sum_{i=1}^m |f_i(x)| - \sum_{j=1}^n |f_j(x)| \right| = \left| \sum_{i=n+1}^m |f_i(x)| \right| < \varepsilon
$$
- Com isso,
$$
\left| \sum_{i=n+1}^m f_i(x) \right| \le \sum_{i=n+1}^m |f_i(x)| < \varepsilon
$$
- Logo, pelo Critério de Cauchy, $\sum f_n(x)$ converge uniformemente.

### Questão 2 (P2 2020)

**Questão:** Seja $f : [1, +\infty) \longrightarrow \mathbb{R}$ uma função não-negativa, contínua, não-crescente. Para cada $n \in \mathbb{N}$ seja $a_n = f(n)$. Prove que:
$$
\sum_{n=1}^\infty a_n \text{ converge } \implies \int_1^{+\infty} f(x)~dx \text{ converge }
$$

**Resolução:** 

- Note que se $x \in (n, n+1)$, então $a_{n+1} = f(n+1) \le f(x) \le f(n) = a_n$. 
- Portanto, para todo $n \in \mathbb{N}$,
$$
\int_n^{n+1} a_{n+1}~dx \le \int_n^{n+1} f(x)~dx \le \int_n^{n+1} a_{n}~dx \iff a_{n+1} \le \int_n^{n+1} f(x)~dx \le a_n
$$
- Seja $S_n = a_1 + \cdots + a_n$. Então
$$
S_{n+1} - a_1 \le \int_1^{n+1} f(x)~dx \le S_n
$$
- Como a série converge, $S_{n+1}$ e $S_n$ convergem. Logo, a integral converge.

### Questão 3 (P2 2020)

**Questão:** Sejam $f_n : X \longrightarrow \mathbb{R}$ para todo $n \in \mathbb{N}$. Mostre que a série de funções $\sum_{n=1}^\infty f_n(x)$ converge uniformemente em $X$ se, e somente se, para cada $\varepsilon > 0$, existe $n_0 \in \mathbb{N}$ tal que
$$
m > n > n_0 \implies \left| \sum_{k=n+1}^m f_k(x) \right| < \varepsilon
$$

**Resolução:**

1. Suponha que a série converge uniformemente.
   - Dado $\varepsilon > 0$ existe $n_0 \in \mathbb{N}$ tal que, para todo $x \in X$, 
   $$
   n > n_0 \implies \left| \sum_{k=1}^n f_k(x) - \sum_{k=1}^\infty f_k(x) \right| < \varepsilon / 2
   $$
   - Portanto, se $m > n > n_0$,
   $$
    \left| \sum_{k=n+1}^m f_k(x) \right| = \left| \sum_{k=1}^m f_k(x) - \sum_{k=1}^n f_k(x) \right| \le \left| \sum_{k=1}^m f_k(x) - \sum_{k=1}^\infty f_k(x) \right| + \left| \sum_{k=1}^n f_k(x) - \sum_{k=1}^\infty f_k(x) \right| < \varepsilon 
   $$

2. Suponha que a "volta" é válida.
   - Dado $\varepsilon > 0$, existe $n_0 \in \mathbb{N}$ tal que 
   $$
   m > n > n_0 \implies \left| \sum_{k=n+1}^m f_k(x) \right| = \left| \sum_{k=1}^m f_k(x) - \sum_{k=1}^n f_k(x) \right| < \varepsilon
   $$
   - Como a sequência das somas parciais é de Cauchy, temos que ela converge. 
   - Portanto, fixando $n$ e tomando $m \to \infty$, 
   $$
   \lim_{m \to \infty} \left| \sum_{k=1}^m f_k(x) - \sum_{k=1}^n f_k(x) \right| = \left| \sum_{k=1}^n f_k(x) - \sum_{k=1}^\infty f_k(x) \right| \le \varepsilon
   $$
   - Logo, a série converge uniformemente.

## Propriedades da convergência uniforme

### Capítulo 12, Seção 2, Exercício 1a

**Questão:** Suponha que $f_n \to f$ e $g_n \to g$ uniformemente no conjunto $X$. Mostre que $f_n + g_n \to f+g$ uniformemente em $X$.

**Resolução:** 

- Como $f_n \to f$ uniformemente, dado $\varepsilon > 0$, existe $n_f \in \mathbb{N}$ tal que 
$$
   n \ge n_f \implies |f_n(x) - f(x)| <  \varepsilon/2, \quad \forall ~x \in X
$$
- E como $g_n \to g$ uniformemente, existe $n_g \in \mathbb{N}$ tal que 
$$
   n \ge n_g \implies |g_n(x) - g(x)| <  \varepsilon/2, \quad \forall ~x \in X
$$
- Tome $N = \max \{ n_f, n_g \}$ e suponha $n \ge N$. 
- Então
$$
   |(f_n(x) + g_n(x)) - (f(x) + g(x))| \le |f_n(x) - f(x)| + |g_n(x) - g(x)| <  \varepsilon, \quad \forall ~x \in X
$$
- Logo, $f_n + g_n \to f + g$ uniformemente.

### Capítulo 12, Seção 2, Exercício 1b

**Questão:** Suponha que $f_n \to f$ e $g_n \to g$ uniformemente no conjunto $X$. Mostre que se $f$ e $g$ forem limitadas, então $f_n \cdot g_n \to f \cdot g$ uniformemente em $X$.

**Resolução:** 

- Como $f$ e $g$ são limitadas, $f_n$ e $g_n$ são limitadas para $n$ suficientemente grande. 
- Considere $L$ e $K$ tais que $|f(x)| \le L$ e $|g(x)| \le K$ para todo $x \in X$.
- Tomemos $n_1 \in \mathbb{N}$ tal que $|f_n| \le L$ e $n_2 \in \mathbb{N}$ tal que $|g_n| \le K$ para todo $x \in X$.
- Como $f_n \to f$ uniformemente, dado $\varepsilon > 0$, existe $n_f \in \mathbb{N}$ tal que 
$$
   n \ge n_f \implies |f_n(x) - f(x)| < \frac{\varepsilon}{2K}, \quad \forall ~x \in X
$$
- E como $g_n \to g$ uniformemente, existe $n_g \in \mathbb{N}$ tal que 
$$
   n \ge n_g \implies |g_n(x) - g(x)| < \frac{\varepsilon}{2L}, \quad \forall ~x \in X
$$
- Tome $N = \max \{ n_1, n_2, n_f, n_g \}$ e suponha $n \ge N$. 
- Então
$$
\begin{aligned}
   |f_n(x) g_n(x) - f(x)g(x)| &= |f_n(x)g_n(x) - f_n(x)g(x) + f_n(x)g(x) - f(x)g(x)| \\
   &= |f_n(x)[g_n(x) - g(x)] + g(x)[f_n(x) - f(x)]| \\
   &\le |f_n(x)||g_n(x) - g(x)| + |g(x)||f_n(x) - f(x)| \\
   &< L \frac{\varepsilon}{2L} + K \frac{\varepsilon}{2K} = \varepsilon
\end{aligned}
$$

### Capítulo 12, Seção 2, Exercício 1c

**Questão:** Suponha que $f_n \to f$ e $g_n \to g$ uniformemente no conjunto $X$. Mostre que, se existir $c > 0$ tal que $|g(x)| \ge c$ para todo $x \in X$, então $1/g_n \to 1/g$ uniformemente em $X$.

**Resolução:** 

- Como $|g(x)| \ge c$, $1/|g(x)| \le c$.
- Note que existe $n_0 \in \mathbb{N}$ tal que $1/|g_n(x)| \le K$. 
- Assim, 
$$
   \frac{1}{|g(x)||g_n(x)|} \le \frac{K}{c}
$$
- Como a convergência é uniforme, podemos tomar 
$$
   |g_n(x) - g(x)| < c \varepsilon/K
$$
- Portanto,
$$
   \left| \frac{1}{g(x)} - \frac{1}{g_n(x)} \right| = \left| \frac{g_n(x) - g(x)}{g_n(x) g(x)} \right| \le \frac{K}{c} \frac{c \varepsilon}{K} = \varepsilon
$$

### Capítulo 12, Seção 2, Exercício 2

**Questão:** Seja $p : \mathbb{R} \longrightarrow \mathbb{R}$ um polinômio de grau $\ge 1$. Mostre que a sequência de funções $f_n : \mathbb{R} \longrightarrow \mathbb{R}$, dadas por $f_n(x) = p(x) + 1/n$, converge uniformemente para $p \in \mathbb{R}$, porém $(f_n^2)$ não converge uniformemente para $p^2$.

**Resolução:** 

- Dado $\varepsilon > 0$, tome $n_0 \in \mathbb{N}$ tal que $n_0 > 1/\varepsilon$.
- Então, para todo $x \in \mathbb{R}$,
$$
   n \ge n_0 \implies |p(x) + 1/n - p(x)| = |1/n| = 1/n \le 1/n_0 < \varepsilon
$$
- Logo, $f_n \to f$ uniformemente.
- Note que $f_n^2 = p^2 + 2p/n + 1/n^2$.
- Escreva $p(x) = a_0 + a_1x + \cdots + a_k x^k$.
- Com isso, 
$$
   |p^2(x) + 2p(x)/n + 1/n^2 - p^2(x)| = |2p(x)/n + 1/n^2| = \frac{1}{n} 2(a_0 + a_1 x + \cdots + a_k x^k) + \frac{1}{n^2}
$$
- Tomando $x=n$, se $\deg p = 1$, temos que $(f_n^2)$ converge para $2_a$. E se $\deg p > 1$, $(f_n^2)$ diverge.
- Tomando $x = n^2$, temos que $(f_n^2)$ diverge.

### Capítulo 12, Seção 2, Exercício 3

**Questão:** Seja a sequência de funções $f_n : [0,1] \longrightarrow \mathbb{R}$, onde $f_n(x) = \sin(nx)/\sqrt{n}$. Mostre que $(f_n)$ converge uniformemente para $0$, mas a sequência das derivadas $f_n'$ não converge em ponto algum do intervalo $[0,1]$.

**Resolução:** 

1. $(f_n)$ converge uniformemente para $0$
   - Basta notar que
   $$
      |f_n(x)| = \left| \frac{\sin(nx)}{\sqrt{n}} \right| \le \frac{1}{\sqrt{n}} \to 0
   $$

2. Sequência das derivadas.
   - Note que 
   $$
      f_n'(x) = \sqrt{n} \cos(nx)
   $$
   - Como $\sqrt{n} \to \infty$, o limite $\lim f_n'$ só existe se $\lim \cos(nx) = 0$.
   - Mas observe que $\cos(2nx) = \cos^2(nx) - \sin^2(nx)$
   - E $\cos^2(nx) = 1 - \sin^2(nx)$.
   - Assim, se $\lim \cos(nx) = 0$, teríamos que $0 = -1$.
   - Logo, $f_n'$ não converge.

### Capítulo 12, Seção 2, Exercício 4

**Questão:** Mostre que a sequência de funções $g_n(x) = x + x^n/n$ converge uniformemente no intervalo $[0,1]$ para uma função derivável $g$ e a sequência das derivadas $g_n'$ converge simplesmente em $[0,1]$, mas $g' \neq \lim g_n'$.

**Resolução:** 

1. $g_n \to g$ uniformemente.
   - Mostremos que $g_n(x) \to g(x) = x$.
   $$
      \left| x+\frac{x^n}{n} - x \right| = \left| \frac{x^n}{n} \right| \le \frac{1}{n} \to 0
   $$
   - E note que $g(x) = x$ é derivável com $g'(x) = 1$.

2. $g_n'$ converge simplemente.
   - Temos que $g_n'(x) = 1 + x^{n-1}$.
   - Se $x = 0$, então $g_n'(x) \to 1$.
   - Se $x = 1$, então $g_n'(x) \to 2$.
   - Se $x \in (0,1)$, então $g_n'(x) \to 1$ pois $\lim x^{n-1} = 0$.
   - Assim, $g_n'$ converge simplesmente em $[0,1]$, mas $g' \neq \lim g_n'$.

### Capítulo 12, Seção 2, Exercício 8

**Questão:** A sequência de funções $f_n : [0,1] \longrightarrow \mathbb{R}$, $f_n(x) = nx(1-x)^n$, converge, porém não uniformemente. Mostre que, apesar disso,
$$
\int_0^1 \lim_{n \to \infty} f_n = \lim_{n \to \infty} \int_0^1 f_n
$$

**Resolução:** 

1. $(f_n)$ converge simplesmente.
   - Se $x = 0$, então $nx(1-x)^n = 0$.
   - Se $x = 1$, então $nx(1-x)^n = 0$.
   - Se $x \in (0,1)$, então $nx(1-x)^n \to 0$.

2. $(f_n)$ não converge uniformemente.
   - Tome $x = 1/n$.
   $$
      |f_n(1/n)| = \left| n \frac{1}{n} \left(1 - \frac{1}{n} \right)^n \right| = \left| \left(1 - \frac{1}{n} \right)^n \right| \to \frac{1}{e}
   $$
   - Como podemos tomar $n$ suficientemente grande tal que 
   $$
      |f_n(1/n)| \ge 1/3
   $$
   - Temos $1/3 \le |f_n(1/n)| < 1/e$. 
   - Logo, a convergência não é uniforme.

3. A integral do limite é o limite da integral.
   - Façamos a mudança de variáveis $y = 1-x$.
   - Então
   $$
   \begin{aligned}
      \int_0^1 nx(1-x)^n ~dx &= \int_0^1 n(1-y)y^n ~dy = \int_0^1 ny^n ~dy - \int_0^1 ny^{n+1} ~dy \\
      &= \left.\left[ \frac{n y^{n+1}}{n+1} - \frac{n y^{n+2}}{n+2} \right]\right|_0^1 = \frac{n}{n+1} - \frac{n}{n+2} \to 0
   \end{aligned}
   $$
   - Por outro lado, $f_n \to 0$. 
   - Logo, 
   $$
   \int_0^1 \lim_{n \to \infty} f_n = \lim_{n \to \infty} \int_0^1 f_n
   $$