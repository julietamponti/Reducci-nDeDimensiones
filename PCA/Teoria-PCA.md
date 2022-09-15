# PCA

La idea de PCA es encontrar las "direcciones" principales de los datos, es decir, aquellas direcciones sobre las cuales podemos proyectar los datos reteniendo su variabilidad.
En concreto, PCA ajusta una hiper-elipse a los datos y devuelve los ejes que la componen también conocidos como *componentes principales*.
Luego, los dats se podrán proyectar sobre estas componentes logrando así una reducción de dimensiones.

¿Cómo utilizo este método sobre una matriz A?

1. Para cada elemtno de la columnas de $A_i$, restarle el promedio de dicha columna. Esto permite centrar los datos en el origen.
2. Para cada elemento de la columna $A_i$, dividirlo por la desviación estándar de dicha columna. Esto primer escalar los datos.
3. Calcular la matriz de covarianza $$cov(A) =  \frac{1}{n-1} A^t A$$
4. Calcular los autovalores y autovectores de la matriz de covarianza. Los autovectores conformarán las componentes principales y los autovalores indicarán la importancia de cada componente.

La matriz de covarianza es simétrica y en cada celda indica la covarianza entre las columnas i y j de nuestra matriz original.
- Cuando la covarianza es cercana a cero, las columnas son independientes.
- Cuando la covarianza es cercana a 1 o -1 las columnas son dependientes.
- Cuando la covarianza es igual a 1 o -1, una columna es combinación lineal de la otra, esto quiere decir que una de ellas es redundante.

Para obtener los componentes principales, simplemente de calculan los autovalores y autovectores de la matriz de covarianza.
