---
up:
  - "[[tech]]"
---
# HTML

## BASICS

1. [[html_structure|Basic Structure]]
2. [[html_head|Head Elements]]
3. [[html_block|Block Elements]]
4. [[html_inline|Inline Elements]]


## FORMS

5. [[html_form_basics|Form Basics]]
6. [[html_input_fields|Input Fields]]
7. [[html_form_validation|Form Validation]]
8. [[html_labels_buttons|Labels and Buttons]]
9. [[html_form_advanced|Advanced Form Features]]

## MULTIMEDIA

10. [[html_images|Images]]
11. [[html_audio|Audio]]
12. [[html_video|Video]]
13. [[html_picture|Responsive Images with `<picture>`]]

## TABLES

14. [[html_tables|Creating Tables]]
15. [[html_table_accessibility|Table Accessibility]]

## ACCESSIBILITY

16. [[html_aria|ARIA Roles and Attributes]]
17. [[html_accessible_forms|Accessible Forms]]
18. [[html_details_summary|Details and Summary]]

## ADVANCED FEATURES

19. [[html_data_attributes|Custom Data Attributes (`data-*`)]]
20. [[html_canvas|Graphics with Canvas]]
21. [[html_svg|Graphics with SVG]]

## LISTS

22. [[html_unordered_lists|Unordered Lists]]
23. [[html_ordered_lists|Ordered Lists]]
24. [[html_definition_lists|Definition Lists]]

## ANCHORS AND LINKS

25. [[html_anchors|Anchor Links]]
26. [[html_links|Internal and External Links]]


# ETIQUETAS DE TEXTO

```html
<div contenteditable>
	<p> lore ipsum...</p>
</div>
```



## **`<em>` VS `<i>`**

- **`<em>`**: Representa énfasis en el texto y tiene significado semántico. Los lectores de pantalla aplican énfasis al leerlo.
- **`<i>`**: Coloca el texto en cursiva pero no tiene significado semántico. Se usa para términos técnicos, frases en otro idioma o títulos de obras.

```HTML
<p>Me <em>alegro</em> de que estés aquí.</p>
<p>Me <i>alegro</i> de que estés aquí (sin semántica).</p>
```

## **`<b>` VS `<strong>`**

- **`<strong>`**: Indica que el texto es de gran importancia y tiene significado semántico.
- **`<b>`**: Coloca el texto en negrita sin significado semántico. Se usa para resaltar texto sin indicar importancia.
```html
<p><strong>Advertencia:</strong> Este es un mensaje importante.</p>
<p><b>Nota:</b> Este es un mensaje destacado.</p>
```

## **`<q>`**: CITAS BREVES EN LÍNEA

- Se utiliza para citas cortas y generalmente agrega comillas automáticamente.
- El atributo `cite` proporciona una fuente para la cita, aunque no siempre se ve.

```html
<p>Según <q cite="https://ejemplo.com">esta fuente</q>, deberías intentarlo.</p>
```

## **`<blockquote>`**: CITAS LARGAS EN BLOQUE

- Usada para citas largas o bloques de texto citados de otra fuente.
- El atributo `cite` indica la fuente de la cita.

```html
<blockquote cite="https://ejemplo.com">
  <p>Esta es una cita larga, tomada de una fuente externa.</p>
</blockquote>
```

## **`<abbr>`**: ABREVIACIONES

- Se usa para abreviaciones o acrónimos y ofrece más información con el atributo `title`.
```html
<p>El término <abbr title="HyperText Markup Language">HTML</abbr> es fundamental para la web.</p>
```

## **`<del>` Y `<ins>`**: TEXTO TACHADO Y TEXTO INSERTADO

- **`<del>`**: Representa texto que ha sido eliminado o sustituido.
- **`<ins>`**: Representa texto que ha sido añadido.

```html
<p>El agua es <del>húmeda</del> insípida.</p>
<p>El agua es <ins>transparente</ins>.</p>
```

