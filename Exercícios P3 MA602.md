---
title: MA602 Análise 2 - Exercícios P3
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

## Séries de potências

### 12.3.1

**Questão:** Seja $r$ o raio de convergência da série de potências $\sum a_n (x - x_0)^n$. Prove que se $r \in \mathbb{R}^+$, então $r = 1/L$, onde $L$ é o maior valor de aderência da sequência limitada $(\sqrt[n]{|a_n|})$. Assim, temos $$r = \frac{1}{(\limsup \sqrt[n]{|a_n|})}$$

**Resolução:**

1. Sejam $a$ e $b$ tais que $a < 1/r < b$. Como $r < 1/a$, temos que $1/a \in R$, porque $r = \sup R = \sup \{ \rho > 0 : \sqrt[n]{|a_n|} < 1/\rho, ~\forall~n \text{ suficientemente grande} \}$. Como $\sqrt[n]{|a_n|} < 1/r$, existem infinitos $n \in \mathbb{N}$ tais que $\sqrt[n]{|a_n|} \ge a$.
2. Como $1/b < r$, existe $\rho \in R$ tal que $1/b < \rho < r$. Assim, dado $n$ suficientemente grande, temos que $\sqrt[n]{|a_n|} < 1/\rho < b$. Ou seja, existem apenas finitos índices $n$ tais que $\sqrt[n]{|a_n|} \ge b$.
3. Portanto, $1/r$ é valor de aderência de $(\sqrt[n]{|a_n|})$ e nenhum número maior do que $1/r$ satisfaz isso.

### 12.3.2

**Questão:** Se $\sqrt[n]{|a_n|} = L$, prove que as séries de potências $$\sum_{n=0}^\infty a_n x^{2n} \quad \text{ e } \quad \sum_{n=0}^\infty a_n x^{2_n + 1}$$ têm ambas raio de convergência igual a $1/\sqrt{L}$.

**Resolução:**

1. A ideia é reescrever a série para ter $x^n$. 
2. Sejam $b_{2n} = a_n$ e $b_{2n-1} = 0$. Assim,
$$
\sum a_n x^{2n} = \sum b_n x^n
$$
3. Temos que os termos ímpares de $b_n$ são nulos e 
$$
\lim \sqrt[n]{|b_n|} = \lim \sqrt[2n]{|b_{2n}|} = \lim \sqrt[2n]{|a_n|} = \lim \sqrt{\sqrt[n]{|a_n|}} = \sqrt{L}
$$
4. Ou seja, temos dois valores de aderência: $0$ e $\sqrt{L}$. Pelo exercício 1, temos que $r = 1/\sqrt{L}$. 
5. Para a outra série, escrevemos $b_{2n} = 0$ e $b_{2n-1} = a_n$. Assim, os termos pares de $b_n$ são nulos e, pelo mesmo argumento, 
$$
\lim \sqrt[n]{|b_n|} = \lim \sqrt[2n-1]{|b_{2n-1}|} = \lim \sqrt[2n-1]{|a_n|} = \sqrt{L}
$$

### 12.3.3

**Questão:** Determine o raio de convergência de cada uma das séries seguintes:

1. $\sum a^{n^2} x^n$.

2. $\sum a^{\sqrt{n}} x^n$.

3. $\sum n^{\frac{\ln n}{n}} x^n$.

**Resolução:**

1. $\sum a^{n^2} x^n$.
   - Note que 
   $$
   \sqrt[n]{|a_n|} = \sqrt[n]{|a^{n^2}|} = |a^{n^2}|^{1/n} = |a|^n \overset{n \to \infty}{\longrightarrow} \begin{cases} 
   0, & |a| < 1 \\
   1, & |a| = 1 \\
   \infty, & |a| > 1
   \end{cases}
   $$
   - Assim, se $|a| < 1$, $r = \infty$; se $|a| = 1$, $r = 1$; se $|a| > 1$, então $r = 0$.

