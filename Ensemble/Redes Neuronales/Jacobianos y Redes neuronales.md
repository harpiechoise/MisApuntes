Las redes neuronales son aproximadores de funciones, es decir, toman la entrada y la salida y aproximan una función que asumimos que existe llamada $f(x)$ que mapea las entradas de $x$ con $y$. Las redes neuronales, como muchas de las técnicas utilizadas en las redes neuronales intentan descubrir una función $f(x)$ que actualmente mapea dos espacios vectoriales. También se puede ver como una forma de descubrir una **transformación lineal** que salga del espacio $x$ y llegue al espacio $y$. 

Para aproximar esta función vamos a ajustar los valores de los pesos $w^l_i$ hasta alcanzar un mínimo para la función de costo $C$. La función de costo, no es mas que una forma de representar nuestro problema. Tomando conceptos de algoritmos de optimizacion, la función de costo puede ser definida de acuerdo a la naturaleza del problema y la función de costo puede ser **cualquier** función mientras tenga lógica con el problema que queremos resolver.

Para ajustar los pesos, primero necesitamos las salidas de la red neuronal, las cuales se denominan $\hat{y}$, la cual es la salida de la **ultima capa de nuestra red neuronal**. recordando nuestro ejemplo anterior, podemos utilizar la siguiente notación
$$
o_1 = \begin{bmatrix}
\sigma(x^Tw¹_1 + b_1) \\
\sigma(x^Tw¹_2 + b_1) \\
\end{bmatrix}
$$
$$
\hat{y} = \sigma(o_1^T w²_1 + b_2)
$$ Y una opción popular y fácil de comprender para nuestra función de costo es el error cuadratico medio: 
$$
\frac{1}{2n}\sum^n_{i=1} (\hat{y} - y)²
$$
donde: 
$\hat{y}$ es la salida de la red neuronal
$y$ es nuestra variable dependiente 

Para comprender vamos a utilizar una función neurona simple:
$$ 
\hat{y} = \sigma(x^T w + b)
$$
