# Equilibrium Calpe — Web

Sitio web estático para **EQUILIBRIUM**, centro de recuperación muscular en Calpe (Alicante), con la sección formativa **QUIRÓN**.

## Estructura de archivos

```
equilibrium-calpe/
├── index.html                 ← Página principal (una sola página)
├── aviso-legal.html           ← Aviso legal (LSSICE)
├── politica-privacidad.html   ← Política de privacidad (RGPD)
├── sitemap.xml
├── robots.txt
├── css/
│   └── styles.css
├── js/
│   └── main.js
└── img/
    ├── logo-equilibrium.png
    ├── logo-quiron.png
    ├── juan-manuel.jpg
    ├── sala-tratamiento.jpg
    ├── despacho.jpg
    └── bono-regalo.jpg
```

## Imágenes necesarias

Coloca las imágenes en la carpeta `/img/` con exactamente estos nombres:

| Archivo | Contenido |
|---|---|
| `logo-equilibrium.png` | Logo Equilibrium (Hombre de Vitruvio blanco sobre negro) |
| `logo-quiron.png` | Logo Quirón (centauro en esfera de cristal) |
| `juan-manuel.jpg` | Foto de Juan Manuel con uniforme verde |
| `sala-tratamiento.jpg` | Sala con camilla — usada en el Hero |
| `despacho.jpg` | Despacho con escritorio |
| `bono-regalo.jpg` | Tarjeta del bono regalo |

> **Tip:** Para mejor rendimiento, convierte las fotos a formato WebP. Tamaño recomendado: hero ≤ 1920px ancho, resto ≤ 1200px.

## Cómo editar los datos más comunes

### Precios de los servicios

Busca en `index.html` el comentario:
```html
<!-- PLACEHOLDER: precio — reemplazar el texto siguiente con el precio real en € -->
<em class="precio-placeholder">Precio a consultar</em>
```
Sustituye `<em class="precio-placeholder">Precio a consultar</em>` por el precio, ej: `<strong>60 €</strong>`.

Hay **4 instancias** (una por servicio). Búscalas todas con Ctrl+F → `PLACEHOLDER: precio`.

---

### Horarios del calendario

Abre `js/main.js` y edita el objeto `HORARIOS` al inicio del archivo:

```js
const HORARIOS = {
  lunes:     ['09:00','10:00','11:00','12:00','16:00','17:00','18:00','19:00'],
  martes:    ['09:00', ...],
  // ...
  sabado:    [],   // ← añadir slots si atiende sábados
  domingo:   [],   // ← añadir slots si atiende domingos
};
```

Cada array contiene los horarios disponibles en formato `'HH:MM'`. Deja el array vacío `[]` para días sin atención.

---

### Horario de atención (sección Ubicación)

Busca en `index.html`:
```html
<!-- PLACEHOLDER: horario real — reemplazar según disponibilidad confirmada -->
<p>Lunes a Viernes: 9:00 — 20:00<br>...
```
Edita el texto de horario según la disponibilidad real.

---

### Modalidad y cursos de Quirón

Busca en `index.html` las etiquetas `PLACEHOLDER` dentro de la sección `#quieon`:
```html
<!-- PLACEHOLDER: confirmar con el profesional si la formación es presencial / online / mixta -->
<!-- PLACEHOLDER: listar cursos cuando se confirmen con el profesional -->
```

---

### Redes sociales (footer)

Busca en `index.html` el bloque `PLACEHOLDER Instagram` y `PLACEHOLDER Facebook` en el footer. Descomenta y añade las URLs reales.

---

### Activar el servicio de Reiki

1. En `index.html`, busca el comentario `PLACEHOLDER REIKI` en la sección de servicios y descomenta el bloque `<article>`.
2. Busca también el comentario `PLACEHOLDER REIKI` en la sección `#reservar` y descomenta el `<button>` de la pill.

---

### Número de WhatsApp

Si cambia el número, edita en `js/main.js`:
```js
const WA_NUMBER = '34665761094';
```

---

### Google Maps

El mapa está embebido como `<iframe>` en la sección `#ubicacion`. Si necesitas ajustar el punto exacto, ve a [maps.google.com](https://maps.google.com), busca la dirección y usa **Compartir → Insertar mapa** para obtener un nuevo `src` de iframe.

---

## Publicar la web

La web es **100% estática** (HTML + CSS + JS). Puedes alojarla en:

- **Netlify / Vercel** — arrastra la carpeta y listo. Gratis.
- **GitHub Pages** — sube el repositorio y activa Pages.
- **Hosting tradicional** — sube por FTP a la carpeta `public_html` o `www`.

Recuerda actualizar las URLs en `sitemap.xml` y en las meta tags `og:image` / `canonical` de `index.html` una vez tengas el dominio definitivo.

---

## Contacto técnico

Para modificaciones o soporte, contacta al desarrollador web o consulta la documentación en línea.

**© 2026 Equilibrium Calpe**
