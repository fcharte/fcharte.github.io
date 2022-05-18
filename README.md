# cosmere

Prototipo para el sitio web de Francisco Charte
 
## Uso

### Añadir un tutorial

Basta con añadir un archivo con contenido HTML o Markdown al directorio `_tutorials`. Debe contener la siguiente cabecera:

~~~ yml
---
layout: post
title: "El título del tutorial"
---
~~~

### Añadir una colección

Para añadir una colección llamada "publicaciones" hay que seguir estos pasos:

#### 1. Añadir la colección a `_config.yml`
~~~ yml
collections:
  publicaciones:
    output: true
~~~

#### 2. Añadir el índice de la colección, `publicaciones.html`
~~~ yml
---
layout: index
permalink: /publicaciones/
title: Publicaciones
---

{% for element in site.publicaciones %}
<article>
<h2><a href="{{ tutorial.url | prepend: site.baseurl | prepend: site.url }}">{{ tutorial.title }}</a></h2>
</article>
{% endfor %}
~~~

#### 3. Añadir un enlace a la colección en `_data/navigation.yml` (sección `site`)

#### 4. Crear un directorio `_publicaciones` y agregar documentos
