---
title: MA602 Análise 2 - Exercícios
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

## Integral de Riemann

### Capítulo 10, Seção 2, Exercício 1 

**Questão:** Defina $f : [0, 1] \longrightarrow \mathbb{R}$ como
$$
f(x) = \begin{cases} f(0) = 0 \\ 
\frac{1}{2^n}, \text{ caso } \frac{1}{2^{n+1}} < x \leq \frac{1}{2^n}, ~n \in \mathbb{N}_0 \end{cases}
$$
Prove que $f$ é integrável e calcule $\int_0^1 f(x)~dx$.

**Resolução:** 

- Vamos definir duas funções: 
$$ 
\phi_m(x) = \begin{cases} \frac{1}{2^n}, ~\text{se}~ \frac{1}{2^{n+1}} < x < \frac{1}{2^n} ~\text{e}~ 1 \leq n \leq m \\ 0, ~\text{caso contrário} \end{cases}
$$
e
$$ 
\psi_m(x) = \begin{cases} \frac{1}{2^n}, ~\text{se}~ \frac{1}{2^{n+1}} < x < \frac{1}{2^n} ~\text{e}~ 1 \leq n \leq m \\ \frac{1}{2^m}, ~\text{caso contrário} \end{cases}
$$

- Note que $\phi_m(x) \leq f(x) \leq \psi_m(x)$ para todo $x \in [0,1]$.

- Tome uma partição $P_m = \{ 0, \frac{1}{2^{m+1}}, \frac{1}{2^{m}}, \ldots, \frac{1}{2}, 1 \}$.

- Com isso, temos que, conforme $m \to \infty$
$$
S(f, P) - s(f, P) \leq S(\psi_m, P_m) - s(\phi_m, P_m) = \frac{1}{2^m} - \frac{1}{2^{m+1}} \to 0 
$$

- Portanto, $f$ é integrável em $[0,1]$.

- Para calcular seu valor, tomamos o limite da soma superior
$$
\sum_{i=0}^k \frac{1}{2^i} \left( \frac{1}{2^i} - \frac{1}{2^{i+1}}  \right) = \frac{1}{6} (4 - 4^{-k}) \to \frac{2}{3}
$$

### Capítulo 10, Seção 2, Exercício 3 (Thomae's function)

**Questão:** Seja $f : [a, b] \longrightarrow \mathbb{R}$ dada por 
$$
f(x) = \begin{cases} 0, \text{ se } x \in \mathbb{R} \setminus \mathbb{Q} \\ 
\frac{1}{q}, \text{ se } x = \frac{p}{q} \text{ é fração irredutível }, ~q>0 
\\
f(0) = 1, \text{ se } 0 \in [a,b]
\end{cases}
$$
Prove que $f$ é contínua apenas nos pontos irracionais de $[a, b]$, que é integrável e que $\int_a^b f(x)~dx = 0$.

<p style="text-align: center;">

