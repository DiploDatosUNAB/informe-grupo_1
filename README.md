# Trabajo práctico 1

En esta primera entrega van a familiarizarse con los datos que eligieron y plantear algunas preguntas para responder en una segunda entrega.

## Entrega

La entrega consiste en el repositorio completo en un estado en el que el archivo .Rmd del informe corre sin errores y genera el archivo .html.

Para entregar el TP, hay que ir a la actividad de entrega en [la solapa TP1](https://campus.unab.edu.ar/course/view.php?id=553&section=5#tabs-tree-start) y copiar el link al commit específico que quieran entregar.

Un link a un commit se ve así: <https://github.com/DiploDatosUNAB/intro_programacion-TP1/commit/36ef70888c0ad7f7851804d9b0d4dea2016eaad5>, y es una URL específica al estado del repositorio correspondiente a ese commit.

Para ver a URL pueden hacer click en estos números en el repositorio de GitHub

![](https://i.imgur.com/irgSUf4.png)

Y en el explorador van a ver la URL correspondiente.

![](https://i.imgur.com/w44Honh.png)

Esta URL es la que tienen que poner en la actividad de entrega en el campus.

Cualquier cambio que realicen *luego* de la entrega no va a ser evaluado y quedará para la próxima entrega.

El estado del repositorio tiene que ser coherente; el archivo .html tiene que coincidir con el archivo .Rmd.
Es decir, asegúrense de *knitear* la última versión del el archivo .Rmd y subir todo al repositorio.
No cambien el archivo .Rmd sin actualizar también el archivo .html y subirlo al repositorio.

Todo el código reportado en el documento final del proyecto debe correr sin errores.
Por favor, no incluyan ningún código extraño o que produzca mensajes de error (el código que produce advertencias es aceptable, siempre y cuando entiendan lo que significan las advertencias).

## Instrucciones

### Datos

Guardá los datos en la carpeta "datos" (salvo que uses datos que vienen en algún paquete).

Si los datos son demasiado pesados para GitHub (que tiene un límite de 100Mb por archivo), comenten en el campus y vemos cómo hacer para que el código funcione igual.

### Informe

Usen la plantilla R Markdown provista para completar su informe.
La misma tiene las secciones marcadas y algunos bloques de código ya creados, pero pueden (deben!) hacer más bloques.

Esta primera entrega práctico va a tener tres secciones:

**Introducción**

Esta sección consiste en entre 2 y 3 párrafos describiendo los datos.
Qué decir sobre los datos dependerá de los datos elegidos pero algunos detalles posibles son:

-   ¿Qué datos son?
-   ¿De dónde provienen? ¿Quién los tomó?
-   ¿En qué período se tomaron?

En general, cualquier detalle que crean relevante para que alguien sin acceso a los datos se haga una buena idea de los mismos.

Esta sección no necesita tener código de R.

**Exploración de los datos**

Esta sección es una primera exploracion de los datos.
¿Qué variables tiene?
¿Cuántas observaciones hay?
¿Cuántas variables?

Seleccioná algunas variables resulten interesantes y mostrá sus propiedades.
Algunas cosas para mostrar:

-   ¿Cuál es su valor medio y desvío estándard?
-   ¿Cuál es su rango (valor máximo y valor mínimo)?
-   ¿Hay alguna anomalía que sugiera que hay datos incorrectos? Valores imposibles (como valores negativos en una variable que sólo puede ser positiva) o poco creíbles.
-   ¿Cuántas observaciones hay por cada grupo? ¿Cuántos valores faltantes? ¿Hay diferencias?

Esta sección sí tiene que tener código de R.

Los resultados del código tienen que estar acompañados de un texto que los describa y que elabore sobre los mismos.
Es decir, no sólo repetir lo que se ve, sino también comentar sobre su significado en el contexto de estos datos.
No hace falta que sean párrafos largos; cada uno no debería tener más de 5-6 frases.

**Todos** los resultados presentados deben tener su código correspondiente.
Cualquier respuesta/resultado presentado sin el correspondiente código R que generó el resultado no se considerará.
Para ser claros: no reporten cosas en el documento que calcularon a mano o miraron por fuera de R (por ejemplo, si cuentan la cantidad de filas, tiene que estar elcódigo que cuenta la cantidad de filas).

Es muy posible que tengan ganas de hacer algún cálculo y que no sepan cómo hacerlo en R.
¡En ese caso es mejor que consulten en el foro en vez de quedarse con las ganas!

**Hipótesis**

Finalmente, esta sección contiene **al menos 3** hipótesis o preguntas que puedan ser respondidas a partir de los datos.
Éstas tienen que ser más o menos interesantes y no cosas que se hayan respondido con la exploración anterior.

Traten de que sean hipótesis o preguntas que relacionen 2 o más variables.
Por ejemplo, "¿Cuál es el mes con más turistas en una región?" no es una pregunta intersante, pero "Existe una relación entre la cantidad de visitas y la cantidad de hoteles en una región" es una hipótesis más jugosa que apunta a la relación entre varias variables y a un fenómeno subyacente que puede tener implicancia y aplicaciones.

**No tienen que responder** estas preguntas en esta entrega.

## Consejos

El archivo Consejos.md tiene algunos errores comunes para evitar que surgieron en ediciones anteriores.
