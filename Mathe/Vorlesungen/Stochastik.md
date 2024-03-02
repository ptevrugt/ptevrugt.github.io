# Stochastik

### Definition: Standardnormalverteilung
Zufallsvariable $X$ heißt **standardnormalverteilt**, wenn $f_X(t) = \frac{1}{\sqrt{2\pi}}e^{-\frac{t²}{2}}$, $t\in\mathbb{R}$.
Warum $\sqrt{2\pi}$? Damit $\int_\mathbb{R}f_X(t)dt=1$.

### Satz 15.3
Sei $X$ [standardnormalverteilt](Stochastik.md#definition-standardnormalverteilung). Dann:  
$\mathbb{E}X =0$  
$\text{Var}X = \mathbb{E}X²=1$

### Definition: Normalverteilung
Zufallsvariable $Y$ heißt **normalverteilt** mit Parametern $\mu\in\mathbb{R}$, $\sigma² > 0$, wenn $Y = \mu + \sigma X$, wobei $X\sim\text{N}(0,1)$.

Interpretation: $\mu$ ist der wahre Wert einer Größe und $\sigma X$ der Messfehler.

**Bez.:** $Y\sim\text{N}(\mu,\sigma²)$

**Bem.:** $\mathbb{E}Y = \mathbb{E}[\mu+\sigma X] = \mu + \sigma \mathbb{E}X = \mu$  
$\text{Var}X = \text{Var}[\mu+\sigma X] = \text{Var}[\sigma X] = \sigma² \text{Var}X = \sigma²$.

Dichte von $Y\sim\text{N}(\mu,\sigma²)$: $f_Y(t) = \frac{\text{d}}{\text{d}t}F_Y(t) = \frac{\text{d}}{\text{d}t}[F_X(\frac{t-\mu}{\sigma})] = F_X'(\frac{t-\mu}{\sigma})\cdot \frac{1}{\sigma} = \frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(t-\mu)²}{2\sigma²}}$

### Definition: Cauchy-Verteilung
Zufallsvariable $X$ heißt **Cauchy-verteilt**, wenn $f_X(t)=\frac{1}{\pi}\cdot \frac{1}{1+t²}$, $t\in\mathbb{R}$.

Verteilungsfunktion: $F_X(t) = \frac{1}{\pi} \int_{-\infty}^t \frac{1}{1+s²}ds = \frac{1}{\pi}\left. \arctan s\right|_{s=-\infty}^{s=t} = \frac{1}{\pi} [\arctan t - (-\frac{\pi}{2}] = \frac{1}{2} + \frac{1}{\pi}\arctan t$  
$F_X(+\infty) = \frac{1}{2}+\frac{1}{\pi}\arctan(+\infty) = \frac{1}{2} + \frac{1}{\pi}\cdot\frac{\pi}{2} = 1$

**Bem.:** $\mathbb{E}X = \int_{-\infty}^{\infty} t \frac{1}{\pi(1+t²)}dt = \infty - \infty$  
$\mathbb{E}X$ existiert nicht! $\frac{1}{\pi}\int_0^\infty \frac{t}{1+t²}dt = \frac{1}{\pi}\left. \frac{1}{2}\log(1+t²)\right|_0^\infty = \infty - 0 = +\infty$

## 16. Singuläre Verteilungen

### Satz 16.1 (Radon-Nikodym, absolut stetige Verteilungen)
Für ein Wahrscheinlichkeitsmaß $\mu$ auf $\mathbb R$ sind folgende Bedingungen äquivalent:

1. $\forall A \in \mathcal B(\mathbb R)$ mit $\lambda(A) = 0 \implies \mu(A) = 0$
2. $\forall \epsilon>0 \exists\delta>0: \forall A \in \mathcal B(\mathbb R)$ mit $\lambda(A)<\delta \implies \mu(A)<\epsilon$
3. $\mu$ hat eine Wahrscheinlichkeitsdichte $f$, d.h. $\mu(B) = \int_B f(x)dx$ $\forall B \in \mathcal B¹(\mathbb R)$

Ein $\mu$ mit diesen Eigenschaften heißt **absolut stetig**.

### Definition: singuläre Verteilung
Eine Zufallsvariable $X$ (bzw. die Verteilung $\mu$ von $X$) heißt **singulär**, wenn:

1. $\exists N \in \mathcal B(\mathbb R)$ mit $\lambda(N) = 0$ s.d. $\mathbb P[x\in N] = 1$
2. $\mathbb P[x=y] = 0$ $\forall y \in \mathbb R$. D.h. $X$ hat keine Atome.

**Bsp.:** Cantor-Menge. $\forall x\in[0,1]$ besitzt Darstellung im ternären System:  
$x=\sum_{n=1}^\infty \frac{\epsilon_n}{3^n} = [0,\epsilon_1\epsilon_2\epsilon_3...]_3$, $\epsilon_k\in{0,1,2}$  
$1 = [1.000...]_3 = [0.222...]_3$  
$\frac{1}{3} = [0.100...]_3 = [0.022...]_3$

Cantor-Menge $C=\{x\in[0,1]: x=\sum_{n=1}^\infty \frac{\epsilon_n}{3^n}\text{ mit } \epsilon_n\in\{0,2\}\}$  
$C = \bigcap_{n=1}^\infty C_n$ mit $\lambda(C_n)=(\frac{2}{3})^n$  
$\lambda(C)\leq\lambda(C_n)=(\frac{2}{3})^n$ mit $n\rightarrow\infty: \lambda(C)=0$.

C ist Lebesgue-Nullmenge.  
C ist überabzählbar.