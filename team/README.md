# Clase 7 · Tu ficha en el Equipo de Desarrollo

Te propongo que agregues tu ficha a la página del equipo de la cursada y después armes una página de perfil. Preparé tres fichas ficticias para que tengas un punto de partida. Trabajá a tu ritmo. En cada paso te indico cómo comprobar que salió bien antes de seguir.

## 1. Entrá al repositorio del curso

Te pido que abras una terminal en la carpeta donde guardás tus proyectos. Si todavía no tenés una copia del repositorio, ejecutá estos comandos. El primero descarga el repositorio en una carpeta llamada `sitio-web` y el segundo entra a esa carpeta.

```bash
git clone https://github.com/alezvi/icaro-102026-1.git sitio-web
cd sitio-web
```

Si ya lo clonaste, abrí la terminal directamente en tu carpeta `sitio-web`. Te voy a pedir que ejecutes los demás comandos desde ahí, en la raíz del repositorio.

**Para comprobarlo**, ejecutá `git status --short --branch`. La primera línea empieza con `##` y muestra el nombre de tu rama. Si Git indica que no encontró un repositorio, revisá en qué carpeta abriste la terminal. Si debajo de la rama aparecen archivos, consultame cómo guardar esos cambios antes de continuar.

## 2. Cambiá a la rama del ejercicio

Cuando publique la rama de la clase, te pido que ejecutes estos comandos de a uno. Con el primero, Git actualiza la información que tiene de `origin`, el repositorio remoto que clonaste. Con el segundo, crea tu copia local de la rama y cambia a ella.

```bash
git fetch origin
git switch --track origin/clase-07-agenda-contactos
```

Si ya tenés esa rama en tu copia local, usá `git switch clase-07-agenda-contactos` en la segunda línea.

**Para comprobarlo**, ejecutá `git branch --show-current`. Espero que veas `clase-07-agenda-contactos`.

### Abrí la página del equipo con Live Server

Te pido que abras la carpeta `sitio-web` en VS Code desde **Archivo → Abrir carpeta**. Si todavía no tenés Live Server, abrí la vista **Extensiones**, buscá **Live Server** de Ritwick Dey e instalala. En el explorador de VS Code, buscá `agenda-contactos/index.html`, hacé clic derecho sobre el archivo y elegí **Open with Live Server**. [Extensión Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)

**Para comprobarlo**, fijate que el navegador muestre una dirección que empiece con `http://` y termine con `/agenda-contactos/index.html`. Deberías ver las tres fichas de ejemplo, entre ellas la de Cosme Fulanito. Dejá Live Server abierto mientras trabajás.

## 3. Creá tu rama de trabajo

Quiero que guardes tu ficha en una rama propia. En el siguiente comando, reemplazá `nombre-apellido` por los tuyos, con minúsculas, guiones y sin tildes. Si usáramos el nombre de ejemplo, la rama se llamaría `ficha/cosme-fulanito`. La opción `-c` crea la rama y cambia a ella en el mismo paso.

```bash
git switch -c ficha/nombre-apellido
```

**Para comprobarlo**, ejecutá `git branch --show-current` y revisá que aparezca tu rama con el prefijo `ficha/`. Si ya la habías creado para este ejercicio, entrá con `git switch ficha/nombre-apellido`, usando tu nombre de rama.

## 4. Completá tu ficha

Te pido que prepares tu foto o avatar, tu nombre, una síntesis de lo que contaste en la primera clase y la ciudad desde donde te conectás.

1. Copiá tu imagen a `images/avatars/`. Poné tu nombre y apellido en minúsculas, con guiones y sin tildes. Conservá la extensión real del archivo. Por ejemplo, `cosme-fulanito.jpg` para un JPG o `cosme-fulanito.png` para un PNG.
2. Abrí `agenda-contactos/index.html` en tu editor. Copiá una ficha completa, desde `<li class="contacto">` hasta su `</li>`, y pegala al final de la lista, justo antes de `</ul>`. Hacé los cambios en esa copia.
3. Dentro del `<h2>` de tu ficha, dejá tu nombre como texto. Si copiaste la ficha de Cosme, reemplazá todo lo que hay entre `<h2>` y `</h2>` por tu nombre. Debajo, escribí una o dos frases sobre tu presentación y actualizá la ciudad, por ejemplo, «Desde Rosario». Más adelante vas a enlazar tu propio perfil.
4. Reemplazá el `<span>` de las iniciales por una imagen como esta. Cambiá `cosme-fulanito.jpg` por el nombre exacto de tu archivo, incluida la extensión. La ruta empieza con `../` porque el HTML está dentro de `agenda-contactos` y debe subir un nivel para llegar a `images`. En este caso, `alt=""` sirve porque tu nombre ya se lee junto a la imagen.

