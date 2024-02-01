Un clasificador linear consiste en un vector de pesos $w$ y un sesgo $b$. Dada una instancia de $x$, la etiqueta predicha $y$ se obtienen de acuerdo a la siguiente ecuación. 
$$
y = \text{sgn}(w^t x + b)
$$
- Función signo
	- La función signo tiene un dominio en los reales $\mathbb{R}$, y su codominio es el conjunto $\{-1, 0, 1\}$, y su definición es la siguiente:
			$$
	
	  sgn(x) \left \{
	    \begin{aligned}
		    1 \text{ si } x > 0 \\
		    0 \text{ si } x = 0 \\
		    -1 \text{ si } x < 0
	    \end{aligned}
	  \right .
			$$
	- La función signo es una manera de clasificar números continuos en categorías basadas en su signo.
	- La función signo se usa en algoritmos de clasificación como una función de activación binaria, debido a que puede tomar una salida continua, y convertirla en una clase a partir de su signo.
- El vector $w^T$ o vector de pesos
	- Es un vector columna de números generado de manera a aleatoria siguiendo una distribución de probabilidad.
	- Existen tantos valores de $w^t$ como componentes de $x$, cada uno de estos valores se multiplica con $x$ para aproximar el valor de $f(x)$ que es la función que intentamos encontrar.
- $b$ o sesgo
	- Es un continuo que representa el punto donde nuestra función $f(x)$ corta el eje en $x$. 
- Derivada: 
	- Si derivamos $y = wx + b$ (la cual es una función lineal en términos de $x$), obtenemos a $w$ que representa la pendiente. 
	- $w$ es la cantidad de variación que existe si $x$ aumenta en unidades.
El proceso de clasificación consta de dos pasos, el primer paso, es encontrar una linea que separa a las clases que se busca separar en dos grupos, los positivos (sobre la linea) y los negativos (por debajo de la linea). Se usa la función signo para determinar de que lado del gráfico esta el punto $y(x)$. 

Para encontrar el mejor $w$ y $b$ para separar ambas clases, se usa el algoritmo FLDA, que lo que hace es maximizar la distancia entre las dos clases $-$ y $+$ mientras minimiza la varianza entre las instancias de una misma clase haciendo que los puntos estén mas juntos.

Para esto vamos a obtener la media $\mu_{+}, \mu_{-}$ y la matriz de covarianza de ambas clases $\sigma_+, \sigma_-$. La distancia entre los centros de ambas clases se puede escribir como:
$$
S_B(w) = (w^T \mu_+ - w^T \mu_-)²
$$
- $S_B$ mide la dispersión total de las medias de las clases con respecto al total.
Y la varianza entre clases se calcula como:
$$
S_w(w) = w^T \sigma_+ w + w^T \sigma_-w
$$
- $S_w$ Mide la dispersión de las medias de las clases respecto al total
LDA combina las dos medidas de distancia con la formula:
$$
J(w) = \frac{S_B(w)}{S_w(w)}
$$
- Esta función busca **maximizar** $S_B$ mientras se minimiza $S_w$, para encontrar la máxima se tiene que calcular su derivada e igualar a cero.
- Para resolver la derivada se usa el método de vectores propios
Y la formulación para encontrar la dirección $w$ o pendiente de mayor separación es:
$$
w^* = (\sigma_+ + \sigma_-)^{-1}(\mu_+ - \mu_-)
$$
Luego de encontrar a $w$ para encontrar a $b$ simplemente tomamos el punto medio entre ambos centros:
$$
b = w^T(\mu_+ + \mu_-) / 2
$$