## **`<time>`**: FECHAS Y HORAS

- Se utiliza para marcar un período específico en el tiempo.
- El atributo `datetime` define una fecha y hora legible por el ordenador.

```html
<p>El evento será el <time datetime="2024-10-02">2 de octubre de 2024</time>.</p>
```

## **`<small>`**: TEXTO PEQUEÑO

- Reduce el tamaño del texto. En HTML5, también se utiliza para notas legales o aclaraciones.

```html
<p>Este texto es normal. <small>Este es más pequeño.</small></p>`
```

## **`<wbr>`**: PUNTO DE RUPTURA

- Inserta un posible punto de ruptura de palabra para ajustar la visualización en pantallas más pequeñas.

```html
<p>Esta palabra es muy larga<wbr> y puede romperse aquí si es necesario.</p>
```

## **`<hr>`**: SEPARADOR DE TEMAS

- Inserta una línea horizontal para marcar una separación temática.

```html
<hr>
<p>Esto es un cambio de tema.</p>
```

## **`<pre>`**: TEXTO PREFORMATEADO

- Preserva espacios y saltos de línea.
```html
<pre>
  Línea 1
    Línea 2 con sangría
  Línea 3
</pre>
```

## **`<address>`**: INFORMACIÓN DE CONTACTO

- Representa información de contacto del autor o propietario.

```html
<address>
  Contacto: <a href="mailto:webmaster@example.com">webmaster@example.com</a>
</address>
```


# ETIQUETAS DE INTERACCIÓN

## **`<kbd>`**: ENTRADA DEL USUARIO

- Representa la entrada del usuario, como atajos de teclado o comandos.
```html
<p>Presiona <kbd>Ctrl + S</kbd> para guardar el archivo.</p>`
```

## **`<samp>`**: SALIDA DEL SISTEMA

- Representa la salida del sistema, como los resultados de un programa.

```html
<p>Resultado: <samp>Error: archivo no encontrado</samp></p>`
```

## **`<code>`**: FRAGMENTOS DE CÓDIGO

- Muestra código fuente o texto que representa código.

```html
<p>Usa el comando <code>git status</code> para verificar el estado del repositorio.</p>
```


# IFRAME (`<iframe>`)

Permite incrustar otro documento HTML dentro de la página actual.

```html
<iframe src="www.ejemplo.com" width="600" height="400" title="Ejemplo"></iframe>
```

Atributos:

- **`src`**: URL del documento a incrustar.
- **`width`** y **`height`**: Dimensiones del iframe.
- **`title`**: Descripción del contenido para accesibilidad.
- **`sandbox`**: Aplica restricciones de seguridad.


# MULTIMEDIA ACCESIBLE

## **`<figure>` Y `<figcaption>`**

- **`<figure>`**: Agrupa contenido como imágenes, gráficos, etc., y su pie de foto.
- **`<figcaption>`**: Proporciona una leyenda o pie de foto, para mejorar la accesibilidad.

```html
<figure>
  <img src="imagen.jpg" alt="Descripción de la imagen">
  <figcaption>Este es el pie de foto que describe la imagen.</figcaption>
</figure>
```

# ATRIBUTOS DE DATOS PERSONALIZADOS (`data-*`)

Permiten almacenar información personalizada en elementos HTML.
  
```html
<div id="producto1" data-id="12345" data-precio="19.99">
  <p>Nombre del producto</p>
</div>
```

En JavaScript, puedes acceder a ellos mediante `dataset`:

```js
const producto = document.getElementById('producto1');
console.log(producto.dataset.id); // "12345"
console.log(producto.dataset.precio); // "19.99"
```

# ENLACES DE ANCLAJE

Permiten crear enlaces a secciones específicas dentro de una página.
```html
<!-- Enlace al elemento con id="seccion1" -->
<a href="#seccion1">Ir a la sección 1</a>

<!-- Elemento de destino -->
<h2 id="seccion1">Sección 1</h2>
```
- - - 