2. $\sum a^{\sqrt{n}} x^n$.
   - Note que
   $$
   \sqrt[n]{|a^{\sqrt{n}}|} = |a|^{\frac{\sqrt{n}}{n}} = |a|^{1/\sqrt{n}}
   $$
   - Como 
   $$
   \lim \ln \left( |a|^{1/\sqrt{n}} \right) = \lim \left( \frac{1}{\sqrt{n}} \ln |a| \right) = 0
   $$
   - Temos que $\lim |a|^{1/\sqrt{n}} = 1$ (para $a \neq 0$).
   - Assim, se $a = 0$, $r = \infty$, e se $a \neq 0$, temos $r = 1$.

3. $\sum n^{\frac{\ln n}{n}} x^n$.
   - Primeiro note que
   $$
   \sqrt[n]{|n^{\frac{\ln n}{n}}|} = n^{\frac{\ln n}{n^2}}
   $$
   - Como no item anterior,
   $$
   \lim \ln \left( n^{\frac{\ln n}{n^2}} \right) = \lim \left( \frac{\ln n}{n^2} \ln n \right) = 0 \implies \lim n^{\frac{\ln n}{n^2}} = 1
   $$

### 12.3.4

**Questão:** Prove que a função $f : (-r, r) \longrightarrow \mathbb{R}$, dada por $f(x) = \sum_{n=0}^\infty a_n x^n$, onde $r$ é o raio de convergência desta série, é uma função par (ímpar) sse. $a_n = 0$ para todo $n$ ímpar (par).

**Resolução:**

1. Caso 1: par.
   $$
   f(x) = f(-x) \iff \sum a_n x^n = \sum a_n (-x)^n = \sum (-1)^n a_n x^n
   $$
   Assim, $a_n = (-1)^n a_n$. Ou seja, $a_n = 0$ para todo $n$ ímpar. 

2. Caso 2: ímpar.
   $$
   f(-x) = - f(x) \iff \sum (-1)^n a_n x^n = - \sum a_n (-x)^n
   $$
   Assim, $(-1)^n a_n = -a_n$. Ou seja, $a_n = 0$ para todo $n$ par. 

3. Observe que todas as afirmações acima são "sse."

### 12.3.5

**Questão:** Seja $\sum_{n=0}^\infty a_n x^n$ uma série de potências cujos coeficientes são determinados pelas igualdades $a_0 = a_1 = 1$ e $a_{n+1} = a_n + a_{n-1}$. Mostre que o raio de convergência desta série é igual a $(-1 + \sqrt{5})/2$.

**Resolução:**

1. Seja $x_n = a_n/a_{n+1}$. Note que $x_{n+1} = \frac{1}{1+x_n}$. De fato,
$$
\frac{1}{1+x_n} = \frac{1}{1 + a_n/a_{n+1}} = \frac{1}{\frac{a_{n+1}+a_n}{a_{n+1}}} = \frac{a_{n+1}}{a_{n+1} + a_n} = \frac{a_{n+1}}{a_{n+2}} = x_{n+1}
$$

2. Assim, $(x_n)$ converge para a solução positiva de $x^2 + x - 1 = 0$, i.e.,
$$
x_n \to \frac{-1 + \sqrt{5}}{2}
$$

3. Portanto, $(\lim \sqrt[n]{|a_n|})^{-1} = \lim x_n$ e o raio de convergência segue:
$$
r = \lim x_n = \frac{-1 + \sqrt{5}}{2}
$$

### 12.3.6

