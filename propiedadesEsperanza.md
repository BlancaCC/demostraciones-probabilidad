---
title: "Propiedades de la esperanza matemática  y desigualdad de Cauchy-Schwarz"
author:  Blanca Cano Camero, Daniel Krell Calvo
date: 2 de Diciembre del 2019
output: pdf_document
---

## Propiedades de la esperanza

### Linealidad

Sea un vector aleatorio n-dimensional:
 $$\textbf{X} = ( X_{1}, ..., X_{n} ) : (\Omega,   \mathcal{A}, P) \rightarrow (\mathbb{R}^n, \mathcal{B}^n, P_x)$$

Se quiere probar que para cualquier $(a_1,..., a_n), (b_1,...,b_n) \in \mathbb{R}^n$,

$$\exists E [X_i] \Rightarrow  \exists E [a_i X_i + b_i]$$
y además si existe $E [\sum_{i=1}^{n}a_i X_i + b_i]$ entonces es igual a $\sum_{i=1}^{n}a_i E[X_i] + b_i$.

#### Demostración

- Caso discreto:

Comencemos por probar su existencia:
$$\sum_{x \in E_x} | \sum_{i=1}^{n}a_ix_i + b_i|P[X_1=x_1,\dotsm,X_n=x_n] \le \sum _{x \in E_x} (\sum _{i=1}^n |a_i||x_i|+|b_i|)  P[X_1=x_1,\dotsm,X_n=x_n]$$
$$= \sum _{i=1}^n |a_i|(\sum _ {x \in E_x}|x_i|  P[\textbf X = x])+|b_i|  < \infty$$

Sabemos que la última expresión es finita por la existencia de $E[X_i] \, \forall i \in \{1,\dotsc,n\}$.

Veamos ahora que se da la igualdad:

$$\sum_{x \in E_x} \sum_{i=1}^{n}(a_ix_i + b_i)P[\textbf X = x] + b_i =  \sum _{i=1}^n a_i(\sum _ {x \in E_x}x_i  P[\textbf X = x])+b_i = \sum_{i=1}^n a_i E[X_i] +b_i$$

- Caso continuo: Existencia por convergencia absoluta de la integral, misma idea que caso discreto.

$$\int _{\mathbb{R}^n} \sum _{i=1}^n|a_ix_i + b_i| f_ {\textbf X}(x_1,...,x_n)  \,dx_1...dx_n \le \int_{\mathbb R^n} (\sum _{i=1}^n|a_i| |x_i| + |b_i|) f_ {\textbf X}(x_1,...,x_n)  dx_1...dx_n = $$
$$= \sum_{i=1}^n |a_i| \int_{\mathbb R^n} |x_i| f_X(x_1,...,x_n) dx_1...dx_n  + |b_i|< \infty$$

Veamos ahora que se da la igualdad:

$$\int _{ \mathbb{R}^n} \sum _{i=1}^n(a_ix_i + b_i) f_ {\textbf X}(x_1,...,x_n)  \, dx_1...dx_n = \sum_{i=1}^n a_i \int_{\mathbb R^n} x_i f_X(x_1,...,x_n) dx_1...dx_n  + b_i=$$
$$=\sum_{i=1}^n a_i E[X_i] + b_i$$

Llegando por tanto a la igualdad que queríamos probar.


### Monotonía

Sean $X_1$, $X_2$ variables aleatorias unidimensionales para las cuales existen sendas esperanzas. Entonces, se tiene que

$$X_1 \le  X_2 \Rightarrow  E[X_1] \le  E[X_2]$$

#### Demostración
Como la suma de varibles aleatorias es una variable aleatoria podemos definir $Z = X_2 -X_1$

Como $Z\geq0$ tenemos que $E[Z]\geq 0$. Aplicando la linealidad de la variable aleatoria
$$E[Z] =  E[X_2] - E[X_1] \ge 0 \Rightarrow E[X_2] \geq E[X_1]$$


## Desigualdad de Cauchy-Schwarz

#### Enunciado

Sean X e Y variables aleatorias definidas sobre el el espacio $\mathcal{L}^2(\Omega,\mathcal{A},P)$ tales que existan $E[X^2]$ y $E[Y^2]$ y $E[XY]$.
Entonces se cumple
$$(E[XY])^2\leq E[X^2]E[Y^2]$$
Además, la igualdad se da si y solo si

- O bien X o Y son degeneradas en 0.
- O bien existen $a$ y $b$ no nulos tales que
$$P(aX+bY=0)=1$$

