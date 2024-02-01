Una definición formal para el proceso de aprendizaje es la siguiente: 
- Se denota $X$ como la instancia del espacio $D$ como una distribución sobre $X$.
	- Es decir, $X$ es el conjunto de todos los posibles vectores de una determinada forma, es decir, representa todas las observaciones posibles de un espacio vectorial con el mismo numero de componentes de cada observación. Por ejemplo si una observación de D, es de la forma $(x_1, y_1, z_1)$. $X$ representa todos los ejemplos con una misma forma los cuales son infinitos.
	- $D$, es una distribución de probabilidad, que agrupa los datos similares, en este caso se pueden reconocer como una agrupación de los casos de similares características de acuerdo a su distribución probabilista en un espacio infinito. 
- Y la función $f$ representa la verdad, y se conoce como la función objetivo:
	- La función $f$, es una función que siempre nos dará el resultado correcto, es una función teorica, dado que nosotros no tenemos acceso a la formulación real de esa función. 
	- Si bien no tenemos acceso a su formulación sabemos cual es su comportamiento, porque tenemos sus entradas y salidas, entendiendo como entrada un valor de $x$ dado en el conjunto de observaciones, y su respectivo valor de $y$ que también es conocido en el caso del *aprendizaje supervisado*.
- Dado un conjunto de datos $\text{D} = {(x_1,y_1), (x_2,y_2)...(x_n,y_n)}$ donde las instancias de $x_i$ son tomadas de manera independiente e idénticamente distribuida desde la distribución $D$. y a su vez $y_i = f(x_i))$
	- El conjunto de datos, es un conjunto de muestras tomadas de una distribución de probabilidad D, de forma totalmente arbitraria e independiente. Es decir, la forma en que la muestra se toma es de manera aleatoria.
	- Se asume que $y_i$ es el resultado de una función que no conocemos aplicada a $(f(x_i))$.
	- La función $h(x)$ aproxima a la función $f(x)$, aunque no se puede demostrar que sean la misma función, asumimos que si la función de costo es baja, tenemos una buena aproximación a $f(x)$.
- El objetivo es construir una función *hipotesis* $h(x)$ que minimice la generalización del error:
	- Minimizar la generalización del error, hace referencia a que se puede medir la cantidad de errores de la función $h(x)$ frente a $f(x)$ debido a que tenemos las salidas de $f(x)$, y en un problema de clasificación binaria, el error se puede calcular como la cantidad de "predicciones" erradas de $h(x)$ frente a $f(x)$, asumiendo que $f(x)$ es la función que mapea f(x)  exactamente y sin errorres a $x$ con $y$.
La formulación de la función a minimizar dentro de una clasificación binaria esta dada por la siguiente formula:
$$
err(h) = \mathbb(E)_{x \sim D}[\mathbb{I}(h(x) \neq f(x))]
$$

