La propagación hacia adelante, hace referencia a como los vectores de entrada, van a propagarse hacia adelante para producir una salida. Los vectores de entrada, también denominados **x** o **variables independientes**, se definen de la siguiente manera: 

$$
x = (x_1, x_2, x_3, ..., x_n)
$$
Donde: 
$$
x \in \mathbb{R}^n
$$
Para describir las matemáticas de las redes neuronales, primero vamos a enfocarnos en una sola neurona

## Función neurona 
Supongamos tenemos un vector de entrada: 
$$
x = \begin{bmatrix}
	x_1 \\
	x_2 \\
	x_3 \\
	\vdots \\
	x_n
\end{bmatrix}
$$
Algo importante a notar es que el vector de entradas es la traspuesta del vector anteriormente tipificado. Y supongamos tenemos un vector de pesos $w$, similar al vector $x$
$$
w = \begin{bmatrix}
w_1 \\
w_2 \\
w_3 \\
\vdots \\
w_n
\end{bmatrix}
$$
Es importante notar que ambos vectores son de tamaño $n$, tanto el vector de entradas, como el vector de pesos, es decir, que tanto $x$, como $w$ tienen la misma cantidad de entradas. 

Y la **función neurona** se define como un producto ponderado al que se le aplica la sigmoide: 
$$
\sigma((\sum_{i=1}^{n} x_i w_i) + b)
$$
La función neurona, nos recuerda a una regresión lineal, pero donde todos los términos van a ser ponderados y sumados, lo que da como resultado un escalar. Cosas importantes a tener en cuenta: 
- $\sum^{n}_{i=1} x_i w_i$ es un escalar
- $b$, es un escalar, llamado **sesgo**, el sesgo va a regular el punto de partida en el gráfico sobre el eje de nuestra función modelada
- $\sigma$(...), se denomina función de activación, y la función **sigmoidea**, es una elección popular para las redes neuronales
- El rango de la función neurona depende de la función de activación 
- La función de activación recibe como parámetro un escalar. 
La función neurona tiene una sumatoria $\sum^{n}_{i=1} x_i w_i$, la cual se expande con propositos de explicar, pero en realidad, esto no es mas que un producto punto entre dos vectores, este producto se puede escribir de la siguiente manera: 
$$
\sum^n_{i=1}x_iw_i = x^Tw
$$
Por lo tanto la función neurona se puede reformular de la siguiente forma:
$$
\sigma(x^Tw + b)
$$
donde: 
- x: Es un vector columna.
- w: es un vector columna.
- b: es un escalar.
- $\sigma$: Es la función sigmoidea.
Este termino interno de la función de activación se denomina $z$, es decir:
$$
z = x^Tw + b
$$
Nada mas es una convención para la función de activación, las funciones de activación por lo general, reciben un argumento llamado $z$, esto es porque no todas las redes neuronales usan la misma función neurona, por ejemplo las redes neuronales convencionales, no utilizan la misma función que estamos revisando, por lo tanto $z$ se entiende como el resultado de cualquier función neurona.

## Mas neuronas
Cuando agregamos mas neuronas, por ejemplo 2 neuronas, el proceso de feed-forward, es similar, pero vamos a tener en cuenta que cada función neurona es independiente, es decir, para un vector de entradas $x$, vamos a tener dos funciones neurona que actúan de manera independiente, es decir, para dos neuronas de una red neuronal con una sola capa tendremos como salida:
$$
\begin{align*}
o = \begin{bmatrix}
\sigma(x^T w_1 + b_1)\\
\sigma(x^Tw_2 + b_1)
\end{bmatrix}
\end{align*}
$$
donde $o$ es la salida, y la formulación presenta un sesgo compartido por capa, también hay otra formulación, donde el sesgo es independiente por función neurona: 
$$
\begin{align*}
o = \begin{bmatrix}
\sigma(x^T w_1 + b_1)\\
\sigma(x^Tw_2 + b_2)
\end{bmatrix}
\end{align*}
$$

Esta función neurona con dos neuronas, eventualmente va a tener dos salidas escalares.

Ahora si agregamos otra capa a nuestra red neuronal, el resultado servirá de entrada a la siguiente capa, imaginemos una red neuronal con 2 neuronas en la capa 1, y 1 neurona en la capa dos:
$$
o_1 = \begin{bmatrix}
\sigma(x^Tw¹_1 + b_1) \\
\sigma(x^Tw¹_2 + b_1) \\
\end{bmatrix}
$$
$$
o_2 = \sigma(o_1^Tw²_1 + b_2)
$$
Donde:
- $w_i^l$ son los pesos de la función neurona
	- $l$: Es la capa a la cual pertenecen
	- $i$: Es la función neurona a la cual pertenecen los pesos
- $o_1$: Es la salida de la primera capa (es un vector)
- $o_2$: Es la salida de la segunda capa (y es un escalar)
- $\sigma$: Es la función de activación, en este caso estamos ocupando la función sigmoidea
Observaciones:
- La cantidad de salidas escalares de una capa, es igual a la cantidad de neuronas de la capa en cuestión
- La cantidad de entradas de la siguiente capa, es independiente de la cantidad de neuronas de la capa anterior.
- En este ejemplo se utiliza el sesgo por capa.
- El numero de neuronas que ponemos es arbitrario para cada capa.
