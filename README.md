# Bienvenidos a mi paso por ASIR

Me llamo Teresa Abraham, actualmente estoy en el segundo trimestre (_terminando ya_) del primer curso del Grado Superior en __Administración de Sistemas Informáticos en Red__.


Durante estos meses hemos tratado dos temas muy importantes: las consultas básicas y las consultas de varias tablas. 

A continuación encontraréis un pequeño índice con los contenidos del documento:

* [Reflexiones personales](#Reflexiones-personales)

* [Ejercicios significativos](#Ejercicios-significativos)

* [Ejercicios de invención propia](#Ejercicios-de-invención-propia)

* [Conclusiones](#Conclusiones)


## Resumen
Como he comentado al principio, hemos tratado dos temas muy importantes en las unidades 6 y 7, voy a intentar resumirlo de la mejor manera pero seguro que me quedo corta, así que ampliaré la información en el apartado de ejercicios significativos.

Empecemos por la Unidad 6 - Consultas básicas...¿Se podría resumir con la palabra __SELECT__? O-JA-LÁ.
Es mucho más que eso, pero podemos empezar por ahí: el SELECT es una instrucción DQL (es decir, de consulta) que se encuentra dentro de las DML (es decir, de manipulación), ya que estamos manipulando DATOS.

Para hacer estas consultas, a las que llamaremos básicas (_pero que de básicas tienen poco_), se necesitan muchas más opciones que nos permitirán definir más correctamente lo que estamos buscando. 

Aquí es donde entrarán las funciones.

Existen muchas funciones, que gracias a unos parámetros nos permitirán hacer consultas mucho más específicas. Existen funciones para muchas cosas, pero nosotros hemos estudiado:
1. Funciones para fechas (MONTHS_BETWEEN, LAST_DAY, EXTRACT...)
2. funciones numéricas (TRUNC, ROUND, ABS, FLOOR...)
3. Funciones de texto (UPPER, LOWER, INITCAP...)
4. Funciones de manipulación de texto (LENGHT, SUBSTR, INSTR, REPLACE...)
5. Funciones de nulos (NVL, NVL2, COLAESCE...)
6. Funciones de conversión (TO_CHAR, TO_DATE y TO_NUMBER)
7. Funciones condicionales (CASE, CAST, DECODE...)

Y lo más divertido... Las expresiones regulares como REGEXP_LIKE, REGEXP_COUNT, REGEXP_INSTR y REGEXP_REPLACE.

Y justo cuando parece que ya vas pillándolo todo, empiezas a controlar las expresiones regulares, parece que las funciones te facilitan la vida y no al revés... 

Entonces llega la Unidad 7 - Consultas de varias tablas. Esta si que se puede resumir con una palabra, y es __JOIN__. Si con una tabla ya nos costaba, imagínate con dos... O tres... O cuatro... 

Bueno, pues eso, que ahora podremos ver datos de distintas tablas en una misma consulta, y es algo que te puede arreglar la vida (si lo entiendes, si no... te la va a complicar).
Se juntarán datos de distintas tablas gracias a las Foreign Keys, es decir, datos que se relacionan (son iguales) en ambas tablas. 

Existen varias formas para crear esta relación pero se podría resumir en:
- Si la columna se llama igual en ambas tablas se usará __JOIN USING__ (nombredelacolumna)
- Si la columna se llama diferente en las tablas se usará __JOIN ON__ (columna1=columna2)

Con el JOIN se mostrarán los datos COINCIDENTES, es decir que tanto de una tabla como en la otra COINCIDAN. Vamos, que los nulos no aparecen, y, si queremos que aparezcan tendremos que usar __LEFT o RIGHT OUTER JOIN__, que permitirá mostrar los datos que no coinciden (por ejemplo, en una base de datos en la que se tienen los ALUMNOS y las EMPRESAS donde hacen prácticas, habrá alumnos que no están en ninguna empresa, y empresas que no tienen alumnos, por lo que si se quieren ver los que no coincidan se usará el OUTER).

Y aquí es donde el JOIN se complica, porque aunque podamos comparar datos de varias tablas, si queremos comparar una fila con otra... no podemos. Para eso se tiene que duplicar la tabla, ponerla al ladito y crear una fila suuuuuper larga que si podremos comparar. A esto se le llama __CROSS JOIN__.

Por último tenemos las __CONSULTAS DE TOTALES__ que permitirán hacer cálculos en vertical, podremos sumar toda la columna o contar todas las filas, por ejemplo.

En las consultas de totales entrarán en juego una nueva forma de ver las columnas, ya que se podrá:
- Sumar toda la columna, solo válido para numeros, con SUM(columna).
- Contar las filas de una columna concreta o de todas (*), con COUNT(columna).
- Calcular la media de todas las filas de la columna, con AVG(columna).
- Comparar todas las filas y sacar el máximo o el mínimo, con MAX(columna) o MIN(columna).

Pero ¿qué pasa?, que el resultado de estas consultas "junta" filas, por lo que los datos del resto de columna también se tendrán que "juntar", o más bien agrupar, y aquí interviene la cláusula GROUP BY.

Por último, como ya hemos visto anteriormente, para filtrar datos se usa la cláusula WHERE, pero para las consultas de totales existe una especial, es la de __HAVING__, que permitirá añadir condiciones y/o comparaciones.

Y aunque este punto se titula "Resumen", tiene de resumen lo que las consultas básicas tienen de básico... POQUITO.

## Reflexiones personales
Aunque por el resumen anterior puede parecer que los temas tratados este trimestre son muy complicados, personalmente tengo que decir que, creo que este trimestre GBD está siendo mi asignatura favorita...

Siempre me ha parecido un tema muy interesante el de las consultas, aunque no lo había visto desde este lado. Cuando navego por páginas me gusta cotillear __los filtros de búsqueda__ que tienen, y ahora cuando estoy haciendo consultas a veces me imagino cómo será la consulta que está ejecutando una página para mostrarme los "vestidos de color negro", _¿será un WHERE TIPO_PRENDA='Vestido' AND COLOR='negro'?_

La asignatura, en general me encanta, siento que me __estimula intelectualmente__, y me hace pelearme con Oracle y volver a empezar, pero cuando los ejercicios me salen, y me doy cuenta de que mi cabeza ya sabe cómo comunicarse con él, me genera una __satisfacción__ y una sensación muy agradable.

Resumiría esta asignatura como __un reto__, puede ser algo bueno o malo, depende de cómo la quiera afrontar cada uno.

## Ejercicios significativos
Para ampliar la información del resumen (_que yo creo que me he quedado corta_), se mostrarán algunos ejercicios para ver de forma práctica de los temas comentados.

Todos ellos forman parte de las prácticas hechas en clase, y corregidas. He decidido exponer ejemplos de dos esquemas únicamente (Geografía y PadreMadre), me parece que se puede entender mejor que si uso ejercicios de esquemas que ni se parecen. 

### JOIN USING
El JOIN USING se utiliza para unir datos de dos tablas que se relacionan con una columna que tiene el mismo nombre en ambas tablas.

En este caso, el enunciado del __ejercicio 9 de la práctica 18 (Geografía)__, se pedía mostrar el nombre de las localidades que NO sean capitales de provincia.
Para eso, se mostrará el nombre de las __localidades y provincias__, para poder compararlos, y para poder mostrarlos en la misma consulta se unirán los datos de ambas tablas Localidades y Provincias, que se relacionan a través de la columna n_provincia.

Tras eso, se compararán los identificadores, la localidad no puede coincidir con la capital de la provincia, y por eso se buscarán las localidades que NO sean capitales.


![Ejercicio JOIN](Ejercicios/JOIN%20EJ9%20P18.png)


### CROSS JOIN
El CROSS JOIN se utiliza para comparar datos de distintas filas en una misma tabla, duplicará esta tabla y cruzará los datos de una y otra, permitiendo comparar distintas filas de una misma tabla.

Se trata del __ejercicio 11 de la práctica 18 (Geografía)__ , que pide mostrar las CCAA que tiene el mismo tamaño de letras en el nombre.
Para poder comparar los nombres de las CCAA se tendrá que "duplicar" la tabla, para asi cruzar todas las filas de ambas tablas, es entonces cuando se usará el CROSS JOIN. Al tratarse de la misma tabla se las denominará C1 y C2, y se extraerá el nombre (de la CCAA) de cada una de ellas.

Tras eso, para comparar la longitud del nombre se hará en la cláusula WHERE, usando como condición la función de LENGTH y además, excluyendo que se compare el nombre de la CCAA consigo mismo.


![Ejercicio_CROSSJOIN](Ejercicios/CROSS%20EJ11%20P18.png)

### LEFT OUTER JOIN
El LEFT OUTER JOIN se utiliza para, en una consulta de varias tablas, obtener además de los datos coincidentes, los que no tienen coincidentes en la tabla a la IZQUIERDA del JOIN.

En el __ejercicio 3 de la práctica 19 (PadreMadre)__ se pedía mostrar el nombre de los hijos, su padre y su madre, y además que se muestren las personas que no tienen un padre o madre en la base de datos. Se trata de una base de datos con una relación recursiva, ya que una persona puede ser hijo/a y padre/madre a la vez.
Para eso, en primer lugar se mostrarán a todas las personas (serán los hijos) de la base de datos, y a través de ellos se unirá con la propia tabla para mostrar al padre y a la madre (se hará con un JOIN ON, ya que el nombre de la columna que les une es distinto).

Con eso se mostrarán las coincidencias, pero como además se necesita sacar a los hijos que no tienen padre y/o madre, es cuando entrará en jeugo el LEFT OUTER que se añadirá antes de ambos JOIN, ya que se requiere que aplique a la tabla de la izquierda del JOIN (es decir, la de los hijos).


![Ejercicio_LEFTOUTER](Ejercicios/LEFT%20OUT%20EJ3%20PR19.png)

### Consulta de totales (COUNT)
En el __ejercicio 7 de la práctica 19 (PadreMadre)__ se pedía una consulta para saber las madres que han tenido hijos con padres distintos.

Para esto entrará en juego el COUNT que usado con (*) contará filas. Para este ejercicio, en primer lugar se ha hecho una consulta de padres y madres y cuántos hijos tienen en común. Sobre esa consulta se ha hecho exactamente lo mismo, pero en vez de contar hijos, se han contado olos padres, por lo que como resultado se obtendrá el nombre de las madres y el número de padres con los que han tenido hijos.

En este caso, además, se ha añadido como condición que sea superior a uno (es decir, más de un padre).

![Ejercicio_CONSTOT](Ejercicios/COUNT%20EJ7%20PR19.png)

### HAVING
Aunque ya se ha visto en la anterior consulta, en esta nos centraremos en el HAVING para encontrar el nombre de las madres que hayan tenido 2 hijas, se trata del __ejercicio 5 de la práctica 19 (PadreMadre)__.

En este caso se tendrá que consultar primero el nombre de las personas que son madre, y se comparará con la misma tabla en la que aparecerán los hijos (que también se filtrará a través de la columna sexo, para que únicamente aparezcan hijas). Se agrupará por el nombre de la madre y se contarán las filas resultantes de esta columna (es decir, número de hijas).

Por último, y la parte importante, se pide que tengan 2 hijas. Para eso se tendrá que condicionar el resultado del COUNT y es donde entra en juego la cláusula HAVING, que es como el WHERE pero para consultas totales, y se señalará que este COUNT tiene que ser IGUAL a 2.

![Ejercicio_HAVING](Ejercicios/HAVING%20EJ5%20PR19.png)

## Ejercicios de invención propia
Dos ejercicios propios: enunciado y solución

## Conclusiones
Principales dificultades
Durante el curso me han surgido algunas dificultades, pero en el buen sentido, porque me han motivado a seguir esforzándome. Creo que la máxima dificultad fue el exámen de Consultas de una tabla, porque yo creía que lo llevaba bastante bien, no tenía problemas en las prácticas pero en el exámen me bloquee, y me frustró bastante, sentí que se me hacía muy difícil.


Qué es lo que mas me ha gustado, y lo que menos
