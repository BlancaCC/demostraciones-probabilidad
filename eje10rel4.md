# Ejercicio 10 

Sean X,Y variables con función de densidad 
$$f_(X,Y)(x,y)= x+y \text{ en } (x,y)\in[0,1]\times [0,1] \text{0 en el resto del intervalo}$$  

Calcular 

##(a)Curvas de regresión de $Y/X$ y $X/Y$,  así como los errores cuadráticos medios asociados. 

###Curvas de regresión de $Y/X$ y $X/Y$
La curva de regresión  $Y/X$ es $Y=E[Y/X]$
Para ello procederé a calcular las respectivas marginales: 

$$f_x(x)=\int_0^1 (x+y) dy =[xy+\frac{y^2}{2}]_0 ^1= x+\frac{1}{2}$$
$$f_y(y)=\int_0^1 (y+x) dx =[yx+\frac{x^2}{2}]_0 ^1= y+\frac{1}{2}$$

Veamos ahora las condicionadas: 
$$f_{x/y=y_0}=\frac{f_{(x,y)(x,y_0)}}{f_y(y_0)} = \frac{x+y_0}{y_0+\frac{1}{2}}$$

$$f_{y/x=x_0}=\frac{f_{(x,y)(x_0,y)}}{f_x(x_0)} = \frac{x_0+y}{x_0+\frac{1}{2}}$$

A partir de las cuales tenemos que 
$$E[Y/X]=\int_0^1 y f_{y/x=x_0}(y) \quad dy =
\int_0^1  y \frac{x_0+y}{x_0+\frac{1}{2}} dy = 
[\frac{x_0 y^2}{2x_0 +1}  +  \frac{y^3}{3(x_0+\frac{1}{2})}]_{y=0}^{y=1}$$

$$E[Y/X]= \frac{x_0 }{2x_0 +1}  +  \frac{1}{3(x_0+\frac{1}{2})} = \frac{3yx_0+2}{6x_0+3}$$


De igual manera 
$$E[X/Y]=\int_0^1 x f_{x/y=y_0}(x) \quad dx =
\int_0^1  x \frac{y_0+x}{y_0+\frac{1}{2}} dx = 
[\frac{y_0 x^2}{2y_0 +1}  +  \frac{x^3}{3(y_0+\frac{1}{2})}]_{x=0}^{x=1}$$

$$E[X/Y]= \frac{y_0 }{2y_0 +1}  +  \frac{1}{3(y_0+\frac{1}{2})} = \frac{3y_0+2}{6y_0+3}$$


### Cálculo del error cuadrático medio 

El **ECM** de la curva de regresión $X/Y$ se calcula como  como $E[Var(X/Y)] = E[X^2]+E[(E[X/Y])^2]$

$$E[X^2]= \int_0^1 x^2 f_x(x)\quad dx =
\int_0^1 x^2 (x+\frac{1}{2}) \quad dx =
\frac{5}{12}$$

$$E[(E[X/Y])^2]= 
\int_0^1 E[X/Y=y]^2 f_y(y)\quad dy = 
\int_0^1 (\frac{3y+2}{6y+3})^2 (y+\frac{1}{2}) \quad dy = $$ $$= \int_0^1 \frac{(3y+2)^2}{6^2(y+\frac{1}{2})}\quad dy=
\int_0^1 \frac{9y^2+12y+4}{36y+18}\quad dy=
\frac{1}{4}\int_0^1 (y + \frac{10}{36}+ \frac{11}{36y+18})dy=$$ $$=
\frac{1}{4}(\frac{1}{2}+ \frac{10}{36} + \frac{11}{36}\log{(\frac{36+18}{18}})) \simeq 0,27836$$

$$E[Var(X/Y)] = E[X^2]+E[(E[X/Y])^2]=0.695$$