```html
<img class="avatar" src="../images/avatars/cosme-fulanito.jpg" alt="">
```

**Para comprobarlo**, guardá el HTML, recargá la página del equipo y buscá tu ficha al final de la lista. Debería mostrar tu foto, tu nombre en negrita, la síntesis y la ciudad. Achicá la ventana y fijate si podés leer todo. Si la imagen no carga, compará el nombre y la extensión que pusiste en `src` con el archivo que guardaste en `images/avatars/`.

## 5. Guardá el primer commit

Primero, quiero que revises qué cambió en la página del equipo y elijas qué archivos va a guardar Git. Desde `sitio-web`, ejecutá estos comandos. En `git add`, reemplazá el nombre de la imagen de ejemplo por el de tu archivo.

```bash
git diff -- agenda-contactos/index.html
git add agenda-contactos/index.html images/avatars/cosme-fulanito.jpg
git diff --cached --name-only
```

En la primera salida deberías reconocer el HTML de tu ficha. Si Git abre una vista que termina con `(END)`, presioná `q` para volver a la terminal. En la última salida deberían aparecer dos rutas, la de `index.html` y la de tu avatar. Cuando estén esas dos, te pido que hagas el commit.

```bash
git commit -m "Agrega mi ficha al equipo"
git log -1 --oneline
git status --short --branch
```

**Para comprobarlo**, buscá el mensaje `Agrega mi ficha al equipo` en el historial. En el estado, la primera línea debería indicar tu rama `ficha/...` y, si ya guardaste todo lo que editaste en este paso, no habrá archivos debajo.

## 6. Desafío individual de HTML y CSS

Ahora te propongo agregar tres intereses debajo de la ciudad. Elegí palabras o frases cortas que te representen y escribí el HTML y el CSS para conseguir este resultado.

- Cada interés se ve como una etiqueta con fondo suave, bordes redondeados y texto legible.
- Si hay espacio, las tres etiquetas quedan una al lado de la otra y separadas entre sí.
- Al angostar la ventana, las etiquetas que ya no entran pasan a la línea siguiente. El avatar y el texto conservan su alineación y la página se puede leer sin desplazarse hacia los costados.

**Para comprobarlo**, guardá los archivos y recargá la página del equipo. Revisá primero con la ventana ancha y después achicala hasta que una etiqueta tenga que bajar. Si se cumple el resultado, guardá la ampliación en un segundo commit. Usá `git status --short` para ver qué archivos editaste, `git add` con esas rutas y `git diff --cached --name-only` para revisarlas antes de guardar. Después de `git commit -m "Agrega mis intereses a la ficha"`, verificá con `git log -2 --oneline` que aparezcan el commit de la ficha y el de los intereses.

## 7. Creá tu perfil y enlazalo desde tu ficha

### 7.1. Explorá el modelo y hacé una copia

Te invito a hacer clic en el nombre de Cosme Fulanito en la página del equipo para abrir [el perfil modelo](perfil.html). Probá **Ampliar portada** con un clic y después con el teclado. Usá `Tab` hasta que el control quede resaltado y presioná la barra espaciadora. En el HTML dejé una casilla vinculada a la etiqueta **Ampliar portada**. En `perfil.css`, el selector `:checked` aplica una altura mayor cuando la casilla está marcada y `transition` suaviza el cambio.

En tu rama, duplicá `agenda-contactos/perfil.html` desde el editor y guardá la copia en la misma carpeta como `perfil-nombre-apellido.html`. Usá tus datos en minúsculas, con guiones y sin tildes. Te pido que mantengas las referencias a `estilos.css` y `perfil.css`, y los atributos `id` de la casilla y `for` de su etiqueta. Así podés reutilizar el diseño y la interacción.

**Para comprobarlo**, revisá que dentro de `agenda-contactos` aparezcan el archivo `perfil.html` y tu copia. En la dirección del perfil modelo que abrió Live Server, reemplazá `perfil.html` por el nombre de tu archivo. Hacé clic en **Ampliar portada**. La imagen debe agrandarse y, con un segundo clic, recuperar su altura inicial.

### 7.2. Personalizá el contenido

Te pido que edites tu copia del perfil con estos cambios.

