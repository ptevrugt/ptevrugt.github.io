# Stochastik

### Definition: Standardnormalverteilung
Zufallsvariable $X$ heißt **standardnormalverteilt**, wenn $f_X(t) = \frac{1}{\sqrt{2\pi}}e^{-\frac{t²}{2}}$, $t\in\mathbb{R}$.
Warum $\sqrt{2\pi}$? Damit $\int_\mathbb{R}f_X(t)dt=1$.

### Satz 15.3.
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

Verteilungsfunktion: $F_X(t) = \frac{1}{\pi} \int_{-\infty}^t \frac{1}{1+s²}ds = \frac{1}{\pi}\left. \arctan s\right|_{s=-\infty}^{s=t} = \frac{1}{\pi} [\arctan t - (-\frac{\pi}{2})] = \frac{1}{2} + \frac{1}{\pi}\arctan t$  
$F_X(+\infty) = \frac{1}{2}+\frac{1}{\pi}\arctan(+\infty) = \frac{1}{2} + \frac{1}{\pi}\cdot\frac{\pi}{2} = 1$

**Bem.:** $\mathbb{E}X = \int_{-\infty}^{\infty} t \frac{1}{\pi(1+t²)}dt = \infty - \infty$  
$\mathbb{E}X$ existiert nicht! $\frac{1}{\pi}\int_0^\infty \frac{t}{1+t²}dt = \frac{1}{\pi}\left. \frac{1}{2}\log(1+t²)\right|_0^\infty = \infty - 0 = +\infty$

## 16. Singuläre Verteilungen

### Satz 16.1. (Radon-Nikodym, absolut stetige Verteilungen)
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

$C$ ist Lebesgue-Nullmenge.  
$C$ ist überabzählbar. $C \leftrightarrow_\text{bij.} \{0,2\}^\infty \leftrightarrow_\text{bij.} \{0,1\}^\infty \leftrightarrow_\text{bij.} [0,1]$  
$C$ abgeschlossen als Schnitt von abgeschlossenen Mengen

#### Cantor-Funktion

1. F(t) ist stetig und monoton steigend
2. $\forall t\in[0,1]\setminus C \exists F'(t) = 0$

Also ist $F'(t)=0$ fast überall und $\int_0^1 F'(t) dt = 0$, aber $F(1) = 1, F(0)= 0$  
Für $F(t)$ gilt $F(1)-F(0) \neq \int_0^1 F'(t)dt = 0$.

