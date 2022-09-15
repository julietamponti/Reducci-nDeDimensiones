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
