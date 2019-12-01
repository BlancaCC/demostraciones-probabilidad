---
title: "Propiedades de la esperanza matemática "
author:  Blanca Cano Camero, Daniel Krell Calvo 
date: 1 de Diciembre del 2019
output: pdf_document
---


## Consideraciones previas

### Definición de la Esperanza matemática

Sea un vector aleatorio n-dimensional: 
 $$\textbf{X} = ( X_{1}, ..., X_{n} ) : (\Omega,   \mathcal{A}, P) \rightarrow (\mathbb{R^n}, \mathcal{B^n}, P_x)$$ 

 La esperanza matemática $E[\textbf{X}] \text{de  }     \textbf{X}$ si existe se define como  un vector cuyas componentes son las esperanzas matemáticas de sus componentes aleatorias. 

 #### Algunas propiedades de la esperanza matemática unidimensional:

##### Linealidad 
 si existe $E[\textbf{X}]$ entontes  $\forall a,b \in \mathbb R,\quad  \exists E[a\textbf{X} + b] =  a E[\textbf{X}]  + b$

Demostración de la existencia: 
- Caso discreto: Por convergencia absoluta de una serie : 

$$\sum_{x \in E_x} |ax + b| P[\textbf X = x] + b \le |a| \sum _{x \in E_x} (x  P[\textbf X = x]  ) +| b| < \infty$$

- Caso continuo: Por convergencia absoluta de la integral 
$$\int _{x \in E_x} |ax + b| f_ {\textbf X}(x) + b  \quad dx\le |a| \int_{x \in E_x} x f_ {\textbf X}(x)  dx +| b| < \infty$$

Demostración de la linealidad: 
Por la linealidad de los operadores suma e integral; 

- Caso discreto: 

$$\sum_{x \in E_x} (ax + b) P[\textbf X = x] + b = a \sum _{x \in E_x} (x  P[\textbf X = x]  ) + b$$


- Caso continuo 
$$\int _{x \in E_x} (ax + b) f_ {\textbf X}(x)+ b \quad  dx= a \int  _{x \in E_x} (x  f_ {\textbf X}(x)) dx + b$$

##### Monotomía 

## Propiedades de la esperanza matemática n-dimensional

### Linealidad  

Se quiere probar que para cualquier $(a_1,..., a_n), (b_1,...,b_n) \in \mathbb{R^n}$, 
$$\exist E [X_i] \Rightarrow  \exist E [a_i X_i + b_i]$$  y además si existe $E [\sum_{i=1}^{n}a_i X_i + b_i]$ entonces es igual a $\sum_{i=1}^{n}a_i E[X_i] + b_i$
 
##### Demostración 

La existencia es consecuencia de la definición de esperanza matemática y la linealidad de la esperanza matemática unidimensional de cada una de sus componenetes, que está ya demostrada en consideraciones previas y además aplicando tal linealidad en la variable aleatoria definida como $\sum_{i=1}^{n}a_i X_i + b_i$ tenemos que 
$$E [\sum_{i=1}^{n}a_i X_i + b_i] = \sum_{i=1}^{n}(a_i E[X_i] + b_i)$$ 

### Monotomía  

Sean $X_1$ $X_2$ variabels aleatoria unidimensionales para las cuales existen sendas esperanzas, entontes se tiene que si 

$$X_1 \le  X_2 \Rightarrow  E[X_1] \le  E[X_2]$$

###### Demostración  
Como la suma de varibles aleatorias es una variable aleatoria podemos definir $Z = X_2 -X_1$

Dada la no negatividad de la esperanza tenemos que $E[Z]> 0$ Aplicando la linealidad de la variable aleatoria 
$$E[Z] =  E[X_2] - E[X_1] \ge 0 \Rightarrow[X_2] > E[X_1]$$
