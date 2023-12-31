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

Primero se analizó el campeonato anual, luego de cada carrera se otorgan puntos debido a la posicion final obtenida y se suman. Al final el piloto con más puntos gana el campeonato.

![image](https://github.com/stefanods4/SAT-F1/assets/153237227/9b021dc2-4df0-498a-b8b2-900ec5a879cc)


En este gráfico se puede observar la gran paridad entre ambos pilotos a lo largo de toda la temporada. En los ultimos años, el piloto campeón se consagra con falta de 4 o 5 carreras para terminar la temporada, es decir que una temporada asi de peleada no es algo común y mucho menos, que la pelea se mantenga hasta la última carrera. Donde se puede observar en el grafico que ambos pilotos se encontraban empatados antes de la misma.

Luego analizamos los resultados carrera a carrera

![image](https://github.com/stefanods4/SAT-F1/assets/153237227/35f1cde1-9b2a-4303-9892-d43a2a8e9957)

En este, no se encuentran grandes diferencias, ambos pilotos pelearon el primer y segundo puesto en 14 de las 21 carreras del año, mostrando claramente la diferencia con el resto de los pilotos y que tan reñida fue la competencia entre estos dos. Lo que si podemos agregar, es que Verstappen la mayoría de las veces en las que se desvió de la posición 1-2, fue cuando no terminó la carrera por problemas técnicos. No así Hamilton quien sufrió menos problemas técnicos, pero fue menos regular en la estrategia y en el manejo. 

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
En este caso, observando el grafico "Resultados por carrera" vemos que en dos ocasiones ambos pilotos clasificaron bien pero tuvieron muy pobre desempeño en las carreras(Azerbaijan e Italia) y 3 veces cambiaron la posicion entre ellos(bahrain, Mexico y Brazil), . Creemos que estas 3 carreras y la carrera final, requiere un analisis especifico para entender que sucedio particularmente en cada una y entender por que si habian clasificado mejor terminaron peor

Otro analisis a tener en cuenta es sobre una de las pocas variables que los equipos pueden controlar y no dependen casi exclusivamente de los pilotos, los PitStops, durante una carrera los corredores entran al "pitlane" para cambiar neumaticos desgastados o arreglar el auto debido a daños. Estas paradas se deben hacer en el menor tiempo posible ya que son consideradas perdidas de tiempo aunque sean necesarias, y se busca realizarlas de la manera mas eficiente posible. Un segundo mas en una parada puede hacer que un piloto pierda una carrera
Observando el siguiente grafico que compara el tiempo promedio de PitStop de estos dos pilotos: 

![image](https://github.com/stefanods4/SAT-F1/assets/153237227/923d8859-db1e-42fe-b376-88d0f1909905)

En este Grafico podemos ver como si bien el tiempo medio de las paradas de ambos es similar, Hamilton tiene mas variabilidad, Mientras que Verstappen fue mas regular a lo largo de toda la temporada con tiempos menores. Existe una diferencia de 3 un segundos entre el limite superior de Verstappen y el de Hamilton, una diferencia enorme en un entorno tan competitivo como este 

Continuando con el analisis de como los equipos y pilotos configuran los autos(set up) para cada carrera.
antes de los analisis hay que aclarar un concepto: "Stint" se le dice a un periodo de vueltas en una carrera en que se uso un mismo juego de ruedas ya que estas se cambian segun el desgaste.

Analisis carrera bahrein

Se puede observar en el boxplot 

![image](https://github.com/stefanods4/SAT-F1/assets/153237227/e2a049b9-7a3d-42ab-acfd-e5741512aa2a)

que Hamilton tiene un tiempo promedio de vuelta menor pero la amplitud es muy similar, siendo la de 
Verstappen un poco mayor 

En esta carrera Hamilton clasifico segundo mientras que Verstappen primero.
La diferencia que le permitio ganar a hamilton reside en la estrategia de carrera.Observando los tiempos por vuelta de ambos corredores en la siguiente tabla podemos hacer un analisis mayor:

https://vscode.dev/github/juzimbimbakis/sat-python-oct-23/blob/clase3/F1/F1%20(1).ipynb#C38:L4

Durante toda la carrera se observa que los tiempos de vuelta de Verstappen son mejores con ruedas de el mismo tiempo de uso. Debido a esto, Hamilton decide parar primero a cambiar ruedas, en la vuelta 13. y luego comienza a marcar menores tiempos que verstappen con ruedas ya muy gastadas. Verstappen cambia ruedas 5 vueltas después, pero con la ventaja obtenida por Hamilton este lo pasa mientras Verstappen esta parado. 
Luego Verstappen con su mejor tiempo de vuelta lo alcanza en la vuelta 28 y lo pasa. En la vuelta siguiente Hamilton decide cambiar ruedas de nuevo. En este Stint, Hamilton baja sus tiempos respecto al juego de gomas anterior casi 1 segundo 94.2 segundos por vuelta aproximadamente. Mientras que verstappen comienza a aumentar sus tiempos de vuelta casi igualando a los de Hamilton antes de parar.
Es decir, se repite lo sucedido anteriormente, Hamilton gira con tiempos menores a verstappen hasta que este para y cambia ruedas en la vuelta 40.
En esta ultima etapa, Hamilton mantiene su ritmo de 94.2 segundos aproximadamente hasta el final de la carrera. Mientras que verstappen, si bien conduciendo muy rápido también tiene tiempos muy irregulares, oscilando sus tiempos de vuelta entre 93.2 y 94 segundos. Esto indica el claro ‘’nerviosismo’’ del corredor por alcanzar a hamilton.  Pero sin lograr pasarlo., permitiendo asi que Hamilton gane la carrera.
En resumen, Verstappen al haber clasificado primero, claramente tenia un auto capaz de girar más rápido pero que gastaría más las ruedas. Durante la carrera este corredor prefirió hacer stints mas largos que su rival, disminuyendo ampliamente su tiempo de vuelta el cual era su principal ventaja en la carrera. Asi permitiendo que su rival lo pase.
Gracias al gran ritmo de carrera(capacidad de mantener un tiempo bajo por vuelta por la mayor cantidad de vueltas posibles) de Hamilton en el ultimo stint, Verstappen no lo pudo alcanzar. Permitiendo asi que gane la carrera

Analisis carrera Brasil:

Se puede observar en el Boxplot

![image](https://github.com/stefanods4/SAT-F1/assets/153237227/b06e555b-0022-4a7a-bd4b-7326d704c4a6)

Se observa un tiempo de vuelta promedio muy similar, aunque la media de verstappen es un poco menor a la de hamilton, al igual que en el anterior, hamilton en general es mas centrado en sus tiempos.
En esta carrera, Hamilton clasifico primero y verstappen tercero. 
Observando los tiempos por vuelta de ambos corredores en la siguiente tabla podemos hacer un analisis mayor:

https://vscode.dev/github/juzimbimbakis/sat-python-oct-23/blob/clase3/F1/F1%20(1).ipynb#C41:L9
 
Una vez comenzada la carrera, antes de que termine la primera vuelta verstappen lo paso quedando primero, hamilton segundo.
Durante el primer stint se puede observar que verstappen gira en tiempos constantemente menores que hamilton, aunque la diferencia es muy poca, de entre 0.3 y 1 segundo. Puede parecer una diferencia casi nula pero al girar constantemente, durante 30 vueltas, manteniendo esta ventaja cada vuelta. le permitió a verstappen le permite alejarse de hamilton
Esto se mantuvo hasta la vuelta 29 donde Hamilton decide parar y cambiar ruedas.
Luego de esto comienza a girar en tiempos menores que Verstappen, con neumáticos ya usados, por lo que decide parar  en la vuelta 33, para evitar que se repita lo sucedido en Bahrein. Sale de los pits por delante de hamilton, otra vez marcando tiempos marginalmente menores. Manteniendo esta diferencia vuelta por vuelta, hasta el final de la carrera, ganando la misma.
Este es un claro ejemplo de cómo Hamilton tenia un mejor auto para la clasificación, pero no lo suficientemente bueno como para tener mejor ritmo de carrera que Verstappen. 
En resumen, el priorizar tener mejor ritmo de carrera, le permitió a verstappen mantenerse al frente durante toda la carrera, ganando la misma.

Analisis carrera Brasil

Analizando el siguiente boxplot:

![image](https://github.com/stefanods4/SAT-F1/assets/153237227/0589074a-0607-4f89-8e44-3dd622db1a94)

Podemos ver que de nuevo, hamilton tiene menores tiempo por vuelta promedio aunque esta vez mayor amplitud que verstappen. 

Hamilton clasifico sexto y verstappen primero.
Observando los tiempos por vuelta de ambos corredores en la siguiente tabla podemos hacer un analisis mayor:
https://vscode.dev/github/juzimbimbakis/sat-python-oct-23/blob/clase3/F1/F1%20(1).ipynb#C41:L9

En este caso existe mayor diferencia en cuanto a los set-up de los autos donde Hamilton claramente aposto a tener un auto mas preparado para la carrera, teniendo claramente un tiempo medio de vuelta inferior al de Verstappen.
Hamilton comenzó sexto, y en la vuelta 9 ya estaba tercero, con verstappen aun primero.
Durante este stint, hamilton, debido a tener que pasar autos, desgasto sus ruedas mas que verstappen pero igualmente ambos mantenían tiempos similares vuelta a vuelta, lo que nos da una idea de la ventaja de ritmo de carrera que tiene Hamilton 
Hamilton decide parar en la vuelta 26 y Verstappen para en la siguiente. En este segundo Stint, ambos con ruedas frescas, Verstappen en primer puesto y Hamilton segundo, ambos giran en tiempos muy similares. En la vuelta 38 Hamilton lo pasa a verstappen y este decide parar a cambiar neumáticos la vuelta siguiente y podemos entender que Verstappen para mantener el ritmo de Hamilton se vio obligado a desgastar sus ruedas ampliamente ya que tuvo que cambiarlas luego de usarlas solo 10 vueltas. Hamilton decide parar en la vuelta 43, habiendo hecho 17 vueltas con ese juego de neumáticos.
En el ultimo Stint Hamilton se encontraba segundo, ambos pilotos girando en tiempos muy similares. Pero Hamilton con tiempos marginalmente inferiores, acercándose a verstappen vuelta a vuelta y pasandolo en la vuelta numero 58. Una vez que lo paso Hamilton mejoro sus tiempos anteriores y Verstappen se desplomo, teniendo hacia el final un segundo de diferencia por vuelta. Mostrando claramente el desgaste en el que incurrió Verstappen para mantener los tiempos al ritmo Hamilton.

Abu Dhabi
A partir del boxplot: 

![image](https://github.com/stefanods4/SAT-F1/assets/153237227/bce93203-b47e-4991-96e8-718a233bb17a)

Podemos ver que Hamilton tiene una media menor que Verstappen y con una amplitud significativamente menor a Verstappen.

Al llegar a la carrera final, ambos corredores estaban empatados en los puntos, en el primer puesto ambos. Por lo que quien termine adelante en esta carrera sería el campeón mundial. 
clasifico primero Verstappen y segundo hamilton.
Observando los tiempos por vuelta de ambos corredores en la siguiente tabla podemos hacer un analisis mayor:

https://vscode.dev/github/juzimbimbakis/sat-python-oct-23/blob/clase3/F1/F1%20(1).ipynb#C44:L13

Hamilton lo paso a Verstappen en la primera vuelta y mantuvo durante todo el primer stint tiempos marginalmente menores a verstappen, similar a lo ocurrido en México, solo que esta vez al revés. 
Verstappen decide parar y cambiar neumáticos en la vuelta 13, mientras que Hamilton lo hace en la 14. Y en el segundo stint se repite lo mismo donde hamilton se alejaba lentamente de Verstappen y con el las chances de salir campeón para este ultimo piloto. 
En la vuelta 35 ambos pilotos vuelven a cambiar para realizar, según ellos creían, el stint final. Donde Verstappen esta vez logro hacer mejores tiempos que Hamilton pero no lo suficientemente bajos como para alcanzarlo.
En la vuelta 48 hamilton recupera su ritmo, empatando el de Verstappen, hasta la vuelta 53, Donde debido a un choque hay un safety car(auto de seguridad) y aqui se ‘’rompe’’ la carrera
Durante un safety car, los autos no tienen permitido pasarse hasta que este se termine, cuando el auto chocado sea retirado de la pista. Además todos deben girar atrás del mismo a un ritmo determinado.
Si a falta de 3 vueltas comienza un safety car, es muy probable que la carrera termine bajo el mismo, y las posiciones no se modificaran
Debido a esto Hamilton decide no cambiar ruedas debido a que si lo hacía, iba a perder la posición con Verstappen. Este último piloto decide si hacerlo ya que el piloto en el tercer puesto no lo podía alcanzar. 
En este momento, los directores de carrera deciden que la misma debe terminarse corriendo, es decir, terminar el safety car y permitir que se corra una sola vuelta. 
En este escenario, Hamilton con ruedas de 20 vueltas, no podía competir contra Verstappen, quien lo paso y se terminó consagrando como Campeón mundial


### Conclusion

Durante todo el analisis pudimos observar el alto nivel de variabilidad que existe en este deporte, muchas variables a controlar, muchas que no se pueden controlar y pueden ocasionar perder tiempo, vueltas, una carrera o hasta incluso un campeonato.
Como demostramos, constantemente los equipos y corredores de F1 buscan mejorar en las variables que pueden controlar, como en los Tiempos de PitStop, y disminuir el efecto negativo que pueden tener aquellas que no se pueden controlar. Buscando el equilibrio optimo entre el mejor tiempo de clasificacion  y el mejor ritmo de carrera. Un muy buen tiempo de clasificacion puede condenar una carrera como sucedio para Hamilton en Mexico y para Verstappen en Brasil. Tambien un tiempo medio en la clasificacion, puede permitir tener un auto mas eficaz con un ritmo de carrera que arrolle con los competidores. Y ademas demostramos como las variables que no se pueden controlar, terminan arruinando una carrera que hasta el momento habia sido excelente para Hamilton, de tal manera que todos lo planeado para que cuando algo falle, falle de manera segura, deja de funcionar, ocasionando que se pierda el campeonato.
Para concluir ver como en un torno tan competitivo y tecnologico, no existe otro deporte en el mundo donde se invierta en tecnologia como en este, existe una gran mezcla entre lo matematico con el azar del deporte. Y los equipos deben trabajar con esto, buscando aumentar las probabilidades de ganar, pero sin olvidarse que sigue siendo un deporte, y confiar siempre en estadisticas puede ocasionar sesgos que pueden costar muy caro.
