# Lenguajes de Marcas Ligeros

Como ya vimos en el tema anterior, los lenguajes de marcas ligeros[^lightml] son lenguajes de marcas para formatear documentos diseñados, en principio, para simplificar el proceso de codificar documentos en HTML o XML. 

Tras ver una introducción de Wiki Markup, el lenguaje de marcas de Wikipedia, vamos a centrarnos en Markdown.[^markdown]

# Markdown

Markdown es un lenguaje de marcas ligero que recientement ha adquirido mucha popularidad como lenguaje de marcas en blogs (Wordpress[^wordpress] lo utiliza por defecto) y como lenguaje para la documentación de proyectos de software libre.

- Es un lenguaje de marcas sencillo que es fácilmente traducible a distintas versiones de HTML o a PDF.

- La principal ventaja es que permite teclear y formatear rápidamente el texto.

- Ojo, como pasaba con Wiki Markdown, no hay programas que interpreten Markdown directamente: es necesario *transformarlo* previamente a formatos de visualización. Sin embargo, el código es perfectamente legible desde cualquier editor de texto.


## Funcionalidades de Markdown

La sintaxis de Markdown[^markdown-syntax] permite fácilmente:

- Estructurar el texto en epígrafes, párrafos, bloques de texto.

- Modificar ligeramente la apariencia del texto: cursivas, negritas, etc.

- Insertar hipervínculos.

- Insertar imágenes.

- Organizar la información en listas de elementos, listas ordenadas, tablas, etc.

Veamos cómo hacerlo.


## Epígrafes y párrafos

