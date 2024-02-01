$$
V(s) = max_a (R(s, a) + \delta V(s'))
$$
- El valor $V$ es el resultado de estar en cierto estado, este valor se re calcula a partir de una formula 
- $s$ Es el estado actual
- $R$ es la recompensa, que recibe 2 parámetros
	- $s$ Es el estado
	- $a$ Es la acción a llevar a cabo
- $s'$ Indica el estado al que nos moveremos cuando llevemos a cabo una acción y cambiemos de estado
- $\delta$ Es una diferencia que multiplica al resultado de $V(s')$, con este valor vamos a ponderar el hecho de que comparando los valores de los estados que tomemos tengan el mismo peso. El factor $\delta$ a pesar de que todas las acciones puntúen, provoca que una de las acciones tenga un valor más alto respecto a las otras. 
Lo que haremos es buscar la acción que mejora el valor de nuestro estado, y buscamos el $s'$ que maximiza la ecuación de Bellman.

En resumen, lo que queremos encontrar es el **conjunto** de acciones que maximizan el valor de la ecuación de Bellman. 
