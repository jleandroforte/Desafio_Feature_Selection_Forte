# Desafio_Feature_Selection_Forte
En este desafío tomamos un camino alternativo para hacer Feature Engineering sobre nuestro dataset y contrastamos los resultados del modelo con los del desafío anterior. 

#**Objetivos de la entrega**

En los desafíos previos evaluamos un modelo de regresión logística para predecir si una observación redunda en una venta o no.

Recordemos que una de nuestras variables, "order", toma el valor 1 cuando se trata de una venta y 0 caso contrario.

Vimos que un modelo simple y con una relativamente leve carga de Feature Engineering arrojaba un accuracy del 90%, lo cual habla de una estructura de datos adecuada para predecir ventas y más tarde, usando Forward Selection y ajustando los parámetros de la regresión, alcanzamos un accuracy total, prediciendo correctamente el valor que toma la variable order todas las observaciones del testing set.

En esta entrega tomamos un camino distinto para la ingeniería de features, en lugar de descansar en el método de forward selection, tomamos la siguiente ruta,

> Eliminamos variables co-lineales, para reducir la multicolinealidad. Esto no sólo nos ayuda cuando usamos una regresión logística, es necesario para cualquier modelo de regresión.

> Agrupamiento de productos: El dataset tiene más de 22 mil productos únicos, que se identifican por un valor numérico, pero ese valor numérico no es representativo de ninguna característica intrínseca de los productos, sólo su descripción. Esto puede generar resultados espurios en modelos de machine learning, por eso vamos a proponer una estrategia para agruparlos y reemplazarlos por variables dummy.

> Tratamiento de la estacionalidad: En entregas anteriores vimos como el revenue responde a un patrón estaciona, *al interior de cada período de 7 días*, esto es un insigth fundamental para reemplazar nuestros valores de la variable "Day", que también es numérica y cuenta los días de observaciones del 1 al 91, y por lo tanto puede complejizar innecesariamente la interpretabilidad de los datos de una regresión.

Finalmente, una vez evaluados estos métodos de Feature Engineering, vamos a estudiar si la aplicación de Principal-Component Analysis es una alternativa válida para obtener resultados óptimos en el modelo de regresión logística.
