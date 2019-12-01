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
Para la segunda parte, si X e Y son no degeneradas por el teorema anterior se da la igualdad si y solo si existen $a,b\neq 0$ con
$$P(a(X-E[X])+b(Y-E[Y]) = 0 ) = 1$$
Basta con tomar $ c = aE[X] + bE[Y]$.
