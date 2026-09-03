# UCSF Surgical Neuroanatomy Collection

Sitio web en HTML puro que reúne los artículos publicados del canal UCSF Surgical
Neuroanatomy Collection (Cureus) como presentaciones navegables: modelos 3D
interactivos de Sketchfab, figuras y tablas de cada artículo.

No requiere build, servidor ni base de datos: son archivos estáticos que se abren
en cualquier navegador.

## Estructura

```
index.html                     Portada (colección organizada por categorías)
articles/<articulo>/index.html Presentación de cada artículo
articles/<articulo>/assets/    Figuras y videos locales de cada artículo
```

Los modelos 3D se cargan por streaming desde Sketchfab, por lo que se necesita
conexión a internet para los elementos interactivos. Las figuras, tablas y videos
están alojados localmente dentro del sitio.

## Publicar en GitHub Pages

1. Crea una cuenta en https://github.com (si no tienes).
2. Crea un repositorio nuevo llamado, por ejemplo, `neuroanatomy-collection`
   (público; GitHub Pages gratis requiere repo público).
3. En la página del repositorio: **Add file → Upload files** y arrastra TODO el
   contenido de esta carpeta (`index.html`, la carpeta `articles/`, etc.).
   - Si la subida web es pesada (~95 MB), puedes hacerlo en 2-3 tandas:
     primero `index.html` y `README.md`, luego cada subcarpeta de `articles/`.
   - Alternativa con terminal (más fiable para archivos grandes):
     ```
     git clone https://github.com/TU-USUARIO/neuroanatomy-collection.git
     cd neuroanatomy-collection
     # copia aquí todo el contenido de esta carpeta
     git add -A && git commit -m "Sitio inicial" && git push
     ```
4. Ve a **Settings → Pages**. En "Build and deployment" elige
   **Deploy from a branch**, rama `main`, carpeta `/ (root)`. Guarda.
5. En 1-2 minutos el sitio estará en:
   `https://TU-USUARIO.github.io/neuroanatomy-collection/`

## Publicar en Netlify

1. Entra a https://app.netlify.com/drop
2. Arrastra esta carpeta completa a la página.
3. Netlify te da una URL inmediata (`https://nombre-aleatorio.netlify.app`),
   que puedes cambiar en **Site settings → Change site name**.
4. Para flujo con GitHub: **Site configuration → Build & deploy → Link repository**
   y conecta el repo de GitHub; cada `git push` actualizará el sitio
   automáticamente.

## Actualizar el sitio

- **GitHub (web):** en el repo, entra al archivo, botón de lápiz para editar, o
  **Upload files** para reemplazar archivos/carpetas. Los cambios se publican
  solos en 1-2 minutos.
- **GitHub (terminal):** edita localmente y `git add -A && git commit -m "..." &&
  git push`.
- **Netlify con repo conectado:** cualquier push a GitHub republica el sitio.
- **Netlify sin repo:** arrastra la carpeta actualizada a la pestaña **Deploys**.

## Agregar un artículo nuevo

1. Crea `articles/<nombre-del-articulo>/` con su `index.html` y `assets/`
   (copia cualquier artículo existente como plantilla).
2. En `index.html` (portada), agrega una entrada en el arreglo `ARTICLES` con
   `slug`, `category`, título, journal, autores, thumbnail, conteos y URL de
   Cureus. Si es una categoría nueva, agrégala al arreglo `CATEGORIES`.
3. Sube los cambios como se describe arriba.

## Dominio propio (opcional)

Tanto GitHub Pages como Netlify permiten conectar un dominio propio
(ej. `neuroanatomy.tudominio.org`) desde su panel de configuración.

---

Modelos vía Sketchfab (SBCVL_UCSF) · Figuras © los autores de cada artículo ·
Contenido de los artículos publicado en Cureus bajo licencia CC-BY.