- **Nombre, presentación y ciudad.** Reemplazá el nombre de Cosme por el tuyo en `<title>`, que aparece en la pestaña, y en `<h1>`, que se ve en la página. Usá la misma presentación y ciudad de tu ficha. Recargá el perfil y compará esos datos con los de tu ficha.
- **Portada.** Guardá una imagen panorámica en `images/portadas/` y cambiá el `src` de la portada para que apunte a tu archivo. Por ejemplo, desde el HTML la ruta sería `../images/portadas/cosme-fulanito.jpg`. Cambiá también el texto de `alt` para que describa tu imagen. Recargá la página y comprobá que se vea la portada que elegiste y que el control siga ampliándola.
- **Frase y repositorio.** Escribí tu frase dentro de `<blockquote>` y cambiá el atributo `href` de **Ver repositorio en GitHub** por la URL de tu repositorio. Leé la frase en el navegador y abrí el enlace para confirmar que llega al repositorio correcto.
- **YouTube y Spotify.** Elegí contenido público que permita insertarse. Copiá la dirección de inserción al `src` de cada `<iframe>`, actualizá su `title` con el nombre del contenido y cambiá el `href` del enlace directo debajo de cada reproductor. Te dejo los pasos de cada plataforma y, en el apartado siguiente, cómo probar los reproductores. [Insertar un video de YouTube](https://support.google.com/youtube/answer/171780?hl=es) · [Insertar contenido de Spotify](https://developer.spotify.com/documentation/embeds/tutorials/creating-an-embed)
- **Contacto.** Te dejé el formulario como referencia de diseño. Hacé clic en la etiqueta **Correo** para comprobar que el cursor pasa al campo correspondiente. Revisá que también estén **Nombre** y **Mensaje**, y que **Enviar** esté deshabilitado.

### 7.3. Enlazá la ficha con tu perfil

Volvé a `agenda-contactos/index.html` y buscá tu ficha. Te pido que dentro del `<h2>` pongas un enlace alrededor de tu nombre. Si tu ficha ya tiene un enlace, editá el que está ahí. Como los dos HTML están en la misma carpeta, en `href` alcanza con el nombre de tu archivo. Así se vería con el nombre de ejemplo.

```html
<h2><a class="enlace-perfil" href="perfil-cosme-fulanito.html">Cosme Fulanito</a></h2>
```

**Para comprobarlo**, recargá la página del equipo y hacé clic en tu nombre. Deberías llegar al perfil que acabás de editar. Hacé clic en **Volver al equipo** para verificar el regreso. Achicá la ventana y revisá que la portada y las secciones se adapten al ancho de la pantalla.

### 7.4. Probá los reproductores con Live Server

Te pido que uses la misma pestaña que abrió Live Server para la página del equipo. Entrá a tu perfil desde tu ficha y desplazate hasta los reproductores. Para esta prueba también vas a necesitar conexión a Internet.

**Para comprobarlo**, revisá que la dirección de tu perfil empiece con `http://` y que puedas reconocer el video y el contenido de audio que elegiste. Probá también los enlaces directos y verificá que abran el mismo contenido en cada plataforma.

### 7.5. Guardá el commit del perfil

Por último, te pido que agregues la página del equipo editada, tu nuevo perfil y la portada. Desde `sitio-web`, ejecutá estos comandos. En la primera línea, sustituí el nombre del HTML y el nombre y la extensión de la imagen por los que usaste.

```bash
git add agenda-contactos/index.html agenda-contactos/perfil-cosme-fulanito.html images/portadas/cosme-fulanito.jpg
git diff --cached --name-only
```

La lista debería mostrar esas tres rutas. Si coinciden con tus archivos, guardá el commit.

```bash
git commit -m "Agrega mi perfil y lo enlaza desde mi ficha"
git log -1 --oneline
git status --short --branch
```

**Para comprobarlo**, confirmá que el último mensaje sea `Agrega mi perfil y lo enlaza desde mi ficha` y que Git siga mostrando tu rama `ficha/...`.

## Lo que aprendimos

Al terminar, espero que puedas hacer estas tareas en otros proyectos.

- Traer una rama de un repositorio remoto, cambiar a ella con `git switch` y crear tu propia rama de trabajo.
- Revisar cambios con `git diff`, elegir qué guardar con `git add` y comprobar tus commits con `git log`.
- Incorporar imágenes y vincular páginas HTML con rutas relativas.
- Adaptar una ficha con HTML y CSS y comprobar que se lea bien con distintos anchos de pantalla.
- Abrir las páginas por HTTP con Live Server desde VS Code.
- Usar el estado `:checked` de una casilla HTML para cambiar la altura de la portada con una transición CSS.
- Insertar contenido con `<iframe>` e identificar cómo se relacionan las etiquetas y los campos de un formulario.
