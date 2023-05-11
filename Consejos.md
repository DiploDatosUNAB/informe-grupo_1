Estos son algunos errores comunes a evitar.

### Rutas de archivo absolutas

**No** usar rutas de archivo absolutas para leer archivos.
Si tu código tiene algo como esto:

``` r
datos <- read_csv("C:/Usuarios/Pepito/Documentos/Diplomatura/intro a la computacion/tp1/datos/mis-datos.csv")
```

Esto en princpio sirve porque esto corre bien en la computadora de quién lo escribió, pero vos que estás leyendo pensá qué pasa si esta persona les pasa el archivo y tratan de correrlo.
La probabilidad de que tengas un archivo en "C:/Usuarios/Pepito/Documentos/Diplomatura/intro a la  computacion/tp1/datos/mis-datos.csv" en nula!
Entones, imaginate qué pasa si tratás de correr esa línea de código.
No corre.

¿Cuál es la solución?

Lo que hay que hacer es, en vez de poner toda la ruta completa "C:/Usuarios/Pepito/Documentos/Diplomatura/intro a la computacion/tp1/datos/mis-datos.csv", sólo poner la ruta relativa "datos/mis-datos.csv".
Entonces, si mi proyecto está en "C:/Usuarios/Pepito/Documentos/Diplomatura/intro a la computacion/tp1", entonces la línea

``` r
datos <- read_csv("datos/mis-datos.csv")
```

va a buscar el archivo "mis-datos.csv" que está adentro de la carpeta "datos" que está adentro del proyecto desde donde estoy ejecutando el código.
Ahí está la gracia de trabajar con proyectos!
Si ahora esta persona te pasa todo su proyecto (la carpeta que está en "C:/Usuarios/Pepito/Documentos/Diplomatura/intro a la computacion/tp1"), vos podés poner ese proyecto donde se te cante en tu computadora y va a correr igual, porque sin importar dónde está esa carpeta en tu computadora, adentro de esa carpeta va a haber una carpeta "datos" y adentro de esa carpeta va a haber un archivo "mis-datos.csv".

## Código que se usa para trabajo interactivo

Hay ciertas líneas de código que uno usa cuando está explorando y que nos ayudan a armar el código, pero que no son parte del código terminado.

`View(datos)` abre una previsualización de los datos en RStudio, pero no hace nada con los datos ni muestra un resultado en el archivo Rmd.
Sirve para facilitar el trabajo interactivo pero no tiene rol en la programación.
Por lo tanto, **`View(datos)` no tiene que aparecer nunca en un código**.

Lo mismo pasa con el código para abrir la ayuda (por ejemplo `?vuelos`).
Eso lo que hace es abrir la ayuda en RStudio, pero no muestra nada en un archivo .Rmd.
Tampoco tiene que estar en el código.

`install.packages("paquete")` instala un paquete en la computadora. 
Es algo que se hace una sola vez, no cada vez que quiero generar una salida a partir de un .Rmd.
Entonces, tampoco tiene que aparecer en el código.
Si le das a alguien un proyecto con un .Rmd que tiene que generar una salida, vos no sos responsable de instalarle los paquetes necesarios para correrlo.
Que esa persona se arregle (hay formas de especificar los paquetes necesarios para un análisis y que se instalen automáticamente, pero es algo avanzado que no vimos ni vamos a ver).

## Descarga o "pre-filtrado" de datos pesados

Es posible que tengas que trabajar con tablas bastante grandes que tardan mucho en leerse pero sobre las cuales después sólo te quedás con una parte.
Por ejemplo, quizás leés datos de COVID de todo el país pero luego te interesa ver datos de una provincia, entonces tu código descarta la gran cantidad de los datos que acaba de leer.

También es posible descargar lo datos automáticamente desde R, pero los datos pueden ser muy pesados y todo el proceso tarda mucho.

En ambos casos, tener un primer bloque de código en el archivo .Rmd que haga todo eso cada vez que *kniteamos* el archivo se vuelve tedioso porque hace que el proceso tarde mucho.
¿No estaría bueno poder correr ese primer paso una sola vez?

Una forma de hacer eso es que el paso de filtrado o descarga de datos esté en otro archivo (un archivo .R) que no produzca un reporte, sino que genere un archivo .csv "limpio".
Luego, el archivo .Rmd que genera el reporte lee ese archivo más chico y no el archivo grande.

Por ejemplo.
Si te interesara analizar datos de covid de Córdoba, pero tenés un csv con los datos nacionales.
Armarías un archivo llamado "filtrar_datos_cordoba.R" con estas líneas

```r
library(readr) 
library(dpyr) 
datos_todos <- read_csv("datos/covid_argentina.csv")

datos_cba <- datos_todos |> 
   filter(provincia == "Córdoba")

write_csv("datos/covid_cordoba.csv")
```

Y listo.
Corrés este archivo una única vez y entonces vas a tener un archivo llamado "covid_cordoba.csv" que es mucho más chico y se lee rápido.
Luego, en tu archivo "reporte_cordoba.Rmd" tu primer bloque leería sólo los datos de córdoba con

```r
library(readr) 
datos <- read_csv("datos/covid_cordoba.csv") 
```

Y luego seguirías con el análisis de los datos de Córdoba.
