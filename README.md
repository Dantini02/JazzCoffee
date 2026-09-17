# JazzCoffe — Mini-web informativa

Proyecto estudiantil para la Unidad 2 (HTML, XML, CSS). Sitio de una sola
página para una cafetería ficticia llamada **JazzCoffe**.

## Estructura del proyecto

```
jazzcoffe/
├── index.html        → Página principal
├── estilos.css        → Hoja de estilos externa
├── datos.xml           → Catálogo de servicios (XML)
├── README.md         → Este archivo
└── assets/
    ├── hero.svg          → Ilustración de portada
    └── interior.svg       → Ilustración del interior del local
```

## Cómo ver el sitio en tu computadora

Como `index.html` usa `fetch()` para leer `datos.xml`, algunos
navegadores **bloquean esa petición si abres el archivo con doble clic**
(protocolo `file://`). Para verlo funcionando por completo, sirve la
carpeta con un servidor local. Con Python instalado:

```bash
cd jazzcoffe
python3 -m http.server 8000
```

Y abre `http://localhost:8000` en tu navegador.

Si solo quieres revisar el HTML/CSS sin el catálogo dinámico, sí puedes
abrir `index.html` directamente con doble clic; verás un aviso en la
sección "Catálogo de servicios" en vez de la tabla.

## Cómo visualizar datos.xml directamente

Puedes abrir `datos.xml` en cualquier navegador (doble clic, o
arrastrándolo a una pestaña) para ver su estructura de etiquetas
(`<catalogo>`, `<servicio>`, `<nombre>`, `<categoria>`,
`<descripcion>`, `<precio>`). En `index.html`, la sección **"Ver
catálogo"** del menú también enlaza directamente al archivo.

## Publicar en GitHub Pages

1. Crea un repositorio nuevo en GitHub (por ejemplo `jazzcoffe`).
2. Sube estos archivos manteniendo la misma estructura de carpetas:
   ```bash
   cd jazzcoffe
   git init
   git add .
   git commit -m "Primera versión del sitio JazzCoffe"
   git branch -M main
   git remote add origin https://github.com/TU-USUARIO/jazzcoffe.git
   git push -u origin main
   ```
3. En GitHub, entra a tu repositorio → **Settings** → **Pages**.
4. En **"Build and deployment"**, selecciona **Source: Deploy from a
   branch**.
5. En **Branch**, elige `main` y la carpeta `/ (root)`. Guarda.
6. Espera uno o dos minutos y GitHub mostrará la URL pública, algo como:
   ```
   https://TU-USUARIO.github.io/jazzcoffe/
   ```
7. Visita esa URL: ahí el `fetch()` de `datos.xml` funcionará sin
   problema, porque GitHub Pages sirve el sitio por HTTPS (no por
   `file://`).

## Checklist de requisitos cubiertos

- [x] `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`, `<footer>` semánticos
- [x] `header`, `nav`, `main`, `section`, `footer`
- [x] `<h1>` con el nombre del proyecto y título de página relevante
- [x] `<ul>` de navegación con 4 enlaces (`#menu`, `#horario`, `#catalogo`, `#contacto`)
- [x] `estilos.css` externo enlazado desde `<head>`
- [x] Elementos variados: `h1/h2/h3`, `p`, `a`, `ul/ol`, `table`, `img`,
      `form`, `input/select/textarea`, `iframe`
- [x] Imagen del "local" (`assets/interior.svg`) con `<img>`
- [x] Formulario con nombre, correo, asunto y mensaje + validación HTML5
      (`required`, `type="email"`, `pattern`, `minlength`)
- [x] `datos.xml` con catálogo de servicios, enlazado y mostrado vía JS
- [x] Pie de página con el texto exacto solicitado
- [x] CSS con selectores de elemento, clase, id, descendiente y
      pseudo-clase (`:hover`, `:focus`, `:nth-child`, `:invalid`)
- [x] Modelo de caja (`box-sizing`, `padding`, `border`, `margin`,
      `width/height`) y layout con Flexbox y Grid
- [x] Comentarios explicando las partes importantes del código
