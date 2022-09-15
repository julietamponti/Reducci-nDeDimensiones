# SVD

La SVD  es una de las herramientas más importantes para la reducciónde dimensiones de un set de datos y surge de realizar una descomposición de una matriz.
Sea A una matriz de *nxm*, se puede demostrar que existen tres matrices U, V  y Σ, tales que: $$A = U * Σ * V^T$$
Donde:
- U es una matriz unitaria de *nxm*.
- V es otra matriz unitaria de *mxm*
- Σ es una matriz diagonal de *nxm*

¿Cuál es la forma de obtener dichas matrices?

1. Calcular los autovalores y autovectores de $A^t A$
2. La matriz Σ se compone de la raíz cuadrada de los autovalores de $A^t A$ de forma diagonal y ordenados de forma descreciente.
3. La matriz U se compone con los autovectores normalizados como columnas.
4. La matriz V se puede obtener resolviedno el sistema $AV= UΣ$ sabiendo que $V^t V$ es la matriz identidad. 

## SVD reducida
Ya sabemos que Σ se obtiene a partir de la raíz cuadrada de los autovalores de la matriz $A^t A$, que son los valores que "estiran" a la base ortogonal compuesta por los vectores de U.
En algunas ocaciones se puede dar que algunos valores de la diagonal de Σ sean cero, y la conscencua que traen es que anulan ciertas componentes a la hora de realizar el producto matricial y de ahi surge el concepto de descomposición en valores singulares reducida. Entonces, de los $σ _1 , σ_2, .., σ_n$ elementos de la matriz Σ, se pueden tomar solo aquellos r valores que son positivos (distintos de cero) de froma tal que $σ _1 , σ_2, .., σ_r$ son positivos.

Teniendo en cuenta lo dicho anteriormente, queda explicito, que solo se van a utilizar las r primeras columnas de la matriz U y las r primeras columnas de la matriz $V^t$, por lo tanto se deduce que el valor r coincide con el rango de la matriz A.

## Aproximación de Rango K
De SVD reducida podemos decir que una matriz A se puede representar de forma compacta, donde se van a utilizar los r valores signlares no nulos unicamente (diagonal de Σ), ya que son los unicos que aportan información, lo que nos permite descartar vectores de las matrices U y V.
¿A qué conclusión se puede llegar?
Analizandolo, podemos pensar que como los valores de la matriz Σ se encuentrna ordenados de mayor a menor, entonces estos representan un grado de importancia de los datos.
En consencuencia, se podría ir más allá de quedarse con los r valores no nulos, ya que se podría obtener una buena aproximación de la matriz A utilizando k valores singulares, siendo *k<r*.

De todas formas, ¿qué tan chico puede ser ese valor de k?
Dependiendo el valor de k que elijamos, vamos a lograr una mejor o peor aproximación de la matriz A, ahora tenemos que enfocarnos en que basarnos para seleccionar dicho valor. Para esto, se define el concepto de *energía* de una matriz de la siguiente manera: $$Σ_{i=1}^{n} {σ_i}^2$$
