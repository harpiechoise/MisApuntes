 Los arboles de decisión hacen divisiones en los datos. Parten haciendo la mayor cantidad posible de divisiones en los datos y escogen la mejor a partir del indice de **impureza de Gini**. Este indice indica la cantidad de información que aporta una variable sobre la predicción del árbol. **Mientras mas alto** el nivel de impureza, menos información aporta a la clasificación la variable, y mientras mas bajo, mas importante es la variable para la predicción.

La formula de la impureza de Gini es: 
$$
Gini(D) = 1-\sum^{C}_{i=1} p²_i
$$
El máximo valor para la función Gini es 0.5. Y el mínimo es 0. 

También para explicar la cantidad de información que existe en una variable se usa la función de entropía. La entropia mide la cantidad de información que hay en una variable. También mide la impureza de una variable, mientras mas alta mas impureza existe en la variable y mientras mas baja sea la entropia, mas información aporta la variable para la predicción.

La formula de la entropia es:
$$
H(x) = - \sum_{x \in X} = p(x) log (p(x))
$$

También se dice que la entropia es el valor esperado de la sorpresa (en términos estadísticos.). 

A diferencia de Gini, el máximo de la función de entropia es 1 y el mínimo es 0

## Gini vs Entropia

Como anteriormente dijimos, tenemos dos criterios para hacer una división en un árbol de decisión, **Impurza Gini** y **Entropia**. ¿Pero en que se diferencian en el contexto de los arboles de decisión y la forma de crear la división de los datos?.

En general Gini es mas facil de computar, pero no es tan sensible a los cambios de probabilidad, por lo tanto si necesitamos mas sensibilidad en los cambios de probabilidad usamos entropia, ademas la entropia puede aumentar la precisión de clasificación minimamente. 
