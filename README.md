# SAT-F1 (Grupo 2)

### Selección DataSet
Para este trabajo obtamos por un dataset relacionado con el Campeonato de Formula 1 del 2021. El dataset estaba compuesto por 7 archivos .csv, de los cuales solo utilizamos 4 de ellos, dado que son las únicas tablas transaccionales. 
Una vez seleccionados los archivos, los importamos a python para luego ir uniendolas entre sí, y generar un único dataset (ds). 

Nos volcamos en esta temática, dado que además de tener interés en este deporte, el campeonato del 2021 fue muy parejo lo que lo hacía interesante para buscar y encontrar distintos factores mediante los cuales Verstappen termina llevandose la victoria por sobre Hamilton. La idea es encontrar, donde radicaron esas pequeñas diferencias del piloto holandés por sobre el británico. 

### Orden y Limpieza de los datos
En primer lugar, le indicamos al programa que en la lectura del .csv utilice la ";" como separadora. 

Luego utilizamos las herramientas de python para poder tener un pantallazo de los datos, y ver que variables (expresadas en las columnas) nos interesaban y cuales no. Una vez realizado esto, procedimos a eliminar algunas columnas y a cambiarle el nombre a otras. 

Otra de las cosas que se hizo, fue reemplazar el dato "\\\N" (que se asigna cuando cuando un corredor no termina la carrera) por el número 21. De esta forma, la variable y columna *"position_final"* (correspondiente a la posición final en la carrera) queda como una varibale enteramente númerica, facilitando el análisis posterior. 

Por otro lado, para facilitar el analisis de los datos, procedimos a filtrar el dataset original y crear dos matrices de datos, cada una correspondiente a los corredores mencionados previamente. Donde *"datos_corredor1"* correspondía a Hamilton, y *"datos_corredor2"* a Verstappen. 

EXPLICAR EL CAMBIO DE VARIABLE A TIPO FLOAT!!!!!!!!!!!!!!!

### Análisis