**Questão:** Prove que a função $$f(x) = \sum_{n=0}^\infty (-1)^n \frac{1}{(n!)^2} \left( \frac{x}{2} \right)^{2n}$$ está bem definida para todo $x \in \mathbb{R}$ e que $$f'' + \frac{f'}{x} + f = 0$$ para todo $x \neq 0$.

**Resolução:**

1. Note que $$\frac{1}{(n!)^2} \left( \frac{x^2}{4} \right)^n \le \frac{1}{n!} \left( \frac{x^2}{4} \right)^n$$ E como a série exponencial $\sum \frac{x^n}{n!}$ converge para todo $x \in \mathbb{R}$, temos que a série converge.

2. Derivando termo a termo,
$$
f'(x) = \sum_{n=1}^\infty \frac{(-1)^n}{(n!)^2} \frac{(2n)}{4^n} x^{2n-1}, \quad f''(x) = \sum_{n=2}^\infty \frac{(-1)^n}{(n!)^2} \frac{(2n)(2n-1)}{4^n} x^{2n-2}
$$

3. Assim, substituindo,
$$
f''(x) + \frac{f'(x)}{x} + f(x) = \sum_{n=2}^\infty \frac{(-1)^n}{(n!)^2} \frac{(2n)(2n-1)}{4^n} x^{2n-2} + \sum_{n=1}^\infty \frac{(-1)^n}{(n!)^2} \frac{(2n)}{4^n} x^{2n-2} + \sum_{n=0}^\infty \frac{(-1)^n}{(n!)^2} \frac{x^{2n}}{4^n} = 0
$$

## Equicontinuidade

### Teorema de Arzelà-Ascoli

**Questão:** Enuncie o Teorema de Arzelà-Ascoli.

**Resolução:**

Seja $f_n : [a,b] \longrightarrow \mathbb{R}$ uma sequência equicontínua de funções e uniformemente limitada. Então $f_n$ possui uma subsequência convergente.

### DF 9.8.1

**Questão:** Usando identidades trigonométricas, mostre as relações de ortogonalidade para as funções seno e cosseno.

1. $\int_0^{2\pi} \sin (jx) \sin (kx) ~dx = \begin{cases} 0, & j \neq k \\ \pi, & j = k \end{cases}$

2. $\int_0^{2\pi} \sin (jx) \cos (kx) ~dx = 0$

3. $\int_0^{2\pi} \cos (jx) \cos (kx) ~dx = \begin{cases} 0, & j \neq k \\ \pi, & j = k \end{cases}$

**Resolução:**

1. $\int_0^{2\pi} \sin (jx) \sin (kx) ~dx$.

   1. Se $j = k$, temos $$\int_0^{2\pi} \sin^2(kx)~dx = \int_0^{2\pi} (1-\cos^2(kx)) ~dx$$ mas $$\cos(2x) = \cos^2(x) - \sin^2(x) = \cos^2(x) - (1-\cos^2(x)) = 2\cos^2(x) - 1$$ implica que $$\cos^2(x) = \frac{\cos(2x)}{2} + \frac{1}{2}$$ Assim,
   $$
   \int_0^{2\pi} (1-\cos^2(kx)) ~dx = 2\pi - \int_0^{2\pi} \left( \frac{\cos(2kx)}{2} + \frac{1}{2} \right)~dx = 2\pi - \left( \pi + \left. \frac{\sin(2kx)}{2 \cdot 2k} \right|_0^{2\pi} \right) = \pi
   $$

   2. Se $j \neq k$, então como $$\sin(jx) \sin(kx) = -\cos(jx) \cos(kx) + \cos(jx - kx)$$ e $$\cos(jx) \cos(kx) = \cos(jx+kx) + \sin(jx) \sin(kx)$$
   temos $$\int_0^{2\pi} \sin(jx) \sin(kx)~dx = -\frac{1}{2} \int_0^{2 \pi} (\cos(jx + kx) - \cos(jx -kx)) ~dx$$
   Calculando, 
   $$-\frac{1}{2} \int_0^{2 \pi} (\cos(jx + kx) - \cos(jx -kx)) ~dx = -\frac{1}{2} \left[ \left. \frac{\sin(jx +kx)}{j+k} \right|_0^{2\pi} - \left. \frac{\sin(jx - kx)}{j - k} \right|_0^{2\pi} \right] = 0$$

2. $\int_0^{2\pi} \sin (jx) \cos (kx) ~dx = 0$: Observe que $2 \sin(jx) \cos(kx) = \sin(jx+kx) + \sin(jx-kx)$.

3. $\int_0^{2\pi} \cos (jx) \cos (kx) ~dx$: Análogo ao primeiro item.

### DF 9.8.2

**Questão:** Considere a sequência de funções definidas em $[0, \infty)$: $$ f_n(x) = \sin \sqrt{x + 4n^2 \pi^2}$$ Mostre que a sequência $(f_n)$ é equicontínua. Isso mostra que o Teorema de Arzelà-Ascoli não tem um análogo para funções definidas em intervalos infinitos.

**Resolução:**

1. Queremos mostrar que para todo $\varepsilon > 0$, existe $\delta > 0$ tal que, para todo $x, y \in [0, \infty)$, 
$$
   |x-y| < \delta \implies |f_n(x) - f_n(y)| < \varepsilon, \quad \forall~f_n
$$

2. Observe que 
$$
|f_n(x) - f_n(y)| = |\sin \sqrt{x+4n^2 \pi^2} - \sin \sqrt{y + 4n^2 \pi^2}|
$$

3. Pelo Teorema do Valor Médio, existe $\xi \in (0, \infty)$ tal que 
   $$
   |f_n(x) - f_n(y)| = |f_n'(\xi)| |x-y| \le |x-y| < \delta 
   $$
   pois $|f_n'(\xi)| \in [0,1]$

4. Assim, tomando $\delta = \varepsilon$, temos que $(f_n)$ é equicontínua. 

5. Observação: $f_n \to 0$.
   - De fato, seja 
   $$
   \theta = \arctan \left( \frac{2 \pi n}{\sqrt{x}} \right), \quad \sin(\theta) = \frac{2 \pi n}{\sqrt{x + 4 n^2 \pi^2}}
   $$
   - Então, 
   $$
   \sqrt{x + 4n^2 \pi^2} = \frac{2 \pi n}{\sin \theta} = \frac{2 \pi n}{\sin \left( \arctan \left( \frac{2 \pi n}{\sqrt{x}} \right) \right)} =: \alpha
   $$
   - Mas
   $$
   \lim_{n \to \infty} \sin \left( \arctan \left( \frac{2 \pi n}{\sqrt{x}} \right) \right) = 1
   $$
   - Com isso, como $\sin \sqrt{x + 4n^2 \pi^2} = \sin \alpha$, tomando $n \to \infty$, temos que $\sin \alpha$ converge para $\sin(2\pi n) = 0$.

### DF 9.8.3

**Questão:** Seja $(f_n)$ uma sequência de funções contínuas definidas em $[0,1]$ tais que 

1. $f_n(0) = a$ para todo $n$.

2. Existe $k > 0$ tal que, para todo $x, y \in [0,1]$, $$|f_n(x) - f_n(y)| \le k |x-y|, \quad \forall ~n$$ Mostre que $(f_n)$ contém uma subsequência convergindo uniformemente.

**Resolução:**

1. Utilizaremos o Teorema de Arzelà-Ascoli. Para isso, precisamos verificar que $(f_n)$ é equicontínua e uniformemente limitada.

2. Equicontinuidade.
   - Seja $K = \max k$. Dado $\varepsilon > 0$, tome $\delta = \varepsilon / K$. Então, para todo $x, y \in [0,1]$, 
   $$
   |x-y| < \delta \implies |f_n(x) - f_n(y)| \le K |x-y| < K \frac{\varepsilon}{K} = \varepsilon, \quad \forall ~f_n
   $$
   - Logo, $(f_n)$ é equicontínua.

3. Limitação uniforme.
   - Note que 
   $$
   |f_n(x)| \le |f_n(0)| + K = |a| + K
   $$
   - Portanto, $(f_n)$ é uniformemente limitada. Por Arzelà-Ascoli, temos que $(f_n)$ possui subsequência uniformemente convergente.

### DF 9.8.4

**Questão:** Mostre que no exercício anterior, a hipótese 2, que é de que as funções sejam uniformemente lipschitzianas, pode ser substituída pela hipótese das $f_n$ serem uniformemente Hölder contínuas, i.e., que existe $k > 0$ e $0 < \lambda \le 1$ tal que $|f(x) - f(y)| \le k |x-y|^\lambda$, para todo $x, y \in [0,1]$.

**Resolução:**

Tome $\delta = (\varepsilon/K)^{1/\lambda}$ na demonstração anterior.

### DF 9.8.5

**Questão:** A sequência $(\sin (nx))$ é equicontínua em $[0,1]$?

**Resolução:**

Suponhamos que a sequência seja equicontínua. Como ela é limitada em $[0,1]$, pelo Teorema de Arzelà-Ascoli, temos que admite subsequência uniformemente convergente. Porém, $\sin(nx)$ não possui subsequência convergente.

### DF 9.8.6

**Questão:** Considere a sequência $\left( \frac{\sin (nx)}{x} \right)$ em $[0,1]$. Tente aplicar o teorema de Arzelà-Ascoli a essa sequência.

**Resolução:**

1. Observe que para $x = 0$, temos $\frac{\sin(nx)}{x} \overset{x \to 0}{\longrightarrow} n$. De fato, tomando $\theta = nx$,
   $$
   \frac{\sin(nx)}{x} = n \frac{\sin(nx)}{nx} = n \frac{\sin \theta}{\theta} \overset{\theta \to 0}{\longrightarrow} n
   $$

2. Assim, a sequência não é uniformemente limitada, pois para $x = 0$,
$$
\left| \frac{\sin(nx)}{x} \right| \overset{n \to \infty}{\longrightarrow} \infty
$$

### DF 9.8.7

**Questão:** Uma família $\mathfrak{F}$ de funções definidas em um intervalo limitado $[a,b]$ é equicontínua em um ponto $x_0 \in [a,b]$ se, dado $\varepsilon > 0$, existir $\delta > 0$ (dependendo de $x_0$ e $\varepsilon$) tal que $$|x-x_0| < \delta \implies |f(x) - f(x_0)| < \varepsilon, \quad \forall~f \in \mathfrak{F}$$ Mostre que se uma família é equicontínua em todos os pontos de $[a,b]$, então ela é equicontínua na definição dada.

**Resolução:**

Usar compacidade e tomar menor dos deltas. Ver Teorema 19 do Elon (p. 285).

### Lista 2, Exercício 1

**Questão:** Dê exemplo de uma sequência de funções contínuas que converge para uma função contínua, mas em que a convergência não seja uniforme.

**Resolução:** Considere $f_n(x) = x/n$ definida em toda reta. Então, dado $x_0 \in \mathbb{R}$ temos que $$f_n(x_0) = \frac{x_0}{n} \overset{n \to \infty}{\longrightarrow} 0$$ Assim, temos convergência pontual, mas não uniforme. De fato, dados $\varepsilon > 0$ e $k \in \mathbb{N}$, temos $$|x| > \varepsilon k \implies |f_k(x)| = \left| \frac{x}{k} \right| > \varepsilon$$

Outro exemplo: A sequência de funções $f_n(x) = x^n(1-x^n)$ converge pontualmente para a função nula no intervalo $[0,1]$, mas essa convergência não é uniforme. De fato, para todo $n \in \mathbb{N}$, podemos achar um ponto $x = \sqrt[n]{1/2}$ tal que $f_n(x) = 1/4$.

### Lista 2, Exercício 2

**Questão:** Dê exemplo de uma sequência de funções contínuas que converge para uma função contínua, mas em que a convergência seja uniforme.

**Resolução:** Temos que $f_n(x) = x^n$ converge uniformemente para $f \equiv 0$ em $[0,1-\delta], 0 < \delta < 1$. De fato, $f_n(x) = x^n \le (1-\delta)^n$. E como $0 < 1-\delta < 1$, 
$$
|f_n(x) - f(x)| = x^n \le (1-\delta)^n \overset{n \to \infty}{\longrightarrow} 0
$$

### Lista 2, Exercícios 3 e 4

**Questão:** Dê exemplo de uma sequência de funções descontínuas que converge para uma função contínua, mas em que a convergência seja uniforme. E dê um exemplo, se possível, em que as funções da sequência possuem um número infinito de descontinuidades.

**Resolução:** 

1. 
   - Considere $f_n(x) : [0,1] \longrightarrow \mathbb{R}$ dada por
   $$
   f_n(x) = \begin{cases}
   \frac{1}{n}, & x = 0 \\
   0, & x \neq 0
   \end{cases}
   $$
   - Afirmamos que $f_n(x) \to f \equiv 0$ uniformemente.
   - Dado $\varepsilon > 0$, tome $N \in \mathbb{N}$ tal que $N > 1/\varepsilon$. Então
   $$
   n > N \implies |f_n(x)| \le \frac{1}{n} < \frac{1}{N} < \varepsilon, \quad \forall x \in[0,1]
   $$

2. 
   - Basta considerar
   $$
   f_n(x) = \begin{cases}
   \frac{1}{n}, & x \in \mathbb{Q} \\
   0, & x \in \mathbb{R} \setminus \mathbb{Q}
   \end{cases}
   $$
   - E aplicar o mesmo argumento acima.

### Lista 2, Exercício 5

**Questão:** Considere as sequências 

1. $x^n/n$,
2. $x^n/(1+x^n)$,
3. $x^n/(n+x^n)$.

Verifique se convergem pontual ou uniformemente em $[0,\infty)$ e $[0,1]$ quando $n \to \infty$.

**Resolução:** 

1. $x^n/n$: vimos (exercício 2.1) que converge pontualmente, mas não uniformemente.

2. $x^n/(1+x^n)$: ver Capítulo 12, Seção 1, Exercício 1.

3. $x^n/(n+x^n)$
   - Escrevemos
   $$
   \frac{x^n}{n+x^n} = \frac{1}{nx^{-n} + 1}
   $$
   - Analisar
   $$
   \lim_{n \to \infty} \frac{n}{x^n} = \lim_{n \to \infty}\frac{1}{x^n \ln(x)}
   $$

### Lista 2, Exercício 6

**Questão:** Seja $f(x) = x^2$ no intervalo $[0,1]$. Calcule $n_0$ tal que $|f(x) - B_n(x)| < 1/1000$ para todo $x \in [0,1]$ e $n > n_0$.

**Resolução:** 

1. Polinômio de Bernstein:
   - Temos que 
   $$
   B_n(x) = \sum_{k=0}^n \binom{n}{k} x^k (1-x)^{n-k} f\left( \frac{k}{n} \right) = \sum_{k=0}^n \binom{n}{k} x^k (1-x)^{n-k} \left( \frac{k}{n} \right)^2
   $$
   - Como
   $$
   \sum_{k=0}^n \binom{n}{k} x^k (1-x)^{n-k} = 1
   $$
   - Temos que 
   $$
   \sum_{k=0}^{n} \binom{n-1}{k-1} x^{k-1} (1-x)^{n-1-(k-1)} = 1
   $$
   - Multiplicando ambos os lados por $nx$ e usando $$\binom{n-1}{k-1} = \left( \frac{k}{n} \right) \binom{n}{k}$$ temos que
   $$
   \sum_{k=0}^{n} \binom{n}{k} k x^{k} (1-x)^{n-k} = nx
   $$
   - Assim, usando $n-1$ em vez de $n$,
   $$
   \sum_{k=0}^{n} \binom{n-1}{k-1} (k-1) x^{k-1} (1-x)^{n-1-(k-1)} = (n-1)x
   $$
   - Novamente multiplicando por $nx$ e usando a mesma identidade,
   $$
   \sum_{k=0}^{n} \binom{n}{k} k (k-1) x^{k} (1-x)^{n-k} = n(n-1)x^2
   $$
   - Portanto, 
   $$
   \begin{aligned}
   n(n-1)x^2 + nx &= \sum_{k=0}^{n} \binom{n}{k} k (k-1) x^{k} (1-x)^{n-k} + \sum_{k=0}^{n} \binom{n}{k} k x^{k} (1-x)^{n-k} \\
   &= \sum_{k=0}^n \binom{n}{k} k^2 x^k(1-x)^{n-k}
   \end{aligned}
   $$
   - Dividindo por $n^2$, temos o desejado:
   $$
   \left( \frac{n-1}{n} \right) x^2 + \frac{1}{n}x = \sum_{k=0}^n \binom{n}{k} x^k(1-x)^{n-k} \left( \frac{k}{n} \right)^2 = B_n(x)
   $$

2. Calcular diferença:
   - Note que
   $$
   \begin{aligned}
   |f(x) - B_n(x)| &= \left| x^2 - \left( \frac{n-1}{n} \right) x^2 + \frac{1}{n}x \right| = \left| x^2 \left( 1 - \left( \frac{n-1}{n} \right) \right) + \frac{1}{n}x \right| \\
   &= \left| \frac{1}{n} x^2  + \frac{1}{n}x \right| = \left| \frac{1}{n}(x^2 + x) \right| = \frac{1}{n} (x^2 + x ) \le \frac{2}{n}
   \end{aligned}
   $$
   - Pois $x^2 + x \le 2$ para todo $x \in [0,1]$.
   - Assim,
   $$
   \frac{2}{n} < \frac{1}{1000} \iff n > 2000
   $$

<!-- 3. Sabemos que $B_n$ converge uniformemente para $f$ em $[0,1]$. Assim, dado $\varepsilon = 10^{-3}$, existe $n_0 \in \mathbb{N}$ tal que 
$$
n > n_0 \implies |f(x) - B_n(x)| < \varepsilon, \quad \forall~x \in [0,1]
$$ -->

### Lista 2, Exercício 7

**Questão:** Calcule o $n$-ésimo polinômio de Bernstein para $f(x) = x^3$ no intervalo $[0,1]$. Escreva por extenso o polinômio de Bernstein de grau $3$ para $f(x) = x^3$ no intervalo $[0,1]$.

**Resolução:** Repetir o argumento acima.

### Lista 2, Exercício 8

**Questão:** Mostre que $e^x$ não pode ser aproximada uniformemente em todo $\mathbb{R}$ por polinômios. O teorema de Bernstein-Weierstrass é falho em intervalos infinitos.

**Resolução:**

1. Suponha que exista um polinômio $p(x)$ tal que $|p(x) - e^x| < 1$ para todo $x$ real. Então existe $M > 0$ tal que 
$$
|x| > M \implies \left| 1 - \frac{e^x}{p(x)} \right| < \frac{1}{|p(x)|}
$$
2. Assim, $$\lim_{x \to +\infty} \frac{1}{|p(x)|} = 0 \implies \lim_{x \to +\infty} \frac{e^x}{p(x)} = 1$$ o que é  absurdo.

### Lista 2, Exercício 9

**Questão:** Mostre que $\log x$ não pode ser aproximada uniformemente em $(0, \infty]$ por polinômios. O teorema de Bernstein-Weierstrass é falho em intervalos infinitos.

**Resolução:** 

1. Suponha que exista um polinômio $p(x)$ tal que $|\ln(x) - p(x)| < 1$ para todo $x \in (0, 1]$. Então temos que
$$
\left| \frac{\ln(x)}{p(x)} - 1 \right| < \frac{1}{|\ln(x)|} \to 0 \quad \text{ quando } \quad x \to 0^+
$$
2. Mas isso é absurdo, pois
$$
\lim_{x \to 0^+} \frac{|p(x)|}{|\ln(x)|} = 0
$$

### Lista 2, Exercício 10

**Questão:** Estude o problema dos momentos.

**Resolução:** 

Seja $f : [0,1] \longrightarrow \mathbb{R}$ uma função contínua. Os **momentos** de $f$ são definidos por $$ M_n = \int_0^1 x^n f(x) ~dx, \quad n \in \mathbb{N}_0 $$

Dados números $M_0, M_1, \ldots$, é possível determinar uma função contínua $f$ cujos momentos são esses números? 

A unicidade segue pelo Teorema de Aproximação de Weierstrass (ver exercício 13 da lista 2).

<!-- (p. 231-232 DF) -->

### Lista 2, Exercício 11

**Questão:** Existência subsequência convergente de $f_n(x) = \sin(nx)$, $x \in [0,2\pi]$?

**Resolução:**

Suponha que exista uma subsequência $(f_{n_k}) = (\sin n_k x)$ que convirja pontualmente para todo $x \in [0,2\pi]$. 

Assim, a sequência $g_k(x) = (\sin n_k x - \sin n_{k+1}x)^2$ converge simplesmente para zero. 

Como $|g_k(x)| \le 4$ para qualquer $x \in [0,2\pi]$, temos que 
$$
\lim_{k \to \infty} \int_0^{2\pi} (\sin n_k x - \sin n_{k+1}x)^2 ~dx = 0
$$

Por outro lado, 
$$
\int_0^{2\pi} \sin(jx) \sin(kx) ~dx = \begin{cases}
0, & j \neq k \\
\pi, & j = k
\end{cases}
$$
implica que 
$$
\int_0^{2\pi} (\sin n_k x - \sin n_{k+1}x)^2 ~dx = 2\pi
$$
o que é uma contradição.

Logo, $(\sin nx)$ não contém subsequência convergente.

<!-- DF p. 225-226, Rudin Example 7.20 -->

### Lista 2, Exercício 12

**Questão:** Determine para quais valores de $x$ em $\mathbb{R}$ a série $$\sum_{n=1}^\infty \frac{(-1)^{n+1}}{n} x^n$$ é convergente.

**Resolução:** 

1. Calcular $\sqrt[n]{|a_n|}$. 
   $$
   \sqrt[n]{|a_n|} = \left| \frac{(-1)^{n+1}}{n} \right|^{1/n} = \left( \frac{1}{n} \right)^{1/n} \overset{n \to \infty}{\longrightarrow} 1
   $$
   Assim, temos que o raio de convergência é $r = 1/\lim \sqrt[n]{|a_n|} = 1$.

2. Avaliar os extremos.
   - Para $x = 1$, como $1 \ge 1/2 \ge 1/3 \ge \cdots \ge 0$ e $\lim 1/n = 0$, pelo teste das séries alternadas, temos que a série converge.
      - Teste da das séries alternadas: Se $x_1 \ge x_2 \ge ... \ge 0$ e $\lim x_k = 0$, então, $\sum_{k=1}^\infty(-1)^{k+1} x_k$ converge.

   - Para $x = -1$, temos 
   $$
   \sum_{n=1}^\infty \frac{(-1)^{n+1}}{n} (-1)^n = \sum_{n=1}^\infty \frac{(-1)^{2n+1}}{n}
   $$

3. Conclusão: converge (para $\ln(x+1)$) para $|x| < 1$ ou $x = 1$.

### Lista 2, Exercício 13

**Questão:** Seja $f:[0,1] \longrightarrow \mathbb{R}$ uma função contínua tal que $$\int_0^1 x^n f(x) ~dx = 0$$ para todo $n \in \mathbb{N}_0$. Mostre que $f(x) = 0$ para todo $x \in [0,1]$.

**Resolução:**

Temos que
$$
\int_0^1 P(x)f(x)~dx = 0
$$
para qualquer polinômio $P(x)$.

Pelo Teorema de Aproximação de Weierstrass, existe uma sequência de polinômios $(P_n)$ tal que $P_n$ converge uniformemente para $f$. Assim, podemos "passar o limite para dentro da integral",
$$
\lim_{n \to \infty} \int_0^1 P_n(x)f(x)~dx = \int_0^1 f^2(x)~dx = 0
$$

O que implica que $f \equiv 0$.

<!-- Rudin, exercise 20, DF p. 232 -->

### Teorema de Bernstein

**Questão:** Enuncie o Teorema de Bernstein.

**Resolução:** Seja $f:[0,1] \longrightarrow \mathbb{R}$ uma função contínua. Definamos a sequência $B_n : [0,1] \longrightarrow \mathbb{R}$ dada por
$$
B_n(x) = \sum_{k=0}^n \binom{n}{k} x^k (1-x)^{n-k} f \left( \frac{k}{n} \right)
$$
Então $B_n$ converge uniformemente para $f$ no intervalo $[0,1]$.

Obs: O Teorema de Aproximação de Weierstrass generaliza esse resultado para qualquer intervalo $[a,b]$.