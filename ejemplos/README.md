# Ejemplos de HTML y CSS

**Módulo 1 · Clase 6**

Abrí los archivos HTML en el navegador y mirá su código fuente en el editor. Cada página se puede abrir directamente y trae sus propios estilos cuando los necesita.

## Un poco de historia

A fines de 1990, Tim Berners-Lee ya tenía en funcionamiento el primer servidor y el primer navegador de la Web en el CERN. La primera página reunía texto y enlaces que explicaban el proyecto World Wide Web. [Historia de la Web en el CERN](https://home.cern/science/computing/the-birth-of-the-web/short-history-web/) · [Primera página](https://info.cern.ch/hypertext/WWW/TheProject.html)

HTML 2.0 documentó los formularios en 1995 y el W3C publicó la primera recomendación de CSS en 1996. Más adelante, CSS pasó a desarrollarse en módulos con sus propios niveles, como los de fondos y bordes, transformaciones y transiciones. [HTML 2.0, sección de formularios](https://www.rfc-editor.org/rfc/rfc1866.html#section-8) · [CSS nivel 1](https://www.w3.org/TR/REC-CSS1/) · [Panorama de CSS del W3C](https://www.w3.org/TR/css/#intro)

## Índice

1. [HTML de los primeros días de la Web](01-html-primeros-dias.html) recrea el estilo de una página temprana con encabezados, párrafos, una lista y enlaces. Usa una estructura HTML actual para que puedas abrirla en tu navegador.
2. [Texto con CSS básico](02-css-basico.html) presenta el mismo contenido con una hoja de estilos dentro de `<style>`. Compará la tipografía, los colores, los márgenes y el interlineado con el primer archivo.
3. [Formulario básico](03-formulario.html) muestra cómo asociar las etiquetas con los campos mediante `for` e `id`. Probá enviar el formulario vacío o con un correo inválido para observar la validación del navegador. Con datos ficticios válidos, el envío por `GET` recarga la página y agrega a la URL los valores identificados por `name`. La demostración funciona sin un servidor que procese los datos.
4. [Características de CSS3](04-css3.html) combina un degradado, bordes redondeados y una sombra. Pasá el cursor sobre el enlace o seleccionalo con `Tab` para ver cómo una transición suaviza su desplazamiento.
5. [Grilla de 12 columnas con Flexbox](05-grilla-flexbox.html) divide una fila en 12 partes iguales y muestra combinaciones de 8 + 4, 6 + 6 y 4 + 4 + 4. Cada ancho equivale a la cantidad de columnas que ocupa dividida por 12. Achicá la ventana a 600 píxeles de ancho o menos para ver cómo se apilan los bloques de contenido.
6. [Grilla de 12 columnas con CSS Grid](06-grilla-css-grid.html) reproduce las mismas combinaciones. `grid-template-columns` define 12 columnas iguales y `grid-column: span 8`, por ejemplo, indica que un bloque ocupa ocho de ellas. A 600 píxeles de ancho o menos, cada bloque de contenido ocupa las 12 columnas.