#### Demostración
Consideremos primero el caso $E[X^2]\neq 0$. Definimos la variable aleatoria $Z=\lambda X + Y$, donde $\lambda = -\frac{E[XY]}{E[X^2]}$. Entonces se cumple
$$E[Z^2]=E[(\lambda X+Y)^2] = E[\lambda^2 X^2 + Y^2 + 2\lambda XY] =$$
$$\lambda^2 E[X^2] + E[Y^2] + 2\lambda E[XY] = $$
$$\frac{E[XY]^2}{E[X^2]}+ E[Y^2] - 2\frac{E[XY]^2}{E[X^2]} = E[Y^2]- \frac{E[XY]^2}{E[X^2]}$$
Como $Z^2 \geq 0$, necesariamente tiene que ser $E[Z^2] \geq 0$. Por lo tanto
$$E[Y^2]- \frac{E[XY]^2}{E[X^2]} \geq 0$$
$$(E[XY])^2\leq E[X^2]E[Y^2]$$
Quedando probada la desigualdad.

Si $E[X^2]=0$, como $X^2\geq 0$ entonces $P[X^2=0] = 1$ y $P[X=0] = 1$. Se sigue que $E[XY]=0$, por lo que se verifica la desigualdad.

Demostraremos ahora la segunda parte del enunciado.
Supongamos que se da la igualdad $$E[XY]^2 = E[X^2]E[Y^2]$$
Si $E[X^2]=0$, entonces $X$ es degenerada en 0, y lo mismo ocurre para la $Y$. Queda considerar entonces cuando ambas esperanzas son no nulas. La igualdad implica $E[Z^2] = 0$, luego $P[Z=0]=P[\lambda X + Y = 0] = 1$. Faltaría con ver que $\lambda$ no sea cero. Pero $E[X^2] \neq 0$ y $E[Y^2]\neq 0$, luego $E[XY] \neq 0$ y $\lambda=-\frac{E[XY]}{E[X^2]} \neq 0$.
Vamos ahora con el recíproco.
Si X o Y son degeneradas la igualdad es evidente. En caso contrario, partimos de que existen $a$ y $b$ no nulos con
$$P(aX+bY=0)=1$$
Equivalentemente
$$P(Y=-\frac{a}{b}X) = 1$$
Entonces, se tiene
$$E[Y^2] = \frac{a^2}{b^2} E[X^2]$$ y
$$E[XY] = E[-\frac{a}{b}X^2] = -\frac{a}{b}E[X^2]$$
Comprobamos que se verifica la igualdad.
$$E[XY]^2 = E[X^2]E[Y^2] $$
$$ \frac{a^2}{b^2}E[X^2] =E[X^2]\frac{a^2}{b^2} E[X^2]$$

#### Corolario
En las condiciones anteriores,
$$(Cov(X,Y))^2 \leq Var(x)Var(Y)$$
Además, se da la igualdas si y solo si alguna variable es degenerada o existen $a$ y $b$ no nulos y $c \in \mathbb{R}$ tales que
$$P(aX+bY = c) = 1$$

#### Demostración
Aplicamos la desigualdad de Cauchy-Schwarz a $X-E[X]$ y $Y-E[Y]$.
$$(E[(X-E[X])(Y-E[Y])])^2 \leq E[(X-E[X])^2]E[(Y-E[Y])^2]$$
$$(Cov(X,Y))^2 \leq Var(X)Var(Y)$$
Para la segunda parte, si X e Y son no degeneradas, por el teorema anterior si se da la igualdad existen $a,b\neq 0$ con
$$P(a(X-E[X])+b(Y-E[Y]) = 0 ) = 1$$
Basta con tomar $c = aE[X] + bE[Y]$.
Para el recíproco, partimos ahora de que exiten $a,b\in \mathbb{R}\setminus \{0\},c\in \mathbb{R}$ tales que
$$P(aX+bY = c) = 1$$
Procedemos de manera análoga a la demostración anterior.
$$P(Y = \frac{c-aX}{b}) = 1$$
Luego
$$Var(Y) = E[(Y-E[Y])^2] = E[(\frac{c-aX}{b}-\frac{c-aE[X]}{b})^2]$$
$$ = E[(-\frac{a}{b}(X-E[X]))^2] = \frac{a^2}{b^2}Var(X)$$
$$Cov(X,Y) = E[(X-E[X])(Y-E[Y])] = -\frac{a}{b}Var(X)$$
De esta manera se verifica la igualdad.
$$(Cov(X,Y))^2 = Var(X)Var(Y)$$
En el caso de que X e Y sean degeneradas la igualdad es evidente, por lo que queda concluida la demostración.