![Thomae's function](640px-Thomae_function_(0,1).png)

</p>

**Resolução:** 

- $f$ não é contínua em $x \in \mathbb{Q}$. 

   - Considere a sequência $(x_n)$ dada por 
   $$
   x_n = \frac{p}{q} \left(1 - \frac{1}{n \sqrt{2}} \right) \overset{n \to \infty}{\longrightarrow} \frac{p}{q} = x
   $$
   - Como cada $x_n$ é irracional, temos que $0 = f(x_n) \not\to f(x)$. Ou seja, $f$ não é contínua em $x$ racional.

- $f$ é contínua em $x \in \mathbb{R} \setminus \mathbb{Q}$.

   - Seja $\varepsilon > 0$ e $n \in \mathbb{N}$ tal que $1/n < \varepsilon$.

   - Note que o conjunto $C = \{ \frac{a}{b} : 1 \leq b \leq n, ~a \in \mathbb{Z} \}$ formado pelos racionais com denominador menor ou igual a $n$ é finito. 
   
   - Escolha $\delta = \min_{c \in C} |x - c|$ e note que $\delta > 0$.
   
   - Suponha $|x - y| < \delta$.
   
   - Se $y$ é irracional, é imediato: $|f(x) - f(y)| = 0 < \varepsilon$. 

   - Caso $y$ seja racional, então $y \notin C$. 

   - Assim, $y$ é da forma $y = p/q$ com $q > n$. Ou seja,
   $$
   |f(x) - f(y)| = |f(y)| = \frac{1}{q} < \frac{1}{n} < \varepsilon
   $$

- $f$ é integrável e $\int_a^b f(x)~dx = 0$.

   - *Observação:* note que os pontos de descontinuidade de $f$ são os racionais, que têm medida nula. Portanto, $f$ é integrável.

   - Note que $0 \leq f(x) \leq 1$, ou seja, $f$ é limitada.

   - Dado $\varepsilon > 0$ e defina
   $$
   F = \left\{ x \in [a,b] : f(x) \geq \frac{\varepsilon}{b-a} \right\}
   $$
   que é o conjunto das frações irredutíveis pertencentes a $[a,b]$ com denominador menor ou igual a $\frac{b-a}{\varepsilon}$. Assim, $F$ é finito.

   - Seja $P$ uma partição de $[a,b]$ tal que a soma dos comprimentos dos intervalos de $P$ que contêm algum ponto de $F$ é menor do que $\varepsilon$. 

   - Observe que se $F \cap [t_{i-1}, t_i] = \emptyset$, então $0 \leq f(x) < \frac{\varepsilon}{b-a}$ para todo $x \in [t_{i-1}, t_i]$. Assim, $M_i \leq \frac{\varepsilon}{b-a}$. 

   - Com isso, temos a seguinte soma superior
   $$
   S(f, P) = \sum M_i (t_i - t_{i-1}) = \sum M_i' (t_i' - t_{i-1}') + \sum M_i'' (t_i'' - t_{i-1}'')
   $$
   em que $[t_{i-1}', t_i']$ são os intervalos que intersectam $F$ e $[t_{i-1}'', t_i'']$ são os intervalos disjuntos de $F$.

   - Como $M_i' \leq 1$ e $\sum (t_i' - t_{i-1}') < \varepsilon$ pela definição da partição, temos que $$ \sum M_i' (t_i' - t_{i-1}') < \varepsilon $$

   - E como $M_i'' \leq \frac{\varepsilon}{b-a}$ e $\sum (t_i'' - t_{i-1}'') < b-a$, temos que $$ \sum M_i'' (t_i'' - t_{i-1}'') < \varepsilon $$

   - Portanto, $S(f, P) < 2 \varepsilon$. Assim, $\overline{\int_a^b} f(x)~dx = 0$.

   - Por fim, como $f(x) \geq 0$ para todo $x$, temos que
   $$
   0 \leq \underline{\int_a^b} f(x)~dx \leq \overline{\int_a^b} f(x)~dx = 0
   $$
   
   - Logo, $f$ é integrável e $\int_a^b f(x)~dx = 0$.

### Capítulo 10, Seção 2, Exercício 4

**Questão:** Seja $f : [a, b] \longrightarrow \mathbb{R}$ uma função integrável com $f(x) \geq 0$ para todo $x \in [a,b]$. Se $f$ é contínua no ponto $c \in [a, b]$ e $f(c) > 0$, prove que $\int_a^b f(x)~dx > 0$.

**Resolução:** 

- Como $f$ é contínua em $c$ e $f(c) > 0$, existe $\delta > 0$ tal que $f(x) > f(c)/2 =: m$ para todo $x \in (c - \delta, c + \delta) \cap [a, b]$.

- Tome uma partição $P$ contendo os pontos $c - \delta$ e $c + \delta$.

- Assim, temos que $s(f, P) > 2m \delta > 0$.

- Logo, como $f$ é integrável, $\int_a^b f(x)~dx \geq s(f, P) > 0$.

### Capítulo 10, Seção 2, Exercício 5

**Questão:** Seja $f : [a, b] \longrightarrow \mathbb{R}$ definida por
$$
f(x) = \begin{cases} x, \text{ se } x \in \mathbb{Q} \\ 
x+1, \text{ se } x \in \mathbb{R} \setminus \mathbb{Q}
\end{cases}
$$
Calcule as integrais (inferior e superior) de $f$.

Usando uma função contínua $g: [a, b] \longrightarrow \mathbb{R}$ em vez de $x$, defina agora 
$$
\varphi(x) = \begin{cases} g(x), \text{ se } x \in \mathbb{Q} \\ 
g(x) + 1, \text{ se } x \in \mathbb{R} \setminus \mathbb{Q}
\end{cases}
$$
Calcule as integrais (inferior e superior) de $\varphi$ em termos da integral de $g$.

**Resolução:** 

- Note que para uma partição $P$ qualquer, temos a seguinte soma inferior
$$
m_i = \inf_{[t_{i-1}, t_i]} x = t_{i-1} \implies \underline{\int_a^b} f = \sup_P \sum_{i=1}^n m_i \Delta t_i = \sum_{i=1}^n \frac{t_{i-1} + t_i}{2} (t_i - t_{i-1}) = \frac{b+a}{2}(b-a) = \frac{b^2-a^2}{2}
$$

- E a seguinte soma superior 
$$
M_i = \sup_{[t_{i-1}, t_i]} x + 1 = t_{i} + 1 \implies \overline{\int_a^b} f = \inf_P \sum_{i=1}^n M_i \Delta t_i = \inf_P \left( \sum_{i=1}^n \sup_{[t_{i-1}, t_i]} x \Delta t_i + \sum_{i=1}^n \Delta t_i \right)
$$
i.e., 
$$
\sum_{i=1}^n \frac{t_{i-1} + t_i}{2} (t_i - t_{i-1}) + (b-a) = \frac{b^2-a^2}{2} + (b-a)
$$ 

- Analogamente, usando $g(x)$ em vez de $x$, 
$$
m_i = \inf_{[t_{i-1}, t_i]} g(x) \implies \underline{\int_a^b} f = \underline{\int_a^b} g
$$ 
e
$$
M_i = \sup_{[t_{i-1}, t_i]} g(x) + 1 \implies \overline{\int_a^b} f = \overline{\int_a^b} g + (b-a)
$$

### Capítulo 10, Seção 3, Exercício 2

**Questão:** Prove que se $f, g : [a,b] \longrightarrow \mathbb{R}$ são integráveis, então são também integráveis as funções $\varphi, \psi : [a,b] \longrightarrow \mathbb{R}$ definidas por 
$$
\varphi(x) = \max \left\{ f(x), g(x) \right\} \text{ e } \psi(x) = \min \left\{ f(x), g(x) \right\}
$$

Conclua que as funções $f_+, f_-: [a,b] \longrightarrow \mathbb{R}$  dadas por 
$$
f_+(x) = \begin{cases}
0, \text{ se } f(x) \leq 0
\\
f(x), \text{ se } f(x) > 0
\end{cases}
$$
e
$$
f_-(x) = \begin{cases}
0, \text{ se } f(x) \geq 0
\\
-f(x), \text{ se } f(x) <> 0
\end{cases}
$$

**Resolução:** 

- Note que 
$$
\varphi = \max \{ f, g \} = \frac{f(x) + g(x) + |f(x) - g(x)|}{2}
$$
e 
$$
\psi = \min \{ f, g \} = \frac{f(x) + g(x) - |f(x) - g(x)|}{2}
$$
são integráveis. 

- Como $f_+ = \max \{ f, 0 \}$ e $f_- = - \min \{ f, 0 \}$, segue que ambas são integráveis.

### Capítulo 10, Seção 4, Exercício 2

**Questão:** Mostre que o conjunto dos pontos de descontinuidade de uma função monótona é enumerável.

**Resolução:**

- Seja $D$ o conjunto dos pontos de descontinuidade de uma função monótona $f$.

- Caso $f$ seja constante, então $D$ é vazio e, portanto, tem medida nula.

- Suponha $D \neq \emptyset$. Para cada $a \in D$ temos que limites laterais diferem, i.e.
$$
   \lim_{x \to a^-} f(x) = a_1 \neq a_2 = \lim_{x \to a^+} f(x)
$$

- Tomando outro ponto em $D$, digamos $b \in D \setminus \{ a \}$, temos que os intervalos $(a_1, a_2)$ e $(b_1, b_2)$ são disjuntos, porque $f$ é monótona. 

- Escolhendo um racional em cada intervalo $(a_1, a_2)$ temos uma função injetora $D \longrightarrow \mathbb{Q}$. Logo, $D$ é enumerável.

### Capítulo 10, Seção 4, Exercício 3

**Questão:** Seja $D$ o conjunto dos pontos de descontinuidade de uma função limitada $f : [a,b] \longrightarrow \mathbb{R}$. Se $D'$ (conjunto dos pontos de acumulação de $D$) é enumerável, prove que $f$ é integrável.

**Resolução:**

- Sabemos que o conjunto dos pontos isolados $D \setminus D'$ é enumerável.

- Assim, $(D \setminus D') \cup D'$ é enumerável.

- Como $D \subset (D \setminus D') \cup D'$, segue que $D$ também é enumerável.

- Logo, $D$ tem medida nula e, com isso, $f$ é integrável.

### Capítulo 10, Seção 4, Exercício 4

**Questão:** Seja $A \subsetneq [a,b]$ um conjunto de medida nula, $B = [a,b] \setminus A$ e $f : [a,b] \longrightarrow \mathbb{R}$ uma função integrável tal que $f(B) = \{ 0 \}$. Mostre que sua integral é igual a zero.

**Resolução:**

- Como em qualquer subintervalo de $[a,b]$, o ínfimo de $|f|$ é zero, temos que
$$
\underline{\int_a^b} |f| = 0
$$

- Como $f$ é integrável, $|f|$ também é. Assim,
$$
\int_a^b |f| = 0 \implies 0 \leq \left| \int_a^b f \right| \leq \int_a^b |f| = 0
$$

- Logo,
$$
\int_a^b f = 0
$$

### Capítulo 10, Seção 4, Exercício 5d

**Questão:** Seja $X$ um subconjunto de $\mathbb{R}$ de conteúdo nulo. Se uma função limitada $g : [a,b] \longrightarrow \mathbb{R}$ coincide com uma função integrável $f : [a,b] \longrightarrow \mathbb{R}$ exceto num conjunto de conteúdo nulo, mostre que $g$ é integrável e sua integral é igual à de $f$.

**Resolução:**

- Como $X$ não pode conter um intervalo, temos que $\inf |g-f| = 0$ em qualquer intervalo. 

- Ou seja, $s(g-f, P) = 0$ para qualquer partição $P$.

- Seja $M = \sup |g-f|$.

- Como $X$ tem conteúdo nulo, dado $\varepsilon > 0$, existem finitos intervalos abertos $I_k$ tais que
$$
X \subset \bigcup_{k=1}^n I_k \quad \text{ e } \quad \sum_{k=1}^n |I_k| < \frac{\varepsilon}{M}
$$

- Como cada $I_k \subset [a,b]$, as extremidades de $I_k$ com $a$ e $b$ formam uma partição $P$ do intervalo. 

- Sejam $I_j$ os intervalos de $P$ que contém pontos de $X$.

- E observe $(g-f)(x) = 0$ para todo $x \in [a,b] \setminus X$.

- Assim,
$$
S(g-f, P) = \sum_{j : [t_{i-1}, t_i] = I_j} M_i \Delta t_i + \sum_{[t_{k-1}, t_k] \neq I_j, \forall j} M_k \Delta t_k \leq \sum_{j : [t_{i-1}, t_i] = I_j} M \Delta t_i < M \frac{\varepsilon}{M} = \varepsilon
$$

- Portanto,
$$
S(g-f, P) = 0 = s(g-f, P) \implies \overline{\int_a^b} (g-f) = \underline{\int_a^b} (g-f) = 0
$$

- Logo, $g-f$ é integrável e 
$$
\int_a^b g = \int_a^b f
$$

## Cálculo com Integrais

### Capítulo 11, Seção 2, Exercício 2

**Questão:** Seja $f: [a, b] \longrightarrow \mathbb{R}$. Mostre que se existe $\lim_{|P| \to 0} \sum (f, P^\ast)$ então $f$ é uma função limitada.

**Resolução:**

- Suponha $f$ ilimitada.

- Dada uma partição $P$, $f$ deve ser ilimitada em pelo menos um intervalo $[t_{i-1}, t_i]$.

- I.e., existe $x_i \in [t_{i-1}, t_i]$ tal que
$$
|f(x_i) \Delta t_i| > \left| \sum_{\substack{j=1 \\ j\neq i}}^n f(\xi_j) \Delta t_j \right| + A, \quad A > 0
$$

- Com isso, temos a seguinte soma de Riemann,
$$
\left| \sum (f, P^\ast) \right| = \left| f(x_i) \Delta t_i +  \sum_{\substack{j=1 \\ j\neq i}}^n f(\xi_j) \Delta t_j \right| \geq \left| |f(x_i) \Delta t_i| - \left| \sum_{\substack{j=1 \\ j\neq i}}^n f(\xi_j) \Delta t_j \right| \right| > A
$$

- Como $A$ é arbitrário, o limite $\lim_{|P| \to 0} \sum (f, P^\ast)$ não existe.

### Capítulo 11, Seção 2, Exercício 4

**Questão:** Sejam $f, g: [a, b] \longrightarrow \mathbb{R}$ integráveis. Para toda partição $P = \{ t_0, \ldots, t_n \}$ de $[a,b]$ sejam $P^\ast = (P, \xi)$ e $P^\# = (P, \eta)$ pontilhamentos de $P$. Prove que
$$
\lim_{|P| \to 0} \sum f(\xi_i) g(\eta_i)(t_i - t_{i-1}) = \int_a^b f(x) g(x) ~dx
$$

**Resolução:**

- Observe que
$$
f(\xi_i) g(\eta_i) = f(\xi_i) g(\xi_i) + f(\xi_i)[g(\eta_i) - g(\xi_i)]
$$

- Multiplicando por $\Delta t_i$ e somando em $i$,
$$
\sum_{i=1}^n f(\xi_i) g(\eta_i) \Delta t_i = \sum_{i=1}^n f(\xi_i) g(\xi_i) \Delta t_i + \sum_{i=1}^n f(\xi_i)[g(\eta_i) - g(\xi_i)] \Delta t_i
$$

- Seja $M = \sup f$. Então, como $g$ é integrável, dado $\varepsilon > 0$, 
$$
\sum_{i=1}^n f(\xi_i)[g(\eta_i) - g(\xi_i)] \Delta t_i \leq M \sum_{i=1}^n [g(\eta_i) - g(\xi_i)] \Delta t_i \leq M (S(g, P) - s(g, P)) <  M \frac{\varepsilon}{M} = \varepsilon
$$

- Portanto, tomando o limite,
$$
\lim_{|P| \to 0} \sum_{i=1}^n f(\xi_i) g(\eta_i) \Delta t_i = \lim_{|P| \to 0} \sum_{i=1}^n f(\xi_i) g(\xi_i) \Delta t_i = \int_a^b f(x) g(x) ~dx
$$

### Capítulo 11, Seção 2, Exercício 5

**Questão:** Dadas $f, g: [a, b] \longrightarrow \mathbb{R}$, para cada partição pontilhada $P^\ast$ de $[a,b]$ define-se a soma de Riemann-Stieltjes 
$$
\sum(f, g, P^\ast) = \sum f(\xi_i)[g(t_i) - g(t_{i-1})]
$$
Mostre que se $f$ é integrável e $g$ possui derivada integrável, então
$$
\lim_{|P| \to 0} \sum (f,g, P^\ast) = \int_a^b f(x) g'(x)~dx
$$

**Resolução:**

- Pelo Teorema do Valor Médio, para cada intervalo $[t_{i-1}, t_i]$ de $P$, existe $\eta_i \in [t_{i-1}, t_i]$ tal que 
$$
g'(\eta_i) = \frac{g(t_i) - g(t_{i-1})}{(t_i - t_{i-1})}
$$

- Com isso, 
$$
\sum_{i=1}^n f(\xi_i)[g(t_i) - g(t_{i-1})] = \sum_{i=1}^n f(\xi_i) g'(\eta_i) (t_i - t_{i-1})
$$

- Pelo exercício anterior,
$$
\lim_{|P| \to 0} \sum (f,g, P^\ast) = \lim_{|P| \to 0} \sum_{i=1}^n f(\xi_i) g'(\eta_i) (t_i - t_{i-1}) = \int_a^b f(x) g'(x) ~dx
$$

### Capítulo 11, Seção 2, Exercício 6

**Questão:** Dada $f : [a,b] \longrightarrow \mathbb{R}$, seja, para cada $n \in \mathbb{N}$,
$$
M(f, n) = \frac{1}{n} \sum_{i=1}^n f(a+ih), \quad h = \frac{(b-a)}{n},
$$
a média aritmética dos valores $f(a+h), f(a+2h), \ldots, f(a+nh) = f(b)$. 

Prove que se a função $f$ é integrável, então
$$
\lim_{n \to \infty} M(f,n) = \frac{1}{b-a} \int_a^b f(x)~dx
$$

Por este motivo, o segundo membro desta igualdade se chama o valor médio da função $f$ no intervalo $[a,b]$.

**Resolução:**

1. Construir uma partição: Note que $P = \{ a, a+h, \ldots, a+nh \}$ é uma partição de $[a,b]$.

2. Pontilhar a partição: Para cada intervalo $[a+(i-1)h, a+ih]$ tome $\xi_i = a+ih$.

3. Escreva a soma de Riemann:
$$
\sum(f, P^\ast) = \sum_{i=1}^n f(a+ih)h = \frac{(b-a)}{n} \sum_{i=1}^n f(a+ih)
$$

4. Compare com $M(f, n)$:
$$
M(f,n) = \frac{1}{b-a} \sum(f, P^\ast)
$$

5. Tome o limite:
$$
\lim_{n \to \infty} M(f,n) = \lim_{n \to \infty} \frac{1}{b-a} \sum(f, P^\ast) = \frac{1}{b-a} \int_a^b f(x)~dx
$$