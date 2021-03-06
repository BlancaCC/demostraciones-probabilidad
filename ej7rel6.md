---
title: "Ejercicio 7 Relación 6"
author:  Blanca Cano Camero, Daniel Krell Calvo
date: 22 de Diciembre del 2019
output: pdf_document
---
**7.  Cierta enfermedad afecta al 0.5% de una poblacion.  Existe una prueba para la detección de la enfermedad, que da positiva en los individuos enfermos con probabilidad 0.99 y da negativa en los individuos sanos con probabilidad 0.99.
a)  Calcular la probabilidad de que un individuo elegido al azar esté realmente enfermo si la prueba da resultado positivo.
b)  Calcular,  aproximadamente,  el  numero  mınimo  de  personas  con resultado positivo en la prueba que hay que elegir, de forma aleatoria e independiente, para que la proporcion de personas realmente enfermas en la muestra sea menor que 1/2 con probabilidad mayor o igual que 0.95.**



a)
Definimos las siguientes variables aleatoria:
E="que un individuo tenga la enfermedad"
S="que un individuo esté sano"
O="positivo en la prueba de detección"
N="negativo en la prueba"

$P[E]=0,005 P[P/E]=0,99 P[P/S]=0,99$
Usando el teorema de Bayes,

$$P[E/O] = \frac{P[O/E]P[E]}{P[O/E]P[E]+P[O/S]P[S]} = \frac{0,99*0,005}{0,99*0,005+0,01*0,995} = \frac{99}{298} \approx 0,3322$$

b)
Definimos
$$S_n = \sum_{i=1}^{n}{E_i},$$
donde cada $X_i$ estudia si un individuo que ha dado positivo tiene la enfermedad. Por el apartado anterior, $X_i\leadsto B(1,p=\frac{99}{298})$, luego $S_n \leadsto B(n,\frac{99}{298})$.
Queremos
$$P[\frac{S_n}{n} < \frac{1}{2}] \geq 0,95$$
$$P[S_n < \frac{n}{2}] \geq 0,95$$

Usando el segundo teorema del límite de De Moivre y Laplace:

$$\frac{S_n - E[S_n]}{\sqrt{Var(S_n)}} = \frac{S_n -np}{ \sqrt{np(1-p)}}
\rightarrow ^L Z \sim \mathcal N(0,1)$$

Aplicando lo anterior:

$P[Z< \frac{\frac{n}{2}-np}{ \sqrt{np(1-p)}}] \geq 0,95$ ;  $P[Z< \frac{\frac{n}{2}-n\frac{99}{298}}{ \sqrt{n\frac{99}{298}(1-\frac{99}{298})}}] \geq 0,95$

Llamemos $a = \frac{\frac{n}{2}-n\frac{99}{298}}{ \sqrt{n\frac{99}{298}(1-\frac{99}{298})}} $

Mirando en la tabla de la normal concluimos que $a \geq 1,65$
de aquí despejamos la n:

 Llegando a una ecuación de segundo grado con soluciones $n=21,45$ y $n= 0$
Descartamos la segunda y llegamos a la conclusión de que el número mínimo es 22.