### Defintion: Cantor-Verteilung
Zufallsvariable $X$ mit Verteilungsfunktion $F$ [Cantor-Funktion](Stochastik.md#cantor-funktion) heißt **Cantor-verteilt**.

### Satz 16.2. (Zerlegungssatz von Lebesgue)
Sei $F$ Verteilungsfunktion des Wahrscheinlichkeitsmaßes $\mu$ auf $\mathbb R$. Dann $\exists p_1,p_2,p_3\in[0,1]$ mit $p_1+p_2+p_3=1$ und Verteilungsfunktionen $F_1,F_2,F_3$ s.d. $F(t) = p_1F_1(t) + p_2F_2(t)+p_3F_3(t)$ bzw. $\mu = p_1\mu_1+p_2\mu_2+p_3\mu_3$ und $\mu_1$ diskret, $\mu_2$ absolut stetig, $\mu_3$ singulär.

## 17. Zufallsvektoren und Faltungsformeln

### Definition: Zufallsvektor
Seien $X_1, ..., X_d: \Omega \rightarrow \mathbb R$ Zufallsvariablen. Die Abbildung $X: \Omega \rightarrow \mathbb R^d, \omega \mapsto (X_1(\omega), ..., X_d(\omega))$ heißt Zufallsvektor. ($X=(X_1,...,X_d)$)

#### Begriffe
- Die gemeinsame Verteilung von $X$ ist Wahrscheinlichkeitsmaß $P_X$ auf $\mathbb R^d$ mit $P_X(B) = \mathbb P[x\in B]$
- Diskret, abs. stetig, singulär wie für Zufallsvariablen definiert. 
- Randverteilungen: Verteilungen von $X_1, ..., X_d$: $P_{X_1},...,P_{X_d}$
    - Falls $X$ diskret: $P_{X_1}(y_1) = \sum_{y_2,...,y_d\in\mathbb R}P_{X_1,...,X_d}(y_1,...,y_d)$
  - Falls $X$ abs. stetig mit Dichte $f(x_1,...,x_d)$: $f_{X_1}(y_1) = \int_\mathbb{R}...\int_\mathbb{R}f_X(y_1,...,y_d)dy_2...dy_d$
- Falls $X_1,...,X_d$ unabhängig mit Zähldichten $P_{X_1}(y_1),...,P_{X_d}(y_d)$: $P_X(y_1,...,y_d) = \mathbb P[X_1=y_1,...,X_d=y_d] = P_{X_1}(y_1)\cdot ... \cdot P_{X_d}(y_d)$
- Falls $X_1,...,X_d$ unabhängig mit Dichten $f_{X_1}(y_1),...,f_{X_d}(y_d)$: $f_X(y_1,...,y_d) = f_{X_1}(y_1)\cdot ... \cdot f_{X_d}(y_d)$

### Faltungsformeln
Seien $X_1, X_2$ unabhängige Zufallsvariablen mit bekannten Verteilungen.  
Frage: Bestimme Verteilung von $X_1+X_2$ oder $X_1\cdot X_2$ oder $\frac{X_1}{X_2}$.  
- Falls $X_1, X_2$ diskret: $P_{X_1+X_2}(z) = \mathbb P[X_1+X_2 = z] = \sum_{y\in\text{Im}{X_1}}P_{X_1}(y)\cdot P_{X_2}(z-y)$.
- Falls $X_1, X_2$ absolut stetig: $f_{X_1+X_2}(z)=\int_\mathbb{R} f_{X_1}(y)\cdot f_{X_2}(z-y)dy$.

### Satz 17.1.
Seien $X_1\sim\text{N}(\mu_1,\sigma_1²)$ und $X_2\sim \text N(\mu_2,\sigma_2²)$ unabhängig. Dann ist $X_1+X_2\sim\text N(\mu_1+\mu_2,\sigma_1²+\sigma_2²)$.

### Faltungsformel für das Produkt
Seien $X_1,X_2$ unabhängige Zufallsvariablen mit Dichten $f_{X_1}$ und $f_{X_2}$. Dichte von $X_1\cdot X_2$:  
$f_{X_1\cdot X_2}(z)=\int_{\mathbb R}f_{X_1}(y)\cdot f_{X_2}(\frac{z}{y})\cdot \frac{1}{|y|}dy$


## 18. Gesetze der großen Zahlen
Allgemein: Zufallsvariablen $X_1,X_2,X_3,\dots$ unabhängig identisch verteilt.  
Aussage: $\frac{X_1+\dots+X_n}{n}\longrightarrow_{n\rightarrow\infty}\mathbb EX_1$

### Konvergenzarten von Zufallsvariablen
Seien $Z_1,Z_2,Z_3,\dots$ Zufallsvariablen und $Z$ auch eine Zufallsvariable.

#### Defintion
Die Folge $Z_1,Z_2,\dots$ konvergiert gegen $Z$ in Wahrscheinlichkeit (oder stochastisch), falls $\forall \epsilon>0: \lim_{n\rightarrow\infty} \mathbb P[|Z_n-Z|>\epsilon]=0$  
**Bez.:** $Z_n \rightarrow^PZ$

#### Defintion
Sei $p>0$. Folge $Z_1, Z_2,\dots$ konvergiert gegen $Z$ in $L^p$, wenn: $\lim_{n\rightarrow\infty}\mathbb E[|Z_n-Z|^p] = 0$.

### Lemma 18.1.
Sei $Z\geq0$ Zufallsvariable. Dann gilt: $\mathbb P[Z\geq a]\leq \frac{\mathbb EZ}{a}$ $\forall a>0$.

### Satz 18.2. (Tschebyschew-Ungleichung)
Sei $X$ Zufallsvariable mit $\mathbb E[X²]<\infty$. Dann gilt: $\mathbb P[|X-\mathbb EX|\geq a]\leq \frac{\text{Var}(X)}{a²}$.

### Satz 18.3. (Markow-Ungleichung)
Sei $Z\geq0$ Zufallsvariable und $f:[0,\infty)\rightarrow [0,\infty)$ monoton steigend. Dann gilt: $\mathbb P[Z\geq a] \leq \frac{\mathbb Ef(z)}{f(a)}$.

### Satz 18.4.
Aus $Z_n\rightarrow^{L^p}_{n\rightarrow\infty}Z$ (für ein $p>0$) folgt $Z_n\rightarrow^P_{n\rightarrow\infty}Z$.  
**Bem.:** Aus $Z_n\rightarrow^PZ$ folgt nicht, dass $Z_n\rightarrow^{L^P}Z$.  
$\Omega=[0,1]$, $\mathbb P$ Lebesgue-Maß.  
Sei $Z=0$, $Z_n=\mathbb 1_{[0,\frac{1}{n}]}\cdot 2^n$

### Satz 18.5. (Schwaches Gesetz der großen Zahlen)
Seien $X_1,X_2,X_3,\dots$ unabhängige (oder unkorreliert) Zufallsvariablen mit $\mathbb EX_i=\mu$ und $\text{Var}X_i=\sigma²$ $\forall i=1,2,\dots$. Dann gilt $\frac{X_1+\dots+X_n}{n}\longrightarrow^{P,L^2}_{n\rightarrow\infty}\mathbb EX_1$.

### Satz 18.6. (Weierstraß, 1885)
Sei $f:[0,1]\rightarrow \mathbb R$ stetige Funktion. Dann gilt $\forall \epsilon>0 \exists\text{Polynom }P \text{ s.d. } \sup_{x\in[0,1]}|f(x)-P(x)|\leq\epsilon$.

## 19. Lemma von Borel-Cantelli
Seien $A_1,A_2,\dots$ Ereignisse.  
- $\limsup A_n =^\text{def}\{\omega\in\Omega:\omega\in A_i \text{ für unendlich viele }i\}=\bigcap_{k=1}^\infty\bigcup_{i=k}^\infty A_i\in\mathcal F$
- $\liminf A_n =^\text{def}\{\omega\in\Omega:\omega\in A_i \text{ für alle }i\text{ bis auf endlich viele}\} = \bigcup_{k=1}^\infty\bigcap_{i=k}^\infty A_i$  

**Bem.:** 
- $\liminf A_n \subset \limsup A_n$ 
- $(\liminf A_n)^\complement=(\bigcup_{k=1}^\infty\bigcap_{i=k}^\infty A_i)^\complement=\bigcap_{k=1}^\infty\bigcup_{i=k}^\infty A_i^\complement=\limsup(A_n^\complement)$
- $(\limsup A_n)^\complement=\liminf(A_n^\complement)$

### Lemma 19.1. (Borel-Cantelli)
Sei $(\Omega,\mathcal F,\mathbb P)$ Wahrscheinlichkeitsraum und $A_1,A_2,\dots\in\mathcal F$ Ereignisse.  
(1) Aus $\sum_{n=1}^\infty\mathbb P[A_n]<\infty$ folgt $\mathbb P[\limsup A_n] = 0$, d.h. $\mathbb P[\text{es treten nur endlich viele Ereignisse ein}]=1$  
(2) Sind $A_1,A_2,\dots$ unabhängig mit $\sum_{n=1}^\infty\mathbb P[A_n]=\infty$, dann gilt $\mathbb P[\limsup A_n]=1$, d.h. $\mathbb P[\text{es treten unendlich viele Ereignisse ein}]=1$