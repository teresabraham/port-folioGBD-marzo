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

Todos ellos forman parte de las prácticas hechas en clase, y corregidas. 

### JOIN, ON y/o USING


### CROSS JOIN

### LEFT OUTER JOIN

### SUM, AVG, COUNT, MAX o MIN

### HAVING

## Ejercicios de invención propia
Dos ejercicios propios: enunciado y solución

## Conclusiones
Principales dificultades
Qué es lo que mas me ha gustado, y lo que menos