Los títulos se marcan con el símbolo de la almohadilla (\#): una almohadilla para títulos de primer nivel, dos para titulos de segundo nivel, etc.

    # Título de primer nivel
    
    ## Título de segundo nivel

    ##### Título de quinto nivel

Los párrafos no se marcan explícitamente. Cualquier conjunto de líneas de texto seguidas será considerado un párrafo. Para separar párrafos, es necesario introducir doble retorno de carro (doble *intro*).

    Lorem ipsum ad his scripta blandit partiendo, eum fastidii accumsan euripidis in...

    Ius id vidit volumus mandamus, vide veritus democritum te nec...

## Apariencia del texto

El texto en *cursiva* se encierra entre asteriscos o guiones bajos:

    Este texto está en *cursiva* y _este también_. 

El texto en **negrita** se encierra entre dobles asteriscos o dobles guiones bajos: 

    Este texto está en **negrita** y __este también__. 
    
Si es necesario formatear texto a la vez en ***Negrita y cursiva*** podemos encerrarlo entre tres pares de asteriscos o apóstrofos: 

    Este texto está en ***requete marcado***. ___Este también___.


Para añadir pequeñas porciones de texto sin formato, que habitualmente aparecen con fuente de ancho fijo, podemos encerrarlo entre acentos graves:

    Este texto `no tiene formato`.
  
Si necesitamos incluir más de una línea de texto sin formato, es más cómodo sangrar el texto.

## Listas no ordenadas

Las listas no ordenadas se especifican añadiendo al principio de cada elemento guiones (`-`), asteriscos (`*`) o símbolos de suma (`+`). 

No se marcan el inicio y el final de la lista. Las listas también se pueden anidar, sangrando el texto.

    Lista de la compra:

    - tomates

      - pera

      - cherry

      - raf

    - pepinos

    - patatas


## Listas ordenadas

Las listas ordenadas se especifican añadiendo al principio de cada elemento cualquier número seguido de un punto (`.`). Cualquier número, no necesariamente tienen que estar ordenados. El resultado visual va a ser una lista ordenada numéricamente.

No se marcan el inicio y el final de la lista.

    Pasos a seguir para levantarse por las mañanas:

    1. Abrir un ojo.

    2. Abrir el otro.

    8. Saltar de la cama.


## Hiperenlaces

En general, los enlaces se especifican encerrando el texto del enlace entre corchetes e incluyendo el destino al que apunta el enlace entre paréntesis.

    Este texto contiene un [enlace a la web de la UCM](http://www.ucm.es)

Podemos incluir, de manera opcional, un título al enlace. 
  
    Este texto contiene un [enlace a la web de la UCM](http://www.ucm.es "Universidad Complutense de Madrid")
  
También es posible crear enlaces automáticos sobre URLs o direcciones de correo-e, encerrándolos entre paréntesis angulares (`<>`).

    Para más información, visita <http://www.ucm.es> o escribe un mensaje a <info@ucm.es>.

## Imágenes

La sintaxis general para insertar imágenes es similar a la de los enlaces: entre corchetes ponemos un texto descriptivo de la imagen y entre paréntesis la ruta al fichero que contienen la imagen.

    ![Texto alternativo](ruta_a_la_imagen)

    ![Texto alternativo](ruta_a_la_imagen "Título Opcional")


## Tablas

Para formetar tablas podemos utilizar guiones `-` y barras verticales `|` para indicar dónde comienzan y dónde terminan las columnas. Las filas se especifican en líneas diferentes, una detrás de otras. Además, podemos elegir la justificación del texto de las columnas, insertando símbolos de dos puntos `:`. 

Veamos un ejemplo, que es lo más ilustrativo. El código siguiente:

    |--------|----------|:----:|---------:|
    | Nombre | Apellido | Edad | Teléfono |
    | Pepe   | Schmidt  |  23  | +34 62222222 |
    | Anne   | Sánchez  |  66  | 800 23 23 23  |
    | Juan Froilán | De Todos los Santos  | 17 | (310) 555 2323 |
    | John   | Connor  | 42 | 02.112233 |


Se visualiza:

|--------|----------|:----:|---------:|
| Nombre | Apellido | Edad | Teléfono |
| Pepe   | Schmidt  |  23  | +34 62222222 |
| Anne   | Sánchez  |  66  | 800 23 23 23  |
| Juan Froilán | De Todos los Santos  | 17 | (310) 555 2323 |
| John   | Connor  | 42 | 02.112233 |



## Bloques de texto

Los bloques de texto se marcan con el símbolo `>`, de manera similar a la de muchos programas de correo.

    A continuación voy a escribir citar un texto:

    > Esto es una cita anónima de dos líneas.

    > Esta es la segunda línea


Los bloques de texto citados pueden anidarse. 

    > Esto es una cita de primer nivel.

    > > Esta es la segunda línea, que aparece anidada.

    > Y volvemos a subir al primer nivel.


## Bloques de código

Para escribir bloques de código de programación o, en general, texto escrito en fuente de ancho fijo, encerramos el texto entre acentos graves (\` \`).

    En UNIX, el comando para listar el contenido de un directorio

    es `ls`. En Windows el comando equivalente es `dir`.


## Caracteres escapados

Hemos visto que Markdown usa algunos símbolos como metacaracteres, con significados concretos.

Si necesitamos insertar cualquiera de estos símbolos es preciso *escaparlos*, es decir, incluirlos precedidos de una barra invertida `\`.

    \\ \` \* \_ \{ \} \[ \] \( \) \# \+ \- \. \!


# Ejercicio

Para practicar con Markdown tenemos el wiki en Github[^wikigithub] y un blog en Wordpress[^lmblog]. En esta segunda práctica, vamos a crear una entrada con contenido lingüístico.

1. Edición en Markdown en el wiki: 

  - Para poder editar el wiki, ya sabes que necesitas crearte una cuenta de usuario en Github[^github]. 

  - Añade una página (haz clic en **New Page**) y elige el título: para que pueda identificar la página de cada uno, vamos a seguir la siguiente convención: titula la página con tu apellido y la primera letra de tu nombre. Si te llamas Pepito Pérez, llama a tu página `perezp-ling`. 

  - Configura el modo de edición como **Markdown** y elabora una página con contenido lingüístico demostrando que eres capaz de manejarte con las reglas de sintaxis básicas de Markdown. 

  - A medida que vayas añadiendo información, previsualiza el resultado final pulsando en **Preview**. Vuelve a **Write** para seguir editando. 

  - Si necesitas almacenar una copia, añade un pequeño mensaje explicando los cambios y haz clic en **Save Page**.


2. Edición en Markdown en el blog:

- Para poder editar entradas en el blog, necesitas crearte (si no la tienes) una cuenta de WordPress[^wordpress] y enviarme un correo con tu nombre de usuario, para que pueda invitarte como *autor*/*editor*.

- Una vez logueado en Wordpress, puedes añadir una nueva entrada de varias maneras (haz clic en *Create a new post* o en *Blog post > Add*) y comienza a editar. Recuerda que puedes (y debes) formatear tu entrada en Markdown.

- Cuando hayas terminado, asegúrate de que todo está a tu gusto, publica tu entrada y avísame enviándome un mensaje de correo-e.


[^wikigithub]: https://github.com/vitojph/2015lmweb/wiki

[^github]: https://github.com/

[^lightml]: Lightweight Markup Language http://en.wikipedia.org/wiki/Lightweight_markup_language

[^markdown]: Markdown http://es.wikipedia.org/wiki/Markdown

[^markdown-syntax]: Sintaxis de Markdown http://daringfireball.net/projects/markdown/syntax

[^wordpress]: https://www.wordpress.com

[^lmblog]: https://2015lmweb.wordpress.com
