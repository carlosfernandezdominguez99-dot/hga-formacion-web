# Web HGA Formación

Sitio web estático (HTML + CSS, sin frameworks ni base de datos) del centro de formación
HGA Formación, en Aracena.

## Estructura

```
index.html                  Portada
cursos.html                 Cursos y precios (autoescuela, CAP/ADR, agroganadera, PRL-ITC)
el-centro.html              Instalaciones y ubicación
preguntas-frecuentes.html   FAQ (contenido que ayuda a posicionar en Google)
contacto.html               Formulario y datos de contacto
assets/style.css            Todos los estilos del sitio
assets/logo.png             Logotipo
```

No hay build ni dependencias: se abre `index.html` en el navegador y ya funciona.

## Cómo editar lo más habitual

**Cambiar un precio** → `cursos.html`. Cada curso es un bloque como este:

```html
<div class="price-row">
  <div>
    <div class="name">Permiso B</div>
    <div class="desc">Automóviles de hasta 3.500 kg</div>
  </div>
  <div class="val">320 €</div>
</div>
```

Solo hay que cambiar el número dentro de `<div class="val">`.

**Añadir un curso nuevo** → copiar un bloque `price-row` entero y cambiarle el texto.

**Cambiar textos** → están directamente en el HTML de cada página, sin código de por medio.

**Cambiar colores o tipografías** → `assets/style.css`, al principio del archivo, en el bloque
`:root` (hay una segunda copia de los mismos colores para el modo oscuro, más abajo).

**Cambiar el teléfono** → aparece en `contacto.html` y en el pie de todas las páginas.

## Formulario de contacto

Ahora mismo el formulario de `contacto.html` es una demostración: no envía nada.
Para que funcione sin necesidad de servidor propio se puede conectar a
[Web3Forms](https://web3forms.com) (gratuito): se crea una clave y se sustituye el
formulario por uno que haga POST a `https://api.web3forms.com/submit` con esa clave.

## Publicar la web

Cualquiera de estas opciones sirve, todas gratuitas para un sitio estático:

- **GitHub Pages** — en el repositorio: *Settings → Pages → Source: Deploy from a branch →
  main / (root)*. Queda publicada en `usuario.github.io/nombre-del-repo`.
- **Vercel** — importar el repositorio en vercel.com, sin configuración: detecta que es
  HTML estático. Permite conectar el dominio propio.
- **Hosting propio** — subir los archivos por FTP a la carpeta pública del hosting.

Para usar un dominio propio (por ejemplo `hgaformacion.es`), se apunta el DNS al proveedor
elegido y se activa el certificado HTTPS, que en GitHub Pages y Vercel es automático.

## Pendiente antes de publicar de verdad

- Confirmar que todos los precios están actualizados.
- Revisar las respuestas del FAQ con el centro (son un borrador razonable, no oficial).
- Sustituir las ilustraciones por fotos reales de las instalaciones y los vehículos.
- Añadir horario de atención concreto y enlaces reales a Instagram, Facebook y LinkedIn.
- Conectar el formulario de contacto.
