# SAT-F1 (Grupo 2)

### Alcance del Trabajo Practico

El alcance del trabajo incluye el manejo de bases de datos en notebooks de python y el analisis de dicha base de datos. En este caso el analisis se basara en la temporada de Formula 1 2021. Se analizara la competencia anual entre dos pilotos: Hamilton y Verstappen, quienes corren para Mercedes-AMG Petronas F1 Team y RedBull Racing repectivamente. Se estudiara que variables influyeron de manera mas determinante sobre la temporada y sobre carreras particulares. Para de esta manera entender por que los resultados fueron de esa manera.

### Selección DataSet
Para este trabajo obtamos por un dataset relacionado con el Campeonato de Formula 1 del 2021. El dataset estaba compuesto por 7 archivos .csv, de los cuales solo utilizamos 4 de ellos, dado que son las únicas tablas transaccionales. 
Una vez seleccionados los archivos, los importamos a python para luego ir uniendolas entre sí, y generar un único dataset (ds). 

Nos volcamos en esta temática, dado que además de tener interés en este deporte, el campeonato del 2021 fue muy parejo lo que lo hacía interesante para buscar y encontrar distintos factores mediante los cuales Verstappen termina llevandose la victoria por sobre Hamilton. La idea es encontrar, donde radicaron esas pequeñas diferencias del piloto holandés por sobre el británico. 

### Orden y Limpieza de los datos
En primer lugar, le indicamos al programa que en la lectura del .csv utilice la ";" como separadora. 

Luego utilizamos las herramientas de python para poder tener un pantallazo de los datos, y ver que variables (expresadas en las columnas) nos interesaban y cuales no. Una vez realizado esto, procedimos a eliminar algunas columnas y a cambiarle el nombre a otras. 

Otra de las cosas que se hizo, fue reemplazar el dato "\N" (que se asigna cuando cuando un corredor no termina la carrera) por el número 21, asignandole la "última posición" a aquellos que no terminaron. De esta forma, la variable y columna *"position_final"* (correspondiente a la posición final en la carrera) queda como una varibale enteramente númerica, facilitando el análisis posterior. 

Ademas tuvimos que cambiar algunos tipos de datos. Primero la variable position_final se cambia a datatype int, antes estaba como tipo 'object'. Seguido a la variable PointsAfterRace se modifican las comas por punto y se pasa de tipo object a tipo float asi admite decimales. 
La variable 'time_lap' que se encuentra en tipo object a tipo float utilizando la funcion tiempo_a_segundos de pandas.

Por ultimo la variable 'date' se transformo del tipo 'object' al tipo datetime con la funcion tp_datetime de pandas.

Por otro lado, para facilitar el analisis de los datos, procedimos a filtrar el dataset original y crear dos matrices de datos, cada una correspondiente a los corredores mencionados previamente. Donde *"datos_corredor1"* correspondía a Hamilton, y *"datos_corredor2"* a Verstappen. 

### Análisis

Primero se analizo el campeonato anual, luego de cada carrera se otorgan puntos debido a la posicion final obtenida y se suman. Al final el piloto con más puntos gana el campeonato.

![image](https://github.com/stefanods4/SAT-F1/assets/153237227/ff4f2eb2-c6fb-46aa-9b2d-f5f52482104b)

En este grafico se puede observar la gran paridad entre ambos pilotos a lo largo de toda la temporada. En los ultimos años, el piloto campeon se consagra con falta de 4 o 5 carreras para terminar la temporada, es decir que una temporada asi de peleada no es algo común y mucho menos, que la pelea vaya hasta la ultima carrera. Donde se puede observar en el grafico que ambos pilotos se encontraban empatados antes de la misma.

Luego analizamos los resultados carrera a carrera

![image](https://github.com/stefanods4/SAT-F1/assets/153237227/35f1cde1-9b2a-4303-9892-d43a2a8e9957)

En este, no se encuentran grandes diferencias, ambos pilotos pelearon el primer y segundo puesto en 14 de las 21 carreras del año, mostrando claramente la diferencia con el resto de los pilotos y que tan reñida fue la competencia entre estos dos.

Siguiendo, decidimos hacer una comparacion que nos parecio de vital importancia: la posicion de clasificacion vs la posicion final de carrera.

![image](https://github.com/stefanods4/SAT-F1/assets/153237227/231e941a-81d0-454c-abd0-b45a5d2f9c7b)


Este analisis decidimos hacerlo debido a lo siguiente. La Formula 1 es la categoria mas competitiva del deporte automotor, es donde mas dinero si invierte en tecnologia y utilizan los autos mas rapidos del mundo. Estos autos se configuran carrera a carrera de manera diferente. Para lograr plasmar las ventajas del auto, en cada circuito particular.
A rasgos generales un auto que es capaz de clasificar mejor, es decir dar una vuelta a mayor velocidad desgastara mas las ruedas y por lo tanto no tendra tan buen ritmo de carrera, esto es 
la capacidad de mantener un tiempo bajo por vuelta, por la mayor cantidad de vueltas posibles. Quien logre encontrar el mejor equilibrio, es muy probable que salga victorioso aunque al tratarse de un deporte, esto puede no terminar cumpliendose siempre. Pero siendo este un ambito tan profesional, los pilotos buscan aumentar las probabilidades de ganar y no solo pensar en ir primeros todo el tiempo.

Siguiendo este punto decidimos buscar la cantidad de veces que estos pilotos mejoraron, mantuvieron o empeoraron durante la carrera respecto de su posicion de clasificicacion

![image](https://github.com/stefanods4/SAT-F1/assets/153237227/f22a5e57-9731-4daf-94f8-0660070805f6)

Por el lado de hamilton podemos observar que 6 veces mejoro la posicion, 11 veces la mantuvo y 4 veces empeoro, mientras que Verstappen mejoro 7, mantuvo 9 y empeoro 4.

Esto nos indica que 11 veces hamilton y 9 veces verstappen encontraron un muy buen equilibrio en su auto. observando el grafico "Posicion final vs Clasificacion" vemos que de esas 11 veces de hamilton 6 clasifico y termino segundo(30% de las carreras), y 3 veces clasifico y termino primero(14,3% del total de carreras).
Mientras que Verstappen 3 veces le sucedio terminando segundo y 6 veces con el primer puesto, mismos porcentajes pero al reves que hamilton, es decir que Verstappen en la busqueda de este "equilibrio" encontro mas veces el mejor(6 contra tres) aunque hamilton lo alcanzo mas veces(11 a 9). 

Continuando con este anilisis, el mejorar la posicion de clasificacion significa que el corredor no pudo encontrar un buen equilibrio, por lo que opto por sacrificar la clasificacion y obtener un mejor ritmo de carrera.
En este caso 





