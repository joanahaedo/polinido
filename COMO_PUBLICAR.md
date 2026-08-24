# Cómo publicar PoliNido con su propio link

Esta carpeta (`polinido_pwa`) es la app completa, lista para subir a un hosting
gratuito. Una vez publicada, cualquiera podrá:
- Abrirla desde el link en el navegador del celular, sin instalar nada.
- Tocar "Agregar a pantalla de inicio" (Android) o "Compartir → Agregar a
  inicio" (iPhone) y les queda un ícono de PoliNido como si fuera una app
  instalada — abre a pantalla completa, sin la barra del navegador.
- Volver a abrirla sin conexión (ya visitada una vez) gracias al `sw.js`.

No hace falta cambiar nada del contenido de la carpeta para publicarla: se
sube tal cual.

## Opción 1 — Netlify Drop (la más rápida, sin crear cuenta)

1. Andá a **https://app.netlify.com/drop** desde la computadora.
2. Arrastrá esta carpeta completa (`polinido_pwa`) directo al recuadro de la
   página.
3. En unos segundos te da un link del tipo
   `https://nombre-al-azar.netlify.app` — ya está online y funciona en
   cualquier celular.
4. Ese link queda activo aunque no crees cuenta. Si más adelante querés
   poder actualizarlo vos misma (por ejemplo subir una foto de logo nueva, o
   cambiar textos), te conviene crear una cuenta gratis en Netlify y
   "reclamar" ese sitio — el mismo Netlify te lo ofrece apenas lo subís.

Esta es la opción más simple si solo querés un link para repartir ya mismo.

## Opción 2 — GitHub Pages (para tener control total y un link permanente)

Requiere una cuenta gratuita de GitHub (si no tenés, se crea en
github.com/join).

1. Entrá a GitHub y creá un repositorio nuevo, público, llamado por ejemplo
   `polinido` (Settings del repo se pueden dejar todo por defecto).
2. Adentro del repo recién creado, usá el botón **"Add file" → "Upload
   files"** y arrastrá TODO el contenido de esta carpeta (`index.html`,
   `manifest.json`, `sw.js`, y la carpeta `icons` completa) — no la carpeta
   `polinido_pwa` en sí, sino lo que está adentro.
3. Confirmá el commit ("Commit changes").
4. Andá a **Settings → Pages** (menú de la izquierda) del repositorio.
5. En "Build and deployment" → "Source", elegí **"Deploy from a branch"**,
   rama `main`, carpeta `/ (root)`, y guardá.
6. Esperá 1-2 minutos. GitHub te va a mostrar el link final, algo como:
   `https://tu-usuario.github.io/polinido/`

Ese link es tuyo, permanente, y lo podés seguir actualizando subiendo
archivos nuevos a ese mismo repositorio cuando quieras cambiar algo.

## Si más adelante querés un dominio propio (ej. polinido.com.ar)

Tanto Netlify como GitHub Pages permiten conectar un dominio propio que
compres aparte (en Argentina, por ejemplo, en nic.ar para `.com.ar`, o en
cualquier registrador internacional). Es un paso opcional y no urgente —
avisame cuando quieras dar ese paso y te guío.

## Actualizar la app más adelante

Cuando yo te pase una versión nueva de PoliNido (con cambios que pidas),
te voy a entregar esta misma carpeta actualizada. Para que los celulares
tomen la versión nueva:
- Volvé a subir los archivos (Netlify Drop: arrastrás de nuevo la carpeta
  sobre el mismo sitio ya creado; GitHub: subís los archivos nuevos al
  mismo repositorio, pisando los viejos).
- Importante: en `sw.js`, la primera línea tiene algo como
  `const CACHE_NAME = "polinido-v1";` — yo le voy a subir el número
  (`v2`, `v3`...) cada vez que te entregue una versión nueva, así los
  celulares que ya tenían la app instalada descargan los cambios en vez de
  seguir mostrando la versión vieja guardada en caché.

## Nota importante sobre los datos

Cada persona que use la app tiene sus datos guardados solo en su propio
celular (no hay una base de datos central). Esto es así ya desde el
prototipo y no cambia por publicar la app en un link propio: para juntar
los registros de todos seguís usando el botón "Descargar CSV + PDF de
fotos" de cada persona, tal como ya lo veníamos haciendo.